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

