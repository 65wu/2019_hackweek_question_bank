# 第六章

下面我们学习python的最后一种的数据类型——字典
字典和列表一样是可修改的，也可以存储任何类型的变量
不过列表的元素下标是有序的数字
而字典的下标则为一种叫键的东西
我们先看看字典长什么样子
```
dict = {'a':1, 'b':2, 'c':3}
```
字典用花括号将它的各个元素囊括其中
其中'a','b','c'称之为“键”,
而对应的1,2,3则之为“值”,
值可以重复，键一般是唯一的,键只能使用数字、字符串和元组,
这种对应关系和函数相同，一个x至多只能有一个y与它对应，但是一个y可以多个x与它对应
实际上，字典本质上就是一个叫做散列函数的东西
___
1.下列字典创建语句不合法的是？(B)
```
A. dict = {'a':1,'a':2,'c':3}
B. dict = {['a','b','c']:[1,2,3]}
C. dict = {('a','b','c'):[1,2,3]}
D. dict = {'a':'1','b':2,'c':'3'}
```
错误解释：
```
A. 虽然出现了一样的键，但python解析器却认定是合法的
B. 键不能使用列表
C. 键可以使用列表
D. 值的类型不要求全部统一
```
___
虽然字典的键要求唯一，但是在键重复时，并不会产生报错，不过旧键的值会被新键的值覆盖掉
我们把上一题的A选项重复键的元素打印出来看看,不过在此之前你得明白如何访问字典里的值
___
#### 访问字典里的值
字典使用键做下标访问相应的值
示例
```
>>>dict = {'a':'A','b':'B','c':'C'}
>>>print(dict['a'],dict['b'],dict['c'])
A B C
```
___
#### 字典值的特性
```
>>>dict = {'a':1,'a':2,'c':3}
>>>print(dict['a'])
2
```
正如你所见，旧键'a'的值1被新键'a'的值2给覆盖掉了
2.下列语句的返回值是？(A)
```
dict = {'a':1,'A':2,'a':3,'A':4}
print(dict['a'],dict['A'],end='')
```
```
A. 3 4
B. 1 2
C. 4 4
D. 1 1
```
___
3.已知有摩斯电码表
![摩斯电码表](http://www.demodashi.com/contentImages/image/20181224/b2QhaA0igGIjyU86ioQ.jpg)
请用字典表示莫斯电码中A-Z字符及其摩斯串,主键为字符，键值为摩斯串
示例部分展示了构建出的字典名，和A、B字符及其摩斯串,注意格式与单双引号

```
morse = {
'A':".-",
'B':"-..."}
```

答案:

```
morse = {
'A':".-",
'B':"-...",
'C':"-.-.",
'D':"-..",
'E':".",
'F':"..-.",
'G':"--.",
'H':"....",
'I':"..",
'J':".---",
'K':"-.-",
'L':".-..",
'M':"--",
'N':"-.",
'O':"---",
'P':".--.",
'Q':"--.-",
'R':".-.",
'S':"...",
'T':"-",
'U':"..-",
'V':".--",
'W':".--",
'X':"-..-",
'Y':"-.--",
'Z':"--.."}
```

___
### 函数
函数是组织好的，可重复使用的，用来实现单一，或相关联功能的代码段。
函数能提高应用的模块性，和代码的重复利用率
到目前为止，你已经接触到了相当多的python自带的内置函数，
其实用户自己也可以构建一些自定义函数
___
#### 构建函数
```
def 函数名(参数列表)：
	函数体
```	
示例
```
def hello_world():
	print("Hello,World")
```
def 声明用户自定义函数， hello_world为函数名,方括号为空说明无参数，函数体为`print("Hello,World")`
4.下列函数定义合法的是？(D)
A.
```
define first():
	print("the first function")
```
B.
```
def second:
	print("the second function")
```
C.
```
def third()
	print("the third function")
```
D.
```
def fourth():
	print("the fourth function")
```
错误解释：
```
A. 声明函数是使用define，而不是def
B. 函数名后方要加上一对圆括号，即便无参数，也不能省略括号
C. 遗忘添加':'
D. 正确
```
———
#### 函数的调用
无参数的函数可直接调用，具体操作如下
```
>>>fourth()
the fourth function
```
不过大多数函数是拥有参数的，如下方这个复杂一些的函数
```
def print_str(str):
	print("刚才输入的是"+"str")
```

含有参数的函数用如下方式调用：
```
>>> print_str("测试")
刚才输入的是测试
```
___
5.已知记下的音频为`.-./.-/-.../-.../../-`
请利用以下函数对音频进行解密(`decode_morse(".-./.-/-.../-.../../-")`)
或许你不是很明白decode_morse函数的内部原理，但是这没关系，你只需要用参数调用一下该函数即可
```
def decode_morse(string):
	MORSE = dict(zip(morse.values(),morse.keys()))
	s = string.split("/")
	for item in s:
		print(MORSE[item],end='')
```
玩家输入正确则返回`RABBIT`
