# 函数

## 定义函数

```py
def function():
    do

function()
```

## 向函数传递信息

```py
def function(var1):
    print (str(var1) + ' is used in function!')

function(var2)
```

实参和形参

传递实参：位置实参和关键词实参

位置实参

```py
def function(var1, var2):
    print (str(var1) + ' is used in function!')
    print (str(var2) + ' is used in function!')

function(var1, var2)
```

在函数中，可根据需要使用任意数量的位置实参，Python将按顺序将函数调用中的实参关联到函数定义中相应的形参。

关键词实参

```py
def function(var1, var2):
    print (str(var1) + ' is used in function!')
    print (str(var2) + ' is used in function!')

function(var1='str1', var2='str2')
```

默认值

```py
def function(var1, var2='str2'):
    print (str(var1) + ' is used in function!')
    print (str(var2) + ' is used in function!')

function(var1='str1')
function('str1')
```

使用默认值时，在形参列表中必须先列出没有默认值的形参，再列出有默认值的形参。这让Python依然能够正确地解读位置实参。

等效的函数调用

可混合使用位置实参、关键字实参和默认值

避免实参错误

返回值

```py
def function(var1, var2):
    var = var1 + " " + var2
    return var
result = function(var1, var2)
```

让实参变为可选

```py
def function(var1, var2, var3=""):
    if var3:
        var = var1 + var2 + var3
    else:
        var = var1 + var2
    return var
    print (var)
function(var1, var2, var3)
```

返回字典

```py
def function(var1, var2)
    var = {
    'var1' : var1,
    'var2' : var2,
    }
    return var
vars = function(var1, var2)
print (vars)
```

结合使用函数和while循环

```py
while true:
    if condition:
        break
```

传递列表

```py
def function(lists):
    for list in lists:
        do
lists = ['var1', 'var2', 'var3']
function(lists)
```

在函数中修改列表

```py
current = lists.pop()
completes.append(current)
```

禁止函数修改列表

```
function_name(list_name[:])
#切片表示法[:]
```

虽然向函数传递列表的副本可保留原始列表的内容，但除非有充分的理由需要传递副本，否则还是应该将原始列表传递给函数，因为让函数使用现成列表可避免花时间和内存创建副本，从而提高效率，在处理大型列表时尤其如此。

传递任意数量的实参，\*lists创建lists空元组，将实参封装到一个元组内。

```py
def function(*lists):
for list in lists:
    print(list)
```

结合使用位置实参和任意数量实参

先匹配位置实参和关键词实参，再将余下的实参都收集到最后一个形参中。

```py
def function(var1, *lists):
    print(var1)
    for list in lists:
        print(list)
```

使用任意数量的关键字实参，\*\*创建一个名叫dictionary的空字典，将所有的键—值对封装到字典中。

```py
def function(var1, var2, **dictionarys)
    dict = {}
    dict['var1'] = var1
    dict['var2'] = var2
    for key,value in dictionarys:
        dict[key] = value
    return dict
```



