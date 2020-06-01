---
layout: post
title: Python语言知识点总结归纳
date: 2020-05-08 23:05:08
updated: 2020-05-14 01:36:55
tags: 
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
- [23. GIL全局解释器锁](#23-gil全局解释器锁)
- [24. 函数是一等公民？](#24-函数是一等公民)
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
- [41. python中如何进行异常处理，如何自定义一个异常类](#41-python中如何进行异常处理如何自定义一个异常类)
- [42. python内置数据结构](#42-python内置数据结构)
- [43. python中函数和方法有什么区别](#43-python中函数和方法有什么区别)
- [44. python中参数类型有哪些](#44-python中参数类型有哪些)
- [45. python中函数传参过程](#45-python中函数传参过程)
- [46. *args和**kwargs](#46-args和kwargs)
- [47. 实参和形参的区别](#47-实参和形参的区别)
- [48. python中可变对象和不可变对象](#48-python中可变对象和不可变对象)
- [49. python中正则使用方式](#49-python中正则使用方式)
- [50. Numpy与Scipy的区别](#50-numpy与scipy的区别)
- [51. python中反射机制](#51-python中反射机制)
- [52. python中如何管理依赖](#52-python中如何管理依赖)
- [53. 如何分析python代码性能](#53-如何分析python代码性能)
- [54. 列表的线性访问和随机访问](#54-列表的线性访问和随机访问)
- [55. Python中单下划线和双下划线](#55-python中单下划线和双下划线)
- [56. Python的作用域以及Python搜索变量的顺序](#56-python的作用域以及python搜索变量的顺序)
- [57. 编码与解码](#57-编码与解码)
- [58. 字符串格式化](#58-字符串格式化)
- [59. 增量赋值](#59-增量赋值)
- [60. 字典推导式](#60-字典推导式)
- [61. exec对字符串执行和eval对字符串求值](#61-exec对字符串执行和eval对字符串求值)
- [62. raise语句的作用](#62-raise语句的作用)
- [63. yeild语句的作用](#63-yeild语句的作用)
- [64. socket编程](#64-socket编程)
- [65. urllib和urllib2](#65-urllib和urllib2)
- [66. requests](#66-requests)
- [67. Beautiful Soup](#67-beautiful-soup)
- [68. select,poll和epoll](#68-selectpoll和epoll)
- [69. python中实现IO多路复用](#69-python中实现io多路复用)
- [68. python常用的并发网络库](#68-python常用的并发网络库)
- [70. python decimal精确计算](#70-python-decimal精确计算)

<!-- /TOC -->

</div>

## 1. Python语言的特性

   Python是一种解释型语言，不需要再运行之前进行编译。
   Python是一种动态类型语言，不需要声明变量的类型。  
   python适合面向对象编程，允许类的定义以及组合和继承。  

## 2. python语言相比其他语言的优点和缺点

**优点**

- 简单易懂，灵活简洁
- 强大的标准库和三方库
- 活跃的社区，许多开源项目
- 开发效率高，迭代便捷
- 应用领域广泛，Web开发、网络编程、自动化运维、Linux系统管理、数据分析、科学计算、人工智能、机器学习

**缺点**

- 执行效率较差,
- 异步生态不完善，相关的库较少(tornado)
- GIL的存在，无法充分利用多核的特性

## 3. python中的元类metaclass

> 不会很常用，在ORM这种复杂结构中晦遇到，同时在看一些框架源代码的过程中可能会遇到很多元类的实例，看起来很晦涩。推荐[Stack overflow](https://stackoverflow.com/questions/100003/what-are-metaclasses-in-python) 一些专业解答，也可以参考下[这篇博客](https://www.cnblogs.com/tkqasn/p/6524879.html)的深刻理解，很详细。

* **str是用来创建字符串对象的类**
* **int是用来创建整数对象的类**
* **type就是创建类对象的类**

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

* **__metaclass__**

> 可以再写一个类的时候为其添加__metaclass__属性，这样就定义了这个类的元类。__metaclass__实际上可以被任意调用，它并不需要是一个正式的类。

```python
# py2
class Foo(object):
    __metaclass__ = something

# py3
class Foo(metaclass=something):
    __metaclass__ = something
```

* **自定义元类**

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

* **真实业务场景下的元类**

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

* **使用元类创建ORM实例**

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
        super(StringField, self).__init__(name, 'varchar(100)')

class IntegerField(Field):
    def __init__(self, name):
        super(IntegerField, self).__init__(name, 'bigint')

# 定义元类，控制Model对象的创建
class ModelMetaClass(type):
    """定义元类"""
    def __new__(cls, name, bases, attrs):
        if name=='Model':
            return super(ModelMetaClass, cls).__new__(cls, name, bases, attrs)
        mappings = dict()
        for k, v in attrs.iteritems():
            # 保存类属性和列的映射关系到mappings字典
            if isinstance(v, Field):
              print('Found mapping: %s==>%s' % (k, v))
             mappings[k] = v
        for k in mapping.iterkeys():
            # 将雷属性移除，是定义的类字段不污染User类属性，只在实例中可以访问这些key
            attrs.pop(k)
        # 假设表名为类名的小写，创建类时添加一个__table__类属性
        attrs['__table__'] = name.lower()
        # 保存属性和列的映射关系，创建类时添加一个__mappings__类属性
        attrs['__mappings__'] = mappings
        return super(ModelMetaClass, cls).__new__(cls, name, bases, attrs)

# 编写Model基类
class Model(dict):
    __metaclass__ = ModelMetaClass

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
        for k, v in self.__mappings__.iteritems():
            fields.append(v,name)
            params.append('?')
            args.append(getattr(self, k,None))
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

> 创建实例时把所有实例的`__dict__`指向同一个字典,这样它们具有相同的属性和方法.

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

> Python GC主要使用引用计数(reference counting)来跟踪和回收垃圾。在引用计数的基础上，通过标记清除机制(mark and sweep)解决容器对象可能产生的循环引用问题，通过分代回收(generation collection)策略，以以空间换时间的方法来提高垃圾回收的效率。

- 引用计数

> 引用计数法的原理是每个对象维护一个ob_ref，用来记录当前对象被引用的次数，也就是来追踪到底有多少引用指向了这个对象，当发生（对象被创建、对象被引用、对象被作为参数传到函数中、对象作为一个元素，存储在容器中）四种情况的时候，该对象的引用计数+1；当发生（该对象的别名被显示销毁时、该对象的引别名被赋予新的对象、一个对象离开它的作用域、该元素从容器中删除时或容器被销毁时），该对象的引用计数器-1。

**简而言之，PyObject是每个对象必有的内容，其中ob_refcnt就是做为引用计数。当有一个对象有心的引用时，它的ob_refcnt就会增加，当引用它的对象被删除，它的ob_refcnt就会减少。当引用计数为0时，该对象生命就结束了。**

**优点：**  
① 高效  
② 运行期没有停顿  
③ 对象有确定的生命周期  
④ 易于实现

**缺点：**  
① 维护引用计数消耗资源，维护引用计数的次数和应用赋值成正比，而不像mark and sweep等基本与回收的内存数量有关。  
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

> 注重对象的行为，而非对象的类型，一个对象能都昨晚函数、表达是的参数，取决于其行为而非类型归属。

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

- 工厂模式
- 构造模式
- 原型模式
- 单例模式
- 装饰器模式
- 代理模式
- 适配器模式
- 外观模式
- 享元模式
- MVC模式
- 惰性计算模式
- 迭代器模式
- 观察者模式
- 策略模式

## 23. GIL全局解释器锁

**[Python的底层](https://www.oschina.net/translate/pythons-hardest-problem)**

> 要理解GIL的含义，我们需要从Python的基础讲起。像C++这样的语言是编译型语言，所谓编译型语言，是指程序输入到编译器，编译器再根据语言的语法进行解析，然后翻译成语言独立的中间表示，最终链接成具有高度优化的机器码的可执行程序。编译器之所以可以深层次的对代码进行优化，是因为它可以看到整个程序（或者一大块独立的部分）。这使得它可以对不同的语言指令之间的交互进行推理，从而给出更有效的优化手段。

> 与此相反，Python是解释型语言。程序被输入到解释器来运行。解释器在程序执行之前对其并不了解；它所知道的只是Python的规则，以及在执行过程中怎样去动态的应用这些规则。它也有一些优化，但是这基本上只是另一个级别的优化。由于解释器没法很好的对程序进行推导，Python的大部分优化其实是解释器自身的优化。更快的解释器自然意味着程序的运行也能“免费”的更快。也就是说，解释器优化后，Python程序不用做修改就可以享受优化后的好处。

> 要想利用多核系统，Python必须支持多线程运行。作为解释型语言，Python的解释器必须做到既安全又高效，但多线程编程会遇到问题，解释器要留意的是避免在不同的线程操作内部共享的数据，同时它还要保证在管理用户线程时保证总是有最大化的计算资源。这时，为了不同线程同时访问时保护数据，当一个线程运行python程序的时候会霸占整个python解释器，也就是给解释器加了一把全局锁，这使得对于任何python程序，不管有多少处理器，多少线程，任何时候都自由一个线程在执行，其他线程在等待正在运行的线程完成才能运行。

> 如果线程运行过程中遇到耗时操作，超时时间超过一个固定值，则单线线程将会解开全局解释器锁，使其他线程运行。所以在多线程中是有先后顺序的，并不是同时运行的。多进程因每个进程都能被系统分配资源，相当于每个进程有了一个python解释器，所以多进程可以实现多个进程同时运行，缺点就是系统资源开销大。

## 24. 函数是一等公民？

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

> 

## 39. 元编程

> 元编程是一种可以将程序当作数据来操作的技术，元编程能够读取，生成，分析或转换其他的程序代码，甚至可以在运行时修改自身。

## 40. 捕获异常

## 41. python中如何进行异常处理，如何自定义一个异常类

## 42. python内置数据结构

## 43. python中函数和方法有什么区别

## 44. python中参数类型有哪些

## 45. python中函数传参过程

## 46. *args和**kwargs

## 47. 实参和形参的区别

## 48. python中可变对象和不可变对象

## 49. python中正则使用方式

> 手写正则邮箱地址

## 50. Numpy与Scipy的区别

## 51. python中反射机制

## 52. python中如何管理依赖

> 每个项目创建独立的虚拟环境

## 53. 如何分析python代码性能

## 54. 列表的线性访问和随机访问

> random.random()用于生成一个0到1的随机符点数: 0 <= n < 1.0 。

> random.uniform(a, b)，用于生成一个指定范围内的随机符点数，两个参数其中一个是上限，一个是下限。如果a > b，则生成的随机数n: a <= n <= b。如果 a < b， 则 b <= n <= a 。

> random.randint(a, b)，用于生成一个指定范围内的整数。其中参数a是下限，参数b是上限，生成的随机数n: a <= n <= b。

> random.randrange([start], stop[, step])，从指定范围内，按指定基数递增的集合中 获取一个随机数。

> random.choice(sequence)从序列中获取一个随机元素，参数sequence表示一个有序类型。

> random.shuffle(x[, random])，用于将一个列表中的元素打乱。

> random.sample(sequence, k)，从指定序列中随机获取指定长度的片断。sample函数不会修改原有序列。

## 55. Python中单下划线和双下划线

## 56. Python的作用域以及Python搜索变量的顺序

> Python作用域简单说就是一个变量的命名空间。代码中变量被赋值的位置，就决定了哪些范围的对象可以访问这个变量，这个范围就是变量的作用域。
在Python中，只有模块（module），类（class）以及函数（def、lambda）才会引入新的作用域。
Python的变量名解析机制也称为 LEGB 法则：本地作用域（Local）→当前作用域被嵌入的本地作用域（Enclosing locals）→全局/模块作用域（Global）→内置作用域（Built-in）

## 57. 编码与解码

> 编码：gbk => unicode => utf16 => url解码

> 解码：url解码 => utf16 =>unicode => gbk

eg:

```python
urllib.quote(line.decode("gbk").encode("utf-16"))
```

## 58. 字符串格式化

## 59. 增量赋值

- x += 1

- x *= 1

- x = x + 1

## 60. 字典推导式

## 61. exec对字符串执行和eval对字符串求值

## 62. raise语句的作用

## 63. yeild语句的作用

## 64. socket编程

## 65. urllib和urllib2

## 66. requests

## 67. Beautiful Soup

## 68. select,poll和epoll

## 69. python中实现IO多路复用

## 68. python常用的并发网络库

- tornado
- gevent
- asyncio

## 70. python decimal精确计算

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
