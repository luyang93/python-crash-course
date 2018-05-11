# 函数

## 定义函数

```python
def function():
    do

function()
```

## 向函数传递信息

```python
def function(var1):
    print (str(var1) + ' is used in function!')

function(var2)
```

实参和形参

传递实参：位置实参和关键词实参

位置实参

```python
def function(var1, var2):
    print (str(var1) + ' is used in function!')
    print (str(var2) + ' is used in function!')

function(var1, var2)
```

在函数中，可根据需要使用任意数量的位置实参，Python将按顺序将函数调用中的实参关联到函数定义中相应的形参。

关键词实参

```python
def function(var1, var2):
    print (str(var1) + ' is used in function!')
    print (str(var2) + ' is used in function!')

function(var1='str1', var2='str2')
```

默认值

```python
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

```python
def function(var1, var2):
    var = var1 + " " + var2
    return var
result = function(var1, var2)
```

让实参变为可选

```python
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

```python
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

```python
while true:
    if condition:
        break
```

传递列表

```python
def function(lists):
    for list in lists:
        do
lists = ['var1', 'var2', 'var3']
function(lists)
```

在函数中修改列表

```python
current = lists.pop()
completes.append(current)
```

禁止函数修改列表

```text
function_name(list_name[:])
#切片表示法[:]
```

虽然向函数传递列表的副本可保留原始列表的内容，但除非有充分的理由需要传递副本，否则还是应该将原始列表传递给函数，因为让函数使用现成列表可避免花时间和内存创建副本，从而提高效率，在处理大型列表时尤其如此。

传递任意数量的实参，\*lists创建lists空元组，将实参封装到一个元组内。

```python
def function(*lists):
for list in lists:
    print(list)
```

结合使用位置实参和任意数量实参

先匹配位置实参和关键词实参，再将余下的实参都收集到最后一个形参中。

```python
def function(var1, *lists):
    print(var1)
    for list in lists:
        print(list)
```

使用任意数量的关键字实参，\*\*创建一个名叫dictionary的空字典，将所有的键—值对封装到字典中。

```python
def function(var1, var2, **dictionarys)
    dict = {}
    dict['var1'] = var1
    dict['var2'] = var2
    for key,value in dictionarys.item():
        dict[key] = value
    return dict
```

将函数存储在模块中，import

导入整个模块

```python
fucntion.py
def fun()

impport function
function.fun(var1, var2)
```

导入特定的函数

```python
form module_name import function_0, function_1, function_2
function_0()
function_1()
function_2()
```

使用as给函数指定别名

```python
from module_name import function_name as function
```

使用as给模块指定别名

```python
import module_name as module
module.function()
```

导入模块中的所有函数

```python
from module_name import *
```

函数编写指南

给函数指定描述性名称

只在其中使用小写字母和下划线

包含简要地阐述其功能的注释

给形参指定默认值时，等号两边不要有空格

建议代码行的长度不要超过79字符，这样只要编辑器窗口适中，就能看到整行代码。如果形参很多，导致函数定义的长度超过了79字符，可在函数定义中输入左括号后按回车键，并在下一行按两次Tab键，从而将形参列表和只缩进一层的函数体区分开来。

如果程序或模块包含多个函数，可使用两个空行将相邻的函数分开，这样将更容易知道前一个函数在什么地方结束，下一个函数从什么地方开始。

所有的import语句都应放在文件开头，唯一例外的情形是，在文件开头使用了注释来描述整个程序。

