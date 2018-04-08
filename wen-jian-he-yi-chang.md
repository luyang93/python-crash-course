# 文件和异常

从文件中读取数据

读取整个文件

```py
filename = 'file_path'
with open(filename) as file_object:
    contents = file_object.read()
    print(contents)
```

逐行读取

```py
filename = 'file_path'
with open(filename) as file_object:
    for line in file_object:
        print(line.strip())
```

创建一个包含文件各行内容的列表，readlines\(\)从文件中读取每一行并储存在列表中，用for循环打印

```py
filename = 'file_path'
with open(filename) as file_object:
    lines = file_object.readlines()

for line in lines:
    print(line.strip())
```

使用文件的内容

```py
filename = 'file_path'
with open(filename) as file_object:
    lines = file_object.readlines()

pi_string = ''
for line in lines:
    pi_string += line.strip()

print(pi_string)
print(len(pi_string))
```



