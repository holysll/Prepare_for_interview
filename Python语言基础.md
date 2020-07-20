---
layout: post
title: Python语言知识点总结归纳
date: 2020-06-03 22:25:17
updated: 2020-07-05 15:35:43
  - python
  - 后端
  - 知识回顾
categories: 编程语言-python

---

> 本文主要对python语言基础知识进行梳理、回顾，把一些需要记住的概念原理，和容易混淆，晦涩的知识点进行归纳。

<!-- more -->

<div style='display: none'>

<!-- TOC -->

- [1. Python语言的特性](#1-python语言的特性)
- [2. python语言相比其他语言的优点和缺点](#2-python语言相比其他语言的优点和缺点)
- [3. python中的元类metaclass](#3-python中的元类metaclass)
- [4. @staticmethod和@classmethod和实例方法](#4-staticmethod和classmethod和实例方法)
- [5. 单例模式](#5-单例模式)
- [6. python常用库](#6-python常用库)
- [7. python中的类型转换](#7-python中的类型转换)
- [8. 文件流操作](#8-文件流操作)
- [9. __new__ 和 __init__的区别](#9-__new__-和-__init__的区别)
- [10. python内存管理与垃圾回收机制](#10-python内存管理与垃圾回收机制)
- [11. python2.x 与python3.x的主要区别](#11-python2x-与python3x的主要区别)
- [12. 如何将python2的代码迁移到python3](#12-如何将python2的代码迁移到python3)
- [13. python新式类和旧式类的区别](#13-python新式类和旧式类的区别)
- [14. 鸭子类型](#14-鸭子类型)
- [15. python自省](#15-python自省)
- [16. 猴子补丁技术](#16-猴子补丁技术)
- [17. python语法糖有哪些](#17-python语法糖有哪些)
- [18. 迭代器和生成器](#18-迭代器和生成器)
- [19. 闭包](#19-闭包)
- [20. 装饰器](#20-装饰器)
- [21. 浅拷贝与深拷贝](#21-浅拷贝与深拷贝)
- [22. 设计模式](#22-设计模式)
    - [1. 工厂模式](#1-工厂模式)
    - [2. 构造模式](#2-构造模式)
    - [4. 原型模式](#4-原型模式)
    - [5. 单例模式](#5-单例模式-1)
    - [6. 装饰模式](#6-装饰模式)
    - [7. 代理模式](#7-代理模式)
    - [8. 适配器模式](#8-适配器模式)
    - [9. 外观模式](#9-外观模式)
    - [10. 享元模式](#10-享元模式)
    - [11. 桥接模式](#11-桥接模式)
    - [12. 组合模式](#12-组合模式)
    - [13. 命令模式](#13-命令模式)
    - [14. 访问者模式](#14-访问者模式)
    - [15. 责任链模式](#15-责任链模式)
    - [16. 备忘录模式](#16-备忘录模式)
    - [17. 中介者模式](#17-中介者模式)
    - [18. 状态模式](#18-状态模式)
    - [19. 模板方法模式](#19-模板方法模式)
    - [20. 解释器模式](#20-解释器模式)
    - [21. 迭代器模式](#21-迭代器模式)
    - [22. 观察者模式](#22-观察者模式)
    - [23. 策略模式](#23-策略模式)
- [23. GIL全局解释器锁](#23-gil全局解释器锁)
- [24. 函数是一等公民](#24-函数是一等公民)
- [25. 函数与方法的区别](#25-函数与方法的区别)
- [26. range与Xrange的区别](#26-range与xrange的区别)
- [27. search与match的区别](#27-search与match的区别)
- [28. 面向对象编程OOP](#28-面向对象编程oop)
- [29. 面向切面编程AOP](#29-面向切面编程aop)
- [30. 封装](#30-封装)
- [31. 继承](#31-继承)
- [32. 多态与多态性](#32-多态与多态性)
- [33. 重载](#33-重载)
- [34. 函数式编程](#34-函数式编程)
- [35. python中的高阶函数](#35-python中的高阶函数)
- [36. 返回函数](#36-返回函数)
- [37. 匿名函数](#37-匿名函数)
- [38. 偏函数](#38-偏函数)
- [39. 元编程](#39-元编程)
- [40. 捕获异常](#40-捕获异常)
- [41. python常见的内置数据结构](#41-python常见的内置数据结构)
- [42. python bytes与bytearray](#42-python-bytes与bytearray)
- [43. 字符串和字节串的区别](#43-字符串和字节串的区别)
- [44. 字符集（字符编码）](#44-字符集字符编码)
- [45. python中参数类型有哪些](#45-python中参数类型有哪些)
- [46. *args和**kwargs的区别](#46-args和kwargs的区别)
- [47. 实参和形参的区别](#47-实参和形参的区别)
- [48. python中函数传参过程](#48-python中函数传参过程)
- [49. python中可变对象和不可变对象](#49-python中可变对象和不可变对象)
- [50. python中正则使用方式](#50-python中正则使用方式)
- [51. Numpy、Scipy、Panadas的区别](#51-numpyscipypanadas的区别)
- [52. python中反射机制](#52-python中反射机制)
- [53. python中如何管理依赖](#53-python中如何管理依赖)
- [54. 如何分析python代码性能](#54-如何分析python代码性能)
- [55. 列表的顺序访问和随机访问](#55-列表的顺序访问和随机访问)
- [56. 随机函数](#56-随机函数)
- [57. Python中单下划线和双下划线](#57-python中单下划线和双下划线)
- [58. Python的作用域以及Python搜索变量的顺序](#58-python的作用域以及python搜索变量的顺序)
- [59. 编码与解码](#59-编码与解码)
- [60. 字符串格式化](#60-字符串格式化)
- [61. 增量赋值](#61-增量赋值)
- [62. exec对字符串执行和eval对字符串求值](#62-exec对字符串执行和eval对字符串求值)
- [63. raise语句的作用](#63-raise语句的作用)
- [64. yield语句的作用](#64-yield语句的作用)
- [65. 协程与生成器](#65-协程与生成器)
- [66. python decimal精确计算](#66-python-decimal精确计算)
- [67. 模块和代码块](#67-模块和代码块)
- [68. 上下文管理器](#68-上下文管理器)

<!-- /TOC -->

</div>

## 1. Python语言的特性

   Python是一种解释型语言，不需要再运行之前进行编译。
   Python是一种动态类型语言，不需要声明变量的类型。  
   python适合面向对象编程，允许类的定义以及组合和继承。  

## 2. python语言相比其他语言的优点和缺点

- **优点**
  - 简单易懂，灵活简洁
  - 强大的标准库和三方库
  - 活跃的社区，许多开源项目
  - 开发效率高，迭代便捷
  - 应用领域广泛，Web开发、网络编程、自动化运维、Linux系统管理、数据分析、科学计算、人工智能、机器学习

- **缺点**
  - 执行效率较差,
  - 异步生态不完善，相关的库较少(tornado)
  - GIL的存在，无法充分利用多核的特性

## 3. python中的元类metaclass

> 不会很常用，在ORM这种复杂结构中会遇到，同时在看一些框架源代码的过程中可能会遇到很多元类的实例，看起来很晦涩。推荐[Stack overflow](https://stackoverflow.com/questions/100003/what-are-metaclasses-in-python) 一些专业解答，也可以参考下[这篇博客](https://www.cnblogs.com/tkqasn/p/6524879.html)的深刻理解，很详细。

- **str是用来创建字符串对象的类**
- **int是用来创建整数对象的类**
- **type就是创建类对象的类**

> 通过type函数动态创建类

```python
# type的语法
type(class_name, class_parents, class_attr_dict)
"""
    class_name: 类名
    class_parents: 父类的元组(针对集成的情况，可为空)
    class_attr_dict: 包函属性的字典

"""

eg:
class MyClass(object):
    pass
    MyClass = type('MyClass', (), {'foo':True})
```

**元类：就是能够创建python中类这种对象的东西，如type就是Python的内建元类**

```python
    MyClass = MetaClass()  # 元类的创建
    my_class = MyClass()  # 类的实例
```

> 实际上Myclass就是通过type()来创建出的MyClass类，它是type()类的一个实例。
> 同时，MyClass本身也是累，也可以创建自己的实例my_class。

- **__metaclass__**

> 可以再写一个类的时候为其添加__metaclass__属性，这样就定义了这个类的元类。__metaclass__实际上可以被任意调用，它并不需要是一个正式的类。

```python
# py2
class Foo(object):
    __metaclass__ = something

# py3
class Foo(metaclass=something):
    __metaclass__ = something
```

- **自定义元类**

> 元类的主要目的为了当创建类时能够自动改变类，通常，你会为API做这样的事情，你希望可以创建符合当前上下文的类。

- 可以使用函数当做元类

```python
# 元类通常会将你传给type的参数作为自己的参数传入
def upper_attr(future_class_name, future_class_parents, future_class_attr):
    """返回一个类对象，将属性都转为大写形式"""
    # 选择所有不以'__'开头的属性
    attrs = ((name, value) for name, value in future_class_attr.items() if not name.startswith('__'))
    # 将他们转化为大写形式
    uppercase_attr = dict{(name.upper(), value) for name, value in attrs}
    # 通过type来做类对象的创建
    return type(future_class_name, future_class_parents, uppercase_attr)  # 返回一个对象，这个对象是个类

class Foo(metaclass=upper_attr):
    _metaclass__ = upper_attr
    bar = 'bip'

print(hasattr(Foo, 'bar'))  # False
print(hasattr(Foo, 'BAR'))  # True

f = Foo()
print(f.BAR)  # 'bip'
```

- 可以使用class来当做元类

```python
class UpperAttrMetaClass(type):
    def __new__(upperattr_metaclass, future_class_name, future_class_parents, future_class_attr):
        attrs = ((name, value) for name, value in future_class_attr.items() if not name.starswith('__'))
        uppercase_attr = dict((name.upper(), value) for name, value in attrs)

    # 复用type.__new__方法，OOP编程。
    # 由于type是元类也是类，本身也是通过__new__方法生成实例，只不过这个实例是一个类。
    return tpye.__new__(upperattr_metaclass, future_classs_name, future_class_parents, uppercase_attr)
```

- **真实业务场景下的元类**

```python
class UpperAttrMetaClass(type):
    def __new__(cls, name, bases, dct):
        attrs = ((name, value) for name, value in dct.items() if not name.startswith('__'))
        uppercase_attr = dict((name.upper(), value) for name, value in attrs)
        return type.__new__(cls, name, bases, uppercase_attr)
```

```python
# supper继承
class UpperAttrMetaClass(type):
    def __new__(cls, name, bases, dct):
        attrs = ((name, value) for name, value in dct.items() if not name.startswith('__'))
        uppercase_attr = dict((name.upper(), value) for name, value in attrs)
        return supper(UpperAttrMetaClass, cls).__new__(cls, name, bases, uppercase_attr)
```

- **使用元类创建ORM实例**

> 熟悉Django框架的，应该知道ORM结构，元类创建API，使得调用简洁明了。

```python
# -*- coding:utf-8 -*-
# 1.定义Field类，用于保存数据表的字段名和字段类型
class Field(object):
    def __init__(self, name, column_type):
        self.name = name
        self.column_type = column_type

    def __str__(self):
        return '<%s:%s>' % (self.__class__.__name__, self.name)

class StringField(Field):
    def __init__(self, name):
        super().__init__(name, 'varchar(100)')

class IntegerField(Field):
    def __init__(self, name):
        super().__init__(name, 'bigint')

# 定义元类，控制Model对象的创建
class ModelMetaClass(type):
    """定义元类"""
    def __new__(cls, name, bases, attrs):
        if name == 'Model':
            return type.__new__(cls, name, bases, attrs)
        print('Found model: %s' % name)

        # 排除掉对Model类的修改
        mappings = dict()
        for k, v in attrs.items():
            # 保存类属性和列的映射关系到mappings字典
            if isinstance(v, Field):
              print('Found mapping: %s==>%s' % (k, v)
              mappings[k] = v
        for k in mappings.keys():
            # 将类属性移除，是定义的类字段不污染User类属性，只在实例中可以访问这些key
            attrs.pop(k)
        # 假设表名为类名的小写，创建类时添加一个__table__类属性
        attrs['__table__'] = name.lower()
        # 保存属性和列的映射关系，创建类时添加一个__mappings__类属性
        attrs['__mappings__'] = mappings
        return type.__new__(cls, name, bases, attrs)

# 编写Model基类
class Model(dict, metaclass= ModelMetaClass):
    """只是简单实现了INSERT功能"""

    def __init__(self, **kw):
        super(Model, self).__init__(**kw)

    def __getattr__(self, key):
        try:
            return self[key]
        except KeyError:
            raise AttributeError(r"'Model' object has no attribute '%s'" % key)

    def __setattr__(self, key, value):
        self[key] = value

    def save(self):
        fields = []
        params = []
        args = []
        for k, v in self.__mappings__.items():
            fields.append(v.name)
            params.append('?')
            args.append(getattr(self, k, None))
        sql = 'insert into %s (%s) values (%s)' % (self.__table__, ','.join(fields), ','.join(params))
        print('SQL: %s' % sql)
        print('ARGS: %s' % str(args))


# 创建一个model，用户表User，定义数据字段就可实现数据表和字段的操作
class User(Model)：
    id = IntegerField('id')  # 对应数据表的id字段
    name = StringField('username')  # 对应数据表的username字段
    email = StringField('email')  # 对应数据表的email字段
    password = StringField('password')  # 对应数据表的password字段

# 创建一个实例
user = User(id=123456, name='Michael', email='test@163.com', password='123456')
# 保存数据库
user.save()
```

## 4. @staticmethod和@classmethod和实例方法

> **[what-is-the-difference-between-staticmethod-and-classmethod-in-python](https://stackoverflow.com/questions/136097/difference-between-staticmethod-and-classmethod)**

> **[real python上详细知识](https://realpython.com/instance-class-and-static-methods-demystified/)**

- **静态方法**

> 静态方法：其实和普通的方法一样，不需要对谁进行绑定，必须有@staticmethod修饰，类和实例都可以访问静态方法，调用方式A。static_foo(x)和a.static_foo(x)。

- **类方法**

> 类方法：即在类里定义的函数方法，需要@classmethod修饰，并且有个隐藏参数cls，传递的是类而不是实例，类可以访问类方法，也可以访问实例方法，访问实例方法时必须带参数self。

- **实例方法**

> 实例方法的调用离不开实例，必须有个参数self，把实例自己传给函数，调用是够是a.foo(x)与foo(a, x)等价。实例可以访问实例方法，也可以访问类方法。

```python
def foo(x)：
    print("executing foo(%s)" % (x))

class A(object):
    # 实例方法
    def foo(self, x):
        print("executing foo(%s, %s)" % (self, x))

    # 类方法
    @classmethod
    def class_foo(cls, x):
      print("executing foo(%s, %s)" % (cls, x)")

    # 静态方法
    @staticmethod
    def static_foo(x):
      print("executing foo(%s)" % x)

a = A()
```

| 实例/类 | 实例方法 | 类方法 | 静态方法 |
| :----: | :----: | :----: | :----: |
| 实例: a = A() | a.foo(x) | a.class_foo(x) | a.static_foo(x) |
| 类: A | 不可用 | A.class_foo(x) | A.static_foo(x) |

## 5. 单例模式

- **使用__new__方法**

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

- **共享属性**

> 创建实例时把所有实例的`__dict__`指向同一个字典，这样它们具有相同的属性和方法.

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

- **装饰器版本**

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
   ···
```

- **import方法**

> 作为python的模块是天然的单例模式

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

- **元类实现单例**

```python
# 通过__init__方法实现元类（优雅）
class Singleton(type):
    def __init__(self, *args, **kwargs):
        print("__init__")
        self.__instance = None
        super(Singleton, self).__init__(*args, **kwargs)

    def __call__(self, *args, **kwargs):
        print("__call__")
        if self.__instance is None:
            self.__instance = super(Singleton, self).__call__(*args, **kwargs)
        return self.__instance

class Foo(metaclass=Singleton):
    __metaclass__ = Singleton

foo1 = Foo()
foo2 = Foo()
print(Foo.__dict__)
print(foo1 is foo2)
```

```python
# 通过元类的__new__方法实现元类（为了实例增加属性重写__new__方法，不推荐）
class Singleton(type):
    def __new__(cls, name, bases, attrs):
        print("__new__")
        attrs["_instance"] = None
        return super(Singleton, cls).__new__(cls, name, bases, attrs)

    def __call__(self, *args, **kwargs):
        print("__call__")
        if self._instance is None:
            self._instance = super(Singleton, self).__call__(*args, **kwargs)
        return self._instance

class Foo(metaclass=Singleton):
   __metaclass__ = Singleton

foo1 = Foo()
foo2 = Foo()
print(Foo.__dict__)
print(foo1 is foo2)
```

**[单例模式伯乐在线详细解释](http://python.jobbole.com/87294/)**

## 6. python常用库

- **标准库**

  **[网友总结参考](https://www.cnblogs.com/haochengdu/p/8855028.html)**

  **[官网中文参考](https://docs.python.org/zh-cn/3.8/library/index.html)**

```python
    os：提供了不少于操作系统相关联的函数  

    sys：通常用于命令行参数

    res：正则表达式操作

    math：数学运算

    decimal：十进制定点和浮点运算

    datetime：日期时间

    collections：容器数据类型

    json：JSON 编码和解码器

    base64：Base16, Base32, Base64, Base85 数据编码

    heapq：堆队列算法

    copy：复制

    threading：基于线程的并行

    multiprocessing：基于进程的并行

    subprocess：子进程管理

    queue：一个同步的队列类

    random：生成伪随机数

    pprint：数据美化输出

    itertools：为高效循环而创建迭代器的函数

    functools：高阶函数和可调用对象上的操作

    operator：标准运算符替代函数

    logging：Python 的日志记录工具

    hashlib：安全哈希与消息摘要

    pickle：Python 对象序列化

    html.parser：简单的 HTML 和 XHTML 解析器

    urllib：URL 处理模块

    traceback：打印或检索堆栈回溯

    __future__：Future 语句定义

    gc：垃圾回收器接口
```

- **科学计算与数据分析库**

  > numpy：科学计算包，支持N维数组运算、处理大型矩阵、成熟的广播函数库、矢量运算、线性代数、傅里叶变换、随机数生成，并可与C++/Fortran语言无缝结合。

  > scipy：建立在NumPy基础上，它是离散傅立叶变换、线性代数、优化和稀疏矩阵等多种高级科学和工程模块最有用的库之一。

  > pandas：主要用于结构化数据的运算和操作，广泛用于数据整理和预处理，其有助于提高Python在数据科学社区的使用。

  > matplotlib：主要用于绘制各种各样的图形，从直方图到线图、热力图，还可以使用Latex命令在图像中添加数学符号。

  > Scikit：主要用于机器学习，该库建立在NumPy、SciPy和matplotlib基础上，包含许多有效的机器学习和统计建模工具，如分类、回归、聚类和降维。

  > Statsmodels：用于统计建模，是一个Python中提供用户探索数据、估计统计模型和执行统计测试的模组。可用于不同类型数据的描述性统计，统计测试，绘图功能和结果统计。

  > Seaborn：用于数据可视化，是一个用于在Python中制作有吸引力和翔实的统计图形库。它是基于matplotlib。Seaborn旨在使可视化成为探索和理解数据的核心组成。  

  > Bokeh：用于在现代网络浏览器上创建交互式图表，仪表盘和数据应用程序。它赋予用户以D3.js的风格生成优雅简洁的图形。此外，它具有超大型或流式数据集的高性能交互能力。

  > Blaze: 将Numpy和Pandas的能力扩展到分布式和流式传输数据集。它可以用于从众多来源包括Bcolz，MongDB,SQLAlchemy,Apache Spark,PyTables等访问数据，与Bokeh一起，可以作为在矩形数据模块上创建有效可视化和仪表盘的强大的工具。

  > Sympy：用于符号计算，具有从基本算数符号到微积分、袋鼠、离散数学和量子物理学的广泛能力，另一个有用的功能是将计算结果格式化为LaTeX代码。

- **第三方库**

  > pymysqldb：是在 Python2.x 版本中用于连接 MySQL 服务器的一个库，导包：import MySQLdb。

  > PyMySQL：是在 Python3.x 版本中用于连接 MySQL 服务器的一个库，导包：import pymysql，当要向下兼容python2时,可以加上：

  ```python
  import pymysql
  pymysql.install_as_MySQLdb()
  import MySQLdb

  # 创建一个连接对象，再使用创建游标
  con = pymysql.connect(host='127.0.0.1', port=3306, user='root', passwd='1234', db='mysql')
  cursor = con.cursor()

  # 执行一个SQL语句
  sql = "select * from user"
  cursor.execute(sql)

  # 从游标中取出所有记录放到一个序列中并关闭游标
  result = cursor.fetchall()
  print(result)
  cursor.close()
  ```

  > djano：是一个高层次的web开发框架，特点是开发快、代码少。可扩展性强。采用MTV（Model、Template、View）模型组织资源，框架功能丰富，模板扩展选择最多。

  > flask： 是一个web开发的微框架，严格来说，它仅仅提供web服务器支持，不提供全栈开发支持。然而，Flask非常轻量、非常简单，特别适合小微原型系统的开发，耗时少，开发效率高。  

  > Tornado：是一个基于异步网络功能库的Web开发框架，能够支持几万个开放连接，Web服务比较稳定。比较适合高并发场景下的Web系统，如秒杀系统、抢票系统等，灵活性较差。

  > Falcon：是一个支持大规模微服务API或移动App后端响应的web开发框架，它完全基于python并提供了非常高性能、可靠性和可扩展性。

  > Pyramid：是一个扩展性很强且灵活的web开发框架，上手十分容易，比较适合中等规模且边开发边设计的场景。它不提供绝对严格的框架定义，根据需求可以扩展开发，对高阶程序员十分友好。

  > Quart：是面向ASGI(异步服务器网关接口)开发的web为框架，采用Flask兼容的API接口，提供非常轻量级的开发方式。

  > requests：用于Web访问，类似于python标准库的urllib2，更容易更方便上手，适合初学者。

  > scrapy： 用于网络爬虫，它是获取特定模式数据的非常有用的框架，从网站首页URL开始,然后挖掘网站内的网页内容来手机信息。

  > selenium：是一个用于测试网站的自动化工具，支持Chrome、Firefox、Safari等主流界面浏览器，同时也支持PhantomJS无界面浏览器。

  > celery：是一个由python编写的简单、灵活、可靠的用于处理大量信息的分布式系统，它同时提供操作和维护分布式所需的工具，专注于实时任务，支持任务调度。是一个分布式队列管理工具，可以用celery提供接口快速实现并管理一个分布式任务队列。

## 7. python中的类型转换

| 函数    | 作用       |      | 函数    | 作用   |      | 函数      | 作用         |
| ------- | ---------- | ---- | ------- | ------ | ---- | --------- | ------------ |
| int()   | 转整型     |      | list()  | 转列表 |      | bin()     | 整数转2进制  |
| float() | 转浮点型   |      | dict()  | 转字典 |      | oct()     | 整数转6进制  |
| str()   | 转字符串   |      | set()   | 转集合 |      | hex()     | 整数转16进制 |
| ord()   | 字符转整数 |      | tuple() | 转元组 |      | complex() | 实数转复数   |

## 8. 文件流操作

- **打开文件**

```python
f=open('file_name', 'file_type')
if f:  # 判断文件是否打开
file_type
with open('file_name', 'file_type') as f:
```

- **访问模式**

```python
w: 只写

r：只读

a: 追加写入
rb: 二进制只读

wb：二进制写入

ab：二进制追加写入

r+：打开一个文件用于读写，文件指针将会放在文件的开头。

w+：打开一个文件用于读写，如果文件已经存在则将其覆盖，如果文件不存在，则创建新文件。

a+：打开一个文件用于读写，追加模式。如果文件存在，文件指针将会放在文件的结尾；如果该文件不存在，穿件新文件用于读写。

rb+: 以二进制格式打开一个文件用于读写，文件指正将会放在文件的开头，一般用于非文本文件如图片等。

wb+:以二进制格式打开一个文件用于读写。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件，一般用于非文本文件如图片等。

ab+:以二进制格式打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾；如果文件不存在，创建新文件用于读写。
```

- **写文件**

```python
f.write(content)  # 打开文件后，将制定内容写入文件中
```

- **读取文件**

```python
f.read(lenth)  # 使用read可以从文件中读取制定长度的数据，并将指针移到这条数据之后。如果为空，则默认读取全部数据。

f.readline()  # 读取文件中一行数据的信息，指针移动到下一行。

f.readlines() # 读取整个文件的数据信息，返回一个列表，列表中每个元素为一行数据信息。
```

- **查看指针位置**

```python
f.tell()  # 查看单签位置，就是指针对应的位置
```

- **指针定位**

```python
seek(offset, from)  # 将指针定位到某个位置

from: # 方向，0表示文件开头；1表示文件当前位置；2表示文件的末尾
offset: 偏移量

eg:
    f.seek(5,0)  # 文件开头，向后偏移5个位置
    f.seek(-3,2)  # 文件结尾，向前偏移3个位置
```

## 9. __new__ 和 __init__的区别

- __new__是一个静态方法，而__init__是一个实例方法
- __new__方法会返回一个创建的实例，而__init__什么都不返回
- 只有在__new__返回一个cls的实例时，后面的__init__才能被调用
- 创建一个新实例时调用__new__方法，初始化一个实例时调用__init__方法

## 10. python内存管理与垃圾回收机制

**[Python垃圾回收机制详解](https://blog.csdn.net/xiongchengluo1129/article/details/80462651)**

> Python GC主要使用引用计数(reference counting)来跟踪和回收垃圾。在引用计数的基础上，通过标记清除机制(mark and sweep)解决容器对象可能产生的循环引用问题，通过分代回收(generation collection)策略，以空间换时间的方法来提高垃圾回收的效率。

- 引用计数

> 引用计数法的原理是每个对象维护一个ob_ref，用来记录当前对象被引用的次数，也就是来追踪到底有多少引用指向了这个对象，当发生（对象被创建、对象被引用、对象被作为参数传到函数中、对象作为一个元素，存储在容器中）四种情况的时候，该对象的引用计数+1；当发生（该对象的别名被显示销毁时、该对象的引别名被赋予新的对象、一个对象离开它的作用域、该元素从容器中删除时或容器被销毁时），该对象的引用计数器-1。

**简而言之，PyObject是每个对象必有的内容，其中ob_refcnt就是做为引用计数。当有一个对象有新的引用时，它的ob_refcnt就会增加，当引用它的对象被删除，它的ob_refcnt就会减少。当引用计数为0时，该对象生命就结束了。**

**优点：**  
① 高效  
② 运行期没有停顿  
③ 对象有确定的生命周期  
④ 易于实现

**缺点：**  
① 维护引用计数消耗资源，维护引用计数的次数和引用赋值成正比，而不像mark and sweep等基本与回收的内存数量有关。  
② 无法解决循环引用的问题。

- 标记清除机制(mark and sweep)

> 基本思路是先按需分配，等到没有空闲内存的时候从寄存器和程序栈上的引用出发，遍历以对象为节点、以引用为边构成的图，把所有可以访问到的对象打上标记，然后清扫一遍内存空间，把所有没有标记的对象释放。为了保证效率，Python只会在垃圾达到一定阈值时，垃圾回收才会启动。主要处理对象是一些容器对象，如list、dict、tuple、set、instance等，因为对于字符串、数值对象是不可能造成循环引用问题。

**缺点：**  
①清除非活动对象前必须顺序扫描整个堆内存，哪怕只剩下小部分活动对象也要扫描所有对象。

- 分带回收策略

> 分代回收的整体思想是：将系统中所有的内存块根据其存活时间划分为不同的集合，每个集合就成为一个“代”，python将内存等为3“代”，分别是年轻代(第0代)、中年代(第1代)、老年代(第2代)，它们对应的是三个链表，它们的垃圾回收集频率随着“代”的存活时间的增大而减小，新创建的对象都会分配在年轻代，年轻代链表总数达到上限时，python垃圾回收机制就回被触发，把那些可以被回收的对象回收，而那些不被回收的对象就会移到中年代去，以此类推，老年代中的对象是存活时间最久的对象，甚至是存活于整个系统的生命周期，存活时间通常利用经过几次垃圾回收来度量。同时，分代回收是建立在标记清除技术基础之上。

> Python默认定义三代对象集合，索引越大，对象存活时间越长。

## 11. python2.x 与python3.x的主要区别

**[比较详细](https://www.pythonheidong.com/blog/article/22/)**

- 输入， py2中：raw_input(); py3中：input()

- 输出， py2中：print语句; py3中：print()函数

- 除法，py2中整数间进行'/'和'//'运算返回的是整数，而py3的'/'运算返回的是浮点数

- 遍历范围，py2中：range()或xrange(); py3中：不等于，py2中：range

- 不等于，py2中：<>或!= ; py3中：!=

- 编码问题，py3默认使用unicode，字节是bytes；而py2中字节是str, 默认支持ascii编码，unicode需要在前面加u

- 异常，py2中：except exec, var ; py3中：except exec as var

- 八进制字面量，py2中：0o777或0777 ; py3中：0o777

- 去掉了repr表达式``，py2中：反引号相当于repr()的作用; py3中：去除反引号写法

- 多个模块变化

| 旧的名字 | 新的名字 |
| ---- | ---- |
| _winreg | winreg |
| ConfigParser | configparser |
| copy_reg | copyreg |
| Queue | queue |
| SocketServer | socketserver |
| repr | reprlib |

- 数据类型，py3中去除long类型，只有int

- rasie，py2中：raise IOError, "file error"; py3中：raise IOError("file error")

- 去除.next()，py2中：next(generator)和generator.next(); py3中：next(generator)

- py3中for循环变量不会导致命名空间泄漏

- py3中不能比较不可排序类型，需同类型比较

- py3中range、zip、map、reduce、filter等返回的是可迭代对象，而不是列表

- py3中新增asynico内置库，async/await原生协程支持异步编程

- py3中移除cmp函数

- py3中去除元组参数解包

- 增加了@abstractmethod和 @abstractproperty两个 decorator，编写抽象方法（属性）更加方便

- 移除了cPickle模块，可以使用pickle模块代替

- 移除了new模块

- 移除了 audiodev, Bastion, bsddb185, exceptions, linuxaudiodev, md5, MimeWriter, mimify, popen2,
rexec, sets, sha, stringold, strop, sunaudiodev, timing和xmllib模块

- 移除了imageop模块

- 迭代器的next()方法改名为__next__()，并增加内置函数next()，用以调用迭代器的__next__()方法

## 12. 如何将python2的代码迁移到python3

**[官方文档](https://docs.python.org/zh-cn/3.9/howto/pyporting.html)**

> 第一步：使用自带的2to3.py文件，可以实现大部分代码从py2到py3的自动转换。命令：2to3 -w example.py

> 第二步：使用Pylint或者Pyflakes工具，检测代码错误。

> 第三步：检查模块和依赖库的变化。

> 第四步：人工修复被破坏的py2代码。

**利用好__future__模块**

```python
from __future__ import division  # 在Python 2 中表现 Python 3.x 中的整除
from __future__ import unicode_literals  # 适应Python 3.x的新的字符串的表示方法
from __future__ import print_function  # 使用打印功能
from __future__ import nested_scopes  # 静态嵌套范围
from __future__ import generators  # 简单生成器
from __future__ import absolute_import  # 绝对/相对导入
from __future__ import with_statement  # with声明
```

## 13. python新式类和旧式类的区别

> 新式类是在创建的时候继承内置的object对象或者是内置类型如list、dict，而旧式类(经典类)是直接声明的，可以用dir()方法查看新式类中内置了很多性的属性和方法。

> 新式类遍历方法是广度优先，经典类是深度优先。

## 14. 鸭子类型

> 编程语言中动态类型语言的一种设计风格，一个对象的特征不是由父类决定，而是通过对象的方法决定。类与类之间不用共同继承一个父类，只需要将它们做的像一件事物即可。

> 注重对象的行为，而非对象的类型，一个对象能都作为函数、表达是的参数，取决于其行为而非类型归属。

```python
class Duck:
    def __init__(self, name):
        self.name = name

    def quack(self):
        print("gua gua")


class Man:
    def __init__(self, name):
        self.name = name

    def quack(self):
        print("女王大人")


def do_quack(ducker):
    ducker.quack()


if __name__ == '__main__':
    d = Duck('duck')
    m = Man('man')
    do_quack(d)
    do_quack(m)

# 结果
'''
gua gua
女王大人
'''
```

## 15. python自省

> 在一些语言中也叫做反射，简单来说就是对象检查。面向对象的语言所写的程序在运行时，所能知道对象的类型。是什么(isinstance)，是什么类型(type)，有那些属性(hasattr)，有哪些变量方法(dir)，有哪些行为(hasattr)，getattr、setattr、delattr、callable。

## 16. 猴子补丁技术

> 是一种让程序行为在运行时扩展或者变更的方法。

> python充分利用动态语言的特性，在程序运行时动态改变类、模块、属性或方法，为的是将第三方代码打补丁在不按预期运行的bug或者feature上，gevent在这方面运用的比较多。

## 17. python语法糖有哪些

> 在计算及科学中，语法糖是某种特殊的语法，对语言的功能没有影响，但对程序员来说，有更好的易用性，简洁性、可读性、方便性。比如索引切片、列表推导式、字典推导式、生成器推导式等等。

- 切片操作

**[Python切片操作详细例子](https://www.jianshu.com/p/15715d6f4dad)**

```python
s = '123456'
s[:3]  # 结果为'123'，取索引索引小于3的值，或叫“取前3位”
s[3:]  # 结果为'456', 取索引大于等于3的值，或叫“从第4位取到最后”
s[2:4]  # 结果为'34', 取索引大于等2，小于4的值，或叫“取第3位到第4位”
s[:]  # 结果为'123456', 取索引全部
s[:-1]  # 结果为'654321' 取倒序
s[::2]  # 结果为'135' 步长为2取值
```

- with打开文件

> 实现的是一个上下文管理器，它主要的特点就是帮助我们自动管理上下文的衔接。即在需要的时候传给我们，不需要的时候自动关闭上下文对象。

```python
with open('test.txt', 'r', encoding='utf-8') as f:
    for line in f:
        print(line,end='')

```

- else语法糖

> for-else、while-else 需要和break语句配合使用。

> try-else-finally

- 动态参数: (*args, **kwargs)

- 匿名函数: lambda x: x * 2

- 推导表达式

> 列表推导表达式：[i for i in s if i%2 != 0]
> 生成器推导表达式： (i for i in s if i%2 != 0)
> 集合推导表达式：{i for i in s if i%2 != 0}
> 字典推导表达式：{i:i*2 for i in s if i%2 != 0}

- yield表达式

> yield是Python中实现**协程(coroutine)**的一个重要基础

```python
def my_generator(s):
    '''生成器'''
    for i in s:
        yield i*2
```

- 装饰器

> 一种设计模式，本质上也是一种python函数，是一种闭包。装饰器需要返回一个对象，该对象可以是经过处理的原参数对象，一个包装且类似原参数的对象。

```python
def my_decorator(func):
    '''装饰器'''
    def inner():
        func()

    return inner
```

- map

> map(function, iterable, ...) 会根据提供的函数对指定序列做映射。function函数，iterable一个或多个序列，其中py2返回的列表，py3返回的是迭代器。

```python
def square(x):
    return x ** 2
map(square, [1,2,3,4,5])

map(lambda x: x ** 2, [1,2,3,4,5])

map(lambda x, y: x + y, [1,3,5,7,9], [2,4,6,8,10])
```

- reduce

> reduce(function, iterable[, initializer]) 函数会对参数序列中元素进行累积。function 有两个参数, iterable可迭代对象，initializer可选，初始参数。用传给 reduce 中的函数 function（有两个参数）先对集合中的第 1、2 个元素进行操作，得到的结果再与第三个数据用 function 函数运算，最后得到一个结果。

```python
def add(x, y):
    return x + y
reduce(add, [1,2,3,4,5])

reduce(lambda x, y: x+y, [1,2,3,4,5])
```

- filter

> filter(function, iterable) 函数用于过滤序列，过滤掉不符合条件的元素，返回由符合条件元素组成的新列表。function判断函数，iterable可迭代对象，该接收两个参数，第一个为函数，第二个为序列，序列的每个元素作为参数传递给函数进行判断，然后返回 True 或 False，最后将返回 True 的元素放到新列表中。

```python
def odd(n):
    return n % 2 == 1
newlist = filter(odd, [1,2,3,4,5,6,7,8,9,10])
print(list(newlist))
```

## 18. 迭代器和生成器

> 迭代器是一个更抽象的概念，任何对象，如果它的类有next方法和iter方法返回自己本身。对于string、list、dict、tuple等这类容器对象，使用for循环遍历是很方便的。在后台for语句对容器对象调用iter()函数，iter()是python的内置函数。iter()会返回一个定义了next()方法的迭代器对象，它在容器中逐个访问容器内元素，next()也是python的内置函数。在没有后续元素时，next()会抛出一个StopIteration异常。

> 生成器(Generator)是创建迭代器的简单而强大的工具。它们写起来就像是正规的函数，只是在需要返回数据的时候使用yield语句，生成器使用yield语句返回一个值，yield语句挂起该生成器函数的状态，保留足够的信息，以便之后从它离开的地方继续执行。每次next()被调用时，生成器会返回它脱离的位置（它记忆语句最后一次执行的位置和所有的数据值）。生成器需要注意：只能遍历一次。

> 区别：生成器能做到迭代器能做的所有事，而且因为自动创建了__iter__()和next()方法，生成器显得特别简洁，而且生成器也是高效的，使用生成器表达式取代列表解析可以同时节省内存。除了创建和保存程序状态的自动方法，当发生器终结时，还会自动抛出StopIteration异常。

## 19. 闭包

> 闭包(closure)是函数式编程的重要的语法结构，也是一种组织代码的结构，提高了代码的复用性。简单说，外函数的内部定义了一个内函数，内部函数使用了外部函数的临时变量，并外函数的返回值是内函数的引用。产生闭包需满足的条件：

- 必须有一个内嵌函数
- 内嵌函数必须引用外部函数的变量
- 外部函数的返回值必须是内嵌函数

> 简单说，闭包就是根据不同的配置信息得到不同的结果，装饰器就是一种闭包，闭包有效的减少了函数所需定义的参数数目。

> 闭包的好处：
    - 取代硬编码中的常量
    - 避免使用全局值，并提供某种形式的数据隐藏
    - 提供一致的函数签名
    - 实现面向对象

```python
def line_conf(a, b):
    def line(x):
        return a*x +b
    return line

line1 = line_conf(1, 1)
line2 = line_conf(4, 5)
print(line1(5), line2(5))  # (6, 25)
```

> **返回闭包时：返回函数不要引用任何循环变量，或者后续会发生变化的变量**。解决方法是在创建一个函数，用函数的参数绑定循环变量当前的值，无论该循环变量后续如何更改，已绑定到函数参数的值不变。

```python
def count():
    def f(j):
        def g():
            return j*j
        return g
    fs = []
    for i in range(1, 4):
        fs.append(f(i))
    return fs

f1, f2, f3 = count()
print(f1())
print(f2())
print(f3())

# 结果
'''
1
4
9
'''
```

## 20. 装饰器

> **以下是一些前人的总结参考：**

**[python装饰器](https://blog.csdn.net/tryhardsilently/article/details/90767627)**

**[Python装饰器各种类型详解](https://blog.csdn.net/yhy1271927580/article/details/72758577)**

**[Python各种类型装饰器详解说明](https://blog.csdn.net/five3/article/details/83447467)**

**[python装饰器的4种类型](https://blog.csdn.net/xiemanr/article/details/72510885)**

**[一文看懂Python系列之装饰器](https://blog.csdn.net/weixin_42134789/article/details/84635252?utm_medium=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-3.nonecase&depth_1-utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-3.nonecase)**

**[python装饰器简介](https://blog.csdn.net/u010358168/article/details/77773199?utm_medium=distribute.pc_relevant_right.none-task-blog-BlogCommendFromMachineLearnPai2-29.nonecase&depth_1-utm_source=distribute.pc_relevant_right.none-task-blog-BlogCommendFromMachineLearnPai2-29.nonecase)**

> 装饰器本质上是一个函数，可以让其他函数在不需要做任何代码处理的前提下增加额外的功能，装饰器的返回值也是一个函数对象(函数的引用)。它经常用于有切面需求的场景，比如：**插入日志、性能测试、事务处理、缓存、权限校验等场景**，装饰器是解决这类问题的绝佳设计。有了装饰器，我们就可以抽离出大量与函数功能本身无关的雷同代码到装饰器中并继续重用。概括的讲，装饰器的作用就是为已经存在的对象添加额外的功能。

- **装饰器自身为函数**

(1). 被装饰的对象为函数，且不带参数  

```python
import time
from functools import wraps

# 装饰器为函数，且不带参数
def time_decorator(func):
    @wraps(func)  # 保证装饰过的函数__name__属性不变
    def inner():
        print("Hello inner")
        start = time.time()
        func()
        end = time.time()
        print('方法{}用时:{}秒'.format(func.__name__, end - start))

    return inner

# 被装饰的对象为函数，且不带参数
@time_decorator
def foo():
    time.sleep(3)
    print("foo is running.")

# 调用装饰后的foo函数
print(foo.__name__)
foo()

# 结果
'''
inner
Hello inner
foo is running.
方法foo用时:3.01444411277771秒
'''
```

> 在以上代码中，@time_decorator装饰器对foo函数进行了装饰，这是一个不带参数的装饰器，当python解释器执行到@time_decorator时，回去调用time_decorator函数，同时将被装饰的对象的函数名foo作为参数传入，这时time_decorator函数接受到一个参数(即方法名foo)，然后进入内嵌函数inner，计算开始时间，调用传进来的foo方法，再计算结束时间，打印函数foo的耗时，最后将结果用内部函数inner返回，其实就是一个闭包函数。

> 首先打印的是foo.__name__，这里是inner而不是foo，本质上是调用inner函数  
> 其次打印的是inner的内容"Hello inner"，然后开始调用foo函数，打印"func1 is running."  
> 最后打印"方法foo用时:3.01444411277771秒"

(2). 被装饰的对象为函数，且带参数  

```python
import time
from functools import wraps

# 装饰器为函数，且不带参数
def time_decorator(func):
    """
    如果原函数有参数，那闭包函数必须保持参数个数一直，并且将参数传递给原方法
    """
    @wraps(func)  # 保证装饰过的函数__name__属性不变
    def inner(name):  # 如果被装饰的函数有形参，那么闭包函数必须有参数，且一致
        print("Hello inner")
        start = time.time()
        func(name)
        end = time.time()
        print('方法{}用时:{}秒'.format(func.__name__, end - start))

    return inner

# 调用装饰后的foo函数，且带参数
@time_decorator
def foo(name):
    time.sleep(3)
    print("hello " + name)

# 调用装饰后的foo函数
print(foo.__name__)
foo('lucy')

# 结果
'''
foo
Hello inner
hello lucy
方法foo用时:3.000863790512085秒
'''
```

> 当被装饰的函数，带参数时，需要在装饰器的闭包函数inner函数中添加一致的参数name，调用func对象时也需要加上一致的参数name，并且返回了以reurn inner形式返回闭包函数，具体调用过程看结果应该不难理解。

> 当然，如果被装饰函数存在多个参数时，这里使用了python中动态参数的概念，利用`(*args, **kwargs)`来接收可变参数和关键字参数，这样装饰器就可以支持任意的组合参数的函数了。装饰器修改如下：

```python
import time
from functools import wraps

# 装饰器为函数，且不带参数
def time_decorator(func):
    @wraps(func)  # 保证装饰过的函数__name__属性不变
    def inner(*args, **kwargs):  # 接收可变参数和关键字参数
        print("Hello inner")
        start = time.time()
        func(*args, **kwargs)
        end = time.time()
        print('方法{}用时:{}秒'.format(func.__name__, end - start))

    return inner

# 调用装饰后的foo函数，且带参数
@time_decorator
def foo(name):
    time.sleep(3)
    print("hello " + name)

# 调用装饰后的foo函数
print(foo.__name__)
foo('lucy')

# 结果
'''
foo
Hello inner
hello lucy
方法foo用时:3.000807762145996秒
'''
```

(3). 被装饰的对象为函数，且带返回值

```python
import time
from functools import wraps

# 装饰器为函数，且不带参数
def time_decorator(func):
    @wraps(func)  # 保证装饰过的函数__name__属性不变
    def inner():
        print("Hello inner")
        start = time.time()
        res = func()
        end = time.time()
        print('方法{}用时:{}秒'.format(func.__name__, end - start))
        return res

    return inner

# 被装饰的对象为函数，且带返回值
@time_decorator
def foo():
    time.sleep(3)
    print("foo is running.")
    return "this is foo's return value"


# 调用装饰后的foo函数
print(foo.__name__)
res = foo()
print('返回值：%s' % res)

# 结果
'''
foo
Hello inner
foo is running.
方法foo用时:3.000837802886963秒
返回值：this is foo's return value
'''
```

> 若被装饰的函数是带返回值的，闭包函数inner中，调用func()时必须相应的带返回值，不然装饰函数时，也不进行返回，默认为None。

(4). 被装饰的对象为函数，且装饰器带参数也有返回值

```python
import time
from functools import wraps

# 装饰器为函数，且带参数带返回值
def time_decorator(arg=None):  # 如果在调用装饰器时为给传参数，则默认值为None
    def wrapper(func):
        @wraps(func)  # 保证装饰过的函数__name__属性不变
        def inner(*args,**kwargs):
            print("Hello inner")
            print("装饰器的参数为：{}".format(arg))
            start = time.time()
            res = func(*args,**kwargs)
            end = time.time()
            print('方法{}用时:{}秒'.format(func.__name__, end - start))
            return res

        return inner
    return wrapper

# 被装饰的对象为函数，且不定参数
@time_decorator('hello')
def foo():
    time.sleep(3)
    print("foo is running.")
    return "this is foo's return value"

# 调用装饰后的foo函数
print(foo.__name__)
res = foo()
print('返回值：%s' % res)

# 结果
'''
foo
Hello inner
装饰器的参数为：hello
foo is running.
方法foo用时:3.000739336013794秒
返回值：this is foo's return value
'''
```

> 带有参数的装饰器，需要写三层嵌套函数，最外一层用来传递装饰器的参数。上面的装饰器即带参数也带返回值，先执行time_decorator('hello')，返回wrapper函数的应用，然后使用wrapper对函数foo进行装饰，内层inner使用的是`*args,**kwargs`接收可变参数和关键字参数，具体运行顺序看结果应该不难理解。

(5). 被装饰的对象为类，且不带参数

```python
from functools import wraps

# 装饰器为函数，且不带参数
def singleton(cls):
    # 在装饰器中声明一个变量，用于保存类的实例，那么这个实例对象将始终是通过一个实例对象
    instances = {}
    @wraps(cls)
    def inner():
        print('Hello inner')
        print('class name: {}'.format(cls.__name__))
        if cls not in instances:
            instances[cls] = cls()
        return instances[cls]
    return inner

# 被装饰的对象是类，且不带参数
@singleton
class Foo():
    def __init__(self):
        self.name = 'lucy'

    def say(self):
        print("her name is {}".format(self.name))

# 实例化装饰后的类
print(Foo.__name__)
foo = Foo()
foo.say()

# 结果
'''
Foo
Hello inner
class name: Foo
her name is lucy
'''
```

> 上面的例子是基于装饰器的单例模式，通过装饰器装饰这个类，是的类在初始化时候始终将初始化实例赋值给instances，而instances是装饰器的一个实例对象，通过实例赋值，instances始终占有同一个内存空间，也就实现了单例模式设计。

> 当然，如果用这个装饰器对类里面方法say进行装饰的话，此时装饰器single接收到的参数cls=say，所以打印"class name"是say，因为cls__name__就是say，这里等同于函数装饰器给函数进行装饰，于是装饰器的内层函数inner需要接受say带来的参数name，不加参数则会报错，其他与前面一样。

```python
from functools import wraps

# 装饰器为函数，且不带参数
def singleton(cls):
    # 在装饰器中声明一个变量，用于保存类的实例，那么这个实例对象将始终是通过一个实例对象
    instances = {}
    @wraps(cls)
    def inner(name):  # 必须和所修饰类里面的函数参数个数一致，否则会报错
        print('Hello inner')
        print('class name: {}'.format(cls.__name__))
        if cls not in instances:
            instances[cls] = cls(name)
        return instances[cls]
    return inner

# 被装饰的对象是类中的函数，调用类中的初始化参数
class Foo():
    def __init__(self):
        self.name = 'lucy'

    @singleton
    def say(self):
        print("her name is {}".format(self.name))

# 实例化装饰后的类
print(Foo.__name__)
foo = Foo()
foo.say()

# 结果
'''
Foo
Hello inner
class name: say
her name is lucy
'''
```

(6). 被装饰的对象为类，且带参数

```python
from functools import wraps

# 装饰器为函数，且不带参数
def singleton(cls):
    # 在装饰器中声明一个变量，用于保存类的实例，那么这个实例对象将始终是通过一个实例对象
    instances = {}

    @wraps(cls)
    def inner(*args, **kwargs):
        print('Hello inner')
        print('class name: {}'.format(cls.__name__))
        if cls not in instances:
            instances[cls] = cls(*args, **kwargs)
        return instances[cls]

    return inner

# 被装饰的对象是类，且带参数
@singleton
class Foo():
    def __init__(self, *args, **kwargs):
        self.id = args[0]
        self.name = kwargs.get('name_dict').get(self.id)

    def say(self):
        print("her name is {}".format(self.name))

# 实例化装饰后的类
print(Foo.__name__)
foo = Foo('1', '2', '3', name_dict={'1': 'Lucy', '2': 'Linda', '3': 'Mary'})
foo.say()

# 结果
'''
Foo
Hello inner
class name: Foo
her name is Lucy
```

(7). 被装饰的对象为类，且装饰器带参数也有返回值

```python
from functools import wraps

# 装饰器为函数，且带参数带返回值
def singleton(arg=None): # 如果在调用装饰器时为给传参数，则默认值为None
    def wrapper(cls):
        # 在装饰器中声明一个变量，用于保存类的实例，那么这个实例对象将始终是通过一个实例对象
        instances = {}

        @wraps(cls)
        def inner(*args, **kwargs):
            print('Hello inner')
            print("装饰器的参数为：{}".format(arg))
            print('class name: {}'.format(cls.__name__))
            if cls not in instances:
                instances[cls] = cls(*args, **kwargs)
            return instances[cls]

        return inner
    return wrapper

# 被装饰的对象是类，且带参数
@singleton('hello')
class Foo():
    def __init__(self, *args, **kwargs):
        self.id = args[0]
        self.name = kwargs.get('name_dict').get(self.id)

    def say(self):
        print("her name is {}".format(self.name))

# 实例化装饰后的类
print(Foo.__name__)
foo = Foo('1', '2', '3', name_dict={'1': 'Lucy', '2': 'Linda', '3': 'Mary'})
foo.say()

# 结果
'''
Foo
Hello inner
装饰器的参数为：hello
class name: Foo
her name is Lucy
'''
```

> 这里与（4）类似，都是带有参数的装饰器，且装饰器为函数，需要写三层嵌套函数，最外一层用来传递装饰器的参数。上面的装饰器即带参数也带返回值，先执行time_decorator('hello')，返回wrapper函数的应用，然后使用wrapper对函数foo进行装饰，内层inner使用的是`*args,**kwargs`接收可变参数和关键字参数，具体运行顺序看结果应该不难理解。

- **装饰器自身为类**

> 类装饰器本质上和函数装饰器原理、作用相同，都是为其它函数增加额外的功能。但是相比于函数装饰器，类装饰器具有灵活度大、高内聚、封装性等优点。使用类装饰器可以直接依靠类内部的__call__方法来实现，当使用 @ 形式将类装饰器附加到函数上时，就会调用类装饰器的__call__方法。而不需要向函数装饰器那样，在装饰器函数中定义嵌套函数，来实现装饰功能。

(1). 被装饰的对象为函数，且不带参数

```python
import time
from functools import wraps

# 装饰器是类，且不带参数
class Decorator(object):
    def __init__(self,func):
        # 初始化函数只会调用一次，当第二次装饰的时候，这一步就滤过了
        print('decorator init')
        print('func name is {}'.format(func.__name__))
        self.func = func

    def __call__(self):
        print('装饰器中的功能：{} 睡眠3秒'.format(self.func.__name__))
        start = time.time()
        res = self.func()
        end = time.time()
        print('方法{}用时:{}秒'.format(self.func.__name__, end - start))
        return res

# 被装饰的对象为函数，且不带参数
@Decorator
def foo():
    time.sleep(3)
    print("foo is running.")

# 调用装饰后的foo函数
print(foo.func.__name__)
foo()

# 结果
'''
decorator init
func name is foo
foo
装饰器中的功能：foo 睡眠3秒
foo is running.
方法foo用时:3.000671863555908秒
'''
```

> 装饰器为类时，调用__init__方法创建实例、传递参数，并调用__call__方法实现对被装饰函数功能的添加。

(2). 被装饰的对象为函数，且带参数

```python
import time
from functools import wraps

# 装饰器是类，且不带参数
class Decorator(object):
    def __init__(self,func):
        # 初始化函数只会调用一次，当第二次装饰的时候，这一步就滤过了
        print('decorator init')
        print('func name is {}'.format(func.__name__))
        self.func = func

    def __call__(self, name):
        print('装饰器中的功能：{} 睡眠3秒'.format(self.func.__name__))
        start = time.time()
        res = self.func(name)
        end = time.time()
        print('方法{}用时:{}秒'.format(self.func.__name__, end - start))
        return res

# 被装饰的对象为函数，且带参数
@Decorator
def foo(name):
    time.sleep(3)
    print("hello " + name)

# 调用装饰后的foo函数
print(foo.func.__name__)
foo('lucy')

# 结果
'''
decorator init
func name is foo
foo
装饰器中的功能：foo 睡眠3秒
hello lucy
方法foo用时:3.0009634494781494秒
'''
```

> 当被装饰的函数，且带参数时，需要在装饰器类的__call__中添加一致的参数name，调用func对象时也需要加上一致的参数name，并且返回了以reurn inner形式返回闭包函数，具体调用过程看结果应该不难理解。

> 当然，如果被装饰函数存在多个参数时，这里使用了python中动态参数的概念，利用`(*args, **kwargs)`来接收可变参数和关键字参数，这样装饰器就可以支持任意的组合参数的函数了。装饰器修改如下：

```python
import time
from functools import wraps

# 装饰器是类，且不带参数
class Decorator(object):
    def __init__(self,func):
        # 初始化函数只会调用一次，当第二次装饰的时候，这一步就滤过了
        print('decorator init')
        print('func name is {}'.format(func.__name__))
        self.func = func

    def __call__(self, *args, **kwargs):
        print('装饰器中的功能：{} 睡眠3秒'.format(self.func.__name__))
        start = time.time()
        res = self.func(*args, **kwargs)
        end = time.time()
        print('方法{}用时:{}秒'.format(self.func.__name__, end - start))
        return res

# 被装饰的对象为函数，且带参数
@Decorator
def foo(name):
    time.sleep(3)
    print("hello " + name)

# 调用装饰后的foo函数
print(foo.func.__name__)
foo('lucy')

# 结果
'''
decorator init
func name is foo
foo
装饰器中的功能：foo 睡眠3秒
hello lucy
方法foo用时:3.000622510910034秒
'''
```

(3). 被装饰的对象为函数，且带返回值  

```python
import time
from functools import wraps

# 装饰器是类，且不带参数
class Decorator(object):
    def __init__(self,func):
        # 初始化函数只会调用一次，当第二次装饰的时候，这一步就滤过了
        print('decorator init')
        print('func name is {}'.format(func.__name__))
        self.func = func

    def __call__(self):
        print('装饰器中的功能：{} 睡眠3秒'.format(self.func.__name__))
        start = time.time()
        res = self.func()
        end = time.time()
        print('方法{}用时:{}秒'.format(self.func.__name__, end - start))
        return res

# 被装饰的对象为函数，且带返回值
@Decorator
def foo():
    time.sleep(3)
    print("foo is running.")
    return "this is foo's return value"

# 调用装饰后的foo函数
print(foo.func.__name__)
res = foo()
print('返回值：%s' % res)

# 结果
'''
decorator init
func name is foo
foo
装饰器中的功能：foo 睡眠3秒
foo is running.
方法foo用时:3.0008039474487305秒
返回值：this is foo's return value
'''
```

> 和之前装饰器是函数一样，若被装饰的函数是带返回值的，闭包函数inner中，调用func()时必须相应的带返回值，不然装饰函数时，也不进行返回，默认为None。

(4). 被装饰的对象为函数，且装饰器带参数也有返回值

```python
import time
from functools import wraps

# 装饰器是类，且带参数带返回值
class Decorator(object):
    def __init__(self, arg=None):  # 如果在调用装饰器时为给传参数，则默认值为None
        print('decorator init')
        self.arg = arg

    def __call__(self, func):
        @wraps(func)  # 保证装饰过的函数__name__属性不变
        def inner(*args, **kwargs):
            print("Hello inner")
            print('装饰器的参数为：{}'.format(self.arg))
            print('装饰器中的功能：{} 睡眠3秒'.format(func.__name__))
            start = time.time()
            res = func(*args, **kwargs)
            end = time.time()
            print('方法{}用时:{}秒'.format(func.__name__, end - start))
            return res
        return inner

# 被装饰的对象为函数，且不带参数
@Decorator('hello')
def foo():
    time.sleep(3)
    print("foo is running.")
    return "this is foo's return value"

# 调用装饰后的foo函数
print(foo.__name__)
res = foo()
print('返回值：%s' % res)

# 结果
'''
decorator init
foo
Hello inner
装饰器的参数为：hello
装饰器中的功能：foo 睡眠3秒
foo is running.
类foo用时:3.000250816345215秒
返回值：this is foo's return value
'''
```

> 和之前装饰器是函数一样，带有参数的装饰器类，会把被装饰函数所带的参数传递给装饰器__init__进行初始化，而__call__作为外层函数接收被装饰函数的函数名，作为参数传递给内层函数inner，这里需要注意的是func传入，不需要在前面加self了，其他的跟函数装饰函数很相似，可以通过结果去理解整个装饰器的运行过程。

(5). 被装饰的对象为类，且不带参数

```python
import time
from functools import wraps

# 装饰器是类，且不带参数
class Decorator(object):
    def __init__(self,func):
        # 初始化函数只会调用一次，当第二次装饰的时候，这一步就滤过了
        print('decorator init')
        print('class name is {}'.format(func.__name__))
        self.func = func

    def __call__(self, *args, **kwargs):
        print('装饰器中的功能：{} 睡眠3秒'.format(self.func.__name__))
        start = time.time()
        res = self.func(*args, **kwargs)
        end = time.time()
        print('类{}用时:{}秒'.format(self.func.__name__, end - start))
        return res

# 被装饰的对象为函数，且不带参数
@Decorator
class Foo():
    def __init__(self):
        self.name = 'lucy'

    def say(self):
        time.sleep(3)
        print("her name is {}".format(self.name))

# 实例化装饰后的类
print("类名：{}".format(Foo.func.__name__))
foo = Foo()
foo.say()

# 结果
'''
decorator init
func name is Foo
类名：Foo
装饰器中的功能：Foo 睡眠3秒
类Foo用时:0.0秒
her name is lucy
'''
```

> 跟函数装饰器装饰类一样，这里把类Foo通过@Decorator类装饰器传递给参数func，但这个类装饰器没有__get__方法，无法返回装饰后的类，而是进行初始化。第二次调用，这时类Foo()就相当于调用了装饰器的__call__方法，在里面调用self.func()方法

(6). 被装饰的对象为类，且带参数

```python
import time
from functools import wraps

# 装饰器是类，且不带参数
class Decorator(object):
    def __init__(self,func):
        # 初始化函数只会调用一次，当第二次装饰的时候，这一步就滤过了
        print('decorator init')
        print('class name is {}'.format(func.__name__))
        self.func = func

    def __call__(self, *args, **kwargs):
        print('装饰器中的功能：{} 睡眠3秒'.format(self.func.__name__))
        start = time.time()
        res = self.func(*args, **kwargs)
        end = time.time()
        print('类{}用时:{}秒'.format(self.func.__name__, end - start))
        return res

# 被装饰的对象为类，且带参数
@Decorator
class Foo():
    def __init__(self, *args, **kwargs):
        self.id = args[0]
        self.name = kwargs.get('name_dict').get(self.id)

    def say(self):
        print("her name is {}".format(self.name))

# 实例化装饰后的类
print("类名：{}".format(Foo.func.__name__))
foo = Foo('1', '2', '3', name_dict={'1': 'Lucy', '2': 'Linda', '3': 'Mary'})
foo.say()

# 结果
'''
decorator init
class name is Foo
类名：Foo
装饰器中的功能：Foo 睡眠3秒
方法Foo用时:0.0秒
her name is Lucy
'''
```

(7). 被装饰的对象为类，且装饰器带参数也有返回值

```python
import time
from functools import wraps

# 装饰器是类，且带参数带返回值
class Decorator(object):
    def __init__(self, arg=None):  # 如果在调用装饰器时为给传参数，则默认值为None
        print('decorator init')
        self.arg = arg

    def __call__(self, func):
        @wraps(func)  # 保证装饰过的函数__name__属性不变
        def inner(*args, **kwargs):
            print("Hello inner")
            print('装饰器的参数为：{}'.format(self.arg))
            print('装饰器中的功能：{} 睡眠3秒'.format(func.__name__))
            start = time.time()
            res = func(*args, **kwargs)
            end = time.time()
            print('类{}用时:{}秒'.format(func.__name__, end - start))
            return res
        return inner

# 被装饰的对象为类，且带参数
@Decorator('hello')
class Foo():
    def __init__(self, *args, **kwargs):
        self.id = args[0]
        self.name = kwargs.get('name_dict').get(self.id)

    def say(self):
        print("her name is {}".format(self.name))

# 实例化装饰后的类
print("类名：{}".format(Foo.func.__name__))
foo = Foo('1', '2', '3', name_dict={'1': 'Lucy', '2': 'Linda', '3': 'Mary'})
foo.say()

# 结果
'''
decorator init
类名：Foo
Hello inner
装饰器的参数为：hello
装饰器中的功能：Foo 睡眠3秒
类Foo用时:0.0秒
her name is Lucy
'''
```

- **特殊的装饰器(类静态属性装饰器)**

```python
# 类静态属性装饰器
class Foo(object):
    def __init__(self, height, weigth):
        self.height = height
        self.weigth = weigth

    @property
    def ratio(self):
        return self.height / self.weigth

foo = Foo(176, 120)
print(foo.ratio)

# 结果为：1.4666666666666666
```

> 其中，@property是一个特殊的装饰器，把ratio方法变成一个属性，所以调用的时候是foo.ratio而不是foo.ratio()。这类特殊装饰器需要python的特定的属性和机制的支持才可以实现，不同特性的装饰器所需机制不同。

```python
# 实现@property装饰器效果

class Prop(object):
    def __init__(self, arg):
        self.arg = arg

    def __get__(self, instance, owner):
        return self.arg(instance)

# 使用效果与原生的@property装饰器的一样
class Foo(object):
    def __init__(self, height, weigth):
        self.height = height
        self.weigth = weigth

    @Prop
    def ratio(self):
        return self.height / self.weigth

foo = Foo(176, 120)
print(foo.ratio)

# 结果为：1.4666666666666666
```

> 经典的装饰器装饰类，通过setattr魔术方法，对Person类进行修改，name作为类属性，`name = TypeCheck(name,required_type)`，这样修改了Person类，使得Person类有了两个类变量，一个是`name = TypeCheck('name', required_type)`，另一个是`age = TypeCheck('age', required_type)`。

> 因此实例化时`Person('lucy', 18)`，self.name中name不是实例变量而是类变量，会调用描述器TypeCheck，赋值的时候，就会调用__set__方法，取值的时候会调用__get__方法。

```python
# 经典的装饰器装饰类
from functools import wraps

class TypeCheck:
    def __init__(self, srcType, dstType):
        self.srcType = srcType
        self.dstType = dstType

    # instance == a, cls == A
    def __get__(self, instance, cls):
        if instance is None:
            return self
        return instance.__dict__[self.srcType]

    def __set__(self, instance, value):
        if isinstance(value, self, dstType):
            instance.__dict__[self.srcType] = value
        else:
            raise TypeError('{} should be {}'.format(value, self.dstType))

# 装饰器自身是一个函数
def type_assert(**kwargs):
    def dec(cls):
        def wraps(*args):
            for name, required_type in kwargs.items():
                setattr(cls, name, TypeCheck(name, required_type))
            return cls(*args)  # 这里是实例化新的Person类后返回实例对象，也就是p
        return wraps
    return dec

# 装饰对象是一个类，且带参数
@type_assert(name=str, age=int)
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

# 实例化新的Person类，这里相对于调用的是wraps函数
p = Person('lucy', 18)
print(p.name)
print(p.age)

# 装饰器修改后的Person类为下面这个新的Person类，因此实例化Person的时候，调用的是下面这个新的Person
class Person:
    name = TypeCheck('name', str)
    age = TypeCheck('age', int)

    def __init__(self, name:str, age:int):
        self.name = name
        self.age = age
```

- 装饰器顺序

> 当有两个或两个以上装饰器装饰一个函数时，装饰器是从上到下执行，从下向上装饰，语法糖语句执行流程的顺序是从下往上（就近原则，靠近函数定义的先执行）。

```python
# 第一个装饰器wrapper1
def wrapper1(func):
    print("wapper1")

    def inner():
        print("inner1")
        return '<b>' + func() + '</b>'

    return inner

# 第二个装饰器wrapper2
def wrapper2(func):
    print("wapper2")

    def inner():
        print("inner2")
        return '<i>' + func() + '</i>'

    return inner

# 两个装饰器
@wrapper1
@wrapper2
def foo():
    print("foo")
    print("end")
    return "hello"

# 调用装饰后的foo函数
res = foo()
print(res)

# 结果
'''
wapper2
wapper1
inner1
inner2
foo
end
<b><i>hello</i></b>
'''
```

> 根据结果，函数foo先用wapper2装饰器进行装饰，接着是用wrapper1再进行装饰，但是在调用过程中又是先执行第一个装饰器wrapper1，然后在执行第二个装饰器wrapper2。

> 具体分析其过程，就近原则先用第二个装饰器wrapper2进行装饰，@wrapper2等价于`foo = wrapper2(foo)`，此时括号内的foo即是函数名，而外部的foo实际指向的是wrapper2的inner。
@wrapper1等价于`foo = wrapper1(foo)`，此时括号内的foo指向的是`wrapper2.inner`，而外部的foo指向wrapper1的inner。

>当执行到@wrapper1时要对下面的函数进行装饰，此时解释器继续往下走，发现并不是一个函数名，而又是一个装饰器，这时@wrapper1装饰器暂停执行，而接着执行接下来的装饰器@wrapper2，接着把foo函数名传入到装饰器wrapper2函数func，从而打印"wrapper2"，在wrapper2装饰完后，此时的foo指向wrapper2的inner函数地址，这是又返回来执行@wrapper1，接着把新的foo（即wrapper2.inner）传入wrapper装饰器函数中，因此打印"wrapper1"，在wrapper1装饰完后，此时的foo指向wrapper1的inner函数地址。

> 在调用foo函数的时候，根据上述分析，此时foo指向wrapper1的inner函数地址，故打印"inner1"，接下来调用func()的时候，实际上调用的是wrapper2.inner()函数，所以会打印"inner2"，而wrapper2.inner()函数中，调用的func()才是最初传入的foo函数，所以打印"foo"和"end"，最后一层层调用完后打印的"`<b><i>hello</i></b>`"。

- 通用万能装饰

```python
from functools import wraps

def decorator_all(func):
    @wraps(func)
    def wrapper(*args, **kwargs):
        print("万能装饰器")
        return func(*args, **kwargs)

    return wrapper

```

## 21. 浅拷贝与深拷贝

> 赋值：对象赋值实际上是对象的引用。类似于改名字，内部结构、内存空间地址都一样，赋值给另一个变量的时候，并没有拷贝这个对象，而是拷贝了这个对象的引用。

> 浅拷贝：另开辟新内存空间，只拷贝父结构，没有拷贝子对象，所以原始数据改变，子对象会改变。

```python
import copy

a = [1, 2, 3, ['a', 'b']]
b = copy.copy(a)
a.append(5)
print(a)
print(b)

# 结果1
'''
a = [1, 2, 3, ['a', 'b'], 5]
b = [1, 2, 3, ['a', 'b']]
'''
# 若a的子对象['a', 'b']发生改变
a[3].append('c')
print(a)
print(b)

# 结果2
'''
a = [1, 2, 3, ['a', 'b', 'c'], 5]
b = [1, 2, 3, ['a', 'b', 'c']]
'''
```

> 深拷贝：另开辟新内存空间，拷贝对象里面所有的元素，包括父子任何元素，与原始对象已经无任何关系，所以原始对象改变不会造成深拷贝后任何父子元素的改变。

```python
import copy

a = [1, 2, 3, ['a', 'b']]
c = copy.deepcopy(a)
a.append(5)
print(a)
print(c)

# 结果1
'''
a = [1, 2, 3, ['a', 'b'], 5]
c = [1, 2, 3, ['a', 'b']]
'''
# 若a的子对象['a', 'b']发生改变，而C始终不变
a[3].append('c')
print(a)
print(c)

# 结果2
'''
a = [1, 2, 3, ['a', 'b', 'c'], 5]
b = [1, 2, 3, ['a', 'b']]
'''
```

## 22. 设计模式

**[Python 实现23种设计模式](https://github.com/weilanhanf/python-design-patterns)**
**[Python 23种设计模式全](https://www.cnblogs.com/baxianhua/p/11770434.html)**
**[Python 常用设计模式](https://refactoringguru.cn/design-patterns/python)**
**[python 设计模式](https://www.cnblogs.com/onepiece-andy/tag/%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F/)**

### 1. 工厂模式

- 简单工厂模式的不足

> 在简单工厂模式中，只提供了一个工厂类，该工厂类处于对产品类进行实例化的中心位置，它知道每个产品对象的创建细节，并决定何时实例化哪一个产品类。简单工厂模式最大的缺点是当有新产品要加入时，必须修改工厂类，加入必要的处理逻辑，这违背了“开闭原则”。在简单工厂模式中，所有的产品都是由同一个工厂创建的，工厂类的职责较重，业务逻辑较为复杂，具体产品与工厂类之间的耦合度高，严重影响了系统的灵活性和扩展性，而工厂方法模式则可以很好地解决这一个问题。

- 工厂方法模式

> 定义一个用于创建对象的接口，但是让子类决定将哪一个类实例化。工厂方法模式让一个类的实例化延迟到其子类。

> 工厂方法模式就是简单工厂模式的进一步抽象。由于面向对象的多态性，工厂方法模式保持了简单工厂的优点，同时克服了它的缺点。工厂方法模式中，核心的工厂被提升为一个抽象类，将具体创建工作交给它的子类完成。这个抽象的工厂类仅规定具体工厂实现的接口，而不明确指出如何实例化一个产品类，这使得工厂方法模式允许系统在不修改原有产品结构的情况下轻重的引进新产品。

```python
# 代码出处：https://www.cnblogs.com/onepiece-andy/p/python_factory_method_pattern.html

#!/usr/bin/env python
# -*- coding:utf-8 -*-

"""
场景:雷锋工厂,不关心执行者,只关心执行结果
创建一个抽象工厂类CreateLeiFeng和一个抽象对象类LeiFeng，当创建具体leifeng对象-Undergradiate去dosomething时，使用继承抽象工厂的UndergraduateFactory工厂类，该类返回一个Undergradiate实例，如果还要去做另一个dosomething时，再创建一个VolunteerFactory工厂方法创建创建一个Volunteer实例就可以了
"""

class LeiFeng(object):

    def Sweep(self):
        print("扫地")

    def Wash(self):
        print("洗衣")

    def BuyRice(self):
        print("买米")


class IFactory(LeiFeng):

    def CreateLeiFeng(self):
        pass


# 大学生
class Undergraduate(LeiFeng):
    pass


# 新增社区服务者
class Volunteer(LeiFeng):
    pass


# 学习雷锋的大学生工厂
class UndergraduateFactory(IFactory):

    def CreateLeiFeng(self):
        return Undergraduate()


# 新增一个社区服务者的工厂e
class VolunteerFactory(IFactory):

    def CreateLeiFeng(self):
        return Volunteer()


if __name__ == "__main__":
    student = UndergraduateFactory()
    volunteer = VolunteerFactory()
    student.BuyRice()
    student.Sweep()
    volunteer.Wash()

# 结果
'''
买米
扫地
洗衣
'''
```

- 抽象工厂模式

> 提供一个创建一系列相关或相互依赖对象的接口，而无须指定他们具体的类。

> 抽象工厂模式是所有形式的工厂模式中最为抽象和最具一般性的一种形式。当系统说提供的工厂生产的具体产品并不是一个简单的对象，而是多个位于不同产品等级结构、属于不同类型的具体产品时，就可以使用抽象工厂模式，抽象工厂模式中的具体工厂不只是创建一种产品，它负责创建一族产品，当一个工程等级结构可以创建出分属于不同产品等级结构的一个产品族中的所有对象时，抽象工厂模式比工厂模式更为简单、更有效率。

```python
# 代码出处：https://www.cnblogs.com/onepiece-andy/p/python-abstract-factory-pattern.html

# !/usr/bin/env python
# -*- coding:utf-8 -*-

"""
设计模式——抽象工厂模式
抽象工厂模式(Abstract Factory Pattern):提供一个创建一系列相关或相互依赖对象的接口，而无需指定它们的类。
"""
import sys
import os

# 抽象用户表类
class User(object):

    def get_user(self):
        pass

    def insert_user(self):
        pass


# 抽象部门表类
class Department(object):

    def get_department(self):
        pass

    def insert_department(self):
        pass


# 操作具体User数据库类-Mysql
class MysqlUser(User):

    def get_user(self):
        print('MysqlUser get User')

    def insert_user(self):
        print('MysqlUser insert User')


# 操作具体Department数据库类-Mysql
class MysqlDepartment(Department):

    def get_department(self):
        print('MysqlDepartment get department')

    def insert_department(self):
        print('MysqlDepartment insert department')


# 操作具体User数据库-Orcal
class OrcaleUser(User):

    def get_user(self):
        print('OrcalUser get User')

    def insert_user(self):
        print('OrcalUser insert User')


# 操作具体Department数据库类-Orcal
class OrcaleDepartment(Department):

    def get_department(self):
        print('OrcalDepartment get department')

    def insert_department(self):
        print('OrcalDepartment insert department')


# 抽象工厂类
class AbstractFactory(object):

    def create_user(self):
        pass

    def create_department(self):
        pass


class MysqlFactory(AbstractFactory):

    def create_user(self):
        return MysqlUser()

    def create_department(self):
        return MysqlDepartment()


class OrcaleFactory(AbstractFactory):

    def create_user(self):
        return OrcaleUser()

    def create_department(self):
        return OrcaleDepartment()


if __name__ == "__main__":
    s = ['Mysql', 'Orcale']
    for db in s:
        myfactory = ''
        if db == 'Mysql':
            myfactory = MysqlFactory()
        elif db == 'Orcale':
            myfactory = OrcaleFactory()
        else:
            print("不支持的数据库类型")
            exit(0)
        user = myfactory.create_user()
        department = myfactory.create_department()
        user.insert_user()
        user.get_user()
        department.insert_department()
        department.get_department()

# 结果
'''
MysqlUser insert User
MysqlUser get User
MysqlDepartment insert department
MysqlDepartment get department
OrcalUser insert User
OrcalUser get User
OrcalDepartment insert department
OrcalDepartment get department
'''
```

> 优点：具体工厂类如MysqlFactory在一个应用中只需要初始化一次，这样改动一个具体工厂变得很容易，只需要改变具体工厂就可以改变整个产品的配置。具体的创建实例过程与客户端分离，客户端通过他们的抽象接口操纵实例，产品的具体类名也被具体工厂的实现分离，不会出现在客户端代码中。

> 缺点：在新增一个具体工厂就需要增加多个类才能实现。

- 工厂方法模式与抽象工厂模式对比

  - 工厂模式的优点：

  > 工厂方法用来创建客户所需要的产品，同时还向客户隐藏了哪种具体产品类将被实例化这一细节 能够让工厂自主确定创建何种产品对象，而如何创建这个对象的细节则完全封装在具体工厂内部，在系统中加入新产品时，完全符合开闭原则。

  - 工厂模式的缺点：

  > 系统中类的个数将成对增加，在一定程度上增加了系统的复杂度，会给系统带来一些额外的开销 增加了系统的抽象性和理解难度。

  - 工厂模式的适用环境：

  > 客户端不知道它所需要的对象的类（客户端不需要知道具体产品类的类名，只需要知道所对应的工厂即可，具体产品对象由具体工厂类创建） 抽象工厂类通过其子类来指定创建哪个对象。

  - 抽象模式的优点：

  > 隔离了具体类的生成，使得客户端并不需要知道什么被创建，当一个产品族中的多个对象被设计成一起工作时，它能够保证客户端始终只使用同一个产品族中的对象，增加新的产品族很方便，无须修改已有系统，符合开闭原则。

  - 抽象模式的缺点：

  > 增加新的产品等级结构麻烦，需要对原有系统进行较大的修改，甚至需要修改抽象层代码，这显然会带来较大的不便，违背了开闭原则。

  - 抽象模式的适用环境：

  > 一个系统不应当依赖于产品类实例如何被创建、组合和表达的细节，系统中有多于一个的产品族，但每次只使用其中某一产品族，属于同一个产品族的产品将在一起使用，这一约束必须在系统的设计中体现出来 产品等级结构稳定，设计完成之后，不会向系统中增加新的产品等级结构或者删除已有的产品等级结构。

### 2. 构造模式

### 4. 原型模式

> 原型模式关注的是大量相同对象或者相似对象的创建问题，意图在于通过复制一个已经存在的实例来获得一个新的实例，以避免重复创建此类实例带来的开销。被复制的实例就是这个“原型”，这个原型是可定制的。

- 原型模式的实现

```python
# 代码来源：https://www.cnblogs.com/onepiece-andy/p/python_prototype_pattern.html

#!/usr/bin/env python
# -*- coding:utf-8 -*-

"""
原型模式(Prototype Pattern):用原型实例指定创建对象的种类,并且通过拷贝这些原型创建新的对象
原型模式是用场景:需要大量的基于某个基础原型进行微量修改而得到新原型时使用
"""
from copy import copy, deepcopy

# 原型抽象类
class Prototype(object):
    def clone(self):
        pass

    def deep_clone(self):
        pass

# 工作经历类
class WorkExperience(object):
    def __init__(self):
        self.timearea = ''
        self.company = ''

    def set_workexperience(self, timearea, company):
        self.timearea = timearea
        self.company = company

# 简历类
class Resume(Prototype):
    def __init__(self, name):
        self.name = name
        self.workexperience = WorkExperience()

    def set_personinfo(self, sex, age):
        self.sex = sex
        self.age = age
        pass

    def set_workexperience(self, timearea, company):
        self.workexperience.set_workexperience(timearea, company)

    def display(self):
        print(self.name)
        print(self.sex, self.age)
        print("工作经历", self.workexperience.timearea, self.workexperience.company)

    def clone(self):
        return copy(self)

    def deep_clone(self):
        return deepcopy(self)

if __name__  == '__main__':
    obj1 = Resume('Liming')
    obj2 = obj1.clone()  # 浅拷贝对象
    obj3 = obj1.deep_clone()  # 深拷贝对象

    obj1.set_personinfo('男', 22)
    obj1.set_workexperience('2010-2018', 'aa')
    obj2.set_personinfo('男', 23)
    obj2.set_workexperience('2010-2019', 'bb')  # 修改浅拷贝的对象工作经历
    obj3.set_personinfo('男', 24)
    obj3.set_workexperience('2010-2020', 'cc')  # 修改深拷贝的对象的工作经历

    obj1.display()
    obj2.display()
    obj3.display()

# 结果
'''
Liming
男 22
工作经历 2010-2019 bb
Liming
男 23
工作经历 2010-2019 bb
Liming
男 24
工作经历 2010-2020 cc
'''
```

- 原型模式的优点

> 原型摸手机用于创建复杂的或者耗时的实例，复制一个已经存在的实例使程序运行高效，相对于工厂模式，原型模式减少了之类的构建。

- 原型模式的缺点

> 每个产品类都必须配置一个克隆方法，并且这个克隆方法需要对类的功能进行整体考虑。

- 原型模式的应用
  - 当一个系统应该独立于它的产品的创建、构成和表示时；
  - 当实例化的类是在运行时刻指定时，例如通过动态装载；
  - 为了避免创建一个与产品类层次平行的工厂类层次时；

### 5. 单例模式

> 单利模式是一种创建型的设计模式，保证某一个类仅有一个实例，而且提供一个访问该实例的全局访问点。比如，最常见的就是当一个office文档已经被打开时，通过另一个窗口再次访问时，系统就会提示此文档已经被占用，智能以只读的方式打开。

- 单例模式的实现步骤

  - (1). 私有化构造函数，防止其他类可以创建这个类的对象；
  - (2). 在本类中创建唯一实例对象（因为构造函数私有化了，所以单例类的唯一实例对象只能在单例类里面创建），使用一个室友静态成员变量保存。
  - (3). 对外提供一个公开的静态函数，用于获取这个唯一的实例对象
  
- 单例模式的实现方式

**可以参考前面总结的，[5. 单例模式](#5-单例模式)**

```python
# 代码出处：https://www.cnblogs.com/onepiece-andy/p/python-singleton-pattern.html

# !/usr/bin/env python
# # -*- coding:utf-8 -*-

"""
python中模块化的操作,可以代替单例模式,生成一个类的实例作为全局变量,其他地方只引用这个实例就可以实现单例，也就是import 方式
"""

# 因为__new__在__init__前被执行，利用__new__实现单例
class Singleton1(object):
    def __new__(cls, *args, **kwargs):
        if not hasattr(cls, '__instance'):  # 创建过的单例带有属性__instance
            cls.__instance = super(Singleton1, cls).__new__(cls, *args, **kwargs)
            return cls.__instance

# 共享属性
# 创建实例时利用__dict__指向同一个字典，这样他们具有相同的属性和方法
class Singleton2(object):
    _state = {}
    def __new__(cls, *args, **kwargs):
        ob = super(Singleton2, cls).__new__(cls, *args, **kwargs)
        ob.__dict__ = cls._state
        return ob

# 利用元类在创建方法时使用__metaclass__来创建
class Singleton3(type):
    def __new__(cls, name, bases, dct):
        if not hasattr(cls, '__instance'):
        cls.__instance = super(Singleton3, cls).__new__(cls, name, bases, dct)
        return cls.__instance

# 利用装饰器
def singleton4(cls, *args, **kwargs):
    instance = {}
    def _single():
        if cls not in instances:
            instances[cls] = cls(*args, **kwargs)
        return instances[cls]
    return _single

class Myclass1(Singleton1):
    a = 1
class Myclass1(Singleton1):
    a = 2
class Myclass3(object):
    __metaclass__ = Singleton3
    a = 3

@singleton4
class Myclass4(object):
    a = 4

if __name__ == "__main__":
    s1 = Myclass1()
    s2 = Myclass1()
    print(s1.a, id(s1.a), id(s2.a))

    s3 = Myclass2()
    s4 = Myclass2()
    print(s3.a, id(s3.a), id(s4.a))

    s5 = Myclass3()
    s6 = Myclass3()
    print(s5.a, id(s5.a), id(s6.a))

    s7 = Myclass4()
    s8 = Myclass4()
    print(s7.a, id(s7.a), id(s8.a))

# 结果
'''
1 140722211689280 140722211689280
2 140722211689312 140722211689312
3 140722211689344 140722211689344
4 140722211689376 140722211689376
'''
```

- 单例模式的优点

  - (1). 由于单例模式要求在全局内只有一个实例，一次可以节省内存空间；
  - (2). 全局只有一个访问点，可以更好地进行数据同步控制，避免多重占用；
  - (3). 单例可以长驻内存，减少系统开销。

- 单例模式的缺点

  - (1). 单例模式的扩展是比较困难的；
  - (2). 赋予了单例太多的职责，某种程度上违反了单一职责原则；
  - (3). 单例模式是并发协作软件模块中需要最先完成的，因此不利于测试；
  - (4). 单例模式在某种情况下会导致“资源瓶颈”。

- 单例模式的应用举例

  - (1). 生成全局唯一的序列号；
  - (2). 访问全局复工的唯一资源，如磁盘、总线等；
  - (3). 单个对象占用资源过多，如数据库等；
  - (4). 系统全局统一管理，如windows系统的资源管理器；
  - (5). 网站计数器。

### 6. 装饰模式
  
> 有时为了给某个对象而不是给整个类添加一个功能，使用继承机制是添加功能的有效途径，但是不够灵活，用户不能控制对组件加边框的方式和时机，并且会导致之类膨胀。一种比较领过的方式是将组件嵌入另一个对象中，这个嵌入的对象叫做装饰。

> 装饰模式：动态地给一个对象增加一些额外的职责。就扩展功能而言，装饰模式提供了一种比使用之类更加灵活的替代方案，以对客户同名的方式动态地给一个对象附加更多的责任，可以在不需要创建更多子类的情况下，让对象的功能得以扩展。

- 装饰模式分析

> 可以在不改变一个对象本身功能的基础上给对象增加额外的新行为，是一种用于替代继承的技术，它通过一种无须定义之类的方式给对象动态增加职责，使用对象间的关联关系取代类之间的继承关系，引入装饰类，在装饰类中既可以调用带装饰的原有类的方法，还可以增加新的方法，以扩展原有类的功能。
  
- 装饰模式的结构
  - 抽象部件(Component)：声明封装器和被封装对象的公用接口。
  - 具体部件(Concrete Component)：类是被封装对象所属的类，定义了基础行为，但装饰器可以改变这些行为。
  - 抽象装饰类(Decorator)：类拥有一个指向被封装对象的引用成员变量，该变量的类型应当被声明为通用部件的接口，这样它就引用具体的部件和装饰，抽象装饰类会将所有操作委派给被封装的对象。
  - 具体装饰类(ConcreteDecorator)：定义了可动态添加到部件的额外行为，具体装饰类会重写抽象装饰类的方法，并在调用父类方法之前或之后进行额外的行为。

- 装饰模式的实现

```python
# 代码来源：https://www.cnblogs.com/onepiece-andy/p/python-decorator-pattern.html
# !/usr/bin/env python
# -*- coding:utf-8 -*-

"""
装饰模式(Decorator Pattern):动态的给一个对象添加一些额外的职责,就增加功能来说,装饰模式比生成子类更为灵活。
特点: 有效的把类的核心职责和装饰功能区分开,而且可以去除相关类中重复的装饰逻辑。
"""

# 定义对象接口
class Person(object):
    def __init__(self, name):
        self.name = name

    def show(self):
        print("装扮的%s" % self.name)

# 装饰类
class Finery(Person):
    def __init__(self):
        pass

    def Decorate(self, component):
        self.component = component

    def show(self):
        if self.component != None:
            self.component.show()

# 装扮——T恤
class TShirts(Finery):
    def __init__(self):
        pass

    def show(self):
        print("T恤")
        self.component.show()

# 装扮——大裤衩
class BigTrouser(Finery):
    def __init__(self):
        pass

    def show(self):
        print("大裤衩")
        self.component.show()

# 装扮——人字拖
class FlipFlops(Finery):
    def __init__(self):
        pass

    def show(self):
        print("人字拖")
        self.component.show()

if __name__ == '__main__':
    p = Person('aaa')
    ff = FlipFlops()
    bt = BigTrouser()
    ts = TShirts()
    ff.Decorate(p)
    bt.Decorate(ff)
    ts.Decorate(bt)
    ts.show()

# 结果
'''
T恤
大裤衩
人字拖
装扮的aaa
'''
```

- 装饰模式的优点

> 对于扩展一个对象的功能，装饰模式比继承模式更加灵活，不会导致类的个数急剧增加，可以通过一种动态的方式来扩展一个对象的功能，通过配置文件可以在运行时选择不同的具体装饰类，从而实现不同的行为，可以对一个对象进行多次装饰，具体部件类和具体装饰类可以独立变化，用户可以根据需要增加新的具体部件和具体装饰类，且原有的类库代码无需改变，符合开闭原则。

- 装饰模式的缺点

> 使用装饰模式进行系统设计时产生很多小对象，大量小对象的产生势必会占用更多的系统资源，在一定程度上影响程序的性能；比继承更加容易出错，拍错也更加困难，对于多次装饰的对象，调试的需找错误可能需要主机排查，较为繁琐。

- 装饰适用环境

> 在不影响其他对象的情况下，以动态、透明的方式传给单个对象添加职责，但不能采用继承的方式对系统进行扩展或者采用继承不利于系统扩展和维护时可以使用装饰模式。

### 7. 代理模式

### 8. 适配器模式
  
> 为了解决接口不兼容的问题，引进一种接口的兼容机制，就是适配器模式，其通过提供一种适配类将第三方提供的接口转换为客户希望的接口。例如：假如你正在开发一款股票市场监测程序， 它会从不同来源下载 XML 格式的股票数据， 然后向用户呈现出美观的图表。在开发过程中， 你决定在程序中整合一个第三方智能分析函数库，但是遇到了一个问题， 那就是分析函数库只兼容 JSON 格式的数据。可以修改程序库来支持 XML，这可能需要修改部分依赖该程序库的现有代码，甚至还有更糟糕的情况， 你可能根本没有程序库的源代码， 从而无法对其进行修改。这时就可以创建一个适配器，能够转换对象接口，使其能与其他对象交互。

> 适配器模式：讲一个类的接口装换成客户希望的另一个接口，适配器模式让那些接口不兼容的类可以一起工作。适配器模式别名包装器(Wrapper)模式，定义中所提及的接口是指广义的接口，它可以表示一个方法的集合。

- 适配器模式的实现

```python
# 代码来源：https://www.cnblogs.com/onepiece-andy/p/python-adapter-pattern.html

#!/usr/bin/env python
# -*- coding:utf-8 -*-

"""
适配器模式(Adapter Pattern):将一个类的接口转换成为客户希望的另外一个接口.Adapter Pattern使得原本由于接口不兼容而不能一起工作的那些类可以一起工作。
应用场景:系统数据和行为都正确,但接口不符合时,目的是使控制范围之外的一个原有对象与某个接口匹配,适配器模式主要应用于希望复用一些现存的类,但接口又与复用环境不一致的情况。
"""

class Target(object):
    def request(self):
        print("普通请求")

class Adaptee(object):
    def specific_request(self):
        print("特殊请求")

class Adapter(Target):
    def __init__(self):
        self.adaptee = Adaptee()

    def request(self):
        self.adaptee.specific_request()

if __name__ == "__main__":
    target = Adapter()
    target.request()

# 结果
'''
特殊请求
'''
```
  
- 适配器模式的结构

> 目标抽象类(Target)：是客户希望调用接口

> 适配器类(Adapter)：通过内部包装的一个Adaptee对象把源接口转换成目标接口

> 适配者类(Adaptee)：需要适配的类
  
- 适配器模式的优点

> 将目标类和适配者类解耦，通过引入一个适配器类来重用现有的适配器类，无需修改原有的结构；
  
> 增加了类的透明性和复用性，提高了适配者的复用性，同一个适配者类可以在多个不同的系统中进行复用；
  
> 灵活性和扩展性非常好；其中类适配器模式置换一些适配者方法很方便，而对象适配者模式可以把多个不同适配者适配到同一个目标，还可以适配一个适配者的子类。

- 适配器模式的缺点

> 一次最多只能适配一个适配者类，不能同时适配多个适配者；

> 适配者类不能为最终类；

> 目标抽象类只能为接口，不能为类

> 对象适配器模式在适配器中置换适配者类的某些方法比较麻烦。

- 适配器模式的适用环境

> 系统需要使用一些现有的类，而这些类的就扣不符合系统的需要，甚至没有这些类的源代码；创建一个可以重复使用的类，用于和一些彼此之间没有太大关联的类，包括一些可能在将来引进的类一起工作。

- 适配器模式和装饰模式比较

> 适配器模式和装饰模式有一定的相似性，都起包装的作用，但二者本质上又是不同的，装饰模式的结果，是给一个对象增加了一些额外的职责，而适配器模式，则是将另一个对象进行了“伪装”。适配器可以任务是对现在业务的补偿式应用，所以尽量不要在设计阶段就使用适配器模式，在两个系统需要兼容时可以考虑使用适配器模式。

### 9. 外观模式

### 10. 享元模式

- 问题引出

> 如果一个软件系统在运行时所创建的相同或相似对象数量太多，将导致运行代价过高，代开系统资源浪费、性能下降等问题。如何避免系统从出现大量相同或相似的对象，同时又不影响客户端程序通过面向对象的方式对这些对象进行操作呢。例如在文字编辑软件中，把每个字符单层对象处理，并分配相应的系统空间，但是随着字符串数量的增加将会逐渐耗尽系统资源，有大量细粒度的对象从此在系统中，导致系统运行效率低下。解决上述问题就可以使用享元模式，通过共享机制来解决系统资源消耗问题。

- 享元模式的原理
  - 内部状态(Intrinic State)：存储在享元对象内部并且不会随着环境改变而改变状态，内部状态可以共享。
  - 外部状态(Extrinsic State)：随着环境改变而改变、不可以共享状态。享元对象的外部状态通常由客户端保存，并在享元对象被创建之后，需要使用的时候再传入到享元对象内部。一个外部状态与另一个外部状态之间是相互独立的。
  
  - (1). 将具有相同内部状态的对象存储在享元池中，享元池中的对象是可以实现共享的；
  - (2). 需要的时候将对象从享元池中取出，即可以实现对象的复用；
  - (3). 通过向取出的对象注入不同的外部状态，可以得到一些列相似的对象，而这些对象在内存中实际上只存储一份。

- 享元模式的结构

  - 抽象享元类(Flyweight)：包含原始对象中部分能在多个对象中共享的状态。
  - 具体享元类(Concrete Flyweight)：定义一个借口绑定中介者。
  - 非共享具体享元类(Unshared Concrete Flyweight)：不同共享的享元类子类。
  - 享元工厂类(Flyweight Factory)：用于创建并管理享元对象，确保合理的共享享元对象，当用户请求一个享元对象时，享元工厂对象提供或创建一个。

- 享元模式实例

```python
#!/usr/bin/env python
# -*- coding:utf-8 -*-

# 假设又一个网上咖啡选购平台，客户可以在该平台上下订单订购咖啡，平台会根据用户的位置进行线下配送

# 咖啡对象构造如下
class Coffee:
    name = ''
    price = 0

    def __init__(self, name):
        self.name = name
        self.price = len(name)
        # 在实际业务中，咖啡价格应该是由配置表进行配置，或者调用接口获取等但是得到，此处为了说明享元模式，将咖啡价格定位名称长度，只是简化

    def show(self):
        print(f"咖啡{self.name}的价格是：{self.price: .2f} 元")

"""
# 对应客户顾客类
class Customer:
    name = ''

    def __init__(self, name):
        self.name = name

    def order(self, coffee_name):
        print(f"顾客{self.name}订购了一杯{coffee_name}咖啡")
        return Coffee(coffee_name)
"""

"""
按照一般的处理流程，客户在网上预订咖啡，其代表用户的Customer类中生成一个Coffee类，直到交易流程结束。整个流程是没有问题的。

但是在高并发的情况下，也就是单位时间内购买咖啡的用户越来越多，生成的咖啡实例就回越来越多，系统资源消耗越来越大，避免重复实例的出现，引入咖啡工厂类能够节约系统资源。
"""

# 引入咖啡工厂类
class CoffeeFactory():
    coffee_dict = {}
    def getCoffee(self, name):
        if self.coffee_dict.__contains__(name) == False:
            self.coffee_dict[name] = Coffee(name)
        return self.coffee_dict[name]

    def getCoffeeCount(self):
        return len(self.coffee_dict)

# 咖啡工厂中，getCoffeeCount直接返回当前实例个数，重写Customer
class Customer:
    coffee_factory = ''
    name = ''

    def __init__(self, name, coffee_factory):
        self.name = name
        self.coffee_factory = coffee_factory

    def order(self, coffee_name):
        print(f"顾客{self.name}订购了一杯{coffee_name}咖啡")
        return self.coffee_factory.getCoffee(coffee_name)

# 假设实际业务中，短时间很多人订了咖啡，则
if __name__ == "__main__":
    coffee_factory = CoffeeFactory()
    customer_1 = Customer("李先生", coffee_factory)
    customer_2 = Customer("刘小姐", coffee_factory)
    customer_3 = Customer("王老板", coffee_factory)
    c1 = customer_1.order("卡布奇诺")
    c1.show()
    c2 = customer_2.order("雀巢咖啡")
    c2.show()
    c3 = customer_3.order("美式咖啡")
    c3.show()
    print(f"创建了{coffee_factory.getCoffeeCount()}个实例")

# 结果
'''
顾客李先生订购了一杯卡布奇诺咖啡
咖啡卡布奇诺的价格是： 4.00 元
顾客刘小姐订购了一杯雀巢咖啡咖啡
咖啡雀巢咖啡的价格是： 4.00 元
顾客王老板订购了一杯美式咖啡咖啡
咖啡美式咖啡的价格是： 4.00 元
创建了3个实例
'''
```

- 享元模式的优点
  - 可以减少内存中对象的数量，使得相同或者相似的对象在内存中只保存一份，从而可以节约系统资源，提高系统性能；
  - 外部状态相对独立，而不会影响内部状态，从而使得享元对象可以在不同的环境中被共享。

- 享元模式的缺点
  - 使得系统变得复杂，需要分析出内部状态和外部状态，这使得程序的逻辑复杂化；
  - 为了使对象可以共享，享元模式需要将享元对象的部分状态外部化，而读取外部状态使得运行时间变长。

- 享元模式的适用环境
  - 一个系统有大量相同或者相似的对象，造成内存的大量消费；对象的大部分状态可以外部化，可以将这些外部状态传入对象中；在使用享元模式是需要维护一个存储对象的享元池，而这需要耗费一定的系统资源，因此在需要多次重复使用享元对象时才值得使用享元模式。

### 11. 桥接模式

### 12. 组合模式

### 13. 命令模式

### 14. 访问者模式

### 15. 责任链模式

### 16. 备忘录模式

### 17. 中介者模式

### 18. 状态模式

### 19. 模板方法模式

- 模版方法模式的引入

> 模板方法模式时行为模式中比较简单的设计模式之一。模版方法关注这样的一类行为：该行为在执行过程中拥有大致相同的动作次序，只是动作在实现的具体细节有所差异。如泡茶和泡咖啡，过程操作步骤都是相似的，可以把这一类行为抽象成一个算法，并将其中的动作序列按先后顺序也抽象出来作为该算法的步骤，至于这些步骤中你那个的实现细节，则由算法发的子类去实现。

> 模版方法模式：定义一个操作中算法的框架，而将一些步骤延迟到子类中。模板方法模式使得子类不改变一个算法结构即可重定义该算法的某些特定步骤。

> 模版方法模式是一种基于继承的代码复用技术，将一些复杂流程的实现步骤封装在一系列基本方法中，在抽象父类中提供一个称之为模版方法的方法来定义这些基本方法的执行次序，而通过其子类来覆盖某些步骤，从而使得相同的算法框架可以有不同的执行结果。

- 模板方法模式的结构
  - 抽象类(AbstractClass)：会声明作为算法步骤的方法，以及一次调用它们的实际模版方法。
  - 具体子类(ConcreteClass)：可以重写所有步骤，但是不能重写模版方法自身。

- 模板方法模式的实现
  - (1). 分析目标算法，确定是否能够将其分解为多个步骤。从所有子类角度出发，考虑哪些步骤能够通用，哪些步骤各不相同。
  - (2). 创建抽象基类并声明一个模板方法和代表算法步骤的一些列抽象方法。在模版方法中根据算法结构一次调用相应步骤，可以用final最终修饰模版方法以防止之类对其进行重写。
  - (3). 虽然可将所有步骤全都设为抽象类型，但默认实现可能会给部分步骤带来好处，因为之类无需实现那些方法。
  - (4). 可以考虑在算法的关键步骤之间添加“钩子”。
  - (5). 为每个算法变体新建一个具体子类，它必须实现所有的抽象步骤，也可以重写部分可选步骤。

```python
# 代码来源：https://www.cnblogs.com/onepiece-andy/p/python-template-method-pattern.html

#!/usr/bin/env python
# -*- coding:utf-8 -*-

"""
模板方法模式(Template Method Pattern):定义一个操作中的算法骨架，将一些步骤延迟至子类中。模板方法使得子类可以不改变一个算法的结构即可重定义该算法的某些特定步骤。

使用场景:当不变和可变的行为在方法的子类实现中混合在一起时,不变的行为就会在子类中重复出现，用模板方法模式把这些不变的行为搬到单一的地方，帮助子类摆脱重复不变的行为纠缠。
"""

class NewPaper(object):
    def question1(self):
        print("题目1")
        print(self.answer1())

    def question2(self):
        print("题目2")
        print(self.answer2())

    def answer1(self):
        return ''

    def answer2(self):
        return ''

class TestPaperA(NewPaper):
    def answer1(self):
        return "答案A1"

    def answer2(self):
        return "答案A2"

class TestPaperB(NewPaper):
    def answer1(self):
        return "答案B1"

    def answer2(self):
        return "答案B2"

if __name__ == "__main__":
    test1 = TestPaperA()
    test2 = TestPaperB()
    print("试卷A")
    test1.question1()
    test1.question2()
    print("试卷B")
    test2.question1()
    test2.question2()

# 结果
'''
试卷A
题目1
答案A1
题目2
答案A2
试卷B
题目1
答案B1
题目2
答案B2
'''
```

- 模版方法模式的优点
  - 在父类中形式化地定义一个算法，而由它的子类来实现细节的处理，在子类实现详细的处理算法时，并不会改变算法中步骤的执行顺序；
  - 提取了类库中的公共行为，将公共行为放在父类中，而通过其子类来实现不同的行为；
  - 可实现一种反向控制结构，通过子类覆盖父类的钩子方法来决定某一特定步骤是否需要执行；
  - 更换和增加新的子类很方便，符合单一职责和开闭原则。

- 模版方法模式的缺点
  - 需要为每个基本方法的不同实现提供一个子类，如果父类中可变的基本方法太多，将导致类的个数增加，系统更加庞大，设计也会更加抽象；
  - 模版方法中步骤越多，其维护工作就可能也困难。

- 模版方法模式的适用环境
  - 当你只希望客户端扩展某个特定算法步骤， 而不是整个算法或其结构时， 可使用模板方法模式；
  - 当多个类的算法除一些细微不同之外几乎完全一样时， 你可使用该模式。 但其后果就是， 只要算法发生变化， 你就可能需要修改所有的类。

### 20. 解释器模式

### 21. 迭代器模式

> 迭代器模式提供一种顺序访问一个聚合对象（聚合对象的两个职责：存储数据和遍历数据）中各个元素，且不用暴露该对象的内部表示。

- 迭代器模式的实现

```python
# 代码来源：https://www.cnblogs.com/onepiece-andy/p/python-iterator-pattern.html

#!/usr/bin/env python
# -*- coding:utf-8 -*-

"""
迭代器模式(Iterator Pattern):提供方法顺序访问一个聚合对象中各元素，而又不暴露该对象的内部表示
"""

# 迭代器抽象类
class Iterator(object):
    def First(self):
        pass

    def Next(self):
        pass

    def Isdone(self):
        pass

    def CurrItem(self):
        pass

# 聚集抽象类
class Aggregate(object):
    def CreateIterator(self):
        pass

# 具体迭代器类
class ConcreteIterator(Iterator):
    def __init__(self, aggregate):
        self.aggregate = aggregate
        self.curr = 0

    def First(self):
        return self.aggregate[0]

    def Next(self):
        ret = None
        self.curr += 1
        if self.curr < len(self.aggregate):
            ret = self.aggregate[self.curr]
        return ret

    def Isdone(self):
        return True if self.curr+1 >= len(self.aggregate) else False

    def CurItem(self):
        return self.aggregate[self.curr]

# 具体聚集类
class ConcreteAggregate(Aggregate):
    def __init__(self):
        self.ilist = []

    def CreateIterator(self):
        return ConcreteIterator(self)

class ConcreteIteratorDesc(Iterator):
    def __init__(self, aggregate):
        self.aggregate = aggregate
        self.curr = len(aggregate)-1

    def First(self):
        return self.aggretegate[-1]

    def Next(self):
        ret = None
        self.curr -= 1
        if self.curr >= 0:
            ret = self.aggregate[self.curr]
        return ret

    def Isdone(self):
        return True if self.curr-1< 0 else False

    def CurrItem(self):
        return self.aggregate[self.curr]

if __name__ == "__main__":
    ca = ConcreteAggregate()
    ca.ilist.append("aa")
    ca.ilist.append("bb")
    ca.ilist.append("cc")
    ca.ilist.append("dd")

    itor = ConcreteIterator(ca.ilist)
    print(itor.First())
    while not itor.Isdone():
        print(itor.Next())
    print("---倒序---")

    itordesc = ConcreteIteratorDesc(ca.ilist)
    print(itordesc.First())
    while not itordesc.Isdone():
        print(itordesc.Next())

# 结果
'''
aa
bb
cc
dd
---倒序---
dd
cc
bb
aa
'''
```

- 迭代器模式的优点
  - (1). 支持一下不同方式遍历一个聚合对象，在同一个聚合对象上可以定义多种遍历方式；
  - (2). 简化了聚合类，由于引入了抽象层，增加新的聚合类和迭代器类都很方便，无须修改原有代码，符合开闭原则。

- 迭代器模式的缺点
  - (1). 在增加新的聚合类时需要对应地增加新的迭代器类，类的个数成对增加，这一定程度上增加了系统的复杂性；
  - (2). 抽象迭代器的设计难度较大，需要充分考虑到系统的扩展；
  - (3). 在自定义迭代器时，创建一个考虑全面的抽象迭代器并不是一件很容易的事情。

- 迭代器模式的适用环境

> 访问一个聚合对象的内容而无需暴露它的内部表示；需要为一个聚合对象提供多种遍历方式；为遍历不同的聚合结构提供一个统一的接口，在该就扣的实现类中为不同的聚合结构提供不同的遍方式，而客户端可以一致性地操作该接口。

### 22. 观察者模式

### 23. 策略模式

## 23. GIL全局解释器锁

**[Python的底层](https://www.oschina.net/translate/pythons-hardest-problem)**

> 要理解GIL的含义，我们需要从Python的基础讲起。像C++这样的语言是编译型语言，所谓编译型语言，是指程序输入到编译器，编译器再根据语言的语法进行解析，然后翻译成语言独立的中间表示，最终链接成具有高度优化的机器码的可执行程序。编译器之所以可以深层次的对代码进行优化，是因为它可以看到整个程序（或者一大块独立的部分）。这使得它可以对不同的语言指令之间的交互进行推理，从而给出更有效的优化手段。

> 与此相反，Python是解释型语言。程序被输入到解释器来运行。解释器在程序执行之前对其并不了解；它所知道的只是Python的规则，以及在执行过程中怎样去动态的应用这些规则。它也有一些优化，但是这基本上只是另一个级别的优化。由于解释器没法很好的对程序进行推导，Python的大部分优化其实是解释器自身的优化。更快的解释器自然意味着程序的运行也能“免费”的更快。也就是说，解释器优化后，Python程序不用做修改就可以享受优化后的好处。

> 要想利用多核系统，Python必须支持多线程运行。作为解释型语言，Python的解释器必须做到既安全又高效，但多线程编程会遇到问题，解释器要留意的是避免在不同的线程操作内部共享的数据，同时它还要保证在管理用户线程时保证总是有最大化的计算资源。这时，为了不同线程同时访问时保护数据，当一个线程运行python程序的时候会霸占整个python解释器，也就是给解释器加了一把全局锁，这使得对于任何python程序，不管有多少处理器，多少线程，任何时候都自由一个线程在执行，其他线程在等待正在运行的线程完成才能运行。

> 如果线程运行过程中遇到耗时操作，超时时间超过一个固定值，则单线线程将会解开全局解释器锁，使其他线程运行。所以在多线程中是有先后顺序的，并不是同时运行的。多进程因每个进程都能被系统分配资源，相当于每个进程有了一个python解释器，所以多进程可以实现多个进程同时运行，缺点就是系统资源开销大。

## 24. 函数是一等公民

> 在python中一切皆对象，num、list、dict、tuple、function、class和模块等都是对象，如公民一样地位平等，可以在运行时创建，并能被赋值给变量，作为集合对象的元素，还能够作为函数的参数和返回值。

> Python 中函数是一等公民，意思是 Python 中的函数和整数、字符串等常见概念的地位是平等的，一个整数和一个字符串等对象可以干的事，一个函数也可以办到。

```python
import re

def factorial(n):
    """
    returns n!
    """
    return 1 if n < 2 else n * factorial(n - 1)

class Domo:
    pass

items = [1, 1.0, 'hello', [1], {'a': 1}, {1}, factorial, Domo(), re, None, object]

for item in items:
    print(f'对象 {item} 的类型是 {type(item).__name__},', f'对象 {type(item).__name__}类 的类型是 {type(type(item)).__name__}.')

# 结果
'''
对象 1 的类型是 int, 对象 int类 的类型是 type.
对象 1.0 的类型是 float, 对象 float类 的类型是 type.
对象 hello 的类型是 str, 对象 str类 的类型是 type.
对象 [1] 的类型是 list, 对象 list类 的类型是 type.
对象 {'a': 1} 的类型是 dict, 对象 dict类 的类型是 type.
对象 {1} 的类型是 set, 对象 set类 的类型是 type.
对象 <function factorial at ...> 的类型是 function, 对象 function类 的类型是 type.
对象 <__main__.Dumb object at ...> 的类型是 Dumb, 对象 Dumb类 的类型是 type.
对象 <module 're' from 'C:\\...\\re.py'> 的类型是 module, 对象 module类 的类型是 type.
对象 None 的类型是 NoneType, 对象 NoneType类 的类型是 type.
对象 <class 'object'> 的类型是 type, 对象 type类 的类型是 type
'''

for item in items:
    print(f'类对象 {item.__class__.__name__} 的基类是: {item.__class__.__bases__}')

print(f'类对象 {object.__name__} 的基类是: {object.__bases__}')

# 结果
'''
类对象 int 的基类是: (<class 'object'>,)
类对象 float 的基类是: (<class 'object'>,)
类对象 str 的基类是: (<class 'object'>,)
类对象 list 的基类是: (<class 'object'>,)
类对象 dict 的基类是: (<class 'object'>,)
类对象 set 的基类是: (<class 'object'>,)
类对象 function 的基类是: (<class 'object'>,)
类对象 Dumb 的基类是: (<class 'object'>,)
类对象 module 的基类是: (<class 'object'>,)
类对象 NoneType 的基类是: (<class 'object'>,)
类对象 type 的基类是: (<class 'object'>,)
类对象 object 的基类是: ()
'''
```

## 25. 函数与方法的区别

> 函数的本质是FunctionObject，其中包括内置函数、匿名函数、递归函数、自定义函数。
函数的作用域是从函数调用开始至函数执行完成，返回给调用者后，在执行过程中开辟的空间会自动释放，即函数执行完成后，函数体内部通过赋值等方式修改变量的值不会保留，会随着返回给调用者后，开辟的空间自动释放。
函数通过"函数名()"形式调用。

> 方法的本质是PyMethodObject，其中包括普通方法（直接用self调用的方法）、私有方法（__函数名,只能在类中被调用的方法）、属性方法（@property，将方法伪装成属性）、特殊方法（`__init__, __call__,__getattr__`等）、类方法、静态方法。
方法的作用域是通过实例化的对象进行方法的调用，调用后开辟的空间不会释放，即调用方法中对变量的修改值会一直保留。
方法是通过"对象.方法名"的方式进行调用。

## 26. range与Xrange的区别

> range()是Python的内置函数，用于创建整数的列表，可以生成递减或者递增的数列。
用法：`range(start, stop, step)`，生成一个序列。

```python
# python3下的range，其实已经把xrange合并过来了
x = range(0，5)
print(type(x))
print(x)

# python3结果
'''
<class 'range'>
range(0, 5)
'''

# python2结果
'''
<type 'list'>
[0, 1, 2, 3, 4]
'''
```

> xrange()在python3中已经移除，xrange用法与range完全相同，但是得到的是一个生成器对象，惰性求值，xrange()函数比range()函数更快。

```python
# xrange
x = xrange(0, 5)
print(type(xrange(0, 5)))
print(x)

# 结果
'''
<class 'range'>
range(0, 5)
'''
```

## 27. search与match的区别

> search()函数会在整个字符串内查找模式匹配，直到找到第一个匹配，然后返回一个包含匹配信息的对象，该对象可以通过group()方法得到匹配的字符串，如果没有字符串没有匹配到，则返回None。

```python
import re

print(re.search("time", "datetime"))
print(re.search("time", "datetime").span())
print(re.search("time1", "datetime"))
print(re.search("hello", "hihelloworld").span())
print(re.search("hello", "hihelloworld").group())

# 结果
'''
<re.Match object; span=(4, 8), match='time'>
(4, 8)
None
(2, 7)
hello
'''
```

> match()函数只检测字符串开头位置是否匹配，匹配成功才会返回结果，否则返回None。

- group() 返回被 RE 匹配的字符串
- start() 返回匹配开始的位置
- end() 返回匹配结束的位置
- span()返回一个元组包含匹配 (开始,结束) 的位置

```python
import re

print(re.match("time", "datetime"))
print(re.match("time", "timedate"))
print(re.match("time", "timedate").span())
print(re.match("time", "timedate").group())

# 结果
'''
None
<re.Match object; span=(0, 4), match='time'>
(0, 4)
time
'''
```

## 28. 面向对象编程OOP

> 面向对象编程OOP（Object Oriented Programming）是一种程序设计思想，把对象作为程序的基本单元，一个对象包含了数据和操作数据的函数。面向对象的程序设计过程吧计算机程序视为一组对象的集合，而每个对象都可以接受其他对象发过来的消息，并处理这些消息，计算机程序的执行就是一系列消息在对象之间传递。

> 在Python中，一切皆对象，当然也可以自定义对象。自定义对象的数据类型就是面向对象中的类的概念，面向对象的设计思想是抽象出类(Class)，根据类(Class)创建实例(instance)。面向对象的抽象程度又比函数要高，因为一个类(Class)既包含数据又包含操作数据的方法。

> 面向对象的三大特性：封装、继承、多态。

## 29. 面向切面编程AOP

> AOP(Aspect Oriented Programming)是一种编程方式，就是在运行时，动态地将代码切入到类的指定方法、指定位置上的编程思想就是面向切面的编程。

> AOP主要作用就是将类似于日志记录，性能统计，安全控制，事务处理，异常处理等重复性的代码块从业务逻辑代码中划分出来，对这些行为的分离。并且将它们独立到非知道业务逻辑的方法中，从而做到改变这些行为的时候不影响业务逻辑代码。

> AOP带来的优点：

- 降低系统的反复代码
- 降低模块间的耦合度
- 提高系统可扩展性
- 增加代码可维护性

> 装饰器是一个很著名的设计模式，经常被用于有切面需求的场景，装饰器的作用就是为已经存在的对象添加额外的功能，所以python中使用装饰器实现AOP。

## 30. 封装

**[python 类的封装](https://blog.csdn.net/max_like/article/details/81346484)**

> 面向对象编程的一个重要特点就是数据封装。类的封装包含数据封装、方法封装、属性封装。

```python
# 数据封装，将程序中需要的数据按照统一的格式封装在类型的内部，通过该类型的对象包装使用数据
class Student:
    def __init__(self, name, age):
        self.name = name
        self.age = age

# 方法封装，函数和方法混合开发，  处理和某个数据关联的功能-> 功能代码封装成函数，将函数封装在类型中处理具体功能的方法，就和对应的数据强制关联，方便统一管理维护
    def get_name(self):
        return self.name

student = Student("张三", "18", get_name())
```

- **属性封装**(重点重点重点)

> 属性是属于对象的特征，对象的特征是属于对象的数据，对象的数据一般不让外界直接访问。但是默认`self.name`不做任何添加的是公共的public，允许内部和外部的访问。

> 受保护的protected：在对象成员前面加一个下划线`self._name`，允许类中或子类中都可以进行访问，但外部不可以访问。

> 私有的private：在成员前面添加两个下划线`self.__name`，私有成员是高级别的封装，只有当前类对象自己能访问，连子类对象也不能访问到这个数据。

```python
# 属性封装的装饰器(https://blog.csdn.net/MrNoboday/article/details/89371430)

class User(object):

    def __init__(self, name):
        self.name = name
        self.__age = 0
        self.__gender = None

    @property  # 只读
    def age(self):
        if self.__age == 0:
            print("you haven't set age!")
            return None
        return self.__age

    @property
    def gender(self):
        if self.__gender is None:
            print("you haven't set gender!")
            return None
        return self.__gender

    @age.setter  # 只写
    def age(self, age):
        if 0 < age < 120:
            self.__age = age
        else:
            print("age set failure!")

    @gender.setter  # 只写
    def gender(self, gender):
        if gender.lower() in ['man', 'wowan']:
            self.__gender = gender.lower()
        else:
            print('gender set failure!')


if __name__ == '__main__':
    user = User('zhangsan')
    print('name:', user.name, 'gender:', user.gender, 'age:',user.age)
    user.age = 18
    user.gender = 'man'
    print('name:', user.name, 'gender:', user.gender, 'age:',user.age)
    user.age = 1000
    user.gender = 'double'
    print('name:', user.name, 'gender:', user.gender, 'age:',user.age)
    user.age = 99  # 这里用了@property装饰器把方法变成属性调用的，所以直接赋值
    print("间接修改的年龄: %s" % user.age)
    print(user._User__age = 88)
    print("直接修改的年龄: %s" % user.age)

# 结果
'''
you haven't set gender!
you haven't set age!
name: zhangsan gender: None age: None
name: zhangsan gender: man age: 18
age set failure!
gender set failure!
name: zhangsan gender: man age: 18
间接修改的年龄: 99
直接修改的年龄: 88
'''
```

> 可以通过属性封装的装饰器去更改私有变量的值。当然还有两种常用的方法：

- 间接：为这个私有变量提供一个操作方法，如`def age(self, age)`
- 直接：实例名._类名__私有变量名 = 值，如`user_User__age = 100`

## 31. 继承

> 继承是一种创建新类的方式，新创建的类加子类，继承的叫父类、超类、基类。继承是类与类之间的关系，继承的作用是减少代码冗余、提高重用性。

> 继承的特征：所有的类都继承自object类，即所有的类都是object类的子类；
            子类一旦继承父类，则可以使用父类中除了私有成员外的所有内容；
            子类继承父类后，并没有捡父类成员完全复制到子类中，而是通过引用关系访问调用；
            子类可以定义独有的成员属性和方法；
            子类中定义的成员和父类成员如果同名，则优先使用子类成员；
            子类如果想扩充父类的方法，可以再定义新方法的同时访问父类的成员进行代码重用；

- 单继承

> 每个类只能继承一个类，优点是传承有序、逻辑清晰、语法简单、隐患少；缺点是功能不能无限扩展，只能在当前唯一的继承链中扩展。

- 多继承

> 每个类允许继承多个类，优点是类功能扩展方便；缺点是继承关系混乱。

```python
class Fish():

    def __init__(self, name):
        self.name = name
    
    def swim(self):
        print("I am swimming...")

class Bird():

    def __init__(self, name):
        self.name = name
    
    def fly(self):
        print("I am flying...")

class Person():

    def __init__(self, name):
        self.name = name
    
    def work(self):
        print("I am working...")

# 单继承
class Student(Person):

    def __init__(self, name):
        self.name = name

class Alien(Fish, Bird, Person):

    def __init__(self, name):
        self.name = name

print("=" * 10 + " 单继承 " + "=" * 10)
student = Student("zhangsan")
student.work()
print("=" * 10 + " 多继承 " + "=" * 10)
alien = Alien("&%$#^@")
alien.swim()
alien.fly()
alien.work()

# 结果
'''
========== 单继承 ==========
I am working...
========== 多继承 ==========
I am swimming...
I am flying...
I am working...
'''
```

> 继承变量函数的查找顺序：
    优先查找自己的变量，没有则继续往上（父类）查找；构造函数如果本类中没定义，则自动查找调用父类构造函数，如果本类中有定义，则不用继续向上查找。

> 构造函数：是一类特使的函数，在类进行实例化之前调用，如果定义了构造函数，则实例化的时候使用此构造函数，而不查找父类构造函数；如果没有定义构造函数，则自动向上查找父类构造函数；如果子类没有定义构造函数，而父类的构造函数带参数，则实例化子类时，应该按父类构造函数参数进行传参。

```python
class Animal():
    pass

class Pet(Animal):

    def __init__(self, name):
        print("我是一只宠物 %s" % name)

class Dog(Pet):
    # __init__就是构造函数，记住一定要有这个参数
    # 每次进行实例化的时候，第一个被自动调用

    def __init__(self):
        print("我初始化为一只小狗")

# 实例化的时候，括号内的参数要与构造函数的参数匹配
dog = Dog()

class Cat(Pet):
    pass

# 在Cat类中，没有找到构造函数，自动从继承的父类Pet中查找
cat = Cat("嘟嘟")

# 结果
'''
我初始化为一只小狗
我是一只宠物 嘟嘟
'''
```

> super
    不是一个关键数字，而是一个类。super的作用是获取MRO（Method Resolution Order）方法解析顺序列表中的第一个类，而这个类往往就是它的父类，和父类没有任何实质性关系，可以用super()调用父类的初始化构造函数。

```python
print(type(super))
help(super)

# 结果
'''
<class 'type'>
Help on class super in module builtins:

class super(object)
 |  super() -> same as super(__class__, <first argument>)
 |  super(type) -> unbound super object
 |  super(type, obj) -> bound super object; requires isinstance(obj, type)
 |  super(type, type2) -> bound super object; requires issubclass(type2, type)
 |  Typical use to call a cooperative superclass method:
 |  class C(B):
 |      def meth(self, arg):
 |          super().meth(arg)
 |  This works for class methods too:
 |  class C(B):
 |      @classmethod
 |      def cmeth(cls, arg):
 |          super().cmeth(arg)
 |  
 |  Methods defined here:
 |  
 |  __get__(self, instance, owner, /)
 |      Return an attribute of instance, which is of type owner.
 |  
 |  __getattribute__(self, name, /)
 |      Return getattr(self, name).
 |  
 |  __init__(self, /, *args, **kwargs)
 |      Initialize self.  See help(type(self)) for accurate signature.
 |  
 |  __repr__(self, /)
 |      Return repr(self).
 |  
 |  ----------------------------------------------------------------------
 |  Static methods defined here:
 |  
 |  __new__(*args, **kwargs) from builtins.type
 |      Create and return a new object.  See help(type) for accurate signature.
 |  
 |  ----------------------------------------------------------------------
 |  Data descriptors defined here:
 |  
 |  __self__
 |      the instance invoking super(); may be None
 |  
 |  __self_class__
 |      the type of the instance invoking super(); may be None
 |  
 |  __thisclass__
 |      the class invoking super()
'''
```

> 菱形继承/钻石继承问题：
    （1）多个子类继承自同一个父类，这些子类又被同一个类继承，于是继承关系图形成了一个菱形图谱。
    （2）多继承的MRO用于保存继承顺序的一个列表，MRO列表的计算原则：子类永远在父类前面；如果多个父类，则根据继承语法中括号内的书写顺序存放；如果多个类继承了同一个父类，孙子类中只会选取继承语法括号中的第一个父类的父类。

```python
class A():
    pass

class B(A):
    pass

class C(A):
    pass

class D(B, C):
    pass

print(D.__mro__)


# 结果
'''
(<class '__main__.D'>, <class '__main__.B'>, <class '__main__.C'>, <class '__main__.A'>, <class 'object'>)
'''
```

> 派生类：派生就是子类在继承父类的基础上衍生出新的属性，子类中独有的，父类中没有的；或子类定义与父类重名的东西，子类有不同于父类的属性，这个子类叫做派生类。通常情况下，子类和派生类是同一个概念，因为子类都是有不同于父类的属性，如果子类和父类属性相同，就没必要创建子类了。

## 32. 多态与多态性

> 多态：指的是以类事物有多种形态，如一个抽象类有多个子类，多态的概念依赖于继承；如在java中，一个函数由于函数签名不同，可以有同名的不同函数存在，调用的时候根据函数签名不同自动找到相应的函数执行。简单来说，就是同一事物的多种形态。Python中的多态不是语法，而是一种设计思想，多态的设计就是要完成对不同类型对象使用相同方法调用能得到各自期望的结果。

```python
# 多态：同一种事物的多种形态，动物分为人、猪、狗等等
class Animal:
    def run(self):
        raise AttributeError('子类必须实现这个方法')

class People(Animal):
    def run(self):
        print('人正在走')

class Pig(Animal):
    def run(self):
        print('猪正在散步')

class Dog(Animal):
    def run(self):
        print('狗正在走')

people = People()
pig = Pig()
dog = Dog()

people.run()
pig.run()
dog.run()

# 结果
'''
人正在走
猪正在散步
狗正在走
'''
```

```python
import abc

# 同一类事物：文件
class File(metaclass=abc.ABCMeta): 
    @abc.abstractmethod
    def click(self):
        pass

# 文件的形态之一：文本文件 
class Text(File):
    def click(self):
        print('open file')

#文件的形态之二：可执行文件
class ExeFile(File):
    def click(self):
        print('execute file')

text = Text()
exefile = ExeFile()

text.click()
exefile.click()
# 结果
'''
open file
execute file
'''
```

> 多态性：指具有不同功能的函数可以使用相同的函数名，这样可以用一个函数名调用不同内容的函数（如向不同的对象发送同一条消息，不同的对象接受时会执行不同的行为）。简单来说，就是一种调用方式，产生不同的执行效果。

```python
# 多态性：一种调用方式，不同的执行效果（多态性）
class Animal:
    def run(self):
        raise AttributeError('子类必须实现这个方法')

class People(Animal):
    def run(self):
        print('人正在走')

class Pig(Animal):
    def run(self):
        print('猪正在散步')

class Dog(Animal):
    def run(self):
        print('狗正在走')

people = People()
pig = Pig()
dog = Dog()

# 多态性：定义统一的接口
def func(obj):  # obj这个参数没有类型限制，可以传入不同类型的值
    obj.run()  # 调用的逻辑都一样，执行的结果却不一样

func(people)
func(pig)
func(dog)

# 结果
'''
人正在走
猪正在散步
狗正在走
'''
```

```python
# 多态性
import abc

# 同一类事物：文件
class File(metaclass=abc.ABCMeta): 
    @abc.abstractmethod
    def click(self):
        pass

# 文件的形态之一：文本文件 
class Text(File):
    def click(self):
        print('open file')

#文件的形态之二：可执行文件
class ExeFile(File):
    def click(self):
        print('execute file')

text = Text()
exefile = ExeFile()

def func(f):
    f.click()

func(text)
func(exefile)

# 结果
'''
open file
execute file
'''
```

> 多态性的好处：
    - 增加了程序的灵活性
    - 增加程序的可扩展性

## 33. 重载

**[python 中的重载](https://blog.csdn.net/qq_37049781/article/details/83959365)**

> 在Python中，具有重载的思想却没有重载的概念。实际上，Python编程中具有重载的目的却无重载的行为，或者说python并不需要重载。python是一门动态语言，不需要声明变量类型，函数中可以接受任何类型的参数也就无法根据参数类型来支持重载，python没有必要去考虑参数的类型问题，这些都可以在函数内部判断处理，并无必要去在写一个函数。python 有多种传参方式，默认参数、可变参数、可变关键字参数，可以处理函数参数中参数可变的问题。

```python
# python3.4 中提供的一个转发机制来实现重载
from functools import singledispatch

@singledispatch  # 只支持根据第一个参数的类型来重载，不支持多参数重载
def function(obj):  # 被重载的函数
    print('%r' % (obj))

@function.register(int)
def function_int(obj):
    print('Integer: %d' % (obj))


@function.register(str)
def function_str(obj):
    print('String: %s' % (obj))

@function.register(list)
def function_list(obj):
    print('List: %r' % (obj))

if __name__ == '__main__':
    function(1)
    function('hello')
    function(range(3))
    function(object)

# 结果
'''
Integer: 1
String: hello
range(0, 3)
<class 'object'>
'''
```

> 重载是对继承的父类方法进行重新定义，重载可以重新定义方法还可以重新定义运算符。因为通过继承的类不一定能满足当前类的需求，在当前类中只需要修改部分内容而达到自己的需求。

> 重载的特点：
    - 减少代码量和灵活指定型类
    - 子类具有父类的方法和属性
    - 子类不能继承父类的私有方法或属性
    - 子类可以添加新的方法
    - 子类可以修改父类的方法

```python
# 方法重载

class Human(object):
    __name = ''  # 定义属性
    __sex = 0
    __age = 0
    __height = 0
    __weight = 0

    def __init__(self, sex, age, height, weight):
        self.__sex = sex
        self.__age = age
        self.__height = height
        self.__weight = weight

    def set_name(self, name):
        self.__name = name

    def show(self):
        print(self.__name, self.__sex, self.__age, self.__height, self.__weight)

class Student(Human):
    __classes = 0
    __grade = 0
    __num = 0

    def __init__(self, classes, grade, num, sex, age, height, weight):  # 重载 __init__方法
        self.__classes = classes
        self.__grade = grade
        self.__num = num
        Human.__init__(self, sex, age, height, weight)

    def show(self):  # 重载 show 方法
        Human.show(self)
        print(self.__classes, self.__grade, self.__num)

if __name__ == '__main__':
    s = Student(3, 2, 19990520, '男', 20, '172', 55)
    s.set_name('小明')
    s.show()

# 结果
'''
小明 男 20 172 55
3 2 19990520
'''
```

> 运算符重载是在类方法中拦截内置的操作——当类的实例出现在内置操作中，Python自动调用重新定义的方法，并将重新定义方法的返回值变成了相应操作的结果。

> python对运算符重载的一些限制：

- 不能重载内置类型的运算符
- 不能新建运算符，只能重载现有的
- 某些运算符不是重载：is、and、or、not

**[Python中运算符重载](https://www.cnblogs.com/laolibk/p/8011472.html)**
**[《流畅的python》](https://www.cnblogs.com/lht-record/p/10306591.html)**

```python
# 运算符重载

class List(object):
    __list = []

    def __init__(self, *args):  # 重载 __init__ 方法
        self.__list = []
        for arg in args:
            self.__list.append(arg)

    def __add__(self, n):  # 重载加法"+"运算符
        for i in range(0, len(self.__list)):
            self.__list[i] +=n

    def __sub__(self, n):  # 重载减法"-"运算符
        for i in range(0, len(self.__list)):
            self.__list[i] -= n

    def __mul__(self, n):  # 重载乘法"*"运算符
        for i in range(0, len(self.__list)):
            self.__list[i] *= n

    def __turediv__(self, n):  # 重载除法"/"运算符
        for i in range(0, len(self.__list)):
            self.__list[i] /= n

    def __floordiv__(self, n):  # 重载整除"//"运算符
        for i in range(0, len(self.__list)):
            self.__list[i] //= n

    def __mod__(self, n):  # 重载求余"%"运算符
        for i in range(0, len(self.__list)):
            self.__list[i] %= n

    def __pow__(self, n):  # 重载次幂"**"运算符
        for i in range(0, len(self.__list)):
            self.__list[i] **= n

    def show(self):
        print(self.__list)

if __name__ == '__main__':
    data_list = List(1, 2, 3, 4, 5, 6, 7, 8, 9)
    data_list.show()

    data_list + 2
    data_list.show()

    data_list - 2
    data_list.show()

    data_list * 2
    data_list.show()

    # data_list / 2
    # data_list.show()

    data_list // 2
    data_list.show()

    data_list % 2
    data_list.show()

    data_list ** 2
    data_list.show()

# 结果
'''
[1, 2, 3, 4, 5, 6, 7, 8, 9]
[3, 4, 5, 6, 7, 8, 9, 10, 11]
[1, 2, 3, 4, 5, 6, 7, 8, 9]
[2, 4, 6, 8, 10, 12, 14, 16, 18]
[1, 2, 3, 4, 5, 6, 7, 8, 9]
[1, 0, 1, 0, 1, 0, 1, 0, 1]
[1, 0, 1, 0, 1, 0, 1, 0, 1]
'''
```

> 一元运算符重载:

| 名称 | 运算符 | 方法 |
| :----: | :---- | :---- |
| 取正 | + | `__pos__` |
| 取负 | - | `__neg__` |
| 按位取反 | ~ | `__invert__` |
| 取绝对值 | `| |` | `__abs__` |

> 常见的算术运算符重载：

| 名称 | 运算符 | 正向方法 | 反向方法 | 就地方法 |
| :----: | :---- | :---- | :----: | :----: |
| 加法 | + | `__add__` | `__radd__` | `__iadd__` |
| 减法 | - | `__sub__` | `__rsub__` | `__isub__` |
| 乘法 | * | `__mul__` | `__rmul__` | `__imul__` |
| 除法 | / | `__truediv__` | `__rtruediv__` | `__itruediv__` |
| 整除 | // | `__floordiv__` | `__rfloordiv__` | `__ifloordiv__` |
| 求余 | % | `__mod__` | `__rmod__` | `__imod__` |
| 次幂 | ** | `__pow__` | `__rpow__` | `__ipow__` |

> 位操作运算符重载：

| 名称 | 运算符 | 正向方法 | 反向方法 | 就地方法 |
| :----: | :---- | :---- | :----: | :----: |
| 位与 | & | `__and__` | `__rand__` | `__iand__` |
| 位或 | `|` | `__or__` | `__ror__` | `__ior__` |
| 位异或 | ^ | `__xor__` | `__rxor__` | `__ixor__` |
| 左移 | << | `__lshift__` | `__rlshift__` | `__ilshift__` |
| 右移 | >> | `__rshift__` | `__rrshift__` | `__irshift__` |

> 比较运算符重载：

| 名称 | 运算符 | 正向方法 | 反向方法 | 后备机制 |
| :----: | :---- | :---- | :----: | :----: |
| 相等 | a == b | `a.__eq__(b)` | `b.__eq__(a)` | 返回id(a) == id(b) |
| 不相等 | a ！= b | `a.__ne__(b)` | `b.__ne__(a)` | 返回not (a == b) |
| 大于 | a > b | `a.__gt__(b)` | `b.__gt__(a)` | 抛出TypeError |
| 大于等于 | a >= b | `a.__ge__(b)` | `b.__ge__(a)` | 抛出TypeError |
| 小于 | a < b | `a.__lt__(b)` | `b.__lt__(a)` | 抛出TypeError |
| 小于等于 | a <= b | `a.__le__(b)` | `b.__le__(a)` | 抛出TypeError |

> 内建函数重载：

```python
def __len__(self):
    return len(obj)

def __reversed__(self):
    return reversed(obj)

def __round__(self):
    return round(obj)
```

> 数值转换函数重载：

```python
def __int__(self):
    return int(obj)

def __float__(self):
    return float(obj)

def __complex__(self):
    return complex(obj)

def __bool__(self):
    return bool(obj)
```

> 成员资格函数in、not in运算符重载

`def __contains__(self, e)`

> 索引和切片运算符重载

`__getitrm__(self, i)`方法
`__setitrm__(self, i, v)`方法
`__delitrm__(self, i)`方法

```python
class Indexer(object):
    def __getitem__(self, index):
        return index ** 2

x = Indexer()
print(x[2])

# 结果
'''
4
'''
```

> 迭代对象重载：

`__next__(self)` 迭代器
`__iter__(self)`可迭代对象

> with环境管理器类内重载:

`__enter__` 方法将在进入 with 语句时被调用返回由 as 变量管理的对象。
`__exit__` 方法将在离开with语句时被调用，且可以用参数来判断离开with语句时是否有异常发生并作出相应的处理。

> 属性相关方法重载

`__getattr__`属性获取
`__setattr__`属性赋值
`__delattr__`属性删除

> 其他

| 方法 | 重载 | 说明 |
| :----: | :---- | :---- |
| `__init__` | 构造函数 | 对象创建: `X = Class(args)` |
| `__new__` | 创建 | 在__init__之前创建对象 |
| `__call__` | 函数调用 | `X(*args, **kwargs)` |
| `__repr__, __str__` | 打印，转换 | `print(X)，repr(X)，str(X)` |
| `__del__` | 析构函数 | 对X对象收回 |

## 34. 函数式编程

> 函数是Python内建支持的一种封装，通过把打断代码拆层函数，通过一层层的函数调用，就可以把复杂任务分解成简单的任务，这种分解可以称之为面向过程的程序设计。函数就是面向过程的程序设计的基本单元。

> 函数式编程（Hunctingal Programming）虽然可以归结到面向过程的程序设计，但其思想更接近数学计算。函数式编程就是一种抽象程度很高的编程范式，纯粹的函数式编程语言编写的函数没有变量，因此，任意一个函数，只要输入是确定的，输出就是确定的，这种纯函数我们称之为没有副作用。而允许使用变量的程序设计语言，由于函数内部的变量状态不确定，同样的输入，可能得到不同的输出，这种函数是有副作用的。

> 函数式编程的一个特点就是，允许把函数本身作为参数传入另一个函数，还允许返回一个函数。Python对函数是编程仅提供部分支持，由于Python允许提供变量，因此python不是纯函数式编程语言。

## 35. python中的高阶函数

> 高阶函数：一个函数可以作为参数传给另外一个函数，或者一个函数的返回值为另外一个函数（若返回值为该函数本身，则为递归），满足其一则为高阶函数。

- abs

```python
# Python内置的绝对值函数
a = abs(-10)  # 直接调用abs()函数
f = abs  # 函数本身赋值给变量，即变量指向函数
b = f(-10)

print(a)
print(b)

# 结果
'''
10
10
'''
```

- map

> map()函数会根据的函数对指定的序列做映射。
map()函数语法：`map(function, iterable, ...)`，其中第一个参数function表示对序列每个元素进行同样的处理的表达式；iterable表示一个或者多个序列。

> 特别注意，py2返回的是列表，py3返回是一个迭代器。

```python
# 计算平方
def square(x):
    return x ** 2
data_list = [1, 2, 3, 4, 5]
res = map(square, data_list)

# 使用匿名函数
ans = map(lambda x: x ** 2, data_list)

print(res)
print(list(res))
print(ans)
print(list(ans))

# 结果
'''
<map object at 0x0000014F2F0F2A58>
[1, 4, 9, 16, 25]
<map object at 0x0000014F2F32B860>
[1, 4, 9, 16, 25]
'''
```

- reduce

> reduce()函数会对参数序列中元素进行积累。函数将一个数据集合（链表、元组等）中的所有数据进行下列操作：用穿个reduce中的函数function(有两个参数)相对集合中的第1、2个元素进行操作，得到的结果在于第三个数据继续用function函数进行运算，如此循环迭代，最后得到结果。

>reduce()函数语法：`reduce(function, iterable[, initializer])`，其中第一个参数是function函数，里面有两个参数；第二个参数iterable是可迭代对象；第三个是可选参数，初始参数。

```python
from functools import reduce

# 两数相加
def add(x, y):
    return x + y
data_list = [1, 2, 3, 4, 5]
res = reduce(add, data_list)  # 1+2+3+4+5

# 使用匿名函数
ans = reduce(lambda x, y: x + y, data_list)  # 1+2+3+4+5

print(res)
print(ans)

# 结果
'''
15
15
'''
```

- filter

> filter()函数用于过滤序列，过滤掉不符合条件的元素，返回符合条件的元素组成的新列表。

> filter()函数语法：`filter(function, iterable)`，reduce()接收连个参数，第一个参数function是判断函数，第二个参数iterable是可迭代对象，序列的每个元素作为参数传递给函数进行判断，然后返回True/False，最后将返回True的元素放到新列表中。

```python
# 过滤出列表中所有奇数
def is_odd(n):
    return n % 2 == 1

data_list = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
res = filter(is_odd, data_list)

# 使用匿名函数
ans = filter(lambda x: x % 2 == 1, range(1, 11))

print(res)
print(list(res))
print(ans)
print(list(ans))

# 结果
'''
<filter object at 0x000001F3A98EB198>
[1, 3, 5, 7, 9]
<filter object at 0x000001F3A990EB38>
[1, 3, 5, 7, 9]
'''
```

- sorted

> sort与sorted的区别：

- sort是应用在list上的方法，sorted可以对所有可迭代的对象进行排序操作。
- list的sort方法返回的是对已经存在的列表进行操作，而内建函数sorted方法返回的是一个新的list，而不是在原来的list上进行的操作。

> sorted()函数语法：`sorted(iterable, key=None, reverse=False)`，其中iterable是可迭代对象；key主要是用来进行比较元素，只有一个参数，具体的函数的参数是取自于可迭代对象中，指定可迭代对象中的一个元素来排序；reverse是排序规则，默认的是False升序，True为降序。

```python
a = [2, 3, 1, 4, 2, 0, -1]
b = a
c = ['a', 'C', 'A', 'b',  'c', 'B']
d = {1: 'D', 3: 'B', 5: 'A', 4: 'E', 2: 'C'}
e = [('Bob', 75), ('Adam', 92), ('Bart', 66), ('Lisa', 88)]
a.sort()

print(a)
print(sorted(b))
print(sorted(b, key=lambda x: x*-1))  # 利用key进行倒序排序
print(sorted(b, reverse=True))  # 利用reverse=True进行倒序排序
print(sorted(b, key=abs))  # 按绝对值大小升序排序
print(sorted(c))  # 字符串排序，按照ASCII大小比较
print(sorted(c, key=str.lower))  # 忽略字符串大小写排序
print(sorted(d))  # 对字典排序默认是对键keys进行排序
print(sorted(d.keys()))  # 对字典按keys值排序
print(sorted(d.items(), key=lambda x: x[0]))  # 还是对字典按keys值排序
print(sorted(d.items(), key=lambda x: x[1]))  # 对字典按键值value排序升序
print(sorted(e,key=lambda x: x[0]))  # 根据姓名升序排序
print(sorted(e,key=lambda x: x[1], reverse=True)) # 根据得分降序

# 结果
'''
[-1, 0, 1, 2, 2, 3, 4]
[-1, 0, 1, 2, 2, 3, 4]
[4, 3, 2, 2, 1, 0, -1]
[4, 3, 2, 2, 1, 0, -1]
[0, -1, 1, 2, 2, 3, 4]
['A', 'B', 'C', 'a', 'b', 'c']
['a', 'A', 'b', 'B', 'C', 'c']
[1, 2, 3, 4, 5]
[1, 2, 3, 4, 5]
[(1, 'D'), (2, 'C'), (3, 'B'), (4, 'E'), (5, 'A')]
[(5, 'A'), (3, 'B'), (2, 'C'), (1, 'D'), (4, 'E')]
[('Adam', 92), ('Bart', 66), ('Bob', 75), ('Lisa', 88)]
[('Adam', 92), ('Lisa', 88), ('Bob', 75), ('Bart', 66)]
'''
```

## 36. 返回函数

> 高阶函数出了可以接受函数作为参数外，还可以把函数作为结果值返回。

```python
# 嵌套函数，内层函数返回值是函数对象
def lazy_sum(*args):
    def sum():
        x = 0
        for i in args:
            x += i
        return x
    return sum

res = lazy_sum(1, 3, 5, 7, 9)  # 这里调用的是求和函数，而非求和结果
print(res)
print(res())

#  结果
'''<function lazy_sum.<locals>.sum at 0x000001A4B6E55488>
25
'''
```

> 实际上是一种闭包，详细参见[19. 闭包](#19-闭包)。**返回闭包时要牢记：返回函数不要引用任何循环变量，或者后续会发生变化的量。**

## 37. 匿名函数

先观摩下大佬博文**[Python 之 lambda 函数完整详解 & 巧妙运用](https://blog.csdn.net/PY0312/article/details/88956795)**

> 匿名函数在python编程语言中使用频率非常高，使用起来非常灵活、巧妙。

- python中使用关键字lambda来创建匿名函数，没有函数名字；
- lambda只是一个表达式，函数体比def简单很多；
- lambda的主体是一个表达式，而不是一个代码块，所以在表达式中只能封装有限的简单的逻辑表达式，复杂的需要函数来实现；
- lambda函数拥有自己的命名空间，且不能范围自有列表之外或者全局命名空间里的参数；

> **注意：**虽然lambda函数看起来只能写一行，却不等同于C或C++的内联函数，内联函数的目的是调用小函数时不占用栈内存从而增加运行效率。

> lambda函数语法：`lambda [arg1 [,arg2,...,argn]]: expression`

- lambda是python关键字，[arg...]和expression由用户自定义
- [arg...]是参数列表，形参可以为多个，逗号隔开
- expression是个参数表达式，且表达式只能是单行的，只能有一个表达式,且逻辑结束后直接返回数据
- 返回值在冒号之后设置，返回值和正常的函数一样,可以是任意数据类型。(但是想要返回多个元素要以容器的形式返回)

```python
# 将lambda函数赋值给一个变量，通过这个变量间接调用该lambda函数
add = lambda x, y: x + y
res = add(1, 2)
print(res)

# 结果
'''
3
'''

# 将lambda函数赋值给其他函数，从而将其他函数用该lambda函数替换
import time
time.sleep = lambda x: None
t = time.sleep(3)
print(t)

# 结果
'''
None
'''

# 列表推导式
s = [lambda : i for i in range(5)]
print(s)

# 结果
'''
[0, 1, 2, 3, 4]
'''

# 嵌套的lambda表达式
f = (lambda x: (lambda y: x + y))
res = f(10)
print(res(5))

# 结果
'''
15
'''
```

## 38. 偏函数

> 函数在执行时，要带上所有必要的参数进行调用，有时参数可以在函数被调用之前提前给定，这种情况下，一个函数有一个或多个参数预先就能用上，以便函数能用更少的参数进行调用。

> 偏函数就是将所要承载的函数作为partial()函数的第一个参数，原函数的个参数一次作为partial()函数后续的参数，除非使用关键字参数。

```python
from functools import partial

# 对整数100，取得对于不同数m的 100 % m 的余数
def mod(n, m):
    return n % m

mod_by_100 = partial(mod, 100)

print(mod(100, 7))
print(mod_by_100(7))

# 结果
'''
2
2
'''

# 最大值中每次都有10
max_new = partial(max, 10)  # 把10作为max的第一个参数，加到最左边
print(max_new(1, 5, 9))

# 等同于
args = (10, 1, 5, 9)
print(max(*args))

# 结果
'''
10
10
'''
```

## 39. 元编程

**[Python黑魔法：元类和元编程](https://zhuanlan.zhihu.com/p/114242597)**
**[Python 元编程](https://blog.csdn.net/leongongye/article/details/48343089)**

> 元编程（Meta Programming）又叫超编程，是指某类计算机程序的编写，这类计算机程序的编写或者超重其他程序（或者自身）作为他们的数据，或者在运行完成部分本应该在编译时完成的工作。多数情况下，与手工编译全部代码相比，程序员可以获得更高的工作效率，或者给与程序员更大的灵活度去处理新的情形而无需重新编译。

> 编写元程序的语言称之为元语言。被操作的程序的语言称之为“目标语言”。一门编程语言可以同时也是自身的元语言的能力称之为“反射”或者“自反”。作为胶水语言的python，对各种语言的库的支持（ctypes、js2py等），就是元编程应用的很好实例。

> 元编程是一种可以将程序当作数据来操作的技术，元编程能够读取，生成，分析或转换其他的程序代码，甚至可以在运行时修改自身。元编程存在的目的，就是多提供了一个抽象层次。

> 在python中，元编程实现通常的手段有：

- 预定义方法

```python
class A(object):
    def __init__(self, o):
        self.__obj__ = o

    def __getattr__(self, name):
        if hasattr(self.__obj__, name):
            return getattr(self.__obj__, name)
        return self.__dict__[name]

    def __iter__(self):
        return self.__obj__.iter__()

l = []
a = A(l)

for i in range(101):
    a.append(i)
print(sum(a))

# 结果
'''
10
10
'''
```

> 这是一个简单的agent类，`__iter__`属于云定义函数，不会调用`__getattr__`来获得，需要额外定义。在`__getattr__`和`__setattr__`两个函数中，可以访问`__dict__`，而在函数`__getattribute__`中使用`self.__dict__`会引发递归，需要用`object.getattribute(self, name)`访问，`getattribute`只能用于新式类。

- 函数赋值

```python
# socket.py中的例子
_delegate_methods = ("recv", "recvfrom", "recv_into", "recvfrom_into", "send", "sendto")

def __init__(self, family=AF_INET, type=SOCK_STREAM, proto=0, _sock=None):
    if _sock is None:
        _sock = _realsocket(family, type, proto)
    self._sock = _sock
    for method in _delegate_method:
        setattr(self, method, getattr(_sock, method))

# http代理装饰器
def http_proxy(proxyaddr, username=None, password=None):
    def reciver(func):
        def creator(family=socket.AF_INET, type=socket.SOCK_STREAM, proto=0):
            sock = func(family, type, proto)
            sock.connect(proxyaddr)
            def newconn(addr):
                http_connect(sock, addr, username, password)
            sock.connect, sock.connect_ex = nerconn, newconn
            return sock
        return creator
    return reciver
```

- 描述器

> 所谓描述器(descriptor)就是带有`__get__`和`__set__`函数的对象，当访问某个对象的某个属性，这个属性又是descriptor时，返回值是descriptor的`__get__`调用的返回，`__set__`也是类似的，带有`__set__`的称为data descriptor，而只有`__get__`的称为non data descriptor

> Python访问某个对象的某个属性时，是按照以下次序的：

- 类的数据描述器
- instance属性，无论其是否是描述器，都不调用`__get__`
- 类属性，包括non data descriptor

```python
class Meta(type):
    def __new__(cls, name, bases, attrs):
        for k, v in attrs.items():
            if hasattr(v, '__meta_init__'):
                v.__meta_init__(k)
        return type.__new__(cls, name, bases, attrs)

class AttrBase(object):
    def __meta_init__(self, k):
        self.name = k
    def __get__(self, obj, cls):
        return obj[self.name]
    def __set__(self, obj, value):
        obj[self.name] = value

class Base(dict, metaclass = Meta):
    pass

class User(dict):
    name = AttrBase()

b = User()
b.name = 'shell'
print(b)
print(b.name)

# 结果
'''
{'name': 'shell'}
shell
'''
```

> 当访问`b.name`时，实际上是去访问了`b['name']`，这个过程不是通过User类重载`__getattr__`实现的，而是通过descriptor。

- 元类

> 具体可以参考之前[python中的元类metaclass](#3-python中的元类metaclass)

- eval函数

> eval()函数来执行一个字符串表达式，并返回表达式的值。
eval()函数的语法：`eval(expression[, globals[, locals]])`，expression是表达式；globals是变量作用域，全局命名空间，如果被提供，这必须是一个字典对象；locals是变量作用域，局部变量命名空间，如果被提供，可以是任何映射对象。

```python
s1 ='2 * 6 / 2 + 2'
s2 = 'pow(2, 3)'
s3 = '2 ** 3'

print(eval(s1))
print(eval(s2))
print(eval(s3))

# 结果
'''
8.0
8
8
```

**经典案例：使用元类在python语言和数据库中间增加一个抽象ORM层**（可参考元类里面给出的[使用元类创建ORM实例](#3-python中的元类metaclass)）

> 元编程常见的应用场景

- 扩展重构语法
- 开发DSL
- 生成代码
- 根据特定场景自动选择代码优化
- 解决一些正交的架构设计问题
- 面向切面编程AOP

## 40. 捕获异常

**[python捕获异常及方法总结](https://www.cnblogs.com/beile/p/10789333.html)**

> 在编写程序或者调试程序时，或多或少存在BUG或者异常，这时候就需要进行异常的捕获，根据异常Traceback定位出错点，进行处理。

- 异常类型

  (1) Python内置异常
  > 在Python中，异常也是对象，python的异常处理能力很强大，有很多内置异常，可以为用户准确反馈出错信息。BaseException是所有内置异常的基类，但用户自定义的类并不几层BaseException，所有的异常类都是从Exception继承，且都在exceptions模块中定义。python自动降所有的异常名称放在内建命名空间中，所以程序不必导入exceptions模块即可使用异常，一旦引发而且没有捕捉SystemExit异常，程序执行就会终止，如果交互式回话遇到一个为捕捉的SystemExit异常，会话就会终止。

```python
"""python内置异常类的层次结构"""
BaseException  # 所有异常的基类
 +-- SystemExit  # 解释器请求退出
 +-- KeyboardInterrupt  # 用户中断执行(通常是"ctrl+C")
 +-- GeneratorExit  # 生成器(generator)发生异常来通知退出
 +-- Exception  # 常规异常的基类
      +-- StopIteration  # 迭代器没有更多的值
      +-- StopAsyncIteration  # 必须通过异步迭代器对象的__anext__()方法引发以停止迭代
      +-- ArithmeticError  # 各种算术错误引发的内置异常的基类
      |    +-- FloatingPointError  # 浮点计算错误
      |    +-- OverflowError  # 数值运算结果太大无法表示
      |    +-- ZeroDivisionError  # 除(或取模)零 (所有数据类型)
      +-- AssertionError  # 当assert语句失败时引发
      +-- AttributeError  # 属性引用或赋值失败
      +-- BufferError  # 无法执行与缓冲区相关的操作时引发
      +-- EOFError  # 当input()函数在没有读取任何数据的情况下达到文件结束条件(EOF)时引发
      +-- ImportError  # 导入模块/对象失败
      |    +-- ModuleNotFoundError  # 无法找到模块或在在sys.modules中找到None
      +-- LookupError  # 映射或序列上使用的键或索引无效时引发的异常的基类
      |    +-- IndexError  # 序列中没有此索引(index)
      |    +-- KeyError  # 映射中没有这个键
      +-- MemoryError  # 内存溢出错误(对于Python 解释器不是致命的)
      +-- NameError  # 未声明/初始化对象 (没有属性)
      |    +-- UnboundLocalError  # 访问未初始化的本地变量
      +-- OSError  # 操作系统错误(EnvironmentError、IOError、WindowsError、socket.error、select.error、mmap.error已合并到OSError中，构造函数可能返回子类)
      |    +-- BlockingIOError  # 操作将阻塞对象设置为非阻塞操作
      |    +-- ChildProcessError  # 在子进程上的操作失败
      |    +-- ConnectionError  # 与连接相关的异常的基类
      |    |    +-- BrokenPipeError  # 另一端关闭时尝试写入管道或试图在已关闭写入的套接字上写入
      |    |    +-- ConnectionAbortedError  # 连接尝试被对等方中止
      |    |    +-- ConnectionRefusedError  # 连接尝试被对等方拒绝
      |    |    +-- ConnectionResetError  # 连接由对等方重置
      |    +-- FileExistsError  # 创建已存在的文件或目录
      |    +-- FileNotFoundError  # 请求不存在的文件或目录
      |    +-- InterruptedError  # 系统调用被输入信号中断
      |    +-- IsADirectoryError  # 在目录上请求文件操作(例如 os.remove())
      |    +-- NotADirectoryError  # 在不是目录的事物上请求目录操作(例如 os.listdir())
      |    +-- PermissionError  # 尝试在没有足够访问权限的情况下运行操作
      |    +-- ProcessLookupError  # 给定进程不存在
      |    +-- TimeoutError  # 系统函数在系统级别超时
      +-- ReferenceError  # weakref.proxy()函数创建的弱引用试图访问已经垃圾回收了的对象
      +-- RuntimeError  # 在检测到不属于任何其他类别的错误时触发
      |    +-- NotImplementedError  # 在用户定义的基类中，抽象方法要求派生类重写该方法或者正在开发的类指示仍然需要添加实际实现
      |    +-- RecursionError  # 解释器检测到超出最大递归深度
      +-- SyntaxError  # Python语法错误
      |    +-- IndentationError  # 缩进错误
      |    |    +-- TabError  # Tab和空格混用
      +-- SystemError  # 解释器发现内部错误
      +-- TypeError  # 操作或函数应用于不适当类型的对象
      +-- ValueError  # 操作或函数接收到具有正确类型但值不合适的参数
      |    +-- UnicodeError  # 发生与Unicode相关的编码或解码错误
      |    |    +-- UnicodeDecodeError  # Unicode解码错误
      |    |    +-- UnicodeEncodeError  # Unicode编码错误
      |    |    +-- UnicodeTranslateError  # Unicode转码错误
      +-- Warning  # 警告的基类
      |    +-- DeprecationWarning  # 有关已弃用功能的警告的基类
      |    +-- PendingDeprecationWarning  # 有关不推荐用功能的警告的基类
      |    +-- RuntimeWarning  # 有关可疑的运行时行为的警告的基类
      |    +-- SyntaxWarning  # 关于可疑语法警告的基类
      |    +-- UserWarning  # 用户代码生成警告的基类
      |    +-- FutureWarning  # 有关已弃用功能的警告基类
      |    +-- ImportWarning  # 关于模块导入时可能出错的警告的基类
      |    +-- UnicodeWarning  # 与Unicode相关的警告的基类
      |    +-- BytesWarning  # 与bytes和bytearray相关的警告的基类
      |    +-- ResourceWarning  # 与资源使用相关的警告的基类，被默认警告过滤器忽略。
```

  (2) requests模块的相关异常
  
  > python在开发爬虫时，经常用到requests库，要调用requests模块的内置异常，需要`from requests.exceptions import xxx`，例如: `from requests.exceptions import ConnectionError, ReadTimeout` 或者 `from requests import ConnectionError, ReadTimeout`。

```python
# requests模块内置异常类的层次结构
IOError
 +-- RequestException  # 处理不确定的异常请求
      +-- HTTPError  # HTTP错误
      +-- ConnectionError  # 连接错误
      |    +-- ProxyError  # 代理错误
      |    +-- SSLError  # SSL错误
      |    +-- ConnectTimeout(+-- Timeout)  # (双重继承，下同)尝试连接到远程服务器时请求超时，产生此错误的请求可以安全的重试
      +-- Timeout  # 请求超时
      |    +-- ReadTimeout  # 服务器未在指定的时间发送任何数据
      +-- URLRequired  # 发出请求需要有效的URL
      +-- TooManyRequired  # 重定向太多
      +-- MissingSchema(+-- ValueError)  # 缺少URL架构(例如http或https)
      +-- InvalidSchema(+-- ValueError)  # 无效的架构，有效架构清常见defaults.py
      +-- InvalidURL(+-- ValueError)  # 无效的RUL
      |    +-- InvalidProxyURL(+-- ValueError)  # 无效的代理RUL
      +-- InvalidHeader(+-- ValueError)  # 无效的Header
      +-- ChunkedEncodingError  # 服务器声明了chunked编码但发送了一个无效的chunk
      +-- ContentDecodingError(+-- BaseHTTPError)  # 无法解码响应内容
      +-- StreamCosumedError(+-- TypeError)  # 此响应的内容已被使用
      +-- RetryError  # 自定义重试逻辑失败
      +-- UnrewindableBodyError  # 尝试倒回正文时，请求遇到错误
      +-- FileModeWarning(+-- DeprecationWarning)  # 文件以文本模式打开，但Requests确定其二进制长度
      +-- RequestsDependencyWarning  # 导入的依赖项与预期的版本范围不匹配

Warning
 +-- RequestsWarning # 请求的基本警告
```

```python
# 简单的requests请求，测试异常
import requests
from requests import ReadTimeout

def get_page(url):
    try:
        response = requests.get(url, timeout=1)
        if response.status_code == 200:
            return response.text
        else:
            print('Get Page Failed', response.status_code)
            return None
    except (ConnectionError, ReadTimeout):
        print('Crawling Failed', url)
        return None

def main():
    url = 'https://www.baidu.com'
    print(get_page(url))


if __name__ == '__main__':
    main()

# 结果
'''
<!DOCTYPE html>
<!--STATUS OK--><html> <head><meta http-equiv=content-type content=text/html;charset=utf-8><meta http-equiv=X-UA-Compatible content=IE=Edge>
...
...
...
</body> </html>
'''
```

  (3) 用户自定义异常

  > 用户可以通过创建一个异常类，直接或间接继承Exception类。

```python
# 自定义一个异常类
class MyError(Exception):

    def __init__(self, msg):
        self.msg = msg

    def __str__(self):
        return self.msg

try:
    raise MyError('类型错误')
except MyError as e:
    print('My exception occured', e.msg)

# 结果
'''
My exception occured 类型错误
'''
```

- 异常捕获

> 当发生异常时，需要对异常进行捕获，然后进行处理。python的异常捕获常用try...except...结构，把可能发生错误的语句放在try模块里，用except来处理异常，每个try都必须至少对应一个except。

| 关键字 | 说明 |
| :--: | :-- |
| try/except | 捕获异常并处理 |
| pass | 忽略异常 |
| as | 定义异常实例 |
| else | 如果try中的语句没有引发异常，这执行else中的语句 |
| finally | 无论是否出现异常，都执行的代码 |
| raise | 抛出/引发异常 |

  (1) 捕获所有异常

  ```python
  # 捕获所有的异常，包含键盘中断和程序退出请求
  try:
    do somethings
  except:
    print('捕获所有异常')
  ```

  (2) 捕获指定异常

  ```python
  # 捕获指定异常
  try:
    do somethings
  except:
    print('捕获指定异常')
  
  # 万能异常
  try:
    do somethings
  except Exception:
    print('万能异常')

  # 捕获指定的IOError
  try:
    f = open("test.txt", 'r')
  except IOError as e:
    print("open exception: %s: %s" % (e.errno, e.strerror))
  
  # 结果
  '''
  open exception: 2: No such file or directory
  '''
  ```

  (3) 捕获多个异常

  ```python
  # except同时处理多个异常，不区分优先级
  try:
    do somethings
  except (<Error1>, <Error2>, ...):
    print('异常说明')
  
  # 区分优先级进行处理异常
  """
  执行try下的语句，如果引发异常，则执行过程会跳到第一个except语句。
  如果第一个except中定义的异常与引发的异常匹配，则执行该except中的语句。
  如果引发的异常不匹配第一个except，则会搜索第二个except，允许编写的except数量没有限制。
  如果所有的except都不匹配，则异常会传递到下一个调用本代码的最高层try代码中。
  """
  try:
    do somethings
  except <Error1>:
    print('异常说明1')
  except <Error2>:
    print('异常说明2')
        .
        .
        .
  except <Errorn>:
    print('异常说明n')
  ```

  (4) 异常中的else

  ```python
  # 如果判断完没有某些异常之后还想做其他事情，就可以用else语句
  try:
    do somethings
  except <Error1>:
    print('异常说明1')
  except <Error2>:
    print('异常说明2')
  else:
    do other things  # try语句没有异常才会跳到这
  ```

  (5) 异常中的finally

  ```python
  # 无论是否发生异常都要执行的操作代码
  str1 = 'hello world'
  try:
    int(str1)
  except IndexError as e:
    print(e)
  except KeyError as e:
    print(e)
  except ValueError as e:
    print(e)
  else:
    print('未发生异常')  # try语句没有异常才会跳到这
  finally:
    print('不管前面怎么样，就是要做')  # 不管前面是否异常，都做的事情
  
  # 结果
  '''
  invalid literal for int() with base 10: 'hello world'
  不管前面怎么样，就是要做
  '''
  ```

  (6) raise主动触发异常
  
  > raise语句用于抛出、触发异常
  raise语法格式：`raise [Exception [, arg [, traceback]]]`，其中，Exception是异常类型，如ValueError，arg是一个可选的异常参数，当不提供时，默认为None，traceback是跟踪异常对象，可选。

  ```python
  # 判断数是否为0，是的话抛出异常:"参数错误"
  def not_zero(num):
    try:
        if num == 0:
            raise ValueError('参数错误')
        return num
    except Exception as e:
        print(e)
  
  not_zero(0)

  # 结果
  '''
  参数错误
  '''
  ```

  (7) 采用Traceback模块查看异常

  > 发生异常时，python利用traceback记住引发异常的以及程序的当前状态，维护着traceback对象，从而获取含有异常发生时函数调用堆栈有关的信息。`traceback.print_exc(file=open('error_log.txt','w+'))`

  ```python
  import traceback

  try:
    1/0
  except Exception as e:
    traceback.print_exc()
  
  # 结果
  '''
  Traceback (most recent call last):
  File "C:/Users/holysll/PycharmProjects/untitled/test/super_parent_class.py", line 12, in <module>
    1/0
  ZeroDivisionError: division by zero
  '''
  ```

  > traceback.print_exc()与traceback.format_exc()的区别：

- format_exc()返回字符串，而print_exc()则直接给打印出来；
- print_exc()还可以接受file参数直接写入到一个文件，如:`traceback.print_exc(file=open('error_log.txt','w+'))`

## 41. python常见的内置数据结构

- 字符串(string)

  - 由字符组成的有序的序列，是字符的集合
  - 使用单引号''、双引号""、三引号''''''表示
  - 有顺序、能索引、可迭代、元素能重复、不可变对象
  - python3中，字符串就是Unicode类型
  - 字符串连接：`"分隔符".join(iterable)`，如：`"".join(['1', '2', '3'])`。**注意：可迭代对象iterable必须是字符串**
  - 字符串拼接：通过str + str 将两个字符串拼接得到一个新的字符串
  - 字符串分割：
    - `str.split(sep=None, maxsplit=-1)`，seq表示分割符，缺省默认为空格，maxsplit表示分割次数，-1表示遍历整个字符串；
    - `str.rsplit(sep=None, maxsplit=-1)`表示从右至左分割；
    - `str.splitlines([keepends])`按照换行符切分字符串，换行符（`'\r', '\r\n', '\n'`），keepends表示是否保留换行符，默认为False不保留，True则保留会输出换行符；
    - `str.partition(seq) -> (head, seq ,tail)`从左到右，遇到分割符就把字符串分割成两部分，返回头、分隔符、尾三部分；若没找到分隔符，就返回头和两个空元素的三元组；
    - `str.rpartition(seq) -> (head, seq ,tail)`从右至左分割；

  - 字符串大小写：
    - `str.upper()` 全大写
    - `str.lower()` 全小写
    - `str.swapcase()`交互大小写

  - 字符串排版：
    - `str.title()` 标题的每个单词都大写
    - `str.capitalize()` 首字母大写
    - `str.center(width[, fillchar])` 字符串居中，并使用填充符(fillchar)填充至长度(width)，填充符默认为空格
    - `str.zfill(width)` 返回指定长度(width)的字符串，右对齐，左边前面填充0
    - `str.ljust(width[, fillchar])` 字符串左对齐，并使用填充符(fillchar)填充至长度(width)，填充符默认为空格
    - `str.rjust(width[, fillchar])` 字符串右对齐，并使用填充符(fillchar)填充至长度(width)，填充符默认为空格

  - 字符串修改：
    - `str.replace(old, new[,count])` 字符串匹配固定字符进行替换，count表示替换次数，默认全部替换
    - `str.strip([chars])` 字符串两端去除指定的字符集(chars)，默认是空格
    - `str.lstrip([chars])` 字符串去除左边指定的字符集(chars)，默认是空格
    - `str.lstrip([chars])` 字符串去除右边指定的字符集(chars)，默认是空格

  - 字符串查找：
    - `str.find(sub[, start[, end]])` 在指定区间[start, end]内，从左至右查找子串，找到返回索引，未找到返回-1
    - `str.rfind(sub[, start[, end]])` 在指定区间[start, end]内，从右至左查找子串，找到返回索引，未找到返回-1
    - `str.index(sub[, start[, end]])` 在指定区间[start, end]内，从左至右查找子串，找到返回索引，未找到抛出异常ValueError
    - `str.rindex(sub[, start[, end]])` 在指定区间[start, end]内，从右至左查找子串，找到返回索引，未找到抛出异常ValueError
  
  - 字符串统计：
    - `str.count(sub[, start[, end]])` 在指定区间[start, end]内，从左至右统计子串sub出现的次数

  - 字符串判断：
    - `str.endswith(suffix[, start[, end]])` 在指定区间[start, end]内，字符串是否是suffix结尾
    - `str.startswith(suffix[, start[, end]])` 在指定区间[start, end]内，字符串是否是suffix开头
    - `str.isalnum()` 是否是字母和数字组成
    - `str.isalpha()` 是否是字母
    - `str.isdecimal()` 是否包含十进制数字
    - `str.isdigit()` 是否全是全部数字（0-9）
    - `str.isidentifier()` 是否是仅包含字母、数字和下划线
    - `str.islower()` 是否都是小写
    - `str.isupper()` 是否都是大写
    - `str.isspace()` 是否只包含空白字符

  - 字符串格式化：
    - `"This is %s" % "python"`
    - `"This is {}".format("python")`
    - `"This {0[0]} {0[1]}".format(("is","python"))`

  - 字符串翻倍：`str * n`，例如`'py' * 3` 结果是`'pypypy'`

- 列表(list)

  - 一个排列整齐的队列，由若干个元素组成
  - 元素可以是任意对象，数字、字符串、字典、元组、列表、对象等
  - 列表内的元素有顺序，可以使用索引，元素能重复，可修改
  - 是线性数据结构，使用中括号[]表示
  - 列表初始化：
    - `s = list()`或`s = []` 生成一个空列表
    - `s = list(iterable)` 可将可循环的结构转化为列表，如：`s = list(range(5))`、`s = [1, 2, 3]`

  - 列表索引访问
    - `list[index]` index即是list的索引，也叫下标，从左至右，丛0开始到列表长度减一(len(list)-1)；若从右至左，索引从-1开始；索引不可以越界，否则抛出异常indexError
  
  - 列表查询：
    - `list.index(value, [start, [stop]])` 在指定区间[start, stop]查找列表内的元素是否与value匹配，匹配到第一个就返回索引，匹配不到，抛出异常ValueError

  - 列表元素统计：
    - `list.count(value)` 返回列表中匹配value的次数

  - 列表元素修改：
    - `list[index] = value`
  
  - 列表增加、插入元素
    - `list.append(object)` 尾部追加元素
    - `list.insert(index, object)` 在指定索引位置插入元素
    - `list.extend(iterable)` 将可迭代对象的元素追加进来
    - `list1 + list2`连个列表连接操作，本质上是add()方法

  - 列表删除元素
    - `list.remove(value)` 从左至右查找第一个value的值，移除该元素
    - `list.pop([index])` 根据指定的索引index弹出该元素，当index为空时，默认弹出尾部第一个元素即index=-1;
    - `list.clear()` 清空列表

  - 列表元素排序
    - `list.sort(key=None, reverse=False)`key是用来比较的元素，具体的函数的参数就是取自于可迭代对象中，指定可迭代对象的一个元素进行排序；reverse是排序规则，reverse=True降序，默认reverse=False升序
    - `list.reverse()` 对列表的元素进行反向排序

  - 列表元素打乱顺序
    - `random.shuffle(list)` 就地打乱列表元素

  - 列表随机取数
    - `random.randint(a, b)` 返回范围[a, b)之间的整数
    - `random.choice(seq)` 从非空序列的元素中随机选择一个元素
    - `random.randrange([start,] stop[, step])` 从指定范围[start, stop]内，按指定步长递增的集合中获取一个随机数
    - `random.sample(list, k)` 从样本空间或总体中随机取出k个不同的元素

  - 列表切片 **[Python切片操作详细例子](https://www.jianshu.com/p/15715d6f4dad)**

    - 切片基本表达式：`object[start_index : end_index : step]` step不写的时候默认为1，**注意索引方向必须与step的方向一致，否则返回空列表**
    - s = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
    - `s[:]` 或`s[::]` 从左往右，切取完整列表  # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
    - `s[::-1]` 从右往左，切取完整列表  # [9, 8, 7, 6, 5, 4, 3, 2, 1, 0]
    - `s[1:6]` 开始索引为1到索引为6，步长为1，从左往右取值  # [1, 2, 3, 4, 5]
    - `s[6:1:-1]` 开始索引为6到索引为1，步长为-1，从右往左取值  # [6, 5, 4, 3, 2]
    - `s[:6]` start_index省略时，这时默认从起点开始，索引为0到索引为6，步长为1，从左往右取值  # [0, 1, 2, 3, 4, 5]
    - `s[:6:-1]` start_index省略时，这时默认从终点开始，索引为9到索引为6，步长为-1，从右往左取值  # [9, 8, 7]
    - `s[6:]` end_index省略，这时默认为终点，索引为6到索引为9，步长为1，从左往右取值  # [6, 7, 8, 9]
    - `s[6:：-1]` end_index省略，这时默认为起点，索引为6到索引为0，步长为-1，从右往左取值  # [6, 5, 4, 3, 2, 1, 0]
    - `s[-1:-6:-1]` end_index省略，默认为终点，索引为-1到索引为-6，步长为-1，从右往左取值  # [9, 8, 7, 6, 5]
    - `s[-6:-1]` step省略，索引为-6到索引为-1，步长为1，从左往右取值  # [9, 8, 7, 6, 5]
    - `s[:-6]` step=1，从左往右取值，从索引0开始到索引-6  # [0, 1, 2, 3]
    - `s[:-6:-1]` start_index省略，这时默认为终点，step=-1，从右往左取值，从索引-1到索引-6  # [9, 8, 7, 6, 5]
    - `s[-6:]` end_index省略，这时为终点，step=1，从左往右取值，从索引-6开始到终点  # [4, 5, 6, 7, 8, 9]
    - `s[-6::-1]` end_index省略，这时为起点，step=-1，从右往左取值，从索引-6到索引0  # [4, 3, 2, 1, 0]
    - `s[1:-6]` step=1，从左往右取值，从索引1到索引为-6  # [1, 2, 3]
    - `s[-1:6:-1]` step=-1，从右往左取值，从索引-1到索引6  # [9, 8, 7]

  - 多层切片操作：
    - `s[:8][2:5][-1:]` 相当于先`s[:8]=[0, 1, 2, 3, 4, 5, 6, 7]`，然后`[0, 1, 2, 3, 4, 5, 6, 7][2:5]=[2, 3, 4]`，最后`[2, 3, 4][-1:]=[4]`

  - 带表达式的切片操作：
    - `s[2+1:3*2:7%3]` 先计算各表达式可知，切片操作相当于`s[3:6:1]=[3, 4, 5]`

  - 常用切片操作
    - 取偶数位置：`s[::2]=[0, 2, 4, 6, 8]`
    - 取奇数位置：`s[1::2]=[1, 3, 5, 7, 9]`
    - for循环里的切片：`for i in range(1, 100)[2::3][-5:]:` 分解为三步，先生成[1, 2, 3, ..., 99]的整数对象，然后step=3，从左往右取值，从索引2（即3）到终点（即99），得到[3, 6, 9, ... , 99]，最后里面取最后五个数[99, 96, 93, 90, 87]

- 元组(tuple)

  - 一个有序的元素组成的集合
  - 有顺序、能索引、元素能重复、不可变对象
  - 小括号()表示，单个元素定义时：(1,) 必须带逗号
  - tuple是只读，没有增删改，其他功能和列表差不多
  - 元组初始化：`t = tuple()`空元组；`t = tuple(iterable)` 可迭代对象元组

- 字典(dict)

  - key-value键值对形式的数据集合
  - 无顺序、key不可重复、可变可迭代
  - 是非线性数据结构，使用大括号{}表示，里面都是键值对key:value的形式
  - 字典的初始化
    - `d = dict()` 或者 `d = {}` 新建一个空字典
    - `d = {'x': 1, 'y': 2}`  # {'x': 1, 'y': 2}
    - `d = dict(x=1, y=2)`  # {'x': 1, 'y': 2}
    - `d = dict(zip('abc',[1, 2, 3]))`  # {'a': 1, 'b': 2, 'c': 3}
    - `d = dict.fromkeys(range(2), 3)`  # {0: 3, 1: 3}
    - `d = dict.fromkeys(('x', 'y'), 2)`  # {'x': 2, 'y': 2}
    - `d = dict([('x', 1),('y', 2)])`  # {'x': 1, 'y': 2}

  - 字典的访问
    - `d[key]` 返回key对应的值value，key不存在时抛出异常KeyError
    - `get(key[, default])` 返回key对应的值value，key不存在时返回缺省值默认为None
    - `setdefault(key[, default])` 返回key对应的值value，key不存在时添加key，value为default，并返回default，默认为None

  - 字典增加和修改：
    - `d[key] = value` 将key对应的值改为value，若key不存在这添加新的kv对
    - `update([other])` 使用另一个字典的kv对更新本字典，若key存在就覆盖该key对应的值，若key不存在，就添加。如`d.update(x=6)`或`d.update({'red': 3, 'x': 9})`或`d.update((('red', 666),('green', 333)))`

  - 字典删除：
    - `d.pop(key[, default])` 若key存在，移除它，并返回key对应的value；若key不存在，返回给定的default，default未设置，key不存在时抛出异常KeyError
    - `d.popitem()` 移除并返回字典中最后一个键值对，若字典为空，抛出KeyError异常
    - `d.clear()` 清空字典
    - `del d['x']` 删除key为x的键值对，本质是删除对象引用

  - 字典遍历：
    - 遍历key：`for k in d: print(k)` 打印的是字典中的key
    - 遍历key：`for k in d.keys(): print(k)` 打印的是字典中的key
    - 遍历key：`for k in d.items(): print(k[0])` 打印的是字典中的key
    - 遍历value：`for k in d: print(d[k])` 打印key对应的value
    - 遍历value：`for k in d.keys(): print(d.get(k))` 打印key对应的value
    - 遍历value：`for v in d.values(): print(v)` 打印字典中的value
    - 遍历value：`for v in d.items(): print(v[1])` 打印字典中的value
    - 遍历item：`for item in d.items(): print(item)` 打印键值对
    - 遍历item：`for item in d.items(): print(item[0], item[1])` 打印键值对
    - 遍历item：`for k, v in d.items(): print(k, v)` 打印键值对
  
  - 字典的遍历移除

    ```python
    d = dict(a=1, b=2, c=3, d=4, e='sss')
    keys = []
    for k, v in d.items():
        if isinstance(v, str):
            keys.append(k)
    for k in keys:
        d.pop(k)
    print(d)

    # 结果
    '''
    {'a': 1, 'b': 2, 'c': 3, 'd': 4}
    '''
    ```

  - defaultdict类
    - `collections.defaultdict([default_factory[, ...]])` 第一个参数是default_factory，缺省是None，它提供一个初始化函数，当key不存在时，会调用这个工厂函数的__missing__(key)的方法，返回一个根据default_factory参数的默认值给这个key的value

    ```python
    # 常规方法
    import random
    d1 = {}
    for k in 'abcdef':
        for i in range(random.randint(1, 5)):
            if k not in d1.keys():
                d1[k] = []
            d1[k].append(i)
    print(d1)

    # 通过defaultdict类
    from collections import defaultdict
    import random

    d2 = defaultdict(list)
    for k in 'abcdef':
        for i in range(random.randint(1, 5)):
            d2[k].append(i)
    print(d2)

    # 结果
    '''
    {'a': [0, 1], 'b': [0], 'c': [0, 1, 2, 3], 'd': [0], 'e': [0, 1, 2, 3, 4], 'f': [0, 1]}
    defaultdict(<class 'list'>, {'a': [0, 1, 2, 3], 'b': [0, 1], 'c': [0], 'd': [0], 'e': [0, 1], 'f': [0, 1, 2]})
    '''
    ```

  - OrderedDict记录顺序：
    - `collections.OrderedDict([items])` key并不是按照加入的顺序排列的，可以使用OrderedDict来记录顺序

    ```python
    from collections import OrderedDict
    import random

    d = {'banana':3, 'apple':4, 'pear':1, 'oranger':2}
    print(d)
    keys = list(d.keys())  # 获取key转化为list
    random.shuffle(keys)  # 打乱顺序
    print(keys)
    od = OrderedDict()
    for key in keys:
        od[key] = d[key]
    print(od)
    print(od.keys())

    # 结果
    '''
    {'banana': 3, 'apple': 4, 'pear': 1, 'oranger': 2}
    ['oranger', 'pear', 'apple', 'banana']
    OrderedDict([('oranger', 2), ('pear', 1), ('apple', 4), ('banana', 3)])
    odict_keys(['oranger', 'pear', 'apple', 'banana'])
    '''
    ```

- 集合(set)

  - 一个无序的不重复的元素序列
  - 是非线性数据结构，使用大括号{}表示
  - 集合的基本应用：元素测试、list和tuple元素去重
  - 集合支持一些数学操作：并集(union)、交集(intersection)、差集(difference)、对称差集(symmetric difference)
  - 集合的创建：
    - `set_name = {value1, value2, ...}` 类似于字典的创建
    - `set_name = set()` 空集合必须用set()创建，而不能用{}，这样创建出来的是字典
    - `set_name = set(list_name)` 把list转化为set类型
  
  - 利用集合去重
    - 列表去重：`set_name = set(list_name)`
    - 字符串去重：`set_name = set(string)`
    - 元组去重：`set_name = set(tuple)`

  - 集合的数学操作
    - 并集：`A | B` 或 `A.union(B)`  # A和B的元素都有，且不会重复
    - 交集：`A & B` 或 `A.intersection(B)`  # A和B的共同有的元素
    - 差集：`A - B` 或 `A.difference(B)`  # A中有，但B中没有的元素
    - 对称差集：`A ^ B` 或 `A.symmetric_difference(B)`  # A有或B有，但不是它们都有，除开公共有的元素

  - 集合判断包含、子集：
    - A包含B：`A.issuperset(B)` 或 `A >= B`
    - B是A的子集：`B.issubset(A)` 或 `B <= A`

  - 集合推导式： `s = {x for x in 'abcdef' if x not in 'abc'}`

  - 集合新增元素
    - 增加单个元素：`A.add(3)`
    - 增加一组元素：`A.update(['a', 'b', 'c'])`

  - 删除集合元素
    - 直接删除指定元素：`A.remove(3)`  # 若元素不存在会报错，建议用discard()方法
    - 如果集合存在指定元素，则删除该元素：`A.discard('a')`
    - 随机删除元素：`A.pop()`  # set 集合的 pop 方法会对集合进行无序的排列，然后将这个无序排列集合的左面第一个元素进行删除
    - 清空集合：`A.clear()`

  - 判断两个集合包含的元素是否相同：`A.isdisjoint(B)`  # 若相同返回True, 否则返回False

## 42. python bytes与bytearray

> 常识普及：通常在常用的ASCII、utf-8 和unicode 编码中，像 a 这样一个英文字符，在内存中占一个字节。一个汉字在ASCII和unicode编码里占两个字节，在utf-8 编码中占三个字节。一个字节有八位，也就是八个数字，也叫8个bit 。计算机中的最小储存单位就是bit，bit是二进制的，所以计算机中的数据全都是0和1，没有其他的数字。

- bytes

  - bytes是字节组成的有序的不可变序列
  - 字符串按照不同的字符集编码encode返回直接序列bytes
    - `encode(encoding="utf-8", errors="strict") -> str`
  - 字节序列bytes按照不同的字符集解码decode返回字符串
    - `bytes.decode(encoding="utf-8", errors="strict") -> str`
  
  - bytes的语法：`class bytes([source[, encoding[, errors]]])`
    - 若没有输入任何参数，默认就是初始化数组为0个元素：`b = bytes()`  # 空bytes
    - 若source为整数，则返回一个长度为source的初始化数组：`b = bytes(3)`   # b'\x00\x00\x00' 创造三个空字节，每个字节为空
    - 若source为字符串，这找找指定的encoding讲字符串转换为字节序列：`b = bytes('hello', encoding="utf-8")`  # b'hello'
    - 若source为可迭代类型，这元素必须为[0,255]中的整数：`b = bytes([1, 2, 3, 4])`  # b'\x01\x02\x03\x04'
    - 若source为与buffer接口一致的对象，从一个字节序列或者buffer复制出一个新的不可变的bytes对象：

    ```python
    # 复制bytes对象
    b1 = bytes([0x61, 0x62])
    b2 = b1
    print(b1, b2)
    print(id(b1), id(b2))
    print(b1 is b2)

    # 结果
    '''
    b'ab' b'ab'
    3162472152320 3162472152320
    True
    '''
    ```

  - 空bytes对象创建方式：
    - 通过构造函数创建空bytes：`b = bytes()`
    - 通过空字符串创建空bytes：`b = b''`

  - bytes操作：与字符串操作基本一样(string)，都是不可变类型
    - 替换：`b'Python'.replace(b'P', b'p')`  # 里面的参数也是bytes类型的
    - 查找：`b'Python'.find(b'o')`  # 返回匹配到字节的索引号，未找到返回-1
    - 十六进制数字组成的字符串转换为bytes

    ```python
    # 十六进制数字组成的字符串
    s = '49 20 6c 69 6b 65 20 50 79 74 68 6f 6e'  # 空格是无效的，要空格需要用ASCII编码
    b = bytes.fromhex(s)
    print(b)

    # 结果
    '''
    b'I like Python'
    '''

    # 字符串转化为十六进制表达
    hex_str = 'I like Python'.encode().hex()
    print(hex_str)
    res = []
    for i in range(len(hex_str)):
        if i % 2 == 0:
            if i == 0:
                res.append(hex_str[i])
            else:
                w = ' ' + hex_str[i]
                res.append(w)
        else:
            res.append(hex_str[i])

    print("".join(res))

    # 结果
    '''
    49206c696b6520507974686f6e
    49 20 6c 69 6b 65 20 50 79 74 68 6f 6e
    '''
    ```

    - 将一个字节数组bytes妆花为整数：`int.from_bytes(bytes, byteorder`

    ```python
    # 大端模式将bytes -> int
    num = int.from_bytes(b'abcd', 'big')
    print(num, hex(num))

    # 大端模式将int -> bytes
    print(num.to_bytes(4, 'big'))  # 第一个参数是给定字节数，不够会在前面补空字符的ASCII码

    b = 97
    print(b.to_bytes(1, 'big'))

    # 结果
    '''
    1633837924 0x61626364
    b'abcd'
    b'a'
    '''
    ```
  
  - 字节序：
    - 大端模式(big-endian)：尾巴放在大地址端
      - Mac OS使用大端模式
      - Java虚拟机是大端模式
      - 网络传输更多使用大端模式
    - 小端模式(little-endian)：尾巴放在低地址端
      - Intel X86 CPU使用小端模式
      - Windows、Linux使用小端模式

- bytearray

  - bytearray是字节组成的有序的可变数组
  - 字节数组bytearray按照不同的字符集解码decode返回字符串
    - `bytearray.decode(encoding="utf-8", errors="strict") -> str`
  
  - bytearray()方法语法：`class bytearray([source[, encodeing[, errors]]])`，返回一个元素可变的新字节数组，每个元素值必须是[0,256]内的整数，其他类型不行
    - 若没有输入任何参数，默认就是初始化数组为0个元素：`b = bytearray()`  # b'' 空bytearray
    - 若source为整数，则返回一个长度为 source 的初始化数组：`b = bytearray(3)`  # bytearray(b'\x00\x00\x00')
    - 若source为字符串，则按照指定的 encoding 将字符串转换为字节序列：`b = bytearray('python', encoding="utf-8")`  # bytearray(b'python')
    - 若source为可迭代类型，则元素必须为[0 ,255]中的整数：
    `b = bytearray([1, 2, 3])`  # bytearray(b'\x01\x02\x03')
    - 若source为与buffer接口一致的对象，从一个字节序列或者buffer复制出一个新的不可变的bytes对象：

    ```python
    # 复制bytes对象
    b1 = bytearray([0x61, 0x62])
    b2 = b1
    print(b1, b2)
    print(id(b1), id(b2))
    print(b1 is b2)

    # 结果
    '''
    bytearray(b'ab') bytearray(b'ab')
    1992609708832 1992609708832
    True
    '''
    ```

    - bytearray操作：与bytes类型方法相同
    - 替换：`bytearray(b'Python').replace(b'P', b'p')`  # 里面的参数也是bytes类型的
    - 查找：`bytearray(b'Python').find(b'o')`  # 返回匹配到字节的索引号，未找到返回-1
    - 十六进制数字组成的字符串转换为bytearray

    ```python
    # 十六进制数字组成的字符串
    s = '49 20 6c 69 6b 65 20 50 79 74 68 6f 6e'  # 空格是无效的，要空格需要用ASCII编码
    b = bytearray.fromhex(s)
    print(b)

    # 结果
    '''
    bytearray(b'I like Python')
    '''

    # 字符串转化为十六进制表达
    hex_str = bytearray('I like Python'.encode()).hex()
    print(hex_str)
    res = []
    for i in range(len(hex_str)):
        if i % 2 == 0:
            if i == 0:
                res.append(hex_str[i])
            else:
                w = ' ' + hex_str[i]
                res.append(w)
        else:
            res.append(hex_str[i])

    print("".join(res))

    # 结果
    '''
    49206c696b6520507974686f6e
    49 20 6c 69 6b 65 20 50 79 74 68 6f 6e
    '''
    ```

  - 索引

  ```python
  # 索引返回的是该字节对应的ASCII编码
  b1 = bytearray(b'abcdef')
  print(b1)
  print(b1[0])  # 当取单个字符时，返回的字符所对应的ASCII编码
  print(b1[:3])  # 当取字符序列的时候，返回的是对应的字符片段

  # 结果
  '''
  bytearray(b'abcdef')
  97
  bytearray(b'abc')
  '''
  ```

  - bytearray增加、插入元素
    - 尾部追加元素：

    ```python
    b = bytearray(b'abcd')
    b.append(101)  # 这里参数是[0,255]内的整数
    print(b)

    # 结果
    '''
    bytearray(b'abcde')
    '''
    ```

    - 指定索引位置插入元素：

    ```python
    b = bytearray(b'abcd')
    b.insert(0, 65)  # 这里第一个参数是索引位置，第二个参数是[0,255]内的整数
    print(b)

    # 结果
    '''
    bytearray(b'Aabcd')
    '''
    ```

  - bytearray追加可迭代的整数集合，在[0,255]范围内

    ```python
    b = bytearray(b'abcd')
    b.extend(range(101, 104))  # 101、102、103
    print(b)

    # 结果
    '''
    bytearray(b'abcdefg')
    '''
    ```

  - bytearray移除元素
    - 指定索引移除， 索引为空时，默认为-1，表示从移除尾部第一个：

    ```python
    b = bytearray(b'abcd')
    b.pop()
    print(b)
    b.pop(0)
    print(b)

    # 结果
    '''
    bytearray(b'abc')
    bytearray(b'bc')
    '''
    ```

    - 找到第一个value移除，找不到则抛出ValueError异常：

    ```python
    b = bytearray(b'abcd')
    b.remove(99)  # 移除c
    print(b)

    # 结果
    '''
    bytearray(b'abd')
    '''
    ```

  - bytearray清空元素

  ```python
  b = bytearray(b'abcd')
  b.clear()
  print(b)

  # 结果
  '''
  bytearray(b'')
  '''
  ```

  - bytearray元素反转

  ```python
  b = bytearray(b'abcd')
  b.reverse()
  print(b)

  # 结果
  '''
  bytearray(b'dcba')
  '''
  ```

## 43. 字符串和字节串的区别

- 字符串有若干个字符组成，以字符为单位进行操作；字节串由若干个字节组成，以字节为单位进行操作。
- 字符串和直接传出了操作的数据单元不同之外，它们支持的所有方法基本相同。
- 字符串和字节串都是不可变序列，不能随意增加和删除数据。
- bytes只负责以字节序列的形式（二进制的形式）来存储数据，至于这些数据到底表示什么内容（字符串、数字、图片、音频等），完全由程序的解析方式决定。
- bytes只是简单记录内存中的原始数据，不在意这些数据的使用。
- 字符串和字节串可以通过不同字符集进行相互转换。
- bytes类型的数据非常适合在互联网上传输，可用于网络通信编程。
- bytes也可以用于存储图片、音频、视频等二进制格式的文件。
- 字符串转换成bytes对象：
  - 字符串内容都是ASCII字符，直接在字符串前面添加`b`前缀就可以将字符串转换为bytes

  ```python
  # 字符串的内容是英文字母，都是ASCII字符
  s= 'abcdefg'
  b1 = b'abcdefg'
  print(b1)
  print(b1[0])  # 当取单个字符时，返回的字符所对应的ASCII编码
  print(b1[:3])  # 当取字符序列的时候，返回的是对应的字符片段

  # 结果
  '''
  b'abcdefg'
  97
  b'abc'
  '''
  ```

  - bytes是一个类，调用构造方法bytes()，可以将字符串按照指定的字符集转换为bytes，若未指定字符集，默认采用utf-8

  ```python
  # 调用构造方法bytes()，把字符串转换为bytes
  s = "我喜欢python，今年25岁"
  b2 = bytes(s, encoding="utf-8")
  print(b2)

  # 结果
  '''
  b'\xe6\x88\x91\xe5\x96\x9c\xe6\xac\xa2python\xef\xbc\x8c\xe4\xbb\x8a\xe5\xb9\xb425\xe5\xb2\x81'
  '''
  ```
  
  - 通过encode()方法见字符串按照指定的字符集转换成对应的字节串，若未指定字符集，默认采用utf-8

  ```python
  # 通过encode()的方法将字符串转换为bytes
  s = "我喜欢python，今年25岁"
  b3 = s.encode("utf-8")  # 如果未指定字符集，默认为utf-8，括号里可不填
  print(b3)

  # 结果
  '''
  b'\xe6\x88\x91\xe5\x96\x9c\xe6\xac\xa2python\xef\xbc\x8c\xe4\xbb\x8a\xe5\xb9\xb425\xe5\xb2\x81'
  '''
  ```

  - 通过调用bytes类中的decode()方法，可以将btyes对象按照指定的字符集转换为字符串

  ```python
  # 通过decode()方法，将bytes转换成字符串
  b4 = b'\xe6\x88\x91\xe5\x96\x9c\xe6\xac\xa2python\xef\xbc\x8c\xe4\xbb\x8a\xe5\xb9\xb425\xe5\xb2\x81'
  s = b4.decode("utf-8")  # 如果未指定字符集，默认为utf-8，括号里可不填
  print(s)

  # 结果
  '''
  我喜欢python，今年25岁
  '''
  ```

## 44. 字符集（字符编码）

> ASCII编码，将符号、数字、英文等存储到计算机

> GB2312编码和GBK编码，将中文存储到计算机

> Unicode字符集，将全世界文字存储到计算机

## 45. python中参数类型有哪些

- 位置参数：也叫必备参数，指函数调用时，传入的实参数量和位置、类型必须与函数定义时保持一致，即形参和实参的位置数量必须一致

```python
# 在调用func函数时，必须按位置传入name和age，多了少了都不行，否则会抛出TypeError异常
def func(name, age):
    """
    :param name: str
    :param age: int
    :return: tuple
    """
    print(name, age)

func('lucy' ,18)
func(*('lucy' ,18))  # 使用*解构

# 结果
'''
lucy 18
lucy 18
'''
```

- 默认参数
  - 函数定义时，为参数设置一个默认值，当函数调用时，没有传入这个参数值，直接使用这个默认值。指定有默认值的形参，必须是在没有默认值的参数的最后，否则会产生语法错误；而且默认参数必须指向不可变对象，如果指向可变对象，多次调用时，可能得到的不是意料之内的结果

  ```python
  def func(x, y=0):
    """
    :param x: int
    :param x: int
    :return:
    """
    return x + y

  print(func(3))  # 传入参数x=3
  print(func(3, 4))  # 传入参数x=3, y=4

  # 结果
  '''
  3
  7
  '''
  ```

- 关键字参数：函数调用时，是指使用形式参数的名字来确定输入的参数值,（形参的名字=输入的参数值），通过此方式指定函数实参时，不再需要与形参的位置完全一致，只要将参数名写正确即可；使用位置参数和关键字参数混合传参的方式时，关键字参数必须位于所有的位置参数（即前面必须传位置参数，最后在传关键字参数，位置得对应）。

```python
def func(x, y):
    """
    :param x: int
    :param x: int
    :return:
    """
    return x + y

print(func(3, 4))  # 位置参数
print(func(x=3, y=4))  # 关键字参数
print(func(y=4, x=3))  # 关键字参数，位置改变
print(func(3, y=4))  # 位置参数与关键字混合

# 结果
'''
7
7
7
7
'''
```

- 可变位置参数：定义参数时前面加一个*，表示这个参数是可变的，可以接受任意多个参数，这些参数构成一个元组，只能通过位置参数传递。

```python
# 可以接收不定参数，返回的类型是元组
def func(*args):
    """
    :param args:
    :return:
    """
    print(type(args))
    sum = 0
    for i in args:
        sum += i
    return sum

print(func(1, 2, 3))
print(func(*(1, 2, 3)))  # 使用*解构

# 结果
'''
<class 'tuple'>
6
<class 'tuple'>
6
'''
```

- 可变关键字参数：定义参数时，在前面加**，`**kwargs`表示这个参数可变，可以接受零个或多个关键字参数，并以字典的形式传入函数体，关键字为字典的key，关键字绑定的值为value，如果可变关键字没有接收到任何参数，则传入函数体一个空字典{}。

```python
# 只接收可变关键字参数
def func(**kwargs):
    """
    :param kwargs:
    :return:
    """
    kwargs_type = (str(type(kwargs))).split("'")[1]
    print("kwargs: 类型为{0}, 值为{1}".format(kwargs_type, kwargs))

func()  # 未传任何参数，返回空字典
func(x=1, y=2, z=3)  # 关键字对传参
func(**{'x': 1, 'y': 2, 'z': 3})  # 使用**解包字典

# 结果
'''
kwargs: 类型为dict, 值为{}
kwargs: 类型为dict, 值为{'x': 1, 'y': 2, 'z': 3}
kwargs: 类型为dict, 值为{'x': 1, 'y': 2, 'z': 3}
'''

# 可变位置参数与可变关键字参数一起使用，这是可变位置参数必须在前面
def func(*args, **kwargs):
    """
    :param args:
    :param kwargs:
    :return:
    """
    args_type = (str(type(args))).split("'")[1]
    kwargs_type = (str(type(kwargs))).split("'")[1]
    print("args: 类型为{0}, 值为{1}".format(args_type, args))
    print("kwargs: 类型为{0}, 值为{1}".format(kwargs_type, kwargs))

print("未传任何参数：")
func()  # 未传任何参数，返回args为空元组，kwargs我空字典
print("只传入可变位置参数：")
func(1, 2, 3)
print("只传入可变关键字参数：")
func(x='a', y='b', z='c')
print("传入可变位置参数和可变关键字参数：")
func(1, 2, 3, x='a', y='b', z='c')
func(1, 2, 3, **{'x': 1, 'y': 2, 'z': 3})  # 使用 **解包

# 结果
'''
未传任何参数：
args: 类型为tuple, 值为()
kwargs: 类型为dict, 值为{}
只传入可变位置参数：
args: 类型为tuple, 值为(1, 2, 3)
kwargs: 类型为dict, 值为{}
只传入可变关键字参数：
args: 类型为tuple, 值为()
kwargs: 类型为dict, 值为{'x': 'a', 'y': 'b', 'z': 'c'}
传入可变位置参数和可变关键字参数：
args: 类型为tuple, 值为(1, 2, 3)
kwargs: 类型为dict, 值为{'x': 'a', 'y': 'b', 'z': 'c'}
args: 类型为tuple, 值为(1, 2, 3)
kwargs: 类型为dict, 值为{'x': 1, 'y': 2, 'z': 3}
'''

# 位置参数，可变位置参数、默认参数、可变关键字参数结合
# 参数定义顺序：位置参数->*args->默认参数->**kwargs
def func(m, n, *args, flag=0, **kwargs):
    """
    :param args:
    :param kwargs:
    :return:
    """
    print("m: %s" % m)
    print("n: %s" % n)
    print("flag: %s" % flag)
    args_type = (str(type(args))).split("'")[1]
    kwargs_type = (str(type(kwargs))).split("'")[1]
    print("args: 类型为{0}, 值为{1}".format(args_type, args))
    print("kwargs: 类型为{0}, 值为{1}".format(kwargs_type, kwargs))


print("只传位置参数：")
func(22, 33)  # 这时默认参数flag=0
print("以关键字参数形式传入位置参数：")
func(m=22, n=33)
print("传入位置参数和可变位置参数：")
func(22, 33, 1, 2, 3)
print("位置参数、可变位置参数、默认参数：")
func(22, 33, 1, 2, 3, flag=666)
print("位置参数、可变位置参数、默认参数和可变关键字参数：")
func(22, 33, 1, 2, 3, flag=666, x='a', y='b', z='c')
print("以**解包形式传入位置参数：")
func(22, 33, 1, 2, 3, flag=666, **{'x': 1, 'y': 2, 'z': 3})

# 结果
'''
只传位置参数：
m: 22
n: 33
flag: 0
args: 类型为tuple, 值为()
kwargs: 类型为dict, 值为{}
以关键字参数形式传入位置参数：
m: 22
n: 33
flag: 0
args: 类型为tuple, 值为()
kwargs: 类型为dict, 值为{}
传入位置参数和可变位置参数：
m: 22
n: 33
flag: 0
args: 类型为tuple, 值为(1, 2, 3)
kwargs: 类型为dict, 值为{}
位置参数、可变位置参数、默认参数：
m: 22
n: 33
flag: 666
args: 类型为tuple, 值为(1, 2, 3)
kwargs: 类型为dict, 值为{}
位置参数、可变位置参数、默认参数和可变关键字参数：
m: 22
n: 33
flag: 666
args: 类型为tuple, 值为(1, 2, 3)
kwargs: 类型为dict, 值为{'x': 'a', 'y': 'b', 'z': 'c'}
以**解包形式传入位置参数：
m: 22
n: 33
flag: 666
args: 类型为tuple, 值为(1, 2, 3)
kwargs: 类型为dict, 值为{'x': 1, 'y': 2, 'z': 3}
'''
```

- 仅限关键字参数：在*号之后的参数只能通过关键字参数传递的叫keyword-only参数。其中，可变位置参数之后的参数也是keyword-only参数

```python
# *号的参数用关键字参数形式传参
def func(*, x):
    """
    :param x:
    :return:
    """
    print(x)

func(x=3)

# 结果
'''
3
'''

# 可变位置参数后的参数，也是仅限关键字参数
def func(*args, x):
    """
    :param args:
    :param x:
    :return:
    """
    args_type = (str(type(args))).split("'")[1]
    print("args: 类型为{0}, 值为{1}".format(args_type, args))
    print("x: %s" % x)

print("---- 只传关键字参数: ----")
func(x=3)
print("---- 传入可变位置参数和关键字参数：----")
func(1,2,3, x=666)

# 结果
'''
---- 只传关键字参数: ----
args: 类型为tuple, 值为()
x: 3
---- 传入可变位置参数和关键字参数：----
args: 类型为tuple, 值为(1, 2, 3)
x: 666
'''

# 可变位置参数、普通参数、默认参数组成仅限关键字参数
def func(*args, x, y=0):
    """
    :param args:
    :param x:
    :param y:
    :return:
    """
    args_type = (str(type(args))).split("'")[1]
    print("args: 类型为{0}, 值为{1}".format(args_type, args))
    print("x: %s" % x)
    print("y: %s" % y)

print("---- 只传关键字参数: ----")
func(x=3)
print("---- 传入可变位置参数和关键字参数：----")
func(1,2,3, x=666)
print("---- 传入可变位置参数、关键字参数和默认参数：----")
func(1,2,3, x=666, y=333)

# 结果
'''---- 只传关键字参数: ----
args: 类型为tuple, 值为()
x: 3
y: 0
---- 传入可变位置参数和关键字参数：----
args: 类型为tuple, 值为(1, 2, 3)
x: 666
y: 0
---- 传入可变位置参数、关键字参数和默认参数：----
args: 类型为tuple, 值为(1, 2, 3)
x: 666
y: 333
'''
```

- 参数解构：参数解构发生在函数调用时，可变参数发生在函数定义的时
  - *解构：解构对象是可迭代对象，结构后的结果为位置参数
  - **解构：解构对象是字典，解构后的结果为关键字参数，这里key必须是str类型，且和函数定义的形参名一致，否则抛出TypeError异常

```python
def add(x, y):
    return x + y

# 位置参数解构
data1 = (1, 2)
print(add(*data1))

# 关键字参数解构
data2 = {'x': 3, 'y': 4}
print(add(**data2))

# 结果
'''
3
7
'''
```

## 46. *args和**kwargs的区别

> *args用来将参数打包成tuple给函数体调用，传递可变位置参数

> **kwargs打包关键字参数成dict给函数体调用，传递可变关键字参数

## 47. 实参和形参的区别

> 实参：调用函数时的参数，赋予的实际数值或者变量，实参和形参都是引用同一个对象

> 形参：定义函数时的参数，是一个新的、本地的变量名，在函数的本地作用域内

## 48. python中函数传参过程

- 值传递

> 值传递实际上就是把实际参数值的副本传入函数，不管函数对该值做了什么操作，而参数本身不会受到任何影响。

```python
def func(a, b):
    a, b = b, a
    print("func里交换处理完a的值为{}，b的值为{}".format(a, b))

if __name__ == '__main__':
    a, b = 3, 4
    print("交换前a的值为{}，b的值为{}".format(a, b))
    func(3, 4)
    print("交换后a的值为{}，b的值为{}".format(a, b))

# 结果
'''
交换前a的值为3，b的值为4
func里交换处理完a的值为4，b的值为3
交换后a的值为3，b的值为4
'''
```

> 通过上面的例子，看出值传递的实质是当系统开始执行函数时，系统对形参执行初始化，就是把实参变量的值赋值给函数的形参变量，在函数中操作的并不是实际的实参变量，而是复制的副本。

- 引用传递

> 果果实际参数的数据类型是可变对象（列表，字典、元组、集合等），则函数传递方式将采用引用传递的方式。**而引用传递方式的低层实现，采用的依然还是值传递的方式。**

```python
# 把字典中的key为a和b所对应的值交换
def func(d):
    d['a'], d['b'] = d['b'], d['a']
    print("func里交换处理a元素的值为{}，b元素的值为{}".format(d['a'], d['b']))

if __name__ == '__main__':
    d = {'a':3, 'b':4}
    print("交换前a元素的值为{}，b元素的值为{}".format(d['a'], d['b']))
    func(d)
    print("交换后a元素的值为{}，b元素的值为{}".format(d['a'], d['b']))

# 结果
'''
交换前a元素的值为3，b元素的值为4
func里交换处理a元素的值为4，b元素的值为3
交换后a元素的值为4，b元素的值为3
'''
```

> 在上面例子中，a元素与b元素的值交换成功，func函数执行完，主程序中字典d的a元素和b元素的值也发生了交换，这很容易造成错觉。实际上，程序开始创建了一个字典对象，并定义了一个d的引用变量（其实就是一个“指针”）指向字典对象，现在内存中有对象本身和指向该对象的引用变量；然后，主程序调用func函数，d变量作为参数传入，把主程序中d变量的值赋给func函数的形参d（这里仍然是值传递），同时把指向这个字典对象的地址值也传进来，他们引用的是同一个字典对象；于是，在func函数中对d这个引用变量进行交换操作时，就等于对这个字典对象进行操作，所以主程序中d变量所引用对象的a元素和b元素的值也被交换。

**总而言之：**

- 不管什么类型的参数，在python函数中对参数直接使用"="等号赋值方式是诶用的，并不能改变参数的值。
- 把这些数据包装成列表、字典等可变对象，然后传参到函数里进行修改，这样数据会发生改变。

## 49. python中可变对象和不可变对象

> 可变对象：list、dict、set、bytearray、array、collections.deque

> 不可变对象：tuple、str、bytes、bool、int、float

**注意：元组是相对不可变的对象， 元组存储的是对象的引用， 当元组中的存在可变对象的引用时， 引用不可变， 但是引用的对象时可变的。**

## 50. python中正则使用方式

> **正则表达式常用的匹配规则**

|  模式   | 描述  |
|  :------:  | :---- |
|    | ***\*\*\*\*一般字符\*\*\*\**** |
|  .  | 匹配除换行符"\n"和"\r"之外的任意字符，在re.S模式下则能匹配任意字符 |
|  \  | 转义字符，使下一个字符标记为或特殊字符、或原义字符、或向后引用、或八进制转义符，如果原始字符串中含有`* . ? + $ ^ [ ] ( ) { } | \`，需要在前面加转义字符\才能正确表示，或者在字符串前面加个r房子转义 |
|  [...]  | 字符集，用来表示一组字符，对应的位置可以是字符集中任意一个字符，字符集中的字符可以逐个列出，也可以给出范围如[abc]或[a-c]，所有的特殊字符在字符集中都失去本原有的含义，需要加\进行转义；常见的字符集[0-9]、[a-z]、[A-Z]、`^[\u4e00-\u9fa5]*$` |
|  [^...]  | 在字符集内的开头加入非，表示匹配不在字符集内的其他任意字符，如[^abc]表示匹配除abc之外的任意字符 |s
|    | ***\*\*\*\*预定义字符集（可以写在字符集[...]中）\*\*\*\**** |
|  \d  | 匹配任意数字，等价于[0-9] |
|  \D  | 匹配任意非数字的字符，等价于[^\d] |
|  \s  | 匹配空白字符，等价于[\t\n\r\f]，如\t(Tab)、\r(回车)、' '(空格)、\f(换页符)、\n(换行符)、\v(垂直制表符) |
|  \S  | 匹配非空白字符，等价于[^\s] |
|  \w  | 匹配字母数字及下划线，等价于[A-Za-z0-9_] |
|  \W  | 匹配非字母数字及下划线的其他字符，等价于[^A-Za-z0-9_] |
|    | ***\*\*\*\*数量词（用在字符或(...)之后）\*\*\*\**** |
|  *  | 匹配前一个字符、子表达式0次或多次，例如`abc*`能匹配ab，也能匹配abc、abcc，\*等价于{0,} |
|  +  | 匹配前一个字符、子表达式1次或多次，例如`abc+`，能匹配abc、abcc，但是不能匹配到ab，+号前的字符至少要匹配一次，+等价于{1,} |
|  ?  | 匹配前一个字符、子表达式0次或1次，例如`do(es)?`可以匹配到do或does，?等价于{0,1} |
|  {n}  | 精确匹配前一个字符、子表达式n次，例如`ab{2}c`可以匹配到abbc，n为非负整数 |
|  {n,}  | 匹配前一个字符、子表达式至少n次(即[n,+∞])，例如`ab{2,}c`可以匹配到abbc或abbbbbbbc，n为非负整数 |
|  {,n}  | 匹配前一个字符、子表达式至多n次(即[0,n])，例如`ab{,2}c`可以匹配到ac、abc或abbc，n为非负整数 |
|  {n,m}  | 匹配前一个字符、子表达式最少匹配n次，最多m次(即[n,m])，例如`ab{1,2}c`可以匹配到abc或abbc，n, m为非负整数，且n<=m |
|  `*?, +?, ??`  | 默认情况下*、+和?的匹配模式是贪婪模式，即会尽可能对的匹配符合规则的字符，*?、+?和??表示启用对应的非贪婪模式。如对于字符串"Pythonnn"，正则表达式Python+能匹配大整个字符串，而Python+?则匹配Python |
|  `{n,m}?`  | 同上，启用非贪婪模式，即只匹配n次，n, m为非负整数，且n<=m |
|    | ***\*\*\*\*边界匹配（不消耗待匹配字符串中的字符）\*\*\*\**** |
|  ^  | 匹配字符串的开头，在多行模式下(re.M)匹配每一行的开头，如^abc可以匹配abc |
|  $  | 匹配字符串的末尾，在多行模式下(re.M)匹配每一行的末尾，如abc$可以匹配abc |
|  \A  | 仅匹配字符串开头，如\Aabc可以匹配abc |
|  \Z  | 仅匹配字符串末尾，如果存在换行，只匹配到换行前的结束字符串，如abc\Z可以匹配abc |
|  \z  | 仅匹配字符串末尾，如果存在换行，同时还会匹配到换行符 |
|  \b  | 匹配单词边界，也就是指单词和空格间的位置，如`er\b`可以匹配到never中的er，但不能匹配到verb中的er |
|  \B  | 匹配非单词边界，也就是指单词和空格间的位置，如`er\B`可以匹配到verb中的er，但不能匹配到never中的er，等价于[^\b] |
|  \G  | 匹配最后匹配完成的位置 |
|    | ***\*\*\*\*逻辑、分组\*\*\*\**** |
|  `|`  | 左右表达式任意匹配一个，类似于"或"。总是先尝试匹配左边的表达式，一旦成功匹配就跳过匹配右边的表达式；如果`|`没有被包括在()中，则它的范围是整个表达式。如`123|456`能匹配到123、456 |
|  (...)  | 匹配圆括号中的正则表达式，或者指定一个子组的开始和结束位置，被括起来的表达式将作为分组，从表达式的左边开始每遇到一个分组的左括号'('，编号+1；另外分组表达式作为一个整体，后面可以接数量词；表达式中的`|`也只能在该组中生效。如`(abc){2}`能匹配到`abcabc`，而`a(123|456)c`能匹配到`a123c、a456c` |
|  `(?P<name>...)`  | 给分组命名，除了愿有你的编号外在指定一个额外的别名，通过分组名字name既可以访问到子组匹配的字串，例如`(?P<id>abc){2}`能够匹配到abcabc |
|  `\<number>`  | 引用序号为`<number>`对应的子组所匹配到的字符串，子组的序号从1开始计算；如果序号以0开头，或者3个数字的长度，那么不会被引用对应的子组，而是用于匹配八进制数字所表示的ASCII码值所对应的字符。例如`(.+) \1`会匹配"python python" 或 "66 66"，但不会匹配holysll" |
|  `(?P=name)`  | 引用别名为`<name>`的分组匹配到的字符串，如`(?P<id>\d)abc(?P=id)`能够匹配到1abc1、5abc5 |
|    | ***\*\*\*\*特殊构造（不作为分组）\*\*\*\**** |
|  `(?:...)`  | (...)的不分组版本，用于使用`|` 或后接数量词。如`(?:abc){2}`能匹配abcabc |
|  `(?aiLmsux)`  | aiLmsux的每个字符代表一种匹配模式，`(?` 后可以紧跟着 'a'，'i'，'L'，'m'，'s'，'u'，'x' 中的一个或多个字符，只能在正则表达式的开头使用，如`(?i)abc`匹配模式是忽略大小写，能够匹配abc、Abc、aBc、abC、ABc、AbC、aBC、ABC |
|  `(?#...)`  | #后的内容将作为主食被忽略，如`abc(?#comment)123`能够匹配abc123 |
|  `(?=...)`  | 之后的字符串内容需要匹配表达式才能匹配成功，不消耗字符创的内容。如`a(?=\d)`能匹配后面全是数字的a |
|  `(?!...)`  | 之后的字符串内容需要不匹配表达式才能匹配成功，不消耗字符创的内容。如`a(?!\d)`能匹配后面不是数字的a |
|  `(?<=...)`  | 之前的字符串内容需要匹配表达式才能匹配成功，不消耗字符创的内容。如`a(?<=\d)`能匹配前面是数字的a |
|  `(?<!...)`  | 之前的字符串内容需要不匹配表达式才能匹配成功，不消耗字符创的内容。如`a(?<!\d)`能匹配后面不是数字的a |
|  `(?(id/name)yes-pattern|no-pattern)`  | 如果序号为id/别名为name的组匹配到字符，则需要尝试yes-patteren匹配规则，否则需要尝试no-pattern匹配规则，no-pattern是可选可省略。如`(<)?(\w+@\w+(?:\.\w+)+)(?(1)>|$)` 是一个邮件格式的正则表达式，可以匹配`<lucy@outlook.com>`和`lucy@outlook.com`，但不会匹配`<lucy@outlook.com`或`lucy@outlook.com>` |

> **正则表达式的匹配模式：**

|  flags   | 描述  |
|  :----:  | :----  |
| re.I(IGNORECASE)  | 忽略大小写，使匹配对大小写不敏感 |
| re.L(LOCALE)  | 做本地化识别（locale-aware）匹配 |
| re.M(MULTILINE)  | 多行匹配模式，影响^ 和 $ |
| re.S(DOTALL)  | 使 . 匹配包括换行在内的所有任意字符 |
| re.U  | 根据Unicode字符集解析字符，这个标志影响\w、\W、\b、\B、\d、\D、\s、\S |
| re.X(VERBOSE)  | 该标志通过给予更灵活的格式以便将正则表达式更易于理解，详细表达式 |
| re.A  | 只匹配ASCII字符 |

> **re分组匹配对象的方法：**

|  方法   | 描述  |
|  :----:  | :----  |
| group([group1, ...])  | 用于获得一个或者多个分组匹配的字符串，当要获得整个匹配的子串时，使用group()或group(0)；groups()等价于(group(1), group(2), ...) |
| start([group])  | 用于获取分组匹配的子串在整个字符串的起始位置（子串第一个字符的索引），参数值默认为0 |
| end([group])  | 用于获取分组匹配的子串在整个字符串的结束位置（子串最后一个字符的索引+1），参数值默认为0 |
| span([group])  | 返回(start(group), end(group))；span(0) 返回匹配成功的整个子串的索引；span(1) 返回第一个分组匹配成功的子串的索引 |

> **re模块中一些重要的函数：**

- search：扫描整个字符串并返回第一个成功的匹配，匹配成功返回一个匹配的对象，否则返回None。

> search()函数语法：`re.search(pattern, string[, flags])` 其中，参数pattern是匹配的正则表达式；参数string是需要匹配的字符串；参数flags是标志位，用于控制正则表达式的匹配模式。

```python
import re

res = re.search(r'www\.(.*)\.(.{3})', 'www.baidu.com', re.I)  # 忽略大小写

if res:
    print(res.groups())  # 从分组1算起

    print("分组0：")
    print(res.group())
    print(res.group(0))

    print("分组1：")
    print(res.group(1))
    print(res.start(1))
    print(res.end(1))
    print(res.span(1))

    print("分组2：")
    print(res.group(2))
    print(res.start(2))
    print(res.end(2))
    print(res.span(2))

# 结果
'''
('baidu', 'com')
分组0：
www.baidu.com
www.baidu.com
分组1：
baidu
4
9
(4, 9)
分组2：
com
10
13
(10, 13)
'''
```

- match：尝试从字符串的起始位置匹配一个模式，如果不是起始位置匹配成功的话，match()就返回none。

> match()函数语法：`re.match(pattern, string[, flags])`其中，参数pattern是匹配的正则表达式；参数string是需要匹配的字符串；参数flags是标志位，用于控制正则表达式的匹配模式。

```python
import re

res = re.search(r'baidu', 'www.baidu.com', re.I)
if res:
    print("search匹配成功")
    print(res.group())
else:
    print("search匹配失败")

rem = re.match(r'baidu', 'www.baidu.com', re.I)
if rem:
    print("match匹配成功")
    print(rem.group())
else:
    print("match匹配失败")

# 结果
'''
search匹配成功
baidu
match匹配失败
'''
```

- compile：用于编译正则表达式，生成一个正则表达式(pattern)对象，供match()和search()这两个函数使用。

> compile()函数语法：`re.compile(pattern[, flags])`其中，参数pattern是匹配的正则表达式；可选参数flags是匹配模式，用于控制正则表达式的匹配模式。

```python
import re

pattern = re.compile(r'\w+', re.I)
res = pattern.search('www.baidu.com')
if res:
    print("compile search匹配成功")
    print(res.group(0))
    print(res.start(0))
    print(res.end(0))
    print(res.span(0))
else:
    print("compile search匹配失败")

rem = pattern.match('www.baidu.com', 4, 8)
if rem:
    print("compile match匹配成功")
    print(rem.group(0))
    print(rem.start(0))
    print(rem.end(0))
    print(rem.span(0))
else:
    print("compile match匹配失败")

# 结果
'''
compile search匹配成功
www
0
3
(0, 3)
compile match匹配成功
baidu
4
9
(4, 9)
'''
```

- findall：在字符串中找到正则表达式所匹配的所有子串，并返回一个列表，如果没有找到匹配的，则返回空列表。match 和 search 是匹配一次 findall 匹配所有。

> findall()函数语法：`re.findall(pattern, string[, flags])`其中，参数pattern是匹配的正则表达式；参数string是需要匹配的字符串；参数flags是标志位，用于控制正则表达式的匹配模式。

```python
import re

res = re.findall(r'\w+', 'Hello World!', re.I)
print(res)  # 返回的是一个列表

# 结果
'''
['Hello', 'World']
'''

# 通过compile编译正则表达式
pattern = re.compile(r'\w+', re.I)
rec = re.findall(pattern, 'Hello World!')
print(rec)

# 结果
'''
['Hello', 'World']
'''
```

- sub：将字符串中与模式pattern匹配的子串都替换为repl。

> sub()函数语法：`re.sub(pattern, repl, string[, count=0, flags])`其中，参数pattern是匹配的正则表达式；参数repl是替换的字符串，也可以是一个函数；参数string是需要匹配的字符串；可选参数count是模式匹配后替换的最大次数，默认0表示替换所有的匹配项；可选参数flags是标志位，用于控制正则表达式的匹配模式。

```python
import re

res0 = re.sub(r'\D', '', 'abc123#￥@', 0, re.I)  # 把非数字部分删除
res1 = re.sub(r'\D', '', 'abc123#￥@', 1, re.I)
res2 = re.sub(r'\D', '', 'abc123#￥@', 3, re.I)
print(res0)
print(res1)
print(res2)

# 结果
'''
123
bc123#￥@
123#￥@
'''

# 通过compile编译正则表达式
pattern = re.compile(r'\D', re.I)
res = re.sub(pattern, '', 'abc123#￥@', 0)  # 这时，不能传入flags匹配模式，而要在compile里传入
print(res)
# 结果
'''
123
'''

# repl是一个函数时，将匹配到的数字乘以2
def double(num):
    print(num.group('value'))
    value = int(num.group('value'))
    return str(value * 2)

result = re.sub(r'(?P<value>\d+)', double, 'a1B23C456d7890')
print(result)

# 结果
'''
1
23
456
7890
a2B46C912d15780
'''
```

- split：按照能够匹配的子串将字符串分割后返回列表。

> split()函数语法：`re.split(pattern, string[, maxsplit=0, flags=0])`其中，参数pattern是匹配的正则表达式；参数string是需要匹配的字符串；可选参数maxsplit是分割次数，默认为0表示不限制次数；可选参数flags是标志位，用于控制正则表达式的匹配模式。

```python
import re

res1 = re.split('\W+', 'www.baidu.com')
res2 = re.split('(\W+)', 'www.baidu.com')
res3 = re.split('\W+', 'www.baidu.com', 1)  # 分割一次
res4 = re.split('p*', 'www.baidu.com')  # 匹配不到的正则表达式
print(res1)
print(res2)
print(res3)
print(res4)

# 结果
'''
['www', 'baidu', 'com']
['www', '.', 'baidu', '.', 'com']
['www', 'baidu.com']
['', 'h', 'e', 'l', 'l', 'o', ' ', 'w', 'o', 'r', 'l', 'd', '']
'''
```

- escape：将字符串中所有的特殊字正则表达式字符转义，当大量主要加反斜杠\进行转义时，这个函数很有用，避免一些不必要的错误，实际上功能有点类似正则表达式前面加r。

> escape()函数语法：`re.escape(pattern)`

```python
import re

res = re.escape('www.python.org')
print(res)

result = re.findall(re.escape('.py'), "python www.python.org proxy.py")
print(result)

# 结果
'''
www\.python\.org
['.py', '.py']
'''
```

> 手写正则邮箱地址：

```python
import re

email_addr = 'Please reply this email to <abc23@sample.com.cn>'
# tool.chinaz.com给出的是：\w[-\w.+]*@([A-Za-z0-9][-A-Za-z0-9]+\.)+[A-Za-z]{2,14}
pattern = re.compile(r'([\w\.-]+)@([\w\.-]+)(\.[\w\.]+)')
res = re.search(pattern, email_addr)
if res:
    print(res.group)
else:
    print("匹配失败")

# 结果
'''
abc23@sample.com.cn
'''
```

**[常用正则表达式](http://tool.chinaz.com/regex)**

|   目标  | 表达式  |
|  :----:  |  :----  |
|   中文字符  | `[\u4e00-\u9fa5]`  |
|   双字节字符(包括汉字在内)  | `[^\x00-\xff]`  |
|   空白行  | `\n\s*\r`  |
|   Email地址  | `\w[-\w.+]*@([A-Za-z0-9][-A-Za-z0-9]+\.)+[A-Za-z]{2,14}`  |
|   网址URL  | `[a-zA-z]+://[^\s]*` 或 `^((https|http|ftp|rtsp|mms)?:\/\/)[^\s]+` |
|   国内电话号码  | `[0-9-()（）]{7,18}`  |
|   国内手机号码  | `0?(13|14|15|17|18|19)[0-9]{9}`  |
|   QQ号码  | `[1-9]([0-9]{5,11})`  |
|   邮政编码  | `\d{6}`  |
|   身份证号  | `^(\d{6})(\d{4})(\d{2})(\d{2})(\d{3})([0-9]|X)$`  |
|   日期格式  | `\d{4}(\-|\/|.)\d{1,2}\1\d{1,2}`  |
|   IP地址  | `(25[0-5]|2[0-4]\d|[0-1]\d{2}|[1-9]?\d)\.(25[0-5]|2[0-4]\d|[0-1]\d{2}|[1-9]?\d)\.(25[0-5]|2[0-4]\d|[0-1]\d{2}|[1-9]?\d)\.(25[0-5]|2[0-4]\d|[0-1]\d{2}|[1-9]?\d)`  |
|   整数  | `-?[1-9]\d*`  |
|   正整数  | `[1-9]\d*`  |
|   负整数  | `-[1-9]\d*`  |
|   正浮点数  | `[1-9]\d*.\d*|0.\d*[1-9]\d*`  |
|   负浮点数  | `-([1-9]\d*.\d*|0.\d*[1-9]\d*)`  |
|   用户名(字母、数字、下划线、-、以及中文)  | `[A-Za-z0-9_\-\u4e00-\u9fa5]+`  |

## 51. Numpy、Scipy、Panadas的区别

> Numpy是数值计算的扩展包，能够高效处理N为数组、复杂函数、线性代数。Numpy专门针对ndarray的操作和运算进行了设计，所以数据的存储效率和输入输出性能远优于Python中的嵌套列表，当数组越大时，Numpy的优势越明显，因此用来存储和处理大型矩阵比嵌套列表结构高效的多，可以说是一种免费而强大的Matlab系统。

**[Numpy库里有哪些函数](https://blog.csdn.net/holysll/article/details/89350260)**

> Scipy是专门用于科学计算的一个常用库，可以插值运算、优化算法、图像处理、常微分方程数值解的求解、信号处理、稀疏矩阵和数学统计等等。Scipy是基于Numpy，并且封装了一些高阶抽象和物理模型，是Numpy和Scipy协同工作，高效解决问题。

**[Python机器学习及分析工具：Scipy篇](https://www.jianshu.com/p/6c742912047f)**

> Pandas是基于Numpy的一种工具，提供了一套名为DataFrame的数据结构，适合统计分析中的表结构，在上层做数据分析，所以也称为表格容器。Pandas 所包含的数据结构和数据处理工具的设计，使得数据清洗和分析非常快捷，并经常和其他Numpy、Scipy数值计算工具、数据可视化工具Matplotlib结合起来使用，其中大量库和一些标准的数据模型、函数和方法，支持着大型数据集的高效处理。

**[Pandas库中的函数](https://blog.csdn.net/holysll/article/details/89396976)**

## 52. python中反射机制

**[Python的反射机制](https://www.jianshu.com/p/8e62449c936c)**

> 反射的核心本质其实就是通过字符串的形式导入模块，通过字符串的形式，去模块中找指定函数，并执行。利用字符串的形式去对象（模块）中操作（增删改查）成员，是一种基于字符串的事件驱动。实现思路：规定用户输入格式 模块名/函数名 通过__import__的形式导入模块，并通过 hasattr和getattr 检查并获取函数返回值。

|  方法  |  描述  |
|  :----:  |  :----  |
|  getattr  |  根据字符串形式去某个模块中寻找东西  |
|  hasattr  |  根据字符串形式去某个模块中判断东西是否存在  |
|  setattr  |  根据字符串形式去某个模块中设置东西  |
|  delattr  |  根据字符串形式去某个模块中删除东西  |

- 实例1：

```python
def f1():
    print("f1是这个函数的名字！")

s = "f1"
print("%s是个字符串" % s)
```

> 在上面代码中，f1是函数f1()的函数名，"f1"是字符串，两者有本质的区别。可以通过f1()的方式调用函数f1，但是不能"f1"()方式去调用函数f1()，实际上就是不能通过字符串来调用名字看起来相同的函数。

> 利用python反射机制简单实现"f1"调用函数f1()：

```python
# test.py
def f1():
    print("f1是这个函数的名字！")
```

```python
# 通过用户输入形式，以字符串形式导入模块
module_name = input("请输入需要导入的模块名：")
# __import__用于以字符串形式导入模块
module = __import__(module_name)
# 在模块寻找的函数名
func = input("请输入需要自行的函数：")
# 判断函数该模块中是否有这个函数
if hasattr(module, func):
    target_func = getattr(module, func)
    target_func()
else:
    print("{}模块中没有{}函数.".format(module_name, func))

# 结果
'''
请输入需要导入的模块名：test
请输入需要自行的函数：f1
f1是这个函数的名字！
'''
# 这样就实现了通过输入字符串f1，调用test.py的里的f1()
```

- 实例2：基于反射模拟Web框架路由系统

```python
# views.py 视图模块
def login():
    print("这是一个登陆页面！")

def logout():
    print("这是一个退出页面！")

def home():
    print("这是网站主页面！")
```

```python
# 根据输入网址url访问相应的页面

def run():
    url = input("请输入想要访问页面的url：").strip()
    module_name, func_name = url.split("/")
    module = __import__("lib." + module_name, fromlist=True)  # 如果和模块不在同一级目录下面，则需要在前面加目录
    if hasattr(module, func_name):
        func = getattr(module, func_name)
        func()
    else:
        print("404")

if __name__ == "__main__":
    run()

# 输入views/login
'''
请输入想要访问页面的url：views/login
这是一个登陆页面！
'''
# 输入views/logout
'''
请输入想要访问页面的url：views/logout
这是一个退出页面！
'''
# 输入views/home
'''
请输入想要访问页面的url：views/home
这是网站主页面！
'''
# 输入views/find
'''
请输入想要访问页面的url：views/find
404
'''
```

## 53. python中如何管理依赖

> Anaconda是包管理和环境管理器，可以帮助用户很方便的管理大量的第三方架包，但是不一定适合所有项目，在加上很多项目部署在linux服务器上，所以就需要对项目依赖进行独立管理。

- 配置pip镜像源

```bash
# window系统，在C:\Users\用户名\pip\pip.ini（没有pip文件夹就新建）
[global]
index-url = https://mirrors.aliyun.com/pypi/simple/

# linux系统，vi ~/.pip/pip.conf
[global]
index-url = https://mirrors.aliyun.com/pypi/simple/
```

- 每个项目创建独立的虚拟环境

```bash
# 第一种：安装virtualenv
pip install virtualenv
# 检查virtualenv是否安装成功
virtualenv --version
# 如果提示-bash: virtualenv: command not found则
find / -name virtualenv  # 全局查找virtualenv
ln -s /usr/local/python3/bin/virtualenv /usr/bin/virtualenv  # 添加软链接
# 创建独立干净的项目虚拟环境
virtualenv --no-site-packages project1
# 启动虚拟环境
source project1/bin/activate
workon project1  # 这种方式也能启动虚拟环境
# 退出虚拟环境
deactivate
# 删除虚拟环境
rmvirtualenv project1


# 第二种：安装virtualenvwrapper
pip install virtualenvwrapper

# 配置环境变量
vi ~/.bashrc 或者 vi ~/.bash_profile
# 添加配置信息
export WORKON_HOME=$HOME/.virtualenvs
export PROJECT_HOME=$HOME/workspace  # 添加项目路径，这样切换到虚拟环境时就会自动切换到项目根目录下
source /usr/local/bin/virtualenvwrapper.sh

# 保存退出后，刷新修改的配置
source ~/.bashrc

# 创建虚拟环境
mkvirtualenv -p python3 project1  # 表示Python的项目
# 查看所有虚拟环境
workon Tab Tab
# 切换、进入虚拟环境
workon project1
# 退出虚环境
deactivate
# 删除虚拟环境
rmvirtualenv project1
```

- 导出项目依赖，锁定版本，迁移

```bash
# 导出项目依赖
pip freeze > requirements.txt
# 安装依赖
pip install -r requirements.txt
```

## 54. 如何分析python代码性能

**[python程序代码性能分析和计时统计](https://blog.csdn.net/lhh08hasee/article/details/80032193)**

> 以下方法分别针对代码块、代码程序文件、 函数进行性能计时统计:

- time.time()或者datetime.datetime.now()

```python
# 结束时间-开始时间
import time
import datetime
start = time.time()  # 或者datetime.datetime.now()
func()  # 需要统计运行时长的函数
end = time.time()
print(end - start)
```

- time.clock()

```python
"""
clock() 函数以浮点数计算的秒数返回当前的CPU时间，用来衡量不用程序的耗时，比time.time更有用。在win系统下，这个函数返回的是真实时间(wall time)，而在Unix/Linux下返回的是CPU 时间。
"""

# test.py
import time

start = time.clock()
func()  # 需要统计运行时长的函数
end = time.time()
print(end - start)
```

- time

```bash
# 在linux下对整个程序做计时统计

/usr/bin/time -p python test.py

# 输入内容
# real 0m2.057s  记录了整体的耗时
# user 0m0.033s  记录了CPU花在任务上的时间，但不保罗内核函数花费的时间
# sys 0m0.011s  记录了内核函数花费的时间
# user + sys  即是cpu总共花费的时间
# real - (user + sys)  得到可能是花费在等待IO的时间

# 打开–verbose开关来获得更多输出信息
/usr/bin/time --verbose python test.py
```

- cProfile：分析分析cpu使用情况

> cProfile：基于lsprof的用C语言实现的扩展应用，运行开销比较合理，适合分析运行时间较长的程序，推荐使用这个模块。

```python
# 命令生成统计文件
python -m cProfile test.py  # 直接输出统计结果

# 上面这条命令等价于
import cProfile
import re
cProfile.run('re.compile("test")')
```

```python
# 命令生成统计文件(二进制数据文件)
python -m cProfile -o stats test.py

# 上面这条命令等价于
import cProfile
import re
cProfile.run('re.compile("test")', 'stats', 'cumtime')

# 然后，通过python分析生成的统计文件
import pstats

p = pstats.Stats("stats")
p.print_stats()

# 结果
'''
Hello World
         5 function calls in 2.001 seconds

   Ordered by: standard name

   ncalls  tottime  percall  cumtime  percall filename:lineno(function)
        1    0.000    0.000    2.001    2.001 test.py:10(<module>)
        1    0.000    0.000    2.001    2.001 {built-in method builtins.exec}
        1    0.000    0.000    0.000    0.000 {built-in method builtins.print}
        1    2.001    2.001    2.001    2.001 {built-in method time.sleep}
        1    0.000    0.000    0.000    0.000 {method 'disable' of '_lsprof.Profiler' objects}
'''
```

> 统计表中各参数含义：

|  参数  |  描述  |
|  :----:  |  :----  |
|  ncalls  |  表示函数调用的次数  |
|  tottime  |  表示指定函数的总的运行时间，除掉函数中调用子函数的运行时间  |
|  percall  |  第一个percall）等于 tottime/ncalls  |
|  cumtime  |  表示该函数及其所有子函数的调用运行的时间，即函数开始调用到返回的时间  |
|  percall  |  （第二个percall）即函数运行一次的平均时间，等于 cumtime/ncalls  |
|  filename:lineno(function)  |  表示每个函数调用的具体信息  |

**[cProfile更多用法参考](https://blog.csdn.net/weixin_40304570/article/details/79459811)**

- timeit

```python
# 计算小段代码的执行时间的模块
from timeit import timeit

print(timeit('math.sqrt(2)', 'import math', number=100000))  # 执行10万次2的开方

# 结果
'''
0.023690600000000006
'''
```

- 装饰器

```python
# 将给需要计时的函数加上装饰器@time_count
from functools import wraps
import time

def time_count(func):
    @wraps(func)
    def wrapper(*args, **kwargs):
        start = time.perf_counter()  # 使用time.perf_counter() 能够提供给定平台上精度最高的计时器
        res = func(*args, **kwargs)
        end = time.perf_counter()
        print('{}.{} : {}'.format(func.__module__, func.__name__, end - start))
        return res
    return wrapper

@time_count
def time_sleep():
    time.sleep(2)
    print("休眠两秒")


if __name__ == '__main__':
    time_sleep()

# 结果
'''
休眠两秒
__main__.time_sleep : 1.9995934
'''
```

- line_profile

> 用cProfile找到需要分析的函数，然后用line_profiler对函数逐行进行性能分析。

```bash
# 安装 line_profile
pip install line_profiler

# 运行kernprof 逐行分析被修饰函数的CPU开销
kernprof.py -l -v test.py  # -v 显示输出；-l 代表逐行分析而不是逐函数分析

# 结果中各参数的含义
'''
Total Time：测试代码的总运行时间
Hits：表示每行代码运行的次数
Time：每行代码运行的总时间
Per Hits：每行代码运行一次的时间
% Time：每行代码运行时间的百分比
'''
```

- memory_profiler：分析内存使用情况

```bash
# 安装memory_profiler和依赖
pip install psutil
pip install memory_profiler

# 命令分析内存使用情况
python -m memory_profiler test.py
```

## 55. 列表的顺序访问和随机访问

> **顺序访问：**链表在内存中不是按顺序存储的，而是通过指针连在一起，为了访问某一元素，必须从链头还是顺着指针才能找到某一个元素。

> **随机访问：**数组在内存中是按顺序存储的，访问数组中的任意元素可以直接通过下标计算得到元素存放的位置，访问耗时与元素在数组中所处的位置无关。

## 56. 随机函数

> `random.random()`用于生成一个0到1的随机浮点数: 0 <= n < 1.0 。

> `random.uniform(a, b)`，用于生成一个指定范围内的随机浮点数，两个参数其中一个是上限，一个是下限。如果a > b，则生成的随机数n: a <= n <= b。如果 a < b， 则 b <= n <= a 。

> `random.randint(a, b)`，用于生成一个指定范围内的整数。其中参数a是下限，参数b是上限，生成的随机数n: a <= n <= b。

> `random.randrange([start], stop[, step])`，从指定范围内，按指定基数递增的集合中获取一个随机数。如`random.randrange(10, 10, 2)`，结果相当于从`[10, 12, 14, 16, ..., 96, 98]`序列中获取一个随机数。

> `random.choice(sequence)`从序列中获取一个随机元素，参数sequence表示一个有序类型，list、tuple、字符串等。如`random.choice(["Python", "C++", "java"])`，随机在列表中选取一个元素。

> `random.shuffle(x[, random])`，用于将一个列表中的元素打乱。如`random.shuffle(["Python", "C++", "java"])`，每次结果是随机排序的。

> `random.sample(sequence, k)`，从指定序列中随机获取指定长度的片断，sample函数不会修改原有序列。如`random.sample([1, 2, 3, 4, 5, 6, 7, 8, 9, 10], 2)`，结果是从列表10个数字中随机选两个元素。

## 57. Python中单下划线和双下划线

- 单下划线开头

> 一种约定，一般来说，_object被看作“私有的”，在模块或类外不可以使用，不能用from module import *导入，当变量是私有的时候，用_object来表示变量是很好的习惯。

- 双下划线开头

> 双下划线开头，__object表示私有成员，只有类对象自己能访问，连子类对象也不能访问到这个数据。

**python中的私有不是真正意义上的private，可以通过`对象._类名__object`机制访问private.**

- 双下划线开头和结尾

> "__object__"指的是python中的一些特殊方法，前后双下划线是专用标识，它们是python的魔法函数，编程是不要用这种方式命名自己的变量和函数。

|  方法  |  描述  |
|  :----:  |  :----  |
|  `__str__`  |  将对象转换成字符串时会执行  |
|  `__init__`  |  初始化方法，为对象变量赋值  |
|  `__new__`  |  构造方法，创建一个对象  |
|  `__call__`  |  在对象后面加括号会执行该方法  |
|  `__getattr__`  |  当使用对象.属性时，若属性存在会调用该方法  |
|  `__setattr__`  |  当使用对象.属性 = value时，会调用该方法  |
|  `__iter__`  |  类内部定义了该方法，对象就变成了可迭代对象  |
|  `__add__`  |  当两个对象使用+号时，会调用该方法  |
|  `__enter__` 和 `__exit__`  |  上下文管理  |

## 58. Python的作用域以及Python搜索变量的顺序

> Python作用域简单说就是一个变量的命名空间。代码中变量被赋值的位置，就决定了哪些范围的对象可以访问这个变量，这个范围就是变量的作用域。
在Python中，只有模块（module），类（class）以及函数（def、lambda）才会引入新的作用域。
Python的变量名解析机制也称为 LEGB 法则：本地作用域（Local）→当前作用域被嵌入的本地作用域（Enclosing locals）→全局/模块作用域（Global）→内置作用域（Built-in）

## 59. 编码与解码

- 基本概念：
 
> 比特 / bit：计算机中最小的数据单位，是单个的二进制数值 0 或 1

> 字节 / byte：计算机存储数据的单元，1 个字节由 8 个比特组成

> 字符：人类能够识别的符号

> 编码：将人类可识别的字符转换为机器可识别的字节码 / 字节序列

> 解码：将机器可识别的字节码 / 字节序列转换为人类可识别的字符

- 编码格式

> Python2 的默认编码是ASCII，不能识别中文字符，需要显示指定字符编码。

> Python3 的默认编码是Unicode，可以识别中文。

> 计算机内存的数据，统一使用Unicode编码；数据传输或保存在硬盘上，是哟还能UTF-8编码。

- 编码和解码
  - 编码(encode)：将Unicode字符串转换为特定编码格式对应的字节码的过程。

  ```python
  s = "学习python"
  print(s.encode())  # encode()函数里参数默认为utf-8
  print(s.encode('gbk'))
  
  # 结果
  '''
  b'\xe5\xad\xa6\xe4\xb9\xa0python'
  b'\xd1\xa7\xcf\xb0python'
  '''
  ```

  - 解码(decode)：将特定编码格式的字节码转换为对应的Unicode字符串的过程。

  ```python
  # encode和decode的编码格式必须一致，如gbk编码，必须用gbk解码
  s1 = b'\xe5\xad\xa6\xe4\xb9\xa0python'
  s2 = b'\xd1\xa7\xcf\xb0python'
  print(s1.decode())  # 用默认的utf-8解码
  print(s2.decode('gbk'))  # 用gbk解码

  # 结果
  '''
  学习python
  学习python
  '''
  ```

- 编码表和适用性

|  编码  |  适用性  |  大小  |  特点  |
|  :----:  |  :----  |  :----:  |  :----  |
|  ASCII码  |  数字、英文字母、特殊字符  |  8bit = 1byte  |  特点编号从0到127，占用空间小  |
|  GB2312码/GBK码  |  支持中文  |  16bit = 2byte  |  GBK码是GB2312码的升级，也支持日文、韩文等  |
|  Unicode码  |  支持国际语言  |  32bit = 4byte  |  占用空间大，适用性强，在ASCII码前面补8个就成了Unicode码  |
|  UTF-8  |  支持国际语言  |  英文：8bit = 1byte  中文：24bit =  3byte  欧洲文字：16bit = 2byte  |  是Unicode的升级，是可变长度的Unicode，两者可以非常容易地互相转换，占用空间小  |

## 60. 字符串格式化

- %格式化: C 语言风格的 sprintf 形式, 用%占位

```python
# %o 八进制输出
print("八进制：%o" % 222)

#  %d 十进制整数输出
print("整数：%d, %d, %d" % (1, 22.33, 0.25))

# %x 十六进制输出
print("十六进制：%x" % 12)

# 浮点数保留两位小数
print("浮点数保留两位小数：%.2f" % 3.1415926)

# 万能格式 %r，把任何类型(str、int、float、list、tuple、set、dict)数据转化为字符串类型
print("%r, %r, %r, %r, %r, %r, %r" % ("abc", 25, 3.1415926, [1, 2, 3], (1, 2, 3), {1, 2, 3}, {'a': 1, 'b': 2, 'c': 3}))

# %s 控制输出字符串的长度
print("%.3s" % ("abcdefg"))
print("%.*s" % (4, "abcdefg"))

# 结果
'''
八进制：336
整数：1, 22, 0
十六进制：c
浮点数保留两位小数：3.14
'abc', 25, 3.1415926, [1, 2, 3], (1, 2, 3), {1, 2, 3}, {'a': 1, 'b': 2, 'c': 3}
abc
abcd
'''
```

```python
# 无法同时传递一个变量和元组
'This is %s' % name
# 当name=(1, 2, 3)时
'This is %s' % (name,)  # 提供一个单元素的元组，而不是一个参数，逗号必须加
```

- str.format()格式化：函数把字符串单层一个模版，通过传入的参数进行格式化，用{}占位

```python
# 匹配位置{}
print('This is {}{}'.format("Python", "!"))

# 匹配位置带编号{i}，i从0按位置递增，位置可以多次使用
print('This is {0}{1} {0} is esay{1}'.format("Python", "!"))

# 关键字传参
print('This is {name}{symbol}'.format(name="Python", symbol="!"))

# 字典传参
print('This is {name}{symbol}'.format(**{"name": "Python", "symbol": "!"}))

# 整数格式化
print("整数：{:d}".format(123))

# 浮点数格式化
print("浮点数保留两位小数：{:.2f}".format(3.1415926))

# 字符串格式化
print("字符串：{:s}".format("abcdefg"))

# 八进制格式化
print("八进制：{:o}".format(222))

# 十六进制格式化
print("十六进制：{:x}".format(12))

# 结合编号的数值格式化
print("编号组合数值格式化：{0:d}, {1:s}".format(123, "abcdefg"))

# 关键字结合数值格式化
print("关键字结合数值格式化：{num:d}, {string:s}".format(num = 123, string = "abcdefg"))

# 百分数精度
print("百分数：{:.2%}".format(3/7))

# 金钱的千分隔符
print("金钱分隔符：{:,}".format(123456789))

# 输出大括号
print("输出大括号：{}为{{1, 2, 3}}".format("集合"))

# 结果
'''
This is Python!
This is Python! Python is esay!
This is Python!
This is Python!
整数：123
浮点数保留两位小数：3.14
字符串：abcdefg
八进制：336
十六进制：c
编号组合数值格式化：123, abcdefg
关键字结合数值格式化：123, abcdefg
百分数：42.86%
金钱分隔符：123,456,789
输出大括号：集合为{1, 2, 3}
'''
```

- f-string格式化：Python 3.6 新加入的方法，风格简洁、易读、速度快

```python
# 字符串格式化
name, age = "lucy", 20
print(f"she is {name}, {age} years old.")

# 字典格式化
info = {'name': "lucy", 'age': 20}
print(f"she is {info['name']}, {info['age']} years old.")

# 浮点数精度限制
print(f"she is {name}, {age: .2f} years old.")

# 指定宽度，为了多行输出时整齐（:< 8左对齐，:> 8右对齐）
print(f"she is {name:<10}, {age:<3} years old.")
name1, age1 = "Liming", 3
print(f"she is {name1:<10}, {age1:<3} years old.")
name2, age2 = "Lee", 101
print(f"she is {name2:<10}, {age2:<3} years old.")

# 整数格式化
print(f"整数：{123:d}")

# 浮点数格式化
print(f"浮点数保留两位小数：{3.1415926:.2f}")

# 字符串格式化
print(f"字符串：{'abcdefg':s}")

# 八进制格式化
print(f"八进制：{222:o}")

# 十六进制格式化
print(f"十六进制：{12:x}")

# 百分数精度
print(f"百分数：{(3/7):.2%}")

# 金钱的千分隔符
print(f"金钱分隔符：{123456789:,}")

# 结果
'''
she is lucy, 20 years old.
she is lucy, 20 years old.
she is lucy,  20.00 years old.
she is lucy      , 20  years old.
she is Liming    , 3   years old.
she is Lee       , 101 years old.
整数：123
浮点数保留两位小数：3.14
字符串：abcdefg
八进制：336
十六进制：c
百分数：42.86%
金钱分隔符：123,456,789
'''
```

> 相对于%，format()的优点：

- (1).在%方法中%s只能替代字符串类型，而.format()方法不用考虑数据类型问题；
- (2).单个参数可以多次输出，参数顺序可以不相同；
- (3).填充方式十分灵活，对齐方式十分强大；
- (4).可以使用列表、元组格式化，可以使用字典格式化(传入用**解构)；

```python
# 几种格式化方法性能比较，性能最好的是f-string
import timeit

def add():
    status = 200
    body = 'hello world'
    return 'Status: ' + str(status) + '\r\n' + body + '\r\n'

# % 格式化
def precent_style():
    status = 200
    body = 'hello world'
    return 'Status: %s\r\n%s\r\n' % (status, body)

# str.format()
def format_style1():
    status = 200
    body = 'hello world'
    return 'Status: {}\r\n{}\r\n'.format(status, body)

# str.format(**dict)字典形式传参
def format_style2():
    status = 200
    body = 'hello world'
    return 'Status: {status}\r\n{body}\r\n'.format(status=status, body=body)

# f-string格式
def f_string():
    status = 200
    body = 'hello world'
    return f'Status: {status}\r\n{body}\r\n'

# 计算时间
print('add: '+ str(min(timeit.repeat(lambda: add()))))
print('precent_style: '+ str(min(timeit.repeat(lambda: precent_style()))))
print('format_style1: '+ str(min(timeit.repeat(lambda: format_style1()))))
print('format_style2: '+ str(min(timeit.repeat(lambda: format_style2()))))
print('f_string: '+ str(min(timeit.repeat(lambda: f_string()))))

# 结果
'''
add: 1.0201557999999995
precent_style: 0.7589769999999998
format_style1: 1.2661715999999998
format_style2: 1.2782307000000017
f_string: 0.5236783999999979
'''
```

## 61. 增量赋值

- `+=`操作首先会尝试调用对象的`__iadd__`方法，如果没有该方法，那么尝试调用`__add__`方法，所以 `+=` 与 `+`的区别实质是`__iadd__`和`__add__`的区别。
  - `__add__`方法接收两个参数，返回它们的和，两个参数的值均不会改变。
  - `__iadd__`方法同样接收两个参数，但它是属于in-place操作，即会改变第一个参数的值，所以`__iadd__`方法的对象只能是可变对象，如list对象提供了`__iadd__`方法，而int对象是没有。

- `*=`操作首先会尝试调用对象的`__imul__`方法，如果没有该方法，那么尝试调用`__mul__`方法，所以 `*=` 与 `*`的区别实质是`__imul__`和`__mul__`的区别。

> 对不可变序列进行重复拼接操作，效率会很低，因为每次都要新建一个序列，然后把原序列中的元素复制到新的序列里面，然后再追加新的元素。

> 不要把可变对象放在元组里。

> 增量赋值不是一个原子操作，出现异常时，仍然进行了操作。

## 62. exec对字符串执行和eval对字符串求值

- exec

> exec函数主要用于动态地执行代码字符串，exec 返回值永远为 None。exec()不仅可以执行python代码，还可以共享上下文，但需要注意尽量不要在全局作用域下用exec()函数执行python代码，以免发生命名空间冲突。

> 为了解决这个问题，可以在执行之前创建一个空字典`scope = {}`，作为exec()函数的第二个参数，这样通过exec执行python代码时创建的变量就会存储在字典scope中。

> 如果exec()函数执行的python代码中含有参数，且要传参，则可以在exec()中 以字典形式进行传参，这时exec就有了第三个参数args。当说要执行的代码是多行时，可以用""" """引起来.

```python
args = {'x': 1, 'y': 2}
scope = {}
print(exec('print(x + y)', scope, args))
print(scope.keys())

# 结果
'''
3
dict_keys(['__builtins__'])
'''
```

- eval

> eval()函数来执行一个字符串表达式，实现一个可以计算表达式的计算器，并返回表达式的值。

> eval()函数的语法：`eval(expression[, globals[, locals]])`，expression是表达式；globals是变量作用域，全局命名空间，如果被提供，这必须是一个字典对象；locals是变量作用域，局部变量命名空间，如果被提供，可以是任何映射对象。

> python中查找变量的顺序是：局部 --> 全局 --> 内置

```python
a = 1  # 当前变量
b = 2  # 当前变量
c = 3  # 当前变量
globals = {'a': 10, 'b': 20}  # 全局变量
locals = {'b': 200, 'c': 300}  # 局部变量

print(eval('a + b + c'))  # 后两个参数省略，默认在当前作用域下，即a+b+c = 1+2+3 = 6
print(eval('a + b + c', globals, locals))  # 指定globals、locals参数，优先局部，再全局，最后当前作用域，即a+b+c = 10+200+300 = 510

# 结果
'''
6
510
'''
```

## 63. raise语句的作用

> 当程序出错时，python会自动触发异常，也可以通过raise语句触发异常；一旦执行了raise语句，之后的语句不再执行；但如果加入了`try...excepet...finally`语句，except里的语句会被执行，finally一样也会被执行。

> raise语法格式：`raise [Exception [, args [, traceback]]]`，参数Exception 是异常的类型数标准异常中任一种（如NameError），args 是自已提供的异常参数；参数traceback可选，是跟踪异常对象。

> raise 语句有如下三种常用的用法：

- 单独`raise`，不加其他参数。在except语句中，引发当前上下文中捕获异常，或默认引发RuntimeError。通俗理解就是，捕捉到了异常，但是又想重新引发它，即传递异常不进行处理，可以调用不带参数的raise。

```python
# 在except语句中使用raise
try:
    s = 'a'
    if not s.isdigit():
        raise ValueError("s must be a number！")

except ValueError as e:
    print("引发异常：", e)
    raise

# 结果
'''
Traceback (most recent call last):
  File "C:/../../../test.py", line 13, in <module>
    raise ValueError("s must be a number！")
ValueError: s must be a number！
'''
```

```python
# 在没有引发过异常的程序使用raise，引发的是默认的RuntimeError
try:
    s = 'a'
    if not s.isdigit():
        raise

except RuntimeError as e:
    print("引发异常：", e)

# 结果
'''
引发异常： No active exception to reraise
'''
```

- `raise 异常类名称`：raise后面带一个异常类名称，表示引发执行类型的异常。

```python
try:
    s = None
    if s is None:
        print('s是空对象')
        raise ValueError
    print(len(s))

except Exception:
    print('空对象没有长度')

# 结果
'''
s是空对象
空对象没有长度
'''
```

- `raise 异常类名称("描述信息")`：在引发指定类型的异常，同时附带异常的描述信息。


```python
# 定义函数
def func(number):
    print(number)
    if number < 1:
        raise Exception("Invalid number!")
        # 触发异常后，后面的代码不会执行
    print(number + 1)

if __name__ == '__main__':
    try:
        func(0)
    except Exception as e:
        print("触发了异常！", e)
    else:
        print("未触发异常！")
    finally:
        print("程序执行完毕！")

# 结果
'''
0
触发了异常！ Invalid number!
程序执行完毕！
'''
```

## 64. yield语句的作用

**[python之yield、yield from](https://blog.csdn.net/qiuqiuit/article/details/86762747)**

> 该关键字用于函数中会把函数包装为生成器(generator)，调用生成器函数时，会返回一个生成器对象，生成器函数是生成器工厂。

```python
def func():
    yield 1
    yield 2
    yield 3

for i in func():
    print(i)

g = func()
print(next(g))
print(next(g))
print(next(g))

# 结果
'''
1
2
3
1
2
3
'''
```

> 简单理解，yield的功效为暂停和继续。

> 在一个函数中，程序执行到yield语句的时候，程序暂停，返回yield后面表达式的值；在下一次调用的时候，yield语句暂停的地方继续执行，如此循环，直到函数执行完。

> next函数和send函数很相似，都能获得生成器的下一个yield后面表达式的值，不同的是send函数包含next()方法，不仅可以向生成器传参，然后执行next()，如果下个元素不存在，迭代越界，生成器对象会抛出StopIteration异常。

```python
def foo():
    print("starting...")
    while True:
        res = yield 4
        print("res:", res)

f = foo()
print(next(f))
print("*"*20)
print(f.send(7))  # 这里调用send()函数给生成器给res赋值7，然后继续调用next(f)，返回4

# 结果
'''
starting...
4
********************
res: 7
4
'''
```

> yield from x 表达式替代for循环，对x对象所做的第一件事是调用iter(x)，从中获取迭代器，因此x可以是任何可迭代对象。任何可迭代对象都应该有一个`__iter__`方法（特殊情况时，只实现了`__getitem__`，未实现`__iter__`，对象也可以迭代），`__iter__`会返回一个迭代器。

```python
def generate_color():
    print("执行generate_color():")
    yield "红色"
    yield "橙色"
    yield "紫色"
    yield "黄色"

class Colors:
    def __init__(self):
        print("执行__init__():")
        self.gen_colors = generate_color()

    def __iter__(self):
        yield from self.gen_colors

colors = Colors()

for color in colors:
    print(color)

# 结果
'''
执行__init__():
执行generate_color():
红色
橙色
紫色
黄色
'''
```

## 65. 协程与生成器

**具体一些例子和详细原理可以参考《流畅的Python》 第16章 协程**

> 从句法上看，协程与生成器类似，都是定义体中包含 yield 关键字的函数。可是，在协 程中，yield 通常出现在表达式的右边（例如，datum = yield），可以产出值，也可 以不产出——如果 yield 关键字后面没有表达式，那么生成器产出 None。协程可能会从 调用方接收数据，不过调用方把数据提供给协程使用的是 .send(datum) 方法，而不是 next(...) 函数。通常，调用方会把值推送给协程，通过.send()双向交换数据的生成器就是协程。

> yield 关键字甚至还可以不接收或传出数据。不管数据如何流动，yield 都是一种流程控 制工具，使用它可以实现协作式多任务：协程可以把控制器让步给中心调度程序，从而激活其他的协程。

```python
# 产生两个值的协程
>>> from inspect import getgeneratorstate
>>> def simple_coro2(a):
...     print('-> Started: a =', a)
...     b = yield a
...     print('-> Received: b =', b)
...     c = yield a + b
...     print('-> Received: c =', c)
>>> my_coro2 = simple_coro2(14)
>>> getgeneratorstate(my_coro2)  # (1)
'GEN_CREATED'
>>> next(my_coro2)  # (2)
-> Started: a = 14
14
>>> getgeneratorstate(my_coro2)  # (3)
'GEN_SUSPENDED'
>>> my_coro2.send(28)  # (4)
-> Received: b = 28
42
>>> my_coro2.send(99)  # (5)
-> Received: c = 99
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
StopIteration
>>> getgeneratorstate(my_coro2)  # (6)
'GEN_CLOSED'
```

> (1) inspect.getgeneratorstate函数指明，处于GEN_CREATED 状态（即协程未启动）。

> (2) 向前执行协程到以第一个yield表达式，打印 -> Started: a = 14 消息，然后产出a的值，并且暂停，等待为b赋值。

> (3) getgeneratorstate 函数指明，处于 GEN_SUSPENDED 状态（即协程在yield表达式处暂停）。

> (4) 把数字28发给暂停的协程；就算yield表达式，得到28，然后把那个数按定给b。打印 -> Received: b = 28 消息，产出 a + b 的值（42），然后协程暂停，等待为 c 赋值。

> (5) 把数字 99 发给暂停的协程；计算 yield 表达式，得到 99，然后把那个数绑定给 c。打印 -> Received: c = 99 消息，然后协程终止，导致生成器对象抛出StopIteration异常。

> (6) getgeneratorstate 函数指明，处于 GEN_CLOSED 状态（即协程执行结束）。

## 66. python decimal精确计算

**[python decimal精确计算](https://blog.csdn.net/weixin_37989267/article/details/79473706)**

- (1). Decimal接收int和string类型参数

```python
from decimal import *

# 不能传入浮点数据，因为浮点数据就不准确
a = Decimal(3.33)*100
b = Decimal('3.33')*100
c = Decimal(3)
print(a)
print(b)
print(c)

# 结果
'''
Decimal('333.0000000000000071054273576')
Decimal('333.00')
Decimal('3')
'''
```

- (2). 浮点数据转换为Decimal类型

```python
from decimal import *

Decimal.from_float(2.222)

# 结果
'''
Decimal('2.221999999999999975131004248396493494510650634765625')
'''
```

- (3). 设定有效数字

> 特别注意，如果prec的长度比数字的长度小的话，扩充*100时就会出错

```python
from decimal import *

# 保留6个有效数字
getcontext().prec = 6
Decimal(1)/Decimal(7)

# 结果
'''
Decimal('0.142857')
'''
```

- (4). 四舍五入，保留几位小数

```python
from decimal import *

# 保留两位小数
Decimal('0.2335662').quantize(Decimal('0.00'))

# 结果
'''
Decimal('0.23')
'''
```

- (5). Decimal转化为字符串类型

```python
from decimal import *

# 保留两位小数
str(Decimal('0.2335662').quantize(Decimal('0.00')))

# 结果
'''
'0.23'
'''
```

## 67. 模块和代码块

> Python 提供了一个办法，把这些定义的方法和变量存放在文件中，为一些脚本或者交互式的解释器实例使用，这个文件被称为模块。模块是一个包含所有你定义的函数和变量的文件，其后缀名是.py，可以被别的程序引入，以使用该模块中的函数等功能。

> 代码块就是可作为可执行单元的一段Python程序文本；模块、函数体和类定义都是代码块。不仅如此，每一个交互脚本命令也是一个代码块；一个脚本文件也是一个代码块；一个命令行脚本也是一个代码块。

## 68. 上下文管理器

> 使用上下文管理器最广泛的案例就是with语句，打开文件，对文件进行操作，然后关闭文件，如果在往文件里写数据的时候发生异常，它也会尝试去关闭文件。

```python
# with语句，确保文件会被关闭
with open('aaa.txt', 'wb') as f
    f.write("sddsa")

# 等价于
f = open('aaa.txt', 'wb')
try:
    f.write('sddsa')
finally:
    f.close()
```

> 利用`__enter__`和`__exit__`方法实现一个上下文管理类

```python
class File(object):
    def __init__(self, file_name, method):
        self.file_obj = open(file_name, method)

    def __enter__(self):
        return self.file_obj

    def __exit__(self, exc_type, exc_val, exc_tb):
        self.file_obj.close()

with File('aaa.txt', 'wb') as f:
    f.write("Hello")

# 执行顺序
'''
(1) with语句先暂存了File类的__exit__方法
(2) 然后吊桶File类的__enter__方法
(3) __enter__方法返回打开文件对象
(4) 打开文件的对象被传给f
(5) 使用write来写文件
(6) 调用之前暂存的__exit__
(7) __exit__关闭了文件
'''
```

> python有个contextlib模块，里面的contextmanager结合生成器可以实现上下文管理

```python
from contextlib import contextmanager

@contextmanager
def open_file(name):
    f = open(name, 'w')
    yield f
    f.close()

with open_file('aaa.txt') as ff:
    ff.write("sssss")
```
