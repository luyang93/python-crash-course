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



