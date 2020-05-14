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

<!-- /TOC -->

</div>

## 1. Python语言的特性

   Python是一种解释型语言，不需要再运行之前进行编译。
   Python是一种动态类型语言，不需要声明变量的类型。  
   python适合面向对象编程，允许类的定义以及组合和继承。  

## 2. python语言相比其他语言的优点和缺点

**优点**
- 
- 简单易懂，灵活简洁
- 强大的标准库和三方库
- 活跃的社区，许多开源项目
- 开发效率高，迭代便捷
- 应用领域广泛，Web开发、网络编程、自动化运维、Linux系统管理、数据分析、科学计算、人工智能、机器学习

**缺点**
- 
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

## 11. python2.x 与python3.x的主要区别

## 12. 如何将python2的代码迁移到python3

## 13. python新式类和旧式类的区别

## 14. 鸭子类型

## 15. python自省

## 16. 猴子补丁技术

## 17. python语法糖有哪些

## 18. 迭代器和生成器

## 19. 闭包

## 10. 装饰器

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

## 41. 实参和形参的区别

## 42. python中可变对象和不可变对象

## 43. lambda函数

## 44. python中正则使用方式

## 45. 
