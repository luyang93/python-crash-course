# 文件和异常

从文件中读取数据

读取整个文件

```py
filename = 'file_path'
with open('filename') as file_object:
    contents = file_object.read()
    print(contents)
```

逐行读取

```py
filename = 'file_path'
with open('filename') as file_object:
    for line in file_object:
        print(line.strip())
```

创建一个包含文件各行内容的列表

```py
filename = 'file_path'
with open('filename') as file_object:
    lines = file_object.readlines()

for line in lines:
    print(line.strip())
```



