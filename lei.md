# 类

创建和实用类，首字母大写

```py
class Dog():
    """创建小狗的类"""
    def __init__(self,name,age):
        """初始化属性name和age"""
        self.name = name
        self.age = age
    def sit(self):
        """模拟小狗被命令时蹲下"""
        print (self.name.title() + " is now sitting.")
    def roll_over(self):
        """模拟小狗被命令时打滚"""
        print (self.name.title() + " is now rolled over!")
```

方法：`__init__()`

包含三个形参，self、name、age。

self，指向实例本身的引用。

name、age，是实例的属性。

其他方法：`sit()、roll_over()`

根据类创建实例

```py
my_dog = Dog('willie', 6)
my_dog.name.title()
my_dog.age
```

访问属性

```py
my_dog.name
```

调用方法

```py
my_dog.sit()
```

创建多个实例

```py
my_dog = Dog('willie', 6)
your_dog = Dog('blacc', 8)
```

使用类和实例

```py
class Car():
    def __init__(self, make, model, year):
        self.make = make
        self.model = model
        self.year = year
    def get_descriptive_name(self):
        long_name = str(self.year) + ' ' + self.make + ' ' + self.model
        return long_name.title()

my_new_car = Car('audi', 'a4', 2016)
print(my_new_car.get_descriptive_name())
```

给属性指定默认值，类中的属性都必须有初始值

```py
class Car():
    def __init__(self, make, model, year):
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0
    def get_descriptive_name(self):
        long_name = str(self.year) + ' ' + self.make + ' ' + self.model
        return long_name.title()
    def read_odometer(self)
        print("This car has " + str(self.odometer_reading) + " miles on it.")


my_new_car = Car('audi', 'a4', 2016)
print(my_new_car.get_descriptive_name())
my_new_car.read_odometer()
```

修改属性的值

直接修改属性的值

```py
my_new_car_odometer_reading = 23
```

通过方法修改属性的值

```py
class Car():
    def update_odometer(self, mileage):
        self.odometer_reading = mileage

my_new_car.update_odometer(23)
```

通过方法对属性的值进行递增

```py
def Car():


    def update_odometer(self, mileage):

    def increment_odometer(self.miles):
        self.odometer_reading += miles

my_used_car.update_odometer(23500)
my_used_car.read_odometer()
```

继承

子类的方法`__init__()`

```py
class Car():
    def __init__(self, make, modle, year):

class ElectricCar(Car):
    """电动汽车的独特之处"""
    def __init__(self, make, model, year):
        """初始化父类属性”“”
        super().__init__(make, model, year)

my_teslar = ElectricCar('tesla', 'model s', 2016)
```

给子类定义属性和方法

```py
class Car():

class ElectricCar(Car):
    def __init__(self, make, model, year):
        super().__init__(make, model, year)
        self.battery_size = 70
    def describe_battery(self):
        print("Thins car has a " + str(self.battery_size) + "-kWh battery.")

my_tesla = ElectricCar('tesla', 'model s', 2016)
my_tesla.describe_battery()
```

重写父类的方法，在子类中定义一个这样的方法，即它与要重写的父类方法同名。

```py
def ElectricCar(Car):
    def fill_gas_tank():
        print("This car doesn't need a gas tank!")
```

将实例用作属性，在ElectricCar类中，添加了self.battery的属性。同事将新创建的Battery实例存储在属性self.battery中。

```py
class Car():

class Battery():
    def __init__(self, battery_size=70):
        self.battery_size = battery_size
    def describe_battery(self):
        print(str(self.battery_size))

class ElectricCar(Car):
    def __init__(self, make, model, year):
    super().__init__(make, modle, year)
    self.battery = Battery()

my_tesla = ElectricCar("tesla", "model s", 2016)
my_tesla.battery.describe_battery()
```

模拟实物

建模方法的高效率，重写类

导入类

导入单个类

```py
car.py
class Car():

my_car.py
from car import Car
```

在一个模块中存储多个类

```py
car.py
class Car():

class Battery():

class ElectricCar(Car):

my_electric_car.py
from car import ElectricCar
```

从一个模块中导入多个类

```py
my_cars.py
for car import Car, ElectricCar
```

导入整个模块

```py
import car
```

导入模块中的所有类，不推荐，列出明确使用了哪一些模块。

```py
from module_name import *
```

在一个模块中导入另一个模块

```py
electric_car.py
from car import Car

class Battery():

class ElectricCar(Car):

car.py
class Car():

my_cars.py
from electric_car import ElectricCar
```

自定义工作流程

一开始应让代码结构尽可能简单。先尽可能在一个文件中完成所有的工作，确定一切都能正确运行后，再将类移到独立的模块中。如果你喜欢模块和文件的交互方式，可在项目开始时就尝试将类存储到模块中。先找出让你能够编写出可行代码的方式，再尝试让代码更为组织有序。

Python标准库

OrderedDict，实例行为几乎与字典相同，区别只在于记录了键—值对的添加顺序。

```py
from collections import OrderedDict

favorite_languages = OrderedDict()

favorite_languages['jen'] = 'python'
favorite_languages['sarah'] = 'c'
favorite_languages['edward'] = 'ruby'
favorite_languages['phil'] = 'python'

for name, language in favorite_languages.items():
    print(name.title() + "'s favorite language is " +
    language.title() + ".")
```

驼峰命名法

类名中的每个单词的首字母都大写，而不使用下划线

实例名和模块名都采用小写格式，并在单词之间加上下划线

对于每个类，都应紧跟在类定义后面包含一个文档字符串

每个模块也都应包含一个文档字符串，对其中的类可用于做什么进行描述

