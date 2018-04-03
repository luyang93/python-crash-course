# 用户输入和while循环 {#用户输入和while循环}
```py
input(str1)    #获取用户输入
```

```py
int()    #获取数值输入
```
%，求模

```py
while True:
    Do
```

使用标志

```py
active = True
while active:
    do
    if condition1:
        active = False
    else:
        do
```

break退出循环

```py
while True:
    do
    if condition:
        break
```

continue，返回循环开头

```py
while True:
    do
    if condition:        
        continue
```
确认程序至少有一个这样的地方能让循环条件为False或让break语句得以执行。

for循环是一种遍历列表的有效方式，但在for循环中不应修改列表，否则将导致Python难以跟踪其中的元素。要在遍历列表的同时对其进行修改，可使用while循环。通过将while循环同列表和字典结合起来使用，可收集、存储并组织大量输入，供以后查看和显示。

while lists:

在列表之间移动元素

pop\(\)

删除包含特定值的所有列表元素

remove\(\)

使用用户输入来填充字典

```py
# 提示输入被调查者的名字和回答
name = input(
"\nWhat is your name? "
)
response = input(
"Which mountain would you like to climb someday? "
)
# 将答卷存储在字典中
responses[name] = response
```



