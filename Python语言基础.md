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
- [24. python新式类和旧式类的区别](#24-python新式类和旧式类的区别)
- [25. 函数与方法的区别](#25-函数与方法的区别)
- [26. range与Xrange的区别](#26-range与xrange的区别)
- [27. search与match的区别](#27-search与match的区别)
- [28. 继承](#28-继承)
- [29. 多态与多态性](#29-多态与多态性)
- [30. Numpy与Scipy的区别](#30-numpy与scipy的区别)
- [31. 函数式编程](#31-函数式编程)
- [32. 面向对象编程OOP](#32-面向对象编程oop)
- [33. 面向切面编程AOP](#33-面向切面编程aop)
- [34. 元编程](#34-元编程)
- [35. 捕获异常](#35-捕获异常)
- [36. python中如何进行异常处理，如何自定义一个异常类](#36-python中如何进行异常处理如何自定义一个异常类)
- [37. python内置数据结构](#37-python内置数据结构)
- [38. python中函数和方法有什么区别](#38-python中函数和方法有什么区别)
- [39. python中参数类型有哪些](#39-python中参数类型有哪些)
- [40. python中函数传参过程](#40-python中函数传参过程)
- [41. *args和**kwargs](#41-args和kwargs)
- [42. 实参和形参的区别](#42-实参和形参的区别)
- [43. python中可变对象和不可变对象](#43-python中可变对象和不可变对象)
- [44. lambda函数](#44-lambda函数)
- [45. python中正则使用方式](#45-python中正则使用方式)
- [46. python中重载](#46-python中重载)
- [47. python中反射机制](#47-python中反射机制)
- [48. python中如何管理依赖](#48-python中如何管理依赖)
- [49. 如何分析python代码性能](#49-如何分析python代码性能)
- [50. 列表的线性访问和随机访问](#50-列表的线性访问和随机访问)
- [51. python中的高阶函数](#51-python中的高阶函数)
- [52. Python中单下划线和双下划线](#52-python中单下划线和双下划线)
- [53. Python的作用域以及Python搜索变量的顺序](#53-python的作用域以及python搜索变量的顺序)
- [54. 编码与解码](#54-编码与解码)
- [55. 字符串格式化](#55-字符串格式化)
- [56. 增量赋值](#56-增量赋值)
- [57. 字典推导式](#57-字典推导式)
- [58. exec对字符串执行和eval对字符串求值](#58-exec对字符串执行和eval对字符串求值)
- [59. raise语句的作用](#59-raise语句的作用)
- [60. yeild语句的作用](#60-yeild语句的作用)
- [61. socket编程](#61-socket编程)
- [62. urllib和urllib2](#62-urllib和urllib2)
- [63. requests](#63-requests)
- [64. Beautiful Soup](#64-beautiful-soup)
- [65. select,poll和epoll](#65-selectpoll和epoll)
- [66. python中实现IO多路复用](#66-python中实现io多路复用)
- [67. python常用的并发网络库](#67-python常用的并发网络库)

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

```python
def line_conf(a, b):
    def line(x):
        return a*x +b
    return line

line1 = line_conf(1, 1)
line2 = line_conf(4, 5)
print(line1(5), line2(5))  # (6, 25)
```

## 20. 装饰器

**[python装饰器](https://blog.csdn.net/tryhardsilently/article/details/90767627)**
**[Python装饰器各种类型详解](https://blog.csdn.net/yhy1271927580/article/details/72758577)**
**[Python各种类型装饰器详解说明](https://blog.csdn.net/five3/article/details/83447467)**
**[python装饰器的4种类型](https://blog.csdn.net/xiemanr/article/details/72510885)**
https://blog.csdn.net/five3/article/details/83447467
https://blog.csdn.net/xiemanr/article/details/72510885
https://blog.csdn.net/yhy1271927580/article/details/72758577

https://blog.csdn.net/weixin_42134789/article/details/84635252?utm_medium=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-3.nonecase&depth_1-utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-3.nonecase

https://blog.csdn.net/u010358168/article/details/77773199?utm_medium=distribute.pc_relevant_right.none-task-blog-BlogCommendFromMachineLearnPai2-29.nonecase&depth_1-utm_source=distribute.pc_relevant_right.none-task-blog-BlogCommendFromMachineLearnPai2-29.nonecase

> 装饰器本质上是一个函数，可以让其他函数在不需要做任何代码处理的前提下增加额外的功能，装饰器的返回值也是一个函数对象。它经常用于有切面需求的场景，比如：**插入日志、性能测试、事务处理、缓存、权限校验等场景**，装饰器是解决这类问题的绝佳设计。有了装饰器，我们就可以抽离出大量与函数功能本身无关的雷同代码到装饰器中并继续重用。概括的讲，装饰器的作用就是为已经存在的对象添加额外的功能。
- 装饰器自身为函数  
(1). 被装饰的对象为函数，且不带参数  

```python
import time

# 装饰器为函数
def time_decorator(func):
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
func1 is running.
方法foo用时:3.01444411277771秒
'''
```

> 在以上代码中，@time_decorator装饰器对foo函数进行了装饰，这是一个不带参数的装饰器，当python解释器执行到@time_decorator时，回去调用time_decorator函数，同时将被装饰的对象的函数名foo作为参数传入，这时time_decorator函数接受到一个参数(即方法名foo)，然后进入内嵌函数inner，计算开始时间，调用传进来的foo方法，再计算结束时间，打印函数foo的耗时，最后将结果用内部函数inner返回，其实就是一个闭包函数。

> 首先打印的是foo.__name__，这里是inner而不是foo，本质上是调用inner函数  
> 其次打印的是inner的内容"Hello inner"，然后开始调用foo函数，打印"func1 is running."  
> 最后打印"方法foo用时:3.01444411277771秒"

(2). 被装饰的对象为函数，且带参数  

```python

```

(3). 被装饰的对象为类，且不带参数  
(4). 被装饰的对象为类，且带参数

- 装饰器自身为类  
(1). 被装饰的对象为函数，且不带参数  
(2). 被装饰的对象为函数，且带参数  
(3). 被装饰的对象为类，且不带参数  
(4). 被装饰的对象为类，且带参数

- 特殊的装饰器

- 装饰器顺序

- 通用万能装饰

```python
def decorator_all(func):
    def wrapper(*args, **kwargs):
        print("万能装饰器")
        return func(*args, **kwargs)
    
    return wrapper

```

## 21. 浅拷贝与深拷贝

## 22. 设计模式

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

## 24. python新式类和旧式类的区别

## 25. 函数与方法的区别

## 26. range与Xrange的区别

## 27. search与match的区别

## 28. 继承

## 29. 多态与多态性

## 30. Numpy与Scipy的区别

## 31. 函数式编程

## 32. 面向对象编程OOP

## 33. 面向切面编程AOP

## 34. 元编程

> 元编程是一种可以将程序当作数据来操作的技术，元编程能够读取，生成，分析或转换其他的程序代码，甚至可以在运行时修改自身 。

## 35. 捕获异常

## 36. python中如何进行异常处理，如何自定义一个异常类

## 37. python内置数据结构

## 38. python中函数和方法有什么区别

## 39. python中参数类型有哪些

## 40. python中函数传参过程

## 41. *args和**kwargs

## 42. 实参和形参的区别

## 43. python中可变对象和不可变对象

## 44. lambda函数

## 45. python中正则使用方式

> 手写正则邮箱地址

## 46. python中重载

## 47. python中反射机制

## 48. python中如何管理依赖

> 每个项目创建独立的虚拟环境

## 49. 如何分析python代码性能

## 50. 列表的线性访问和随机访问

> random.random()用于生成一个0到1的随机符点数: 0 <= n < 1.0 。

> random.uniform(a, b)，用于生成一个指定范围内的随机符点数，两个参数其中一个是上限，一个是下限。如果a > b，则生成的随机数n: a <= n <= b。如果 a <b， 则 b <= n <= a 。

> random.randint(a, b)，用于生成一个指定范围内的整数。其中参数a是下限，参数b是上限，生成的随机数n: a <= n <= b。

> random.randrange([start], stop[, step])，从指定范围内，按指定基数递增的集合中 获取一个随机数。

> random.choice(sequence)从序列中获取一个随机元素，参数sequence表示一个有序类型。

> random.shuffle(x[, random])，用于将一个列表中的元素打乱。

> random.sample(sequence, k)，从指定序列中随机获取指定长度的片断。sample函数不会修改原有序列。

## 51. python中的高阶函数

> 高阶函数：一个函数可以作为参数传给另外一个函数，或者一个函数的返回值为另外一个函数（若返回值为该函数本身，则为递归），满足其一则为高阶函数。

- map

- filter

- reduce

- sorted

> sort 是应用在 list 上的方法，sorted 可以对所有可迭代的对象进行排序操作。

- abs 

## 52. Python中单下划线和双下划线

## 53. Python的作用域以及Python搜索变量的顺序

> Python作用域简单说就是一个变量的命名空间。代码中变量被赋值的位置，就决定了哪些范围的对象可以访问这个变量，这个范围就是变量的作用域。
在Python中，只有模块（module），类（class）以及函数（def、lambda）才会引入新的作用域。
Python的变量名解析机制也称为 LEGB 法则：本地作用域（Local）→当前作用域被嵌入的本地作用域（Enclosing locals）→全局/模块作用域（Global）→内置作用域（Built-in）

## 54. 编码与解码

> 编码：gbk => unicode => utf16 => url解码

> 解码：url解码 => utf16 =>unicode => gbk

eg:

```python
urllib.quote(line.decode("gbk").encode("utf-16"))
```

## 55. 字符串格式化

## 56. 增量赋值

- x += 1

- x *= 1

- x = x + 1

## 57. 字典推导式

## 58. exec对字符串执行和eval对字符串求值

## 59. raise语句的作用

## 60. yeild语句的作用

## 61. socket编程

## 62. urllib和urllib2

## 63. requests

## 64. Beautiful Soup

## 65. select,poll和epoll

## 66. python中实现IO多路复用

## 67. python常用的并发网络库

- tornado
- gevent
- asyncio
