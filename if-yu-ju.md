# if语句

=，代表陈述，赋值

==，代表发问，判断相等

大小写敏感

!=，判断不相等

&lt;，&lt;=，&gt;，&gt;=

and，or

```python
if ... in ...:
#检查特定值是否包含在列表中
```

```python
if ... not in ...:
#检查特定值是否包含在列表中
```

```python
if ...:
#if语句
```

```python
if ...:
else ...:
#if-else语句
```

```python
if ...:
elif ...:
else ...:    
#if-elif-else语句
```

```python
if ...:
elif ...:
elif ...:
elif ...:
elif ...:
elif ...:
else ...:
#if-多个elif-else语句
```

```python
if ...:
elif ...:
elif ...:
elif ...:
elif ...:
elif ...:
#if-多个elif，省略else
```

else是一条包罗万象的语句，只要不满足任何if或elif中的条件测试，其中的代码就会执行，这可能会引入无效甚至恶意的数据。如果知道最终要测试的条件，应考虑使用一个elif代码块来代替else代码块。这样，你就可以肯定，仅当满足相应的条件时，你的代码才会执行。

