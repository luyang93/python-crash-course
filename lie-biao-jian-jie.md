# 列表简介 {#列表简介}

\[\]，方括号！方括号！方括号！

```py
lists = ['str1', 'str2', 'str3']

print (lists[0])
lists[0].title()

```

index从0开始，-1倒数第一个

```py
lists.append('str1')    
#添加到列表末尾

lists.insert(1，'str1')    
#在索引1处添加空位并写入元素
del lists[2]    
#删除索引2处的元素

lists.pop()    
#获取列表最后一个元素，并从列表里删除

lists.pop(3)    
#获取列表中索引3处的元素，并从列表里删除

lists.remove('str1')    
#删除列表里'str1'的元素

lists.sort()    
#按字母顺序排列，永久改变

lists.sort(reverse=True)    
#按字母倒序排列，永久改变

sorted(lists)    
#临时按照字母顺序排序，不改变lists

sorted(lists,reverse=True)    
#临时按照字母倒序排序，不改变lists

lists.reverse()    
#反转列表元素的排列顺序

len(lists)    
#输出列表的长度
```



