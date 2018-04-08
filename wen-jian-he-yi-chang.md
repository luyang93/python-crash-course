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

存储数据，json

json.dump\(\)和json.load\(\)

```py
import json
numbers = list(range[0,6])
filename = 'numbers.json'
with open(filename, 'w') as file_obj:
    json.dump(numbers, file_obj)
```

```py
import json
filename = 'numbers.json'
with open(filename) as file_obj:
    numbers = json.load(file_obj)
    print(list(numbers))
```

```py
import json
filename = 'username.json'
try:
    with open(filename) as file_obj:
        username = json.load(file_obj)
except FileNotFoundError:
    with open(filename, 'w') as file_obj:
        username = input("你叫什么名字？")
        json.dump(username, file_obj)
        print("我已经记得你了" + username)
else:
    print('欢迎回来' + username)
```

重构

```py
import json

def get_stored_username():
    """Get stored username if available."""
    filename = 'username.json'
    try:
        with open(filename) as f_obj:
            username = json.load(f_obj)
    except FileNotFoundError:
        return False
    else:
        return username

def get_new_username():
    """Prompt for a new username."""
    username = input("What is your name? ")
    filename = 'username.json'
    with open(filename, 'w') as f_obj:
        json.dump(username, f_obj)
    return username

def greet_user():
    """Greet the user by name."""
    username = get_stored_username()
    if username:
        print("Welcome back, " + username + "!")
    else:
        username = get_new_username()
        print("We'll remember you when you come back, " + username + "!")

greet_user()
```















