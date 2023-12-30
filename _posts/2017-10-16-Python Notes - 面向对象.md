---
layout: post
title: Python Notes - 面向对象
date: 2017-12-26
categories: code
tag: python 

---

* content
{:toc}




## 模块              {#module}

### 模块标准文件模板

```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-

' a test module '

__author__ = 'Michael Liao'
```

第1行和第2行是标准注释，第1行注释可以让这个hello.py文件直接在Unix/Linux/Mac上运行，第2行注释表示.py文件本身使用标准UTF-8编码；

第4行是一个字符串，表示模块的文档注释，任何模块代码的第一个字符串都被视为模块的文档注释；

第6行使用`__author__`（双下划线）变量把作者写进去，这样当你公开源代码后别人就可以瞻仰你的大名；

以上就是Python模块的标准文件模板。

### 命令行测试

```python
if __name__=='__main__':
    test()
```

当我们在命令行运行该模块文件时，Python解释器把一个特殊变量`__name__`置为`__main__`，而如果在其他地方导入该`hello`模块时，`if`判断将失败，因此，这种`if`测试可以让一个模块通过命令行运行时执行一些额外的代码，最常见的就是运行测试。

### 作用域

正常的函数和变量名是**公开的（public）**，可以被直接引用，比如：`abc`，`x123`，`PI`等

类似`_xxx`（单下划线）和`__xxx`（双下划綫）这样的函数或变量就是**非公开的（private）**。private函数和变量“不应该”被直接引用，而不是“不能”被直接引用，是因为Python并没有一种方法可以完全限制访问private函数或变量，但是，从编程习惯上不应该引用private函数或变量。

## 面向对象编程        {#object}

### 类与对象

#### 类

```python
class Student(object):
    def __init__(self, name, score):	#构造方法，公共属性
        self.name = name
        self.score = score
    
    def __init__(self, name, score):    #构造方法，私有属性
        self.__name = name
        self.__score = score
        
    def get_name(self):					#私有属性访问控制
        return self.__name

    def get_score(self):
        return self.__score
    
    def set_name(self, name):
       	self.__name = name
    
    def set_score(self, score):
        self.__score = score

    def print_score(self):				#普通方法
        print('%s: %s' % (self.name, self.score))
```



##### 构造方法`__init__` 

- 注意到`__init__`方法的**第一个参数永远是`self`**，表示创建的实例本身；在创建实例的时候，必须传入与`__init__`方法匹配的参数，**但`self`不需要传**
- 在`__init__`方法内部定义属性（把属性绑定到`self`，因为`self`就指向创建的实例本身）

##### 普通方法

**第一个参数是`self`(必须写)**，其他和普通函数一样。要调用一个方法，只需要在实例变量上直接调用，**`self`不用传递**，其他参数正常传入

##### 私有属性

属性的名称前加上双下划线`__`，只有类内部可以访问，外部不能访问

##### 关于变量名格式

在Python中，变量名类似`__xxx__`的，也就是以双下划线开头，并且以双下划线结尾的，是特殊变量，特殊变量是可以直接访问的，不是private变量，所以，不能用`__name__`、`__score__`这样的变量名。

有些时候，你会看到以一个下划线开头的实例变量名，比如`_name`，这样的实例变量外部是可以访问的，但是，按照约定俗成的规定，当你看到这样的变量时，意思就是，“虽然我可以被访问，但是，请把我视为私有变量，不要随意访问”。

双下划线开头的实例变量，不能直接访问`__name`是因为Python解释器对外把`__name`变量改成了`_Student__name`，所以，仍然可以通过`_Student__name`来访问`__name`变量：

```
>>> bart._Student__name
'Bart Simpson'
```

但是**强烈建议不要这么干**，因为**不同版本的Python解释器可能会把`__name`改成不同的变量名**。

#### 对象

```python
bart = Student('Bart Simpson', 59)
bart.print_score()

#使用type()判断对象类型
>>> type(123)
<class 'int'>
>>> type('str')
<class 'str'>
>>> type(None)
<type(None) 'NoneType'>
#如果一个变量指向函数或者类，也可以用type()判断
>>> type(abs)
<class 'builtin_function_or_method'>
>>> type(a)
<class '__main__.Animal'>

#判断基本数据类型可以直接写int，str等，但如果要判断一个对象是否是函数，可以使用types模块中定义的常量：
>>> import types
>>> def fn():
...     pass
...
>>> type(fn)==types.FunctionType
True
>>> type(abs)==types.BuiltinFunctionType
True
>>> type(lambda x: x)==types.LambdaType
True
>>> type((x for x in range(10)))==types.GeneratorType
True

#能用type()判断的基本类型也可以用isinstance()判断：
>>> isinstance('a', str)
True
>>> isinstance(123, int)
True
>>> isinstance(b'a', bytes)
True
#并且还可以判断一个变量是否是某些类型中的一种，比如下面的代码就可以判断是否是list或者tuple：
>>> isinstance([1, 2, 3], (list, tuple))
True
>>> isinstance((1, 2, 3), (list, tuple))
True
```

### 继承与多态

#### 基本形式

类：

```python
class Animal(object):				#父类
    def run(self):
        print('Animal is running...')

class Dog(Animal):					#Animal的子类（继承）
    def eat(self):					#子类自己的方法
        print('Eating meat...')
	def run(self):					#子类重写父类方法（多态）
        print('Dog is running...')
        
class Cat(Animal):
    pass
```

对象：

```python
b = Animal() # b是Animal类型
c = Dog() # c是Dog类型

#判断一个变量是否是某个类型,用isinstance()判断。总是优先使用isinstance()判断类型，可以将指定类型及其子类“一网打尽”。
>>> isinstance(b, Animal)	
True
>>> isinstance(c, Dog)
True
>>> isinstance(c, Animal)
True
>>> isinstance(b, Dog)
False

#多态的好处:新增一个Animal的子类，不必对extra_run()做任何修改，实际上，任何依赖Animal作为参数的函数或者方法都可以不加修改地正常运行，原因就在于多态。
def extra_run(animal):
    animal.run()
   
>>> extra_run(Animal())
Animal is running...
>>> extra_run(Dog())
Dog is running...
>>> extra_run(Cat())
cat is running...
```

“开闭”原则：

对扩展开放：允许新增`Animal`子类；

对修改封闭：不需要修改依赖`Animal`类型的`extra_run()`等函数。

#### 静态语言 vs 动态语言

对于静态语言（例如Java）来说，如果需要传入`Animal`类型，则传入的对象必须是`Animal`类型或者它的子类，否则，将无法调用`run()`方法。

对于**Python**这样的**动态语言**来说，则**不一定需要传入`Animal`类型（Animal 或其子类）**。我们只需要**保证传入的对象有一个`run()`方法**就可以了：

```python
class Timer(object):
    def run(self):
        print('Start...')

>>> extra_run(Timer())
Start... 
```

