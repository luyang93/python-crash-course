# 字典

字典，花括号，**键——值对**

```py
alien_0 = {'color': 'green', 'points': 5}
print(alien_0['color'])
print(alien_0['points'])
```

添加/修改键——值对

```py
alien_0['x_position'] = 0
alien_0['y_position'] = 25
print(alien_0)
```

```py
alien_0 = {}
#空字典
```

```py
del alien_0['points']    
#删除键——值对
```

遍历键——值对，items\(\)

```py
user_0 = {
      'username': 'efermi',
      'first': 'enrico',
      'last': 'fermi',
      }

for key, value in user_0.items():
      print("\nKey: " + key)
      print("Value: " + value)
```

遍历键，keys\(\)

```py
favorite_languages = {
      'jen': 'python',
      'sarah': 'c',
      'edward': 'ruby',
      'phil': 'python',
      }
for name in favorite_languages.keys():      #for name in favorite_languages:
      print(name.title())
```

按顺序，sorted\(\)

遍历值，values\(\)

```py
favorite_languages = {
    'jen': 'python',    
    'sarah': 'c',
    'edward': 'ruby',
    'phil': 'python',
    }

print("The following languages have been mentioned:")

for language in favorite_languages.values():
    print(language.title())
```

去除重复值，set\(\)

在列表中储存字典

```py
alien_0 = {'color': 'green', 'points': 5}
alien_1 = {'color': 'yellow', 'points': 10}
alien_2 = {'color': 'red', 'points': 15}

aliens = [alien_0, alien_1, alien_2]

for alien in aliens:
    print(alien)
```

```py
lists = []
for ... in ...:
    dict = {}
    lists.append(dict)
```

在字典中存储列表

```py
# 存储所点比萨的信息
pizza = {
      'crust': 'thick',
      'toppings': ['mushrooms', 'extra cheese'],
      }
  
# 概述所点的比萨
print("You ordered a " + pizza['crust'] + "-crust pizza " + "with the following toppings:")
for topping in pizza['toppings']:
      print("\t" + topping)
```

在字典中存储字典

```py
users = {
    "name1" : {
        "first" : "first_thing",
        "second" : "second_thing",
        "third" : "third_thing",
        },
    "name2" : {
        "first" : "first_thing",
        "second" : "second_thing",
        "third" : "third_thing",
        },
    }
```



