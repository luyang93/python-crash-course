# **操作列表** {#操作列表}

```py
for ... in ...：
#单数代表元素，复数代表列表
```
缩进问题
```py
range(1,6)    
#1,2,3,4,5
```
列表解析
```py
squares = [value**2 for value in range(1,11)]
#将for循环和创建新元素的代码合并成一行，并自动附加新元素
```
for语句末尾没有冒号
```py
lists[3:6]    #从3到5
lists[:4]    #从开始到3
lists[3:]    #从3到最后
lists[-3:]    #最后3个
```
遍历切片
```py
for player in players[:3]:
```
复制列表
```py
friend_foods = my_foods[:]
```
元组，定义使用圆括号\(\)，访问使用方括号\[\]
```py
dimensions = (200,50)
dimensions[0]
```
不允许修改元组数据，只能重新定义dimensions
for循环遍历
```py
dimensions = (200, 50)
for dimension in dimensions:
    print(dimension)
```
元组是更简单的数据结构，如果需要存储的一组值在程序的整个生命周期内都不变，可使用元组。

