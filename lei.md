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

