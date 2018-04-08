测试代码

测试函数

单元测试：用于核实函数的某个方面没有问题

测试用例：是一组单元测试，这些单元测试一起核实函数在各种情形下的行为都符合要求

全覆盖测试：用例包含一整套单元测试，涵盖了各种可能的函数使用方式

可通过的测试

```py
module_name.py

def func_name()
    do
    return
```

```py
test_func_name.py

import unittest
from module_name import func_name:
class Test_func_name(unittest.TestCase)
    def test_some_of_function(self):
    result_func = func_name()
    self.assertEqual(result_func, 'true_result')

unittest.main()
```

assertEqual，断言方法，断言方法用来核实得到的结果是否与期望的结果一致。

不能通过的测试

测试未通过的处理

添加新测试

在TestCase类中使用很长的方法名是可以的；这些方法的名称必须是描述性的，这才能让你明白测试未通过时的输出

测试类

各种断言方法

unittest.TestCase类中

```py
assertEqual(a, b)
asserNotEqual(a, b)
assertTrue(x)
assertFalse(x)
assertIn(item, list)
assertNotIn(item, list)
```



