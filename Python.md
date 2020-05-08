<!-- markdown-toc start - Don't edit this section. Run M-x markdown-toc-generate-toc again -->
**Python语言知识点总结归纳**


   * [Python语言知识点](#python语言知识点)
      * [1 Python语言的特性](#1-Python语言的特性)
      * [2 Python的函数参数传递](#2-python的函数参数传递)
      * [3 Python中的元类(metaclass)](#3-python中的元类metaclass)
      * [4 @staticmethod和@classmethod](#4-staticmethod和classmethod)
      * [5 单例模式](#5-单例模式)
         * [1 使用__new__方法](#1-使用__new__方法)
         * [2 共享属性](#2-共享属性)
         * [3 装饰器版本](#3-装饰器版本)
         * [4 import方法](#4-import方法)

<!-- markdown-toc end -->





# Python语言知识点


## 1 Python语言的特性

Python是一种解释型语言，不需要再运行之前进行编译。
Python是一种动态语言，不需要声明变量的类型。
python适合面向对象编程，允许类的定义以及组合和继承。

## 2 Python的函数参数传递

看两个例子:

```python
a = 1
def fun(a):
    a = 2
fun(a)
print a  # 1
```

## 3 python中的元类metaclass


## 4 staticmethod和classmethod


## 5 单例模式


### 1 使用`__new__`方法

```python
class Singleton(object):
    def __new__(cls, *args, **kw):
        if not hasattr(cls, '_instance'):
            orig = super(Singleton, cls)
            cls._instance = orig.__new__(cls, *args, **kw)
        return cls._instance

class MyClass(Singleton):
    a = 1
```

### 2 共享属性

创建实例时把所有实例的`__dict__`指向同一个字典,这样它们具有相同的属性和方法.

```python

class Borg(object):
    _state = {}
    def __new__(cls, *args, **kw):
        ob = super(Borg, cls).__new__(cls, *args, **kw)
        ob.__dict__ = cls._state
        return ob

class MyClass2(Borg):
    a = 1
```

### 3 装饰器版本

```python
def singleton(cls):
    instances = {}
    def getinstance(*args, **kw):
        if cls not in instances:
            instances[cls] = cls(*args, **kw)
        return instances[cls]
    return getinstance

@singleton
class MyClass:
  ...
```

### 4 import方法

作为python的模块是天然的单例模式

```python
# mysingleton.py
class My_Singleton(object):
    def foo(self):
        pass

my_singleton = My_Singleton()

# to use
from mysingleton import my_singleton

my_singleton.foo()

```
**[单例模式伯乐在线详细解释](http://python.jobbole.com/87294/)**
