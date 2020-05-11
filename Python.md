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
      * [6 python常用库](#6-python常用库)
         * [1 标准库](#1-标准库)
         * [2 科学计算库](#1-科学计算库)
         * [3 第三方库](#1-第三方库)
      * [7 python中的类型转换](#5-python中的类型转换)
      * [8 文件流操作](#8-文件流操作)

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

## 6 python常用库
### 1 标准库
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

### 2 科学计算库
```
numpy
scipy
pandas
statistics：数学统计函数
```

### 3 第三方库
```
pymysql：连接数据库
djano
flask
requests
selenium
scrapy
celery
md5
```

## 7 python中的类型转换
| 函数| 作用 |  | 函数 | 作用 |  | 函数 | 作用 |
| -- | -- | -- | -- | -- | -- | -- | -- |
| int() | 转整型 |  | list() | 转列表 |  | bin() | 整数转2进制 |
| float() | 转浮点型 |  | dict() | 转字典 |  | oct() | 整数转6进制 |
| str() | 转字符串 |  | set() | 转集合 |  | hex() | 整数转16进制 |
| ord() | 字符转整数 |  | tuple() | 转元组 |  | complex() | 实数转复数 |

## 8 文件流操作
### 打开文件
```
f=open('文件名', '访问模式')
if f:  # 判断文件是否打开

with open('文件名', '访问模式') as f:

```
### 访问模式

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

### 写文件
```
f.write(写入的内容)  # 打开文件后，将制定内容写入文件中
```

### 读取文件
```
f.read(读取数据的长度)  # 使用read可以从文件中读取制定长度的数据，并将指针移到这条数据之后。如果为空，则默认读取全部数据。

f.readline()  # 读取文件中一行数据的信息，指针移动到下一行。

f.readlines() # 读取整个文件的数据信息，返回一个列表，列表中每个元素为一行数据信息。
```
### 查看指针位置
```
f.tell()  # 查看单签位置，就是指针对应的位置
```

### 指针定位
```
seek(offset, from)  # 将指针定位到某个位置

from: 方向，0表示文件开头；1表示文件当前位置；2表示文件的末尾
offset: 偏移量

eg:
  f.seek(5,0)  # 文件开头，向后偏移5个位置
  f.seek(-3,2)  # 文件结尾，向前偏移3个位置
```
