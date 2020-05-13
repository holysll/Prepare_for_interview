---
layout: post
title: Python语言知识点总结归纳
date: 2020-05-12 23:05:08
tags: 
  - python
  - 后端
  - 知识回顾
categories: 编程语言-python

---

  本文主要对python语言基础知识进行梳理、回顾，把一些需要记住的概念原理，和容易混淆，晦涩的知识点进行归纳。

<!-- more -->

<div style='display: none'>

<!-- TOC -->

- [1.Python语言的特性](#1-python语言的特性)
- [2.Python的函数参数传递](#2-python的函数参数传递)
- [3.python中的元类metaclass](#3-python中的元类metaclass)
- [4.staticmethod和classmethod](#4-staticmethod和classmethod)
- [5.单例模式](#5-单例模式)
- [6.python常用库](#6-python常用库)
- [7.python中的类型转换](#7-python中的类型转换)
- [8.文件流操作](#8-文件流操作)

<!-- /TOC -->

</div>

## 1. Python语言的特性

   Python是一种解释型语言，不需要再运行之前进行编译。  
   Python是一种动态类型语言，不需要声明变量的类型。  
   python适合面向对象编程，允许类的定义以及组合和继承。  

## 2. Python的函数参数传递

看两个例子:

```python
a = 1
def fun(a):
    a = 2
fun(a)
print a  # 1
```

```python
a = []
def fun(a):
    a.append(1)
fun(a)
print a  # [1]
```

## 3. python中的元类metaclass

> 不会很常用，在ORM这种复杂结构中晦遇到，同时在看一些框架源代码的过程中可能会遇到很多元类的实例，看起来很晦涩。推荐[Stack overflow](https://stackoverflow.com/questions/100003/what-are-metaclasses-in-python) 一些专业解答，也可以参考下[这篇博客](https://www.cnblogs.com/tkqasn/p/6524879.html)的深刻理解，很详细。

* **str是用来创建字符串对象的类**
* **int是用来创建整数对象的类**
* **type就是创建类对象的类**

> 通过type函数动态创建类

```python
# type的语法
type(类名, 父类的元组(针对集成的情况，可为空), 包函属性的字典)

eg:
  class MyClass(object):
    pass
  MyClass = type('MyClass', (), {'foo':True})
```

** 元类：就是能够创建python中类这种对象的东西，如type就是Python的内建元类 **

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

> 可以使用函数当做元类

> 可以使用class来当做元类


## 4. staticmethod和classmethod



## 5. 单例模式

  * **使用`__new__`方法**

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

* **共享属性**

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

* **装饰器版本**

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

**[单例模式伯乐在线详细解释](http://python.jobbole.com/87294/)**

## 6. python常用库

- **标准库**

  **[网友总结参考](https://www.cnblogs.com/haochengdu/p/8855028.html)**

  **[官网中文参考](https://docs.python.org/zh-cn/3.8/library/index.html)**

```
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

  > Statsmodels：用于统计建模，是一个Python中提供用户探索数据、估计统计模型和执行统计测试的模组。可用于不同类型数据的描述性统计，统计测试，绘
  > 图功能和结果统计。

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

```
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
