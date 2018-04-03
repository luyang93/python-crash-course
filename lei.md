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



























