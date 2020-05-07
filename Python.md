<!-- markdown-toc start - Don't edit this section. Run M-x markdown-toc-generate-toc again -->
**Python语言知识点总结归纳**

* [Python语言特性](#python语言特性)
      * [1 Python的函数参数传递](#1-python的函数参数传递)
      * [2 Python中的元类(metaclass)](#2-python中的元类metaclass)
      * [3 @staticmethod和@classmethod](#3-staticmethod和classmethod)

<!-- markdown-toc end -->





# Python语言特性

## 1 Python的函数参数传递

看两个例子:

```python
a = 1
def fun(a):
    a = 2
fun(a)
print a  # 1
```
