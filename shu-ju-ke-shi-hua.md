# 数据可视化

matplotlib

绘制简单的折线图——plt.plot\(\)

```python
import matplotlib.pyplot as plt

input_values = [1, 2, 3, 4, 5]
squares = [1, 4, 9, 16, 25]
plt.plot(input_values, squares, linewidth=5, color='red')

# Set chart title and label axes.
plt.title("Square Numbers", fontsize=24)
plt.xlabel("Value", fontsize=14)
plt.ylabel("Square of Value", fontsize=14)

# Set size of tick labels.
plt.tick_params(axis='both', labelsize=14)

plt.show()
```

绘制散点图——plt.scatter\(\)

```python
import matplotlib.pyplot as plt

x_values = list(range(1, 1001))
y_values = [x**2 for x in x_values]

# 删除轮廓,设定点大小,设定颜色
plt.scatter(x_values, y_values, c=(0, 0, 0.8), edgecolor='none', s=40)

# Set chart title, and label axes.
plt.title("Square Numbers", fontsize=24)
plt.xlabel("Value", fontsize=14)
plt.ylabel("Square of Value", fontsize=14)

# Set size of tick labels.
plt.tick_params(axis='both', which='major', labelsize=14)

# Set the range for each axis.
plt.axis([0, 1100, 0, 1100000])

plt.show()
```

颜色映射

```python
plt.scatter(x_values, y_values, c=y_values, cmap=plt.cm.Blues,
            edgecolor='none', s=40)
```

自动保存图表

```python
plt.savefig('squares_plot.png', bbox_inches='tight')
```

随机漫步

```python
random_walk.py

from random import choice

class RandomWalk():
    """A class to generate random walks."""

    def __init__(self, num_points=5000):
        """Initialize attributes of a walk."""
        self.num_points = num_points

        # All walks start at (0, 0).
        self.x_values = [0]
        self.y_values = [0]

    def fill_walk(self):
        """Calculate all the points in the walk."""

        # Keep taking steps until the walk reaches the desired length.
        while len(self.x_values) < self.num_points:

            # Decide which direction to go, and how far to go in that direction.
            x_direction = choice([1, -1])
            x_distance = choice([0, 1, 2, 3, 4])
            x_step = x_direction * x_distance

            y_direction = choice([1, -1])
            y_distance = choice([0, 1, 2, 3, 4])
            y_step = y_direction * y_distance

            # Reject moves that go nowhere.
            if x_step == 0 and y_step == 0:
                continue

            # Calculate the next x and y values.
            next_x = self.x_values[-1] + x_step
            next_y = self.y_values[-1] + y_step

            self.x_values.append(next_x)
            self.y_values.append(next_y)
```

```python
rw_visual.py

import matplotlib.pyplot as plt

from random_walk import RandomWalk

# Keep making new walks, as long as the program is active.
while True:
    # Make a random walk, and plot the points.
    rw = RandomWalk(50000)
    rw.fill_walk()

    # Set the size of the plotting window.
    plt.figure(dpi=300, figsize=(10, 10))

    point_numbers = list(range(rw.num_points))
    plt.scatter(rw.x_values, rw.y_values, c=point_numbers, cmap=plt.cm.Blues,
        edgecolor='none', s=1)

    # Emphasize the first and last points.
    plt.scatter(0, 0, c='green', edgecolors='none', s=100)
    plt.scatter(rw.x_values[-1], rw.y_values[-1], c='red', edgecolors='none',
        s=100)

    # Remove the axes.
    plt.axes().get_xaxis().set_visible(False)
    plt.axes().get_yaxis().set_visible(False)

    plt.show()

    keep_running = input("Make another walk? (y/n): ")
    if keep_running == 'n':
        break
```

使用Pygal模拟扔色子

```python
die_visual.py

from die import Die
from matplotlib import pyplot as ptl
from pygal import Bar

# 创建一个六面筛子
die1 = Die(10)
die2 = Die(8)
# 创建记录结果的列表
results = []

# 扔10000次筛子
for roll_num in range(0, 100000):
    result = die1.roll() + die2.roll()
    results.append(result)

# 分析结果
frequencies = []
max_rusult = die1.num_sides + die2.num_sides
for number in range(1 + 1, max_rusult + 1):
    frequency = results.count(number)
    frequencies.append(frequency)

# 可视化
hist = Bar()
hist.title = 'Results of rolling one D' + str(die1.num_sides) + ' + D' + str(die2.num_sides) + ' 100000 times.'
hist.x_labels = map(str, range(1 + 1, max_rusult + 1))
hist.x_title = "Result"
hist.y_title = "Frequency of Result"

hist.add('D' + str(die1.num_sides) + ' + D' + str(die2.num_sides), frequencies)
hist.render_to_file('die_visual.svg')
hist.render_to_png('die_visual.png')
```

```python
die.py

from random import randint

class Die():
    """A class representing a single die."""

    def __init__(self, num_sides=6):
        """Assume a six-sided die."""
        self.num_sides = num_sides

    def roll(self):
        """"Return a random value between 1 and number of sides."""
        return randint(1, self.num_sides)
```

