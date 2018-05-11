# 测试代码

测试代码

测试函数

单元测试：用于核实函数的某个方面没有问题

测试用例：是一组单元测试，这些单元测试一起核实函数在各种情形下的行为都符合要求

全覆盖测试：用例包含一整套单元测试，涵盖了各种可能的函数使用方式

可通过的测试

```python
module_name.py

def func_name()
    do
    return
```

```python
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

```python
assertEqual(a, b)
asserNotEqual(a, b)
assertTrue(x)
assertFalse(x)
assertIn(item, list)
assertNotIn(item, list)
```

一个要测试的类

```python
survey.py

class AnonymousSurvey():
    """Collect anonymous answers to a survey question."""

    def __init__(self, question):
        """Store a question, and prepare to store responses."""
        self.question = question
        self.responses = []

    def show_question(self):
        """Show the survey question."""
        print(self.question)

    def store_response(self, new_response):
        """Store a single response to the survey."""
        self.responses.append(new_response)

    def show_results(self):
        """Show all the responses that have been given."""
        print("Survey results:")
        for response in self.responses:
            print('- ' + response)
```

```python
language_survey.py

from survey import AnonymousSurvey

# Define a question, and make a survey object.
question = "What language did you first learn to speak?"
my_survey = AnonymousSurvey(question)

# Show the question, and store responses to the question.
my_survey.show_question()
print("Enter 'q' at any time to quit.\n")
while True:
    response = input("Language: ")
    if response == 'q':
        break
    my_survey.store_response(response)

# Show the survey results.
print("\nThank you to everyone who participated in the survey!")
my_survey.show_results()
```

测试AnonymousSurvey类

```python
test_survey.py

import unittest
from survey import AnonymousSurvey

class TestAnonymousSurvey(unittest.TestCase):
    """Tests for the class AnonymousSurvey."""

    def setUp(self):
        """
        Create a survey and a set of responses for use in all test methods.
        """
        question = "What language did you first learn to speak?"
        self.my_survey = AnonymousSurvey(question)
        self.responses = ['English', 'Spanish', 'Mandarin']


    def test_store_single_response(self):
        """Test that a single response is stored properly."""
        self.my_survey.store_response(self.responses[0])
        self.assertIn(self.responses[0], self.my_survey.responses)


    def test_store_three_responses(self):
        """Test that three individual responses are stored properly."""
        for response in self.responses:
            self.my_survey.store_response(response)
        for response in self.responses:
            self.assertIn(response, self.my_survey.responses)


unittest.main()
```

方法setUp\(\)

unittest.TestCase类包含方法setUp\(\)，让我们只需创建这些对象一次，并在每个测试方法中使用它们。如果你在TestCase类中包含了方法setUp\(\)，Python将先运行它，再运行各个以test\_打头的方法。这样，在你编写的每个测试方法中都可使用在方法setUp\(\)中创建的对象了。

运行测试用例时，每完成一个单元测试，Python都打印一个字符：测试通过时打印一个句点；测试引发错误时打印一个E；测试导致断言失败时打印一个F。这就是你运行测试用例时，在输出的第一行中看到的句点和字符数量各不相同的原因。如果测试用例包含很多单元测试，需要运行很长时间，就可通过观察这些结果来获悉有多少个测试通过了。

