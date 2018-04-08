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

写入文件，'r'读取模式，'w'写入模式，'a'附加模式，'r+'读写模式，默认只读模式。只能写入字符串，srt\(\)将数值转换为字符串。

```py
filename = 'file_path'
with open(filename， 'w') as file_object:
    file_object.write("summary")
```

写入多行

```py
file_object.write('sentence1\n')
```

附加到文件，如果文件存在，则添加到末尾，如果文件不存在，则创建空文件。open\(filename,'a'\)

处理ZeroDivisionError异常

使用try-except代码块

```py
try:
    print(5/0)
except ZeroDivisionError:
    print('You cant divide by zero!')
```

使用异常避免崩溃

else代码块，try-except-else

```py
while True:
    do
    if True:
        break
    try:
        do
    except Error:
        do
    else:
        do
```

处理FileNotFoundError异常

```py
try:
    with open(filename) as file_obj:
        do
except FileNotFoundError:
    do
```

分析文本

```py
try:
    with open(filename) as file_obj:
        do
except FileNotFoundError:
    do
else:
    do
```

使用多个文件

```py
def count_words(filename):
    try:
        with open(filename) as file_obj:
            contents = file_obj.read()
    except FileNotFoundError:
        print("No exist!")
    else:
        num_words = contents.split()
        print(str(len(num_words)))


filename = 'alice.txt'
count_words(filename)
```

失败是一声不吭，pass，什么都不发生，充当占位符

```py
def count_words(filename):
    try:
        with open(filename) as file_obj:
            contents = file_obj.read()
    except FileNotFoundError:
        psss
    else:
        num_words = contents.split()
        print(str(len(num_words)))


filename = 'alice.txt'
count_words(filename)
```

存储数据

















