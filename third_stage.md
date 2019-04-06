# 第三章
在python的世界中我们可以使用input()函数来接受一个标准输入数据
input()接收任意任性的输入，并将所有输入默认为字符串处理，并返回字符串类型

样例:

	>>>input()
	测试
	'测试'
	
第一行中我们调用input()函数进行输入
第二行我们输入`测试`
第三行input()函数默认我们的输入数据是字符串类型，并输入数据的字符串类型返回
____

## 简单难度
1.请问以下语句的返回结果是？(b)
```
>>>input()
第一题
```

```
A. 第一题
B. '第一题'
C. "'第一题'"
D. '"第一题"'
```
___
2.请通过input向机器人们询问“”
格式:
第一空代码:`_________`(`input()`)
第二空输入:`_________`(`这是在哪儿？`)
____
在python中，条件语句是通过一条或多条语句的执行结果（True或者False）来决定执行的代码块。
我们使用if语句进行条件判断
以下是if的语法
```
	if condition_1:
    	statement_block_1
```
当condition_1判断为真时，才会执行statement_block_1语句
样例输入：
	
	a = 1
	if a == 1:
		print("if语句被执行了")

样例输出：
	
	if语句被执行了
___
除了if语句外你还可以使用else语句进行搭配使用
```
if condition_1:
    statement_block_1
else:
    statement_block_2
```
当 condition_1为真时执行statement_block_1语句，不执行statement_block_2语句
当 condition_1为假时不执行statement_block_1语句，执行statement_block_2语句
___
样例输入
```
	a = 0
	if a == 1:
		print("上方的语句被执行了")
	else
		print("下方的语句被执行了")
	
```
样例输出
```
	下方的语句被执行了
```
___
我们可以用三个布尔变量A,B,C记录三个机器人是否说了真话
如B = Flase 代表B说谎 
3.现在假设A机器人说的是真话，B说的是谎话，请填写以下语句
```
	________ :
		B = False
```
选择以下正确的选项填入(C)
```
	A. if A == true
	B. IF A == True
	C. if A == Ture
	D. if A =  Ture
```
错误解释
```
	A. 在python中true不是合法的布尔值
	B. 在python中IF无法被python识别
	C. 正确
	D. '='为赋值，应使用'=='以此来判断是否相等
```
___
4.现在假设C机器人说的是真话, A与B说的都是谎话,请按要求填写以下语句(
(1)`A = False`
(2)`B = False`
)
在(1)处为布尔变量的值赋值为否
在(2)处为布尔变量的值赋值为真
```
	if C == True:
		___(1)___
		___(2)___
	
```
5.请尝试向以下程序发出输出值，以判断究竟哪个机器人说了真话
```
def lie(A,B,C):
    a = A
    b = B
    c = C
    if A == True :
        B = False
    else:
        B = True

    if B == True:
        C = False
    else:
        C = True

    if C == True:
        A = B = False

    if (a == A)&(b == B)&(c == C):
        print("推理正确")
    else:
        print("自相矛盾")
```
样例输入，当只有A机器人说真话的时候：
```
	lie(True,False,True)
```
样例输出：
```
	自相矛盾
```

当只有B机器人说真话的时候，输入语句__________(`lie(False,True,False)`)(返回推理正确)

当只有C机器人说真话的时候，输入语句__________(`lie(False,False,True)`)(返回自相矛盾)