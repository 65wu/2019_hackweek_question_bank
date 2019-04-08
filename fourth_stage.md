# 第四章

本章我们会学习python的循环语句
在python中，基本的循环语句有两种,分别是`for`循环和`while`循环
___
###for循环
or循环可以用来把一些集合中的所有元素依次访问一次
for循环的语法格式如下：
```
	for iterating_var in sequence:
  		statements(s)
```
其中 `for`和`in`都是关键字，
`iterating_var`是元素，
`sequence`使我们要遍历的集合，
`statements(s)`是合法的python语句

我们用以下的例子体会一下

样例输入：

		for i in 'NcuHome':
			print i
			
样例输出：
```
N
c
u
H
o
m
e
```
在这个例子中,i是元素，用它来代表字符串'NcuHome'中每个字母
'NcuHome'是我们要遍历的集合
`print(i)`是循环里执行的语句，我们用print把当前的i打印出来
在循环里，i是变动的,它先是从首字母'N'出发，在执行完print(i)后，i又进发字母'c'，在执行完print(i)后，又继续往后，直到终点字母'e'，在把集合中的每一个元素都遍历以后，for循环也便结束了
___
根据以上的例子，完成以下题目
1.请问以下语句的输出结果是？(D)
```
	for i in '123456789':
		print(i)
```

A.
```
123456789
```
B.
```
'1' '2' '3' '4' '5' '6' '7' '8' '9'
```
C.
```
'1'
'2'
'3'
'4'
'5'
'6'
'7'
'8'
'9'
```
D.
```
1
2
3
4
5
6
7
8
9
```
错误解释:
用for循环输出字符串的每一个字符时，字符不会带上引号
同时python中的print()函数，在默认情况下，每次成功输出后都会在末尾加上换行符
___
从刚才的习题中，你已经初步接触到for循环输出字符串，但是像刚刚那种情况，字符串'123456789'
在这样的数字字符串中，它的每一个字符都是相关联的，是有序的，是有规律的，相比把每一个元素都表示出来
我们有更简洁的方法
现在让我们学习一下和for循环经常搭配的range()函数
___
### range()函数
`range(start, stop[, step])`
range函数共有三个参数
+ start代表计数的起始元素，默认为0
+ stop代表计数的末尾元素，且不包含末尾元素
+ step代表步长，默认为1，表示range()增长的速度

样例输入:

		for i in range(1,10):
			print(i)
			
样例输出：
```
1
2
3
4
5
6
7
8
9
```
在这个样例中,起始元素为1，之后迭代到9，但不包括末尾元素10，并且默认步长为1
于是显示出以上结果
通过range()函数，我们可以很轻松的输出一个有序数组所有的元素，而不用像之前那样列举出所有元素
___
2.请问以下语句的输出结果是？(A)
```
	for i in range(0,1):
		print("*",end='')
```
```
A. *
B. **
C. "*"
D. 无输出
```
错误解释:
range(0,1)中的(0,1)相当于是一个左闭右开区间，
当 i = 0时输出`*`,由于步长默认为1，这一轮结束后,i++，i==1,于是循环退出
最终只输出了一个`*`
___
3.请问以下三串代码中，哪一串代码的打印出的几何图形是实心三角形？(A)
A.
```
r = int(input())
for i in range(1,r,2):
    for j in range( int( ( r-i )/2 ) ):
        print(" ",end='')
    for k in range(i+1):
        if k == 0:
            print("/",end='')
        elif k == i:
            print("\\",end='')
        else:
            print("-",end='')
    print("")
```
B.
```
r = int(input())
for i in range(1,r+1):
    for j in range(1,r+1):
        if( (j == 1) | (j == r) )&( (i != 1) & (i != r) ):
            print(" | ",end='')
        elif ( (i == 1) | (i == r) ) & ( (j != 1) & (j != r) ):
            print(" - ",end='')
        else:
            print(" + ",end='')
    print('\n')
```
C.
```
r = int(input())
for i in range(1,r+1):
    for j in range(1,r+1):
        if ( i+j in range( int((r+3)/2) , int((3*r+1)/2) + 1) ) & ( i - j in range( int((1-r)/2) ,int((r-1)/2) + 1) ):
            print("+",end='')
        else:
            print(" ",end='')
    print()
```
错误解释：
A选项为三角形
B选项为矩形
C选项为菱形
___