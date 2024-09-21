# 输入输出
## input函数
- **功能**：接受键盘输入，返回**string类型的变量**
- **格式**：`input([prompt])` ==（）中可加可选参数（提示信息）==
- **示例**：`name = input(“请输入你的名字：”)`

## eval函数
- **功能**：计算字符串表达式，返回计算结果;把字符串变成数字
- **格式**：`eval(expression)`
- **示例**：`eval(3 + 5)`

## print函数
- **功能**：输出各种数据到屏幕
- **格式**：`print(object)`
- **示例**：`print(“:)”)`

# 数据类型
## 变量命名
- 可以包含==数字、字母、下划线==，但==数字==不能打头
- 区分大小写
- 不能用系统关键词
- **示例**:`test = ‘Hello world!’`   
	 `Test = 123`
	 **同时定义多个变量**:`name, age = Li, 18`
	 **同时修改多个变量**：`x, y = 1,2` `x, y = y, x` 先进行 = 右侧的运算，即==先将x=1,y=2赋到右边==，实现的效果为x和y的值互换

# Number数据类型
## 整型数据
- **进制**：
    不加前缀：十进制
	前缀0o：八进制
	前缀0x：十六进制
- **布尔类型**：真为1，假为0
- **bool函数返回Flase**：
	 1. 常量None或False
	 2. 值为零的数值：0 0.0 0j
	 3. 空序列或集合：空字符串 空元祖 空列表

## 浮点型数据
- C中**double类型**实现
- **科学计数法**：3.25e3——e代表10，3为指数

## 复数型数据
- 实部和虚部都是**浮点数**
- **书写方法**：a+bj或a+bJ
- **complex函数**生成复数：
	 **格式**：`complex(实部，虚部)`
	 **提醒**：输入值空着代表为0
	     如：`c=complex(5)` 执行完后c的值为（5+0j）；`c=complex()` 执行完后c的值为0j

# String数据类型
## 概述
- 字符串写在一对**单引号、双引号或三个双引号**中
- **空字符串**：`'' ` 或 `""`

## int函数
- **功能**：字符串转化为整数
- **格式**：`int（‘string’，数制）` 数制不指定时默认为10
- **示例**：
	`int（‘35’）`返回整数35
	`int（‘35’，8）`返回整数29
	`int（‘35-1’）`*报错*  ==int函数不能进行运算==

## float函数
- **功能**：字符串转化为浮点数
- **格式**：`float（‘string’）`
- **示例**：
	`float（‘35’）`返回浮点数35.0
	`float（‘35.5）’`返回浮点数35.5
	==float函数同样不能运算==

## 常用转译字符
- **续行符**：\\（位于行尾时）
	 **示例**：```
	    s1=‘Hello\
	    World！’```代码虽然在两行，但输出在一行
- **反斜杠符号**：\\\\（为了避免混淆）
- **单引号**：\\‘
- **双引号**：\\”
	 **示例**：
        `s2=’It’s a book.‘` *语法错误* 单引号不成对出现
        **修改1**：`s2=‘It\’s a book.’`
        **修改2**：`s2=“It’s a book.”` 
- **换行**：\\n
- **回车**：\\r
- **制表符**：\\t

## 子串截取
- **语法格式**：`s[beg:end]`
- **功能**：截取字符串string的beg到==（end-1）==的字符
- **省略**：
	 - *省略beg*：从字符串第一个字符开始截取 ，等价于s\[0:end]
	 - *省略end*：一直截取到最后一个字符（包含最后一个字符
	 - *省略beg和end*：截取整个字符串
- **下标索引**（给字符串的字符编号）：
    - 从前往后：0 1 2 3 4 ……==第一个为0==
    - 从后往前：…… -3 -2 -1 ==最后一个为-1==
- **示例**：**两种索引方式可以混用** 
```
s=‘欢迎学习Python语言程序设计！’
print（s[2:4]) #输出“学习” 
print(s[-3:-1]) #输出“设计”
print(s[2:-1]) #输出“学习Python程序设计”
```

## 截取单个字符
- **语法格式**：`s[idx]`， idx为要截取的字符的下标
- 只可以访问**不可以进行赋值**
- **示例**：
```
s=‘欢迎学习Python语言程序设计！’
print(s[2]) #输出“学”
s[2]=‘付’ #错误!!!
```

# List数据类型
## 概述
- 列表中可以包含多个元素，每个元素的类型可以任意
- 所有元素在一对\[]中，其中每两个元素之间用，隔开
- **空列表**：即\[]，不包含任何元素的列表
- **示例**：`ls=[1,2.5,'test',3+4j,True,[3,1.63],5.3]`

## 列表元素索引
- **索引方式**：从前往后、从后往前(==与字符串的索引类似==)
- **截取列表**：`ls[beg:end]`
	 - ==截取的语法也几乎和字符串的截取完全相同==
	 - 输出仍为一个==列表==
	 - end取不到，取到（end-1）
- **访问列表的单个元素**：`ls[idx]`
	 - 仍然和字符串类似
	 - 输出为一个==元素==，==不是列表==！！！
	 - **示例**：
		 `print(ls[2:3]) #输出“['test']”`
		 `print(ls[2]) #输出“test”`
- **元素修改**：`ls[idx]=value`
- **示例**：
```
ls=[1,2.5,'test',3+4j,True,[3,1.63],5.3]
ls[2]=15 #将下标为2的数据修改为15` ==15可以写成元素，也可以写成列表==
ls[2]=['program',23.15] #将下标为2的数据替换为['program',23.15]
ls[1:4]=['python',20] #将下标为1到3的数据替换为['python',20]
ls[0:2]=[] #将下标为0到1的数据替换为空列表，即删除前两个元素
```

# Tuple数据类型
## 概述
- 元组可以包含多个元素，元素类型可以不同
- 所有元素在一对（）中，其中每两个元素之间用，隔开
- **空元组**：即（），不包含任何元素的元组
- ==元组中的元素**不能修改**==

## 元组元素的索引
- 索引方式和列表完全相同
- **截取元组**：`t[beg:end]` 截取出来的是==元组==
- **访问元组的单个元素**：`t[idx]` 访问的是==元素==
- 字符串、列表和元组统称为**列表类型数据**，只有==列表==可以修改

# Set数据类型
## 概述
- 集合可以包含多个不同类型的元素，但集合中的元素**无序、互异且可哈希**
- **不可哈希**：列表、集合和字典 （==以上不可包含==） ^ae257b

## 创建集合
- 一对**大括号**中用**逗号**隔开：
	 **示例**：
	 `a={10,2.5,5.3,'test',3+4j,True,5.3,2.5}`
	 `print(a) #输出“{True,2.5,5.3,10,(3+4j),'test'}”`
- **set函数**
	 **格式**：`set([iterable])` 可迭代（iterable）对象指可以一次返回一个它的元素，如**字符串、列表、元组**
	 **示例**：
	 `b=set('hello')`
	 `print(b) #输出"{‘e’,'l','o','h'}"`
	 `c=set([10,2.5,5.3,'test',3+4j,True,5.3,2.5])`
	 `print(c) #输出"{True,2.5,5.3,10,(3+4j),'test'}"`
	 `d=set((10,2.5,5.3,'test',3+4j,True,5.3,2.5))`
	 `print(d) #输出"{True,2.5,5.3,10,(3+4j),'test'}"` ^a181bc
- **注意**
	 - 集合中元素不可通过下标访问（==无序==）
	 - 集合主要用于**并 交 差**等集合运算，以及基于集合的元素快速检索
	 - **创建空集合**：`set（）` *注意*：不可以用{}，因为创建的是**空字典**

# Dictionary数据类型
## 概述
- **无序**对象集合
- 一种映射类型， 每个元素是一个键（key）：值（value）对
- **键**必须**唯一**，不同元素的键不能相同
- 键必须==可哈希==，**不能是列表、集合、字典**
- **值**可以是**任意类型**
- **空字典**：{}
## 创建字典
 - **创建空字典**：（两种方法） ^90b6d8
	 - `a={}`
	 -  `b=dict()`
- **创建字典** ^25151e
	 - **方法一**：
		 `{k1:v1,k2:v2,...kn:vn} #ki和vi分别是每个元素的键和值`
		 **示例**：`a={'one':1,'two':2,'three':3}`
	- **方法二**：
		 `dict(**kwarg) #**kwarg是一个或多个赋值表达式， 中间用，隔开`
		 **示例**：`b=dict(one=1,two=2,three=3)`
	- **方法三**：
		 `dict(z) #z是zip函数的返回值`
		 **示例**：`c=dict(zip(['one','two','three'],[1,2,3]))`
	- **方法四**：
		 `dict（ls）#ls是元组的列表，每个元组包含两个元素，分别为键和值`
		 **示例**：`d=dict([('one',1),('two',2),('three',3)])`
	 - **方法五**：
		 `dict(dictionary) #dictionary是一个已有的字典`
		 **示例**：`dict({'one':1,'two':2,'three':3})`

## zip函数
- **功能**：将不同对象（可迭代对象：**字符串 列表 元组**）中对应的元素打包成==元组==

## 访问字典元素
- 通过**键**访问，且字典可进行嵌套
- **示例**：
```
	 info={'name':'张三','age':19,'score':{'python':95,'math':92}}
	 print(info['name']) #输出“张三”
	 print(info['age']) #输出“19”
	 print(info['score']) #输出“{‘python’：95，‘math’：92}”
	 print(info['score']['python']) #输出“95”
	 print(info['score']['math']) #输出“92”
```

# 占位运算符和算术运算符
## 占位运算符
- **功能**：在**字符串**中占位，表示不同类型的数据，实际数据在字符串外给出
- **常用占位符**
	 `%d` 有符号整型十进制数
	 `%f或%F` 有符号浮点型十进制数
	 `%s` 字符串
- **示例**：（精度指定 位数指定 空白填充\[只能填充0，其他无效]）
	 `print('%s上次的数学成绩%d,本次%d,成绩提高%f'%('小明',85,90,5/85))`
	 输出为 小明上次数学成绩85，本次90，成绩提高0.058824
	 `print('%5s上次的数学成绩%5d,本次%5d,成绩提高%.2f'%('小明',85,90,5/85))`
	  输出为 小明上次数学成绩   85（一共占5个字符），本次   90，成绩提高0.06（保留两位小数）
	 `print('%5上次的数学成绩%05d,本次%05d,成绩提高%08.2f'%('小明',85,90,5/85)`
	  输出为 小明上次数学成绩00085（一共占5个字符，用0填充空位），本次00090，成绩提高00000.06（一共占8个字符，保留两位小数）
- 为做区分`%%`表示一个%

## 算数运算符
- **加减乘除**：+ - * /
- **整除**：// 保留整数部分
- **模**：% 取余数
- **正号负号**：+ -
- **乘方**：**  x\*\*y x的 y次幂

# 赋值运算符、比较运算符和逻辑运算符
## 赋值运算符

- = 将左边的值赋给右边
- += `y+=x 等效于 y=y+x
- 加减乘除 整除 模 乘方同理

## 比较运算符
- == 等于
- != 不等于
- > 大于
- < 小于
- >= 大于等于
- <= 小于等于
- 符合时返回**True**，否则返回**False**

## 逻辑运算符
- **与**：and  `x and y`
- **或**：or     `x or y`
- **非**：not  `not xp`

# 位运算符
## 数制转换
- **十进制转二进制**：除基取余，把十进制数一直除以2，将得到的余数从**最低位**开始依次排列，得到对应的二进制数
- **二进制转十进制数**：按权重展开即可

## 位运算符
- &：按位与     `y&x`
- |   :  按位或     `y|x`
- ^  :按位异或   `y^x` (同0异1)
- <<:左移位      `y<<x` (右侧补0)
- >>:右移位      `y>>x` (左侧补0)
- ~  ：按位取反 `~x`

# 身份运算符和成员运算符
## 身份运算符
- is：`x is y` x和y对应同样的存储单元，返回True；否则返回False
- is not：`x is not y` x和y不对应同样的存储单元，返回True；否则返回False
- **示例**：
```
x,y=15,15
print(x is y) #输出“True”
print(x is not y) #输出“False”
print(x is 15) #输出“True” 数值型数据对应的数值相等就对应同样的存储单元
x,y=[1,2,3],[1,2,3]
print(x is y) #输出“False”
print(x==y) #输出“True”
print(x is [1,2,3]) #输出“False” 集合的值即使完全相同也对应不同的存储单元
x=y #赋值运算符运算后左右变量对应相同的存储单元
print(x is y) #输出“True”
```
## 成员运算符
- **用途**：判断可迭代对象（序列、集合或字典）中有没有某个个元素 ^e8bfc6
- **运算符**：
	 in：      `x in y` 元素x属于y时，返回True
	 not in：`x  not in y`
- **示例**
```
# 列表
x,y=15,['abc',15,True]
print(x in y) #输出True

# 元组
x,y=20,(20,'Python')
print(x in y) #输出True

# 集合
x,y=20,{15,20,25}
print(x in y) # 输出True

# 字符串
x,y='Py','Python'
print(x in y) # 输出True
# 要是原字符串的子串，如to就会返回False

# 字典
x,y='one',{'one':1,'two':2,'three':3}
print(x in y) # 输出True
print(1 in y) # 输出False
# 判断字典时，判断的实际是字典中！某个元素的键!
```

# 序列运算符和运算符优先级
## 序列运算符
- +（拼接）：`x+y`
  **示例**：
  ```
     x,y=[12,False],['abc',15,True]
	 z=x+y
	 print(z) #输出"[12,False,'abc',15,True]"
	 # 字符串同理
  ```
- \* （重复）：`x*n` n为重复的次数
   **示例**:
	```
	s='我学习Python‘
	s_3=s*3
	print(s_3) # 输出“我喜欢学习Python我喜欢学习Python我喜欢学习Python”
   ```

## 运算符优先级
![[Pasted image 20240705094352.png]]
**注**：=是从右结合运算符，再用相同优先级的运算符时，要从右往左进行计算

# 条件语句
##  流程图
- **开始 结束**：圆角矩形或圆 ==必须有一个开始和结束==
- **数据处理**：矩形
- **条件判断**：菱形 ==唯一可以有多个分支，，注意表明条件==

## 条件语句语法
- **if elif else**：最简单的语句只有if，elif和else都是可选项 ==条件后面要有冒号==
- **格式**：
```
	if 条件1:
		语句序列1
	elif 条件2:
		语句序列2
	elif 条件n：
		语句序列n
	else：
		语句序列（n+1）
```
- **pass**：占位作用，执行时什么也不做 ==在开发过程中，暂代还未完成的语句序列==

# 循环语句
## 循环语句语法
## for循环
- **作用**：遍历可迭代对象中的每一个元素 ^183fd5
- **格式**：
```
for 变量名 in 可迭代对象：
	语句序列
```
- **示例**1：依次访问可迭代对象中的每一个元素
```
ls = ['Python', 'C++', 'Java']
for k in ls:
	print(k)
```

- **示例**2：for遍历字典时，遍历的是字典的键
```
d = {'Python':1, 'C++':2, 'Java':3}
for k in d:
	print('%s:%d'%(k,d[k]))
```
## range函数
- **作用**：for循环需要遍历一个数列中的所有数字时，可利用range函数生成一个==可迭代对象==
- **语法**：`range([beg,]end[,step])`
- **示例**：
```
print(list(range(1,5,2))) #输出"[1,3]" 不包含end，beg默认时是0
print(list(range(5,-1,-2))) #输出"[5,3，1]"
print(list(range(1,5))) #输出"[1,2,3,4]"
print(list(range(5))) #输出"[0,1,2,3,4]"
```
- **示例**：for循环实现1到n的求和
```
n= eval(input("请输入一个大于0的整数")) #input返回字符串，通过eval函数或int函数转化为整数
sum=0
for i in range(1,n+1)
	sum+=i
	print(sum)
```
## while循环
- **语法**：
```
while 循环条件:
	语句序列
```
- **示例**：while循环实现1到n的求和
```
n = eval(input("请输入一个大于0的整数"))
i,sum = 1, 0
while i <= n:
	sum += i
	i += 1
print(sum)
```
## 索引
### len函数+循环实现
- **len函数**：获取可迭代对象中元素的数量
- **示例**：
```
ls = ['Python', 'C++', 'Java']
for k in range(len(ls))
	print(k, ls[k])
```
输出为
```
0 Python
1 C++
2 Java
```
### enumerate函数实现
- **enumerate函数**：输入可迭代对象，返回索引序列（索引+对应的元素）
- **示例**：
```
ls = ['Python', 'C++', 'Java']
for k, v in enumerate(ls, 1): #索引从1开始（默认从0开始）
	print(k, v)
```
输出为
```
0 Python
1 C++
2 Java
```

# break、continue和else
## break和else
- **break**:跳出循环
- **else**：==for循环遍历完列表所有元素、while循环条件为False，或跳出循环后==，执行else分支
- **示例**：
```
n=eval(input('请输入一个大于1的整数：'))
m=int(n**0.5)
for i in range(2,m+1):
	if n%i=0:
	print('%d不是素数'%n)
	break
else：
	print('%d是素数'%n)
```
## continue
- **continue**：结束==本次==循环，开始下次循环
- **示例**：
```
sum = 0
while True: #永真循环，只能通过break跳出循环
	n = eval(input('请输入一个整数（输入0结束程序）：'))
	if n == 0:
		break
	if n%3 != 0:
		continue 转到第2行
	sum+=n
print('所有输入的数中，所有是3的倍数的整数之和为:%d'%sum)
```

# 函数
## 形参与实参
- **定义函数**：
```
def 函数名(形参1， 形参2，形参3):
	函数体
```
- **形参**：==定义函数时==，函数名后小括号内的参数列表
- **实参**：==调用函数时==，函数名后小括号内的参数列表（ps.调用函数时，实参被传递给形参）
- **注**：函数体内对形参的值进行修改时，不会改变实参的值；若实参是==列表==等对象时，对形参的值进行修改，会影响实参的值
- **示例**：
```
def ModifyVal(x, y):
	x = y
def ModifyListElement(ls, idx, val): #idx为列表中元素的下标
	ls[idx] = val
a, b = 5, 10
print(a, b) #输出“5 10”
ModifyVal(a, 10)
print(a, b) #输出“5 10”
c = [1, 2, 3]
print(c) #输出“[1, 2, 3]"
ModifyVal(c,[3,2,4])
print(c) #输出“[1, 2, 3]”
ModifyListElement(c, 1, 5)
print(c) #输出“[1, 5, 3]
```
## 默认参数
- **格式**：==带默认值的形参必须在后==
```
def StudentInfo(name, country = '中国',level):
	函数体
```
## 调用函数时体现形参、实参关系的方法
- **位置参数**：括号内实参和形参的位置一一一对应
- **关键词参数**:调用函数时通过形参的关键词将实参传递给形参
	`StudentInfo(country = '美国', name = '大卫', level = '优秀')`
- **注**：位置参数与关键词参数可以混用，但关键词参数必须在后
	`StudentInfo( name = '大卫', '美国')`==会报错==
	`StudentInfo('大卫', '良好'， country = '美国')`==会报错，因为country被赋予了多个值，混用时位置参数并不会跳过已经通过关键词赋值的参数==
## 不定长参数
- **带不定长参数函数的定义方式**：
```
def 函数名([普通形参列表,]*不定长参数名,[普通形参列表])：
	函数体
或
def 函数名([普通形参列表,]**不定长参数名)：
	函数体
```
**注**：
	\*不定长参数名对应一组位置参数，会封装成==元组==
	\*\*不定长参数名对应一组关键词参数，会被封装成==字典==
- **示例**：
```
def StudentInfo1(name, *args):
	print('姓名:', name, '，其他：', args)
def StudentInfo2(name, **args):
	print('姓名:', name, '，其他：', args)
def StudentInfo3(name, *args, country = '中国'):
	print('姓名:', name, '国家：', country, '，其他：', args)
StudentInfo1('李晓明','良好','中国')
StudentInfo2('李晓明',中文水平 = '良好',国家 = '中国')
StudentInfo3('李晓明',19,'良好')
StudentInfo3('李晓明',19,'良好', country = '中国')

#输出依次为
姓名: 李晓明 ，其他： ('良好', '中国')
姓名: 李晓明 ，其他： {'中文水平': '良好', '国家': '中国'}
姓名: 李晓明 国家： 中国 ，其他： (19, '良好')
姓名: 李晓明 国家： 中国 ，其他： (19, '良好')
```
## 拆分参数列表
- **列表、元组**拆分出的结果可作为**位置参数**
- **字典**拆分出的结果可作为**关键词参数**
- **示例**：
```
def SumVal(*args):
	sum = 0
	for i in args:
		sum+=i
	print('求和结果为:', sum)
ls = [3, 5.2, 7, 1]
SumVal(*ls) #等价于SumVal(ls[0], ls[1], ls[2], ls[3])
```

```
def StudentInfo(name, chineselecel, country):
	print('姓名：%s, 中文水平：%s, 国家：%s'%(name, chineselevel, country))
d = {'country':'中国','chineselevel':'良好','name'='李晓明'}
StudentInfo(**d) #等价于StudentInfo(country = '中国', chineselevel='良好', name = '李晓明')
```
## 返回值
- **return**：将函数的运算结果返回到==调用函数的位置==
- 默认是`return None`(或者直接写为`return`)
- 返回字符串、列表、元组
```
return 'string' #返回字符串用‘’或“”
return [element1, element2, element3] #将三个元素封装成列表
return (element1, element2, element3) #将三个元素封装成元组

return 1,2,3 #返回3个数值数据，实际会封装成元组(1, 2, 3)返回
```

## 模块与import语句
- **语法格式**：
```
import module1 #导入模块module1.py
import module2
import module3
import module4
或
import module1, module2, module3, module4
```
- **调用模块中函数格式**
```
import fibo
fibo.PrintFib(5) #调用fibo函数中的PrintFib函数
```
 **注**：import时模块中的非函数模块会被执行
## 全局变量_name_
- 每个模块都有一个全局变量_name_
- **作用**：获取当前模块的名称
- **单独执行时**， \_name_的值为\_main_
- **作为模块导入，调用执行时**， \_name_的值为==模块的名字==（没有__)
## from … import
- **语法格式**：
```
from 模块名 import 标识符1,标识符2,……,标识符N
```
- ==不用写模块名==直接调用模块中的函数
```
from fibo import PrintFib
PrintFib(5)
```
- 导入模块中**所有标识符**（非函数模块不会被执行）
```
_all_ = ['PrintFib'] #可对_all_列表进行修改，以达到部分导入的目的
from fibo import * #导入列表_all_中存在的标识符，默认为所有

```
- 修改**调用的模块名**
```
import fibo as f #导入模块fibo，并为其起别名f
f.PrintFib(5) #调用fibo模块中的PrintFib函数
```
- 修改**调用的标识符名**
```
from fibo import PrintFib as pf #导入模块fibo中的标识符Print
Fib，并为其起别名pf
pf(5) #调用PrintFib函数
```
## 包
- **包**：模块的文件夹
- **定义包**：创建一个文件夹，并在文件夹下创建一个_init_.py文件（类似于文件夹，在一个包中还可以定义一个子包，子包中也是默认会创建一个_init_.py文件）
- **一个包的结构示例**：
```
sound #包
	_init_.py
	formats #子包
		_init_.py
		wavread.py
		aiffread.py
		auread.py
		...
```
- **包的导入与调用**
```
# 使用import导入
import sound.effects.echo #导入sound包的effects子包中的echo.py模块
sound.effects.echo.echofilter() #调用时要制定完整的包名和模块名

# 使用from import导入模块
from sound.effects import echo
echo.echofilter() #调用时只加上模块名即可

# 使用from import直接导入模块中的标识符
from sound.effects.echo import echofilter
echofilter() #调用时写函数名即可
```
- **层次关系**：包 - 模块（.py）- 标识符（函数）
## 第三方模块的获取与安装
- **安装指令**：`pip intall numpy`(在命令行中)
- **指定下载地址**：`pip intall numpy -i (指定的下载地址)`
## 局部变量
- **定义**：函数中定义的变量（包括形参）
- **作用域**：定义局部变量的位置到函数结束的位置
## 全局变量
- **定义**：所有函数外定义的变量
- ==所有函数==中都可以使用
## global关键字
- **作用**：声明在函数中使用的变量是全局变量
- **示例**：
```
def GlobalVar():
    global x
    print(x)
```
## nonlocal关键字
- **作用**：声明内层函数中的变量是外层函数的局部变量，而不是一个新的局部变量
- **示例**：
```
def outer():
    x=10
    def inner()
        nonlocal x #inner和outer中的x为同一个局部变量
        x=20
        print(x)
    inner()
    print(x)
```
# 类
## 类的定义
- **面向对象的基本观点**是一切系统都是由==对象==构成的
- **类**对应==数据类型==，**对象**对应==变量==
- **类的定义**：包含属性（哪些类型的数据）和方法（数据处理）==封装性：封装了数据和操作==
- **创建类语法格式**：
```
class 类名:
	语句1
	语句2
	……
	语句N
```
- **示例**：定义一个空类
```
class Student:
	pass #空语句，起占位作用，表示Student类中没有任何属性和方法
```
- **创建类的实例对象语法格式**：`实例对象名 = 类名(参数列表)`
- **示例**：
```
class Student:
	pass
if __name__ == '_main_':
	stu1 = Student() #创建一个Student类的对象，并将其赋给变量stu1 
```
## 类属性定义及其访问
- **语法格式**：
```
class Student:
	name = 'Unknown' #定义Student类中有一个name属性
```
- **访问类的属性**：类名.属性名 or 对象名.属性名
- **示例**：
```
class Student:
	name = 'Unknown'
if __name__ == '_main_':
	print(Student.name) #通过类名访问类的属性，输出“Unknown”
	stu1 = Student() #创建一个类Student的实例对象stu1 
	stu2 = Student()
	print(stu1.name,stu2.name) #通过对象名访问类的属性，输出“Unknown Unknown”
	Student.name='未知' #将Student的类属性name赋为“未知”,类和对象的属性都发生变化
	stu1.name='李晓明' #将stu1的name属性赋值为“李晓明” 
	stu2.name='马红' #将stu2的name属性赋值为“马红”，对对象的属性进行赋值后，对象和类的属性就相互独立了，修改任意一者都不会影响另一者
```
## 常用内置方法
### \_\_str\_\_
- **作用**：调用format()和print()函数时，自动执行（==返回值必须是字符串==）
- **示例**：
```
class Complex:
	def __init__(self, real, image):
		self.real = real
		self.image = image
	def __str__(self):
		return str(self.real)+'+'+str(self.image)+'i'
if __name__ == '__main__':
	c = Complex(3, 5)
	print(c) #输出“3+5i”
```
## 比较运算的内置方法
- **功能描述**：
![[Pasted image 20240719101118.png]]
- **示例**：
```
class Student:
	def __init__(self, name, age):
		self.name = name
		self.age = age
	def __le__(self, other):
		return self.age<=other.age
if __name__ == '__main__':
	stu1 = Student('李晓明', 19)
	stu2 = Student('马红', 20)
	print('马红的年龄小于等于李晓明的年龄：', 'stu2<=stu1') #输出“马红的年龄小于等于李晓明的年龄：False”
```

## 内置函数
### isinstance
- **作用**：判断一个==对象==所属的类是否是==指定的类或指定类的子类==
- **示例**：`isinstance(stu,Person) #形参分别为对象和类，是的时候返回True`
### issubclass
- **作用**：判断一个==类==是否是==另一个类的子类==
- **示例**：`issubclass(Student, Person) #形参为两个类，是的时候返回True`
### type
- **作用**：获取一个对象所属的类
- **判断一个对象的类型是否是==指定类**==：`type(对象名) == 类名 #属于时返回True`
## 普通方法
- **类中的方法（函数）**：普通方法和内置方法
- **普通方法定义要求**：使用def进行定义，第一个参数必须为方法内所要使用的实例对象（一般命名为self）
- **调用类的普通方法的格式**：`实例对象.方法名(实参列表)`==调用时，self不用传入参数==
- **示例**：
```
class Student: #定义Student类 
	name='Unknown' #定义Student类中有一个name属性 
	def SetName(self, newname): #定义类的普通方法SetName 
		self.name=newname #将self对应实例对象中的name属性值赋为newname 
	def PrintName(self): #定义类的普通方法PrintName 
		print('姓名：%s'%self.name) #输出self对应实例对象中的name属性值 
if __name__=='__main__': 
	stu1=Student() #定义Student类对象stu1 
	stu2=Student() #定义Student类对象stu2 
	stu1.SetName('李晓明') #通过stu1对象调用SetName方法 
	stu2.SetName('马红')
	stu1.PrintName() #通过stu1对象调用PrintName方法 
	stu2.PrintName()
```
- **注**：类的普通方法==不能通过类名直接调用==
## 构造方法（炉石传说里的战吼）
- **构造方法的方法名**：`__init__` （==左右各两个下划线==）
- 构造方法会在==一个类对象被创建时自动执行==
- **示例**：
```
class Student:
	def __init__(self, name = '未知'): #_init_必有一个形参self，用以指定方法所作用的实参对象
		self.name = name
stu = Student('李明') #创建一个实例对象stu，并执行_init_函数，将stu的name属性赋值为“李明”（默认为未知）
```
## 析构方法（炉石传说里的亡语）
- **析构方法的方法名**：`__del__`
- 构造方法会在==一个类对象被销毁时自动执行==
- **对象销毁的三种情况**：
	 1. 局部变量作用域结束
	 2. 使用del函数删除对象
	 3. 程序结束时，所有的对象都会被销毁
- **示例**：
```
class Student:
	def __init__(self,name):
		self.name = name
		print('%s have been created'%self.name)
	def __del__(self):
		print('%s have been deleted'%self.name)
def func(name):
	stu = Student(name)
if __name__ == '__main__'
	stu1 = Student('李晓明')
	stu2 = Student('马红')
	stu3 = stu2 #多个变量对应同一片内存空间时，只有所有变量都被删除时，才会自动执行析构方法
	del stu2
	func('张刚') #执行构造方法后立刻执行析构方法，因为stu为局部变量，函数结束后其作用域结束，从而被销毁
	del stu3 #此时才会执行马红的析构方法
	stu4 = Student('刘建') #程序结束，对象李晓明和刘建依次被销毁，执行析构方法
```
## 继承
- **概念**：基于已有的类（称作父类、基类或超类）创建新的类（子类）
- **特性**：子类会继承父类中定义的所有属性和方法，另外也可在子类中增加新的属性和方法
- **分类**：
	 1. 单继承：一个子类只有一个父类
	 2. 多重继承：一个子类有多个父类
## 子类的定义
- **语法格式**：
```
class 子类名(父类名1, 父类名2, ……, 父类名M):
	语句1
	语句2
```
- **示例**：
```
class Person:
	def SetName(self, name):
		self.name = name
class Student(Person):
	def SetSno(self,sno):
		self.sno = sno
if __name__ == '__main__':
	stu = Student()
	stu.SetSno('1810100')
	stu.SetName('李晓明') #调用Student类从Person类中继承过来的方法SetName
```
## 方法重写
- **方法重写**：子类可以重新定义从父类继承过来的方法
- **示例**：
```
class Person:
	def __init__(self, name):
		self.name = name
	def PrintInfo(self):
		print(self.name)
class Student(Person):
	def __init__(self, sno, name):
		self.sno = sno
		self.name = name
	def PrintInfo(self):
		print(self.sno, self.name) #重写了父类Person中的PrintInfo方法
def PrintPersonInfo(person):
	person.PrintInfo()
if __name__ == '__main__':
	p = Person('李晓明')
	stu = Student('1810100', '李晓明')
	p.PrintInfo() #执行Person类中的PrintInfo方法
	stu.PrintInfo() #执行Student类中的PrintInfo方法
	PrintPersonInfo(p) #执行Person类中的PrintInfo方法
	PrintPersonInfo(stu) #执行Student类中的PrintInfo方法
```
## 鸭子类型
- **作用**：不固定传入实参的类型，根据传入的数据进行自适应的调整
- **示例**：
```
class Person:
	def CaptureImage(self):
	print('Person类中的CaptureImage方法被调用')
class Camera:
	def CaptureImage(self):
	print('Camera类中的CaptureImage方法被调用')
def CaptureImageTest(arg):
	arg.CaptureImage() #arg即为鸭子类型
if __name__ == '__main__':
	p = Person()
	c = Camera()
	CaptureImageTest(p) #执行Person类中的CaptureImageTest方法
	CaptureImageTest(c) #执行Camera类中的CaptureImageTest方法
```
- 通过鸭子类型实行自适应->==多态性==
## super方法
- **作用**：获取父类的代理对象，根据该代理对象调用被重写的父类方法（调用父类中的方法）
- **语法格式**：`super([类名[,对象名或类名]])`
- **示例**：
```
class Person:
	def __init__(self, name):
		print('Person类构造方法被调用')
		self.name = name
class Student(Person):
	def __init__(self,sno,name):
		print('Student类构造方法被调用')
		super.__init__(name) #调用父类Person的构造方法
		self.sno = sno
class Postgraduate(Student):
	def __init__(self,sno,name,tutor):
		print('Postgraduate类构造方法被调用')
		super().__init__(sno,name) #调用父类Student的构造方法
		self.tutor = tutor
if __name__ == '__main__'
	pg = Postgraduate('1810100', '李晓明', '马红') #依次调用Postgraduate Student Person的构造方法
	print('学号:%s,姓名：%s,导师：%s'%(pg.sno, pg.name, pg.tutor))
```
## 私有属性
- **定义**：*类内可以直接访问*，类外无法直接访问的属性
- **私有属性命名**：以\_\_(两个下划线)开头
- **示例**：
```
class Student: 
	name='未知' 
	__id='未知' #定义Student类中有一个__id私有属性
	def SetInfo(self,newname,newid): 
		self.name=newname
			self.__id=newid
	def PrintInfo(self): 
		print('姓名：%s，身份证号：%s'%(self.name,self.__id))
	if __name__=='__main__’: 
		stu=Student()
		stu.SetInfo('李晓明','120XXXXXXXXXXXXXXX') #通过stu调用
		stu.PrintInfo() #通过stu对象调用PrintInfo方法 
		#print('身份证号：%s'%stu.__id) #取消前面的注释，则程序会报错 
```
- **类外访问私有属性的方法**：私有属性名前加上“\_类名” ==一个下划线==
	即可将上述最后一行代码改为`print('身份证号：%s'%stu._Student__id)`
## 类方法
- **类方法的特点**：既可以通过类名调用，也可以通过实例对象调用。方法的第一个参数是==类本身==
- **使用方法**：使用`@classmethod`修饰
- **示例**：
```
class Complex:
	def __init__(self,real = 0, image = 0):
		self.real = real
		self.image = image
	@classmethod
	def add(cls, c1, c2): #第一个参数是类本身
		print(cls)
		c = Complex()
		c.real = c1.real + c2.real
		c.image = c1.image + c2.image
		return c
if __name__ == '__main__':
	c1 = Complex(1,2.5)
	c2 = Complex(2.2,3.1)
	c = Complex.add(c1, c2) #通过类名、实例对象调用方法都可
	print('c1+c2的结果为%.2f+%.2fi'%(c.real, c.image))
```
## 静态方法
- **静态方法的特点**：既可以通过类名调用，也可以通过实例对象调用。==无类方法的第一个参数==
- **使用方法**：使用`@staticmethod`修饰
- - **示例**：
```
class Complex:
	def __init__(self,real = 0, image = 0):
		self.real = real
		self.image = image
	@staticmethod
	def add(c1, c2): #无类方法中的第一个参数
		c = Complex()
		c.real = c1.real + c2.real
		c.image = c1.image + c2.image
		return c
if __name__ == '__main__':
	c1 = Complex(1,2.5)
	c2 = Complex(2.2,3.1)
	c = Complex.add(c1, c2) #通过类名、实例对象调用方法都可
	print('c1+c2的结果为%.2f+%.2fi'%(c.real, c.image))
```
# 序列、集合和字典
## 可变类型和不可变类型
- **可变类型**：列表、字典
- **不可变类型**：数字、字符串、元组
- **区分标准**：保存的元素值是否可以做修改
- **示例**：
```
#数字
n1, n2 = 1, 1
print(id(n1), id(n2)) #两个相同的内存地址
n2 = 3
print(id(n1), id(n2)) #n2的内存地址被修改
n1 = 3
print(id(n1), id(n2)) #n1的内存地址被修改，且与n2相同

#字符串与数字相同
#元组
t1, t2 = (1, 2, 3), (1, 2, 3)
print(id(t1), id(t2)) #即使t1和t2对应的值相同，但也对应不同的内存地址
t2 = (1, 2, 3)
print(id(t1), id(t2)) #t2的内存地址变为另一个新的内存地址

#列表
ls1, ls2 = [1, 2, 3], [1, 2, 3]
print(id(ls1), id(ls2)) #两个不同的内存地址
ls2[1] = 5
print(id(ls1), id(ls2)) #修改列表中的元素，列表的内存地址不变，可变类型的特点
ls2 = [1, 2, 3]
print(id(ls1), id(ls2)) #ls2的内存地址变为一个新的内存地址，因为这相当于创建了一个新的对象
```
## 创建列表和拼接列表
- **list方法创建列表对象**：根据==元组==创建列表对象
- **示例**：
```
ls = list((1, 'one', '--'))
print(ls)
print(ls[0], ls[-1]) #输出第一个和倒数第一个元素
print(ls[0:-1]) #输出第一个到倒数第二个元素
```
- **拼接列表**： [[#序列运算符和运算符优先级]]
## 复制列表元素
- **问题**：通过将旧列表赋值给新列表的方法创建列表时，新列表和旧列表对应同一个内存空间，两者并不独立，修改其中的一个时，另一个也会被修改
- **通过元素截取实现列表元素的复制**：
```
ls1 = [1,2,3]
ls2 = ls1[:]
print(ls1,ls2) #相同的元素值
print(id(ls1),id(ls2)) #不同的内存地址
ls1[1]=5
print(ls1,ls2) #ls2的元素不再受影响，此时ls1和ls2相互独立
```
- **元素截取复制法的弊端**：当列表中有元素为列表时，通过元素截取法复制出的列表中的列表元素和原来列表中的列表元素对应的内存地址相同
```
ls1=[1,[2,3]]
ls2=ls1[:]
print(id(ls1[1]),id(ls2[1])) #ls1[1]和ls2[1]对应的内存地址相同
```
- **通过deepcopy函数实现列表元素的复制**：
```
import copy
ls1=[1,[2,3]]
ls2=copy.deepcopy(ls1)
print(id(ls1[1]),id(ls2[1])) #ls1[1]和ls2[1]对应的内存地址不同
```
## 列表元素的查找、插入和删除
### 查找
- **index方法**：根据指定值查找第一个匹配的列表元素的位置
- **语法格式**：`ls.index(x)` ls为要进行查找操作的列表对象，x为要查找的元素值，返回第一个值为x的元素的位置编号
- **示例**：
```
ls=[1,3,5,3]
print(ls.index(3)) #输出“1”
```
### 插入
- **insert方法**：将元素插入到列表的指定位置
- **语法格式**：`ls.insert(index,x)`
- **append方法**：在列表的最后添加新元素
- **语法格式**：`ls.append(x)`
- **示例**：
```
ls=[1,2,3]
ls.insert(0,'Python')
print(ls) #输出“['Python',1,2,3]”
ls.append([5,10])
print(ls) #输出“['Python',1,2,3,[5,10]]”
```
### 删除
- **del方法**：删除某个变量或列表中的某个元素
- **删除列表中连续多个元素**：截取列表中连续多个元素并将其赋值为空列表
- **remove方法**：删除特定的元素
- **语法格式**：`ls.remove('a')` 移除ls列表中的'a'元素
- **示例**：
```
ls=[0,1,2,3,4,5,6,7,8,9]
del ls[8]
print(ls) #输出“[0,1,2,3,4,5,6,7,9]”
ls[1:6]=[]
print(ls) #输出“[0,6,7,9]”
```
### 列表元素的最值、出现次数和列表长度
### 最值
- **max和min方法**：获取一个列表中最大元素和最小元素的值
- **语法格式**：`max(ls) min(ls)`
- **示例**：
```
ls=[23,56,12,37,28]
print(max(ls)) #输出“56”
print(min(ls)) #输出“12”
```
### 统计元素出现次数
- **count方法**：统计某个值在列表中出现的次数
- **语法格式**：`ls.count(ls)`
- **示例**：
```
ls=[23,37,12,37,28]
print(ls.count(37)) #输出“2”
print(ls.count(56)) #输出“0”
```
### 计算列表长度
- **len方法**：获取一个列表中包含元素的个数
- **语法格式**：`len(ls)`
- **示例**：
```
ls=[23,37,12,37,28]
print(len(ls)) #输出“5”
```
## 列表元素的排序
- **sort方法**：对列表中的元素按照指定规则进行排序
- **语法格式**：`ls.sort(key=None,reverse=False)` key可接受一个函数，为排序时比较的规则；reverse代表降序，默认为升序
- **示例**：
```
class Student:
	def __init__(self,sno,name)
		self.sno=sno
		self.name=name
	def __str__(self)
		return 'StudentNumber:'+self.sno+',Name:'+self.name
if __name__=='__main__':
	ls1=[23,56,12,37,28]
	ls1.sort(reverse=True)
	print(ls1) #输出“[12,23,28,37,56]”
	ls2=[Student('1810101','Li Xiao Ming'),Student('1810100','Ma Hong'),Student('1810102','Zhang Gang')]
	ls2.sort(key=lambda stu:stu.sno) #按照列表元素实例对象的学号进行排序
	for stu in ls2:
		print(stu)
		#输出：
		#StudentNumber:1810100,Name:Ma Hong
		#StudentNumber:1810101,Name:Li Xiao Ming
		#StudentNumber:1810102,Name:Zhang Gang
# 按学号排序的另一种实现方法
def GetStuSno(stu):
	return stu.sno
ls2.sort(key=GetStuSno)
```
## 元组的操作
- **使用tuple方法创建元组**：`t = tuple([1,'one','--'])`
- **使用()创建单个元素的元组注意事项**：
```
t1 = (15)
t2 = (15,) #加上一个逗号，创建的才是元组
print(type(t1)) #<class 'int'>
print(type(t2)) #<class 'tuple'>
```
- ==元组中的元素值不允许修改==
- max函数 min函数获取元组中的最大 最小元素
## 集合的创建和插入元素
### 创建
- ==只能用[[#^a181bc |set函数]]创建新几何==
- *集合会自动过滤重复值的元素*
### 插入元素
- **add方法**：插入的元素x必须是[[#^ae257b |可哈希对象]]（除了列表 集合 字典）
- **语法格式**：`s.add(x)` 把x作为一个新的元素插入到集合中
- **update方法**：插入的元素x必须是[[#^e8bfc6 |可迭代对象]]（字符串 列表 集合 字典）
- **语法格式**：`s.update(x)` 把x==拆分成多个元素==后，插入到集合中
- **示例**：
```
s1 = set([1,2])
s2 = set([1,2])
s1.add('Python')
s2.update('Python')
print(s1) #输出“{1,2,'Python'}”
print(s2) #输出“{1,2,'P','y','t','h','o','n'}”
s1.add([4,5]) #会报错，因为列表为不可哈希对象
s2.update(3) #会报错，因为整型数字为不可迭代对象
```
## 集合的运算 
- **交集**：`s1.intersection(s2)`
- **并集**：`s1.union(s2)`
- **差集**：`s1.difference(s2)` s1中有，s2中没有的元素组成的集合
- **对称差集**：`s1.symmetric_difference(s2)` s1中没有或s2中没有组成的集合
- 以上运算均不会改变s1,s2的值，只会返回相应的集合运算结果
- **示例**：
```
s1 = set([1,2,3])
s2 = set([2,3,4])
s3 = s1.intersection(s2) #{2,3}
s4 = s1.union(s2) #{1,2,3,4}
s5 = s1.difference(s2) #{1}
s6 = s1.symmetric_difference(s2) #{1,4}
```
- **子集**：`s1.issubset(s2)` s1是s2的子集时返回True，否则返回False
- **父集**：`s1.issuperset(s2)` s1是s2的父集时返回True，否则返回False
## 字典的创建和初始化
- [[#^25151e |创建字典]]
- [[#^90b6d8 |创建空字典]]
- **初始化字典元素**：fromkeys方法
- **语法格式**：`d.fromkeys(seq[,value])`seq为键序列；value为值序列，默认为None
- **示例**：
```
d1 = {}.fromkeys(['sno','name','major'])
d2 = dict().fromkeys(['sno','name','major'],'Unknow')
# d1 = {'sno':None,'name':None,'major':None}
# d2 = {'sno':'Unknown','name':'Unknown','major':'Unknown'}

d1 = dict(age=18)
print(d1)
d2 = d1.fromkeys(['sno','name','major']) #原有的元素会被清除；不会修改d1的值，只会返回初始化后的值
print(d2) #d2中有三个元素
#d1中仍然是只有一个元素
```
## 字典元素的修改、插入和删除
### 修改和插入
- 给指定键的元素赋值时，如果**键在字典中已存在**，则会==对键对应的元素值做修改==；如果**键在字典中不存在**，则会==在字典中插入一个新的元素==
- **update方法一次修改或插入多个元素**
- **语法格式**：
```
d.update(d2) #用另一个字典对象d2的元素修改或插入字典d
d.update(键1=值1,键2=值2,……,键N=值N)
```
- **示例**：
```
stu = dict(sno='1810101')
print(stu) #{'sno':'1810101'}
stu['sno']='1810100'
print(stu) #{'sno':'1810100'}
stu['name']='李晓明' #在字典中插入一个新的元素
print(stu) #{'sno':'1810100','name':'李晓明'}

stu.update({'name':'马红','age':19})
print(stu) #{'sno':'1810100','name':'马红','age':19}
stu.update('name'='张刚','major'='计算机')
print(stu) #{'sno':'1810100','name':'张刚','age':19,'major':'计算机'}
```
### 删除
- **pop方法**：从字典中删除键为key的元素，并返回该元素的值；该元素不存在时，返回default参数的值
- **语法格式**：`d.pop(key[,default])`
- **示例**：
```
d=dict(sno='1810100',name='李晓明',age=19)
print(d) #{'sno':'1810100','name':'李晓明','age':19}
del d['age']
name = d.pop('name')
print(name) #李晓明
print(d) #{'sno':'1810100'}
major=d.pop('major','Not found')
print(major) #Not found
```
## 字典的浅拷贝和深拷贝
### 浅拷贝
- **作用**：返回一个对字典d进行浅拷贝得到的新字典`d.copy()`
- **示例**：
```
stu1={'name':'李晓明','age':19,'score':{'python':95,'math':92}}
stu2=stu1
stu3=stu1.copy()
print(id(stu1),id(stu2),id(stu3)) #stu1和stu2对应同一个内存地址，stu3不同，但字典中的可变类型元素对应的地址相同
```
- 对应同一片内存空间意味着修改其中之一会影响另一个
### 深拷贝
- 拷贝得到的新字典完全独立（**包括字典中的可变类型元素**）
- **语法格式**：`copy.deepcopy(d)`
## 判断字典中是否存在键及拼接两个字典
### 判断字典中是否存在键
- **get方法**：判断是否存在键为key的元素的值并返回该值；若不存在，则返回default的值
- **语法格式**：`d.get(key,default=None)`
### 拼接两个字典
- **方法1**：`dMerge=dict(d1,**d2)`
- **方法2**:
```
dMerge=d1.copy()
dMerge.update(d2)
```
## 字典的其他常用操作
- **计算字典中元素的个数**：`len(d)`
- **清楚字典中的所有元素**：`d.clear()`
- **获取字典中的键的集合**：`d.keys()` 返回`dict_keys(所有键组成的一个列表)`'
- **示例**:
```
d = dict(sno='1810100',name='李晓明')
print(d.keys())
```
-  **获取字典中的值的集合**：`d.values()` 返回`dict_values(所有值组成的一个列表)`'
- **获取地点中元素数组**：items方法可返回按（键，值）方式遍历的对象
- **语法格式**：`d.items()`
- **示例**：
```
d=dict(sno='1810100',name='李晓明')
for key,value in d.items()：#必须有key和value两个变量
	print(key,value)
#输出:
#sno 1810100
#name 李晓明
```
## 切片和列表生成表达式
### 切片
- 从序列对象中取一部分生成新的序列对象
- **示例**：
```
ls=list(range(0,20))
print(ls1) #[0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19]
ls2=ls1[3:10:2] #下标3到9，步长为2
print(ls2) #[3,5,7,9]
ls3=ls1[-1:-11:-3] #最后一个到倒数第十个，步长为3
print(ls3) #[19,16,13,10]
```
### 列表生成表达式
- 可使用**for if以及一些运算**生成列表中的元素
- **示例**：
```
ls=[x*x for x in range(10)]
print(ls) #[0,1,4,9,16,25,36,49,64,81]
ls=[x*x for x in range(10) if x%2!=0]
print(ls) #[1,9,25,49,81]
#列表表达式也支持多层循环的形式
snolist=['1810101','1810102','1810103']
namelist=['李晓明','马红','张刚']
ls=['学号：'+sno+',姓名：'+name for sno in snolist for name in namelist] #列表中共会有9个元素
```
## 生成器
- **作用**：不用一次性生成大量元素保存在列表中，避免占用大量的内存空间
- **第一种生成器**：将==列表生成表达式==中的中括号\[]换为小括号()即可
- **示例**：
```
g(x*x for x in range(10))
print(type(g)) #<class 'generator'>
for i in g:
	print(i, end='')
```
- **第二种生成器**：利用==yield关键字==
- **示例**：
```
def faclist(n):
	result = 1
	for i in range(2,n+2):
		yield result #遇到yield时暂停执行并返回result，下次执行时继续从此处开始
		result*=i
for i in faclist(10):
	print(i,end='')
```

## 迭代器
- **可迭代对象**：可直接使用for循环遍历的对象
- **迭代器**：可通过next函数不断获取下一个值得对象（==并不是所有可迭代对象都是迭代器==）
- **isinstance方法可判断可迭代对象或迭代器**
- **示例**：
```
from collections.abc import Iterable,Iterator
ls = [1,2,3,4,5]
g=(x for x in range(1,6))
print(isinstance(ls,Iterable)) #True
print(isinstance(g,Iterable)) #True
print(isinstance(ls,Iterator)) #False 可迭代但不是迭代器 
print(isinstance(g,Iterator) #True
```
- **iter函数**：对于可迭代对象 ，通过iter函数得到迭代器
- **示例**：
```
from collections.abc import Iterator
ls = [1,2,3,4,5]
it = iter(ls)
print(isinstance(it,Iterator)) #True
```
- **next函数**：对于迭代器，不断获取下一个元素；当元素获取完再调用会引发StopIteration异常
- **示例**：
```
g = (x for x in range(1,3))
print(next(g)) #1
print(next(g)) #2
```
- **自定义迭代器**：*必须*在类中实现__next__和__iter__两个方法
- **示例**：
```
from collections.abc import Iterator
class Faclist: #阶乘
	def __init__(self):
		self.n = 1
		self.fac = 1
	def __next__(self):
		self.fac*=self.n
		self.n+=1
		return self.fac
	def __iter__(self):
		return self
if __name__=='__main__':
	facs=Faclist()
	print(isinstance(facs,Iterator)) #True
	for i in range(1,6):
		print(next(facs))
```
# 字符串
## 创建字符串和引号的区别
- **单引号**：字符串中包含单引号时，必须在单引号字符前加转义符“\\”
- **双引号**：字符串中包含双引号时，必须在双引号字符前加转义符“\\”
- 字符串中有单引号时，用双引号创建字符串；有双引号时，用单引号创建字符。增强代码的可读性
- **三引号**：允许直接将字符串写成多行的形式（单引号双引号要在结尾加上续行符“\\”）
- **示例**：
```
s1 = 'Hello\
World!' #输出分两行
s2 = '你好！\n欢迎学习Python语言程序设计！'
print(s1)
print(s2)
str = '''你好！
欢迎学习Python语言程序设计！
祝你学习愉快！''' #输出分三行
```
- 使用三引号定义字符串时，字符串中单双引号都不需要加转义符，但可以加**转义符**
## 字符串比较
- **比较规则**：
	1. 从左往右逐个字符比较，若对应相同，则继续比较下一个字符
	2. 找到不同的字符时，具有==较大ASCII码==的字符串值更大
	3. 字符串都对应相同时，==长字符串更大==
- **示例**：
```
str1 = 'Python'
str2 = 'C++'
str3 = 'Python3.7'
str4 = 'Python'
print(str1>str2) #True
print(str1<=str2) #False
print(str1<str3) #True
print(str1>=str3) #False
print(str1==str4) #True
print(str1!=str4) #False
```
## 字符串切割
### split方法
- **作用**：按照指定的分隔符对字符串进行切割，返回由切割结果组成的==列表==
- **语法格式**：`str.split(sep=None,maxspilt=-1)` sep为指定的分隔符，默认为None，表示空白符（空格 换行 制表符等）；maxsplit为最大分割次数，默认值为-1，表示不对分割次数做限制 
- **示例**：
```
str1 = 'It is a book!'
str2 = 'Python##C++##Java##PHP'
ls1 = str1.spilt()
ls2 = str2.spilt('##')
ls3 = str2.spilt('##',2)
print(ls1) #['It','is','a','book!']
print(ls2) #['Python','C++','Java','PHP']
print(ls3) #['Python','C++','Java##PHP']
```
### splitlines方法
- **作用**：固定以结束符（’\\r‘、’\\n‘、’\\r\\n‘）作为分隔符进行切割，返回切割后结果组成的列表
- **语法格式**：`str.splitlines([keepends])` keepends表示切割结果中是否保留最后的行结束符，默认为False（不保留）
- **示例**：
```
str = 'Hello!\nHi!\r\nHappy!\r'
ls1 = str.splitlines()
ls2 = str.splitlines(True)
print(ls1) #['Hello!','Hi！','Happy!']
print(ls2) #['Hello!\n','Hi!\n\r','Happy!\r']
```
## 字符串的检索和替换 
### 字符串的检索
- **find方法**：在指定的检索范围内从左至右顺序检索，找到需要检索的字符串==第一次==出现的位置，返回**子串第一个字符在字符串中的索引值**
- **rfind方法**：在指定的检索范围内从右至左顺序检索，找到需要检索的字符串==第一次==出现的位置,返回**子串第一个(从左往右)字符在字符串中的索引值**
- **index与rindex方法**：与find和rfind方法作用相同，但==find方法==检索不到时==返回-1==，==index方法==检索不到时会引发==ValueError异常==
- **语法格式**：
```
str.find(sub[,start[,end]])
str.index(sub[,start[,end]])
str.rfind(sub[,start[,end]])
str.rindex(sub[,start[,end]])
```
- **示例**：
```
str = 'cat dog cat dog cat dog'
print(str.find('cat')) #0
print(str.rfind('cat')) #16
print(str.find('mouse')) #-1
```
### 字符串的替换
- **replace方法**：将字符串中的指定字串替换为其他内容，返回*替换之后的字符串*，==不修改原字符串==
- **语法格式**：`str.replace(old,new[,max])` max为做多替换的字串的数量
- **示例**：
```
str = 'cat dog cat dog cat dog'
str1 = str.replace('cat','mouse') #mouse dog mouse dog mouse dog
str2 = str.replace('cat','mouse',2) #mouse dog mouse dog cat dog
```
## 去除字符串空格和大小写转换
- **去空格**：strip、lstrip和rstrip方法
- **语法格式**：
```
str.strip() #去除str中头部和尾部的空格
str.lstrip() #去除str中头部的空格
str.rstrip() #去除str中尾部的空格
```
- **去除所有空格**：`str.replace(' ','')`
- **大小写转换**：capitalize、lower、upper和swapcase方法（==不改变原字符串==）
- **语法格式**：
```
str.capitalize() #字符串中第一个字母大写，其他字母都小写
str.lower() #字符串中所有字母小写
str.upper() #字符串中所有字母大学
str.swapcase() #字符串中，大写字母变小写字母，小写字母变大写字母
```
## 字符串的其他常用操作
- **复制字符串**：字符串为不可变类型，无法秀发i字符串中的某个元素，可直接使用复制运算符“=”进行字符串的复制
- **连接字符串**：拼接运算（+）或join方法
- **join方法语法格式**：`str.join(seq)` seq为一个序列，str为使用的连接符
- **示例**：
```
str1 = ','
str2 = ' '
str3 = ''
ls = ['I','like','Python']
print(str.join(ls1)) #I,like,Python
print(str.join(ls2)) #I like Python
print(str.join(ls3)) #IlikePython
```
- **计算一个字符串中字符数量（字符串长度）**：len函数
- **判断字符串A是否是字符串B的字串**：
```
str = 'cat dog cat'
print('cat' in str) #True
print('mouse' in str) #False
```
## 占位符和format方法
- **占位符**：![[Pasted image 20240724135441.png]]
- **format语法格式**：`str.format(*args,**kargs)`
- **示例**：
```
str1 = '{0}的计算机成绩是{1}，{0}的数学成绩是{2}'
str2 = '{name}的计算机成绩是{cs}，{name}的数学成绩是{ms}'
print(str1.format('李晓明',90,85)) #李晓明的计算机成绩是90，李晓明的数学成绩是85
print(str2.format(cs=90,ms=85,name='李晓明')) #李晓明的计算机成绩是90，李晓明的数学成绩是85
```

```
class Student:
	def __init__(self,name,cs):
		self.name=name
		self.cs=cs
s = Student('李晓明',90)
str1='{0.name}的计算机成绩是{0.cs}'
str2='{stu.name}的计算机成绩是{stu.cs}'
print(str1.format(s)) #李晓明的计算机成绩是90
print(str2.format(stu=s)) #李晓明的计算机成绩是90
```

# 正则表达式的基础语法
- **部分匹配模式**：![[Pasted image 20240724141920.png]]![[Pasted image 20240724141951.png]]![[Pasted image 20240724142024.png]]
- **特殊序列**：![[Pasted image 20240724142054.png]]![[Pasted image 20240724142110.png]]
- **单词字符**：数字 字母 汉字 下划线
- **空字符**：空格 制表符 换行符
- 写正则表达式的字符串时，**在字符串前加上字符r**，使得后面的字符串忽略转义符（不需要写\\\\才等于\\了
- 如`'\\bfoo\\b'`可写作`r'\bfoo\b'`

# re模块使用
## compile和match
- **compile函数**：将==字符串==形式的正则表达式编译成一个==正则表达式对象==
- **语法格式**：`re.compile(pattern,flags=0)` pattern为字符串形式的正则表达式；flags指定匹配选项，可以用或运算符(|)连接多个选项
- **flag参数对应的匹配选项**：常用`re.I`和`re.M`![[Pasted image 20240725103149.png]]
- **match函数**：用于对字符串==开头==的若干字符进行正则表达式的匹配
- **语法格式**：`re.match(pattern,string,flags=0)` 匹配成功时，返回一个Match对象；匹配失败时，返回None
- **示例**：
```
import re
result1 = re.match(r'python','Python是一门流行的编程语言',re.I)
result2 = re.match(r'python','我喜欢学习Python',re.I)
result3 = re.match(r'python','''我喜欢学习Python
Python是一门流行的编程语言''',re.I|re.M)
print(reusult1) #<re.Match object;span=(0,6),match='Python'>  span为匹配的字符序列在字符串中的位置信息，match保存匹配到的字符序列的信息
print(reusult2) #None 
print(reusult3) #None re.match函数会忽略匹配选项re.M
```
- **注**：`print(re.match('www', 'www.runoob.com').span())` ==只打印字符串的位置信息==
- **正则表达式对象中的match方法**：`Pattern.match(string[,pos[,endpos]])` pos指定从string的哪个位置开始匹配，匹配范围pos至（endpos-1）
- **优点**：正则表达式对象可以在正则表达式需要被多次使用时提高效率
- **示例**：
```
import re
pattern = re.compile(r'python',re.I)
result1 = pattern.match('Python是一门流行的编程语言')
result2 = pattern.match('我喜欢学习Python！'，5)
print(result1) #<re.Match object;span=(0,6),match='Python'>
print(result2) #<re.Match object;span=(5,11),match='Python'>
```
## search
- **search函数**：对==整个字符串==从左至右进行扫描，并返回==第一个匹配==的结果
- **语法格式**：`re.search(pattern,string,flags=0)`
- **示例**：
```
import re
result1 = re.search(r'python','Python是一门流行的编程语言',re.I)
result2 = re.search(r'python','我喜欢学习Python！',re.I)
result3 = re.search(r'python','我喜欢学习Python，Python简单易学！',re.I)
result4 = re.search(r'Java','我喜欢学习Python！',re.I)
print(result1) #<re.Match object;span=(0,6),match='Python'>
print(result2) #<re.Match object;span=(5,11),match='Python'>
print(result3) #<re.Match object;span=(5,11),match='Python'>
print(result4) #None
```
- **与match函数的区别在于**：match只匹配字符串开头的若干字符，search匹配整个字符串的字符
- **正则表达式对象中的search方法**：`Pattern.search(string[,pos[,endpos]])` 
## 匹配对象
- 作为判断条件时，search函数和match函数返回的**Match对象**为**True**；**None**为**False**
- **Match对象常用方法**：![[Pasted image 20240725140450.png]]
- group()传入一个组号时，返回**字符串**；传入多个组号时，返回**元组**；不传入参数时，返回**与正则表达式匹配的整个字符串**
- **示例**：
```
import re
str = '''sno:#1810101#,name:#李晓明#,age:#19#,major:#计算机#
sno:#1810102#,name:#马红#,age:#20#,major:#数学#'''
rlt = re.search(r'name:#([\s\S]*?)#[\s\S]*?major:#([\s\S]*?)#',str,re.I)
if rlt: #匹配成功时执行
	print(rlt.group()) #name:#李晓明#，age:#19#,major:#计算机# 由于search只匹配第一个出现的符合要求的字符串，所以第二行未被匹配
	print(rlt.group(1),rlt.start(1),rlt.end(1)) #李晓明 20 23
	print(rlt.group(2),rlt.start(2),rlt.end(2)) #计算机 41 44
	print(rlt.groups()) #('李晓明','计算机')元组
```
## findall和finditer
- **findall函数**：在字符串中找到**所有**与正则表达式匹配的字串
- **语法格式**：`re.findall(pattern,string,flags=0)` 以==列表==的形式返回匹配数据；匹配失败时返回空列表。
- **示例**：
```
import re
str = '''sno:#1810101#,name:#李晓明#,age:#19#,major:#计算机#
sno:#1810102#,name:#马红#,age:#20#,major:#数学#'''
rlt = re.findall(r'name:#([\s\S]*?)#[\s\S]*?major:#([\s\S]*?)#',str,re.I)
print(rlt) #[('李晓明','计算机'),('马红','数学')]
```
- **finditer函数**：在字符串中找到**所有**与正则表达式匹配的字串
- **语法格式**：`re.finditer(pattern,string,flags=0)` 以==迭代器==的形式返回匹配数据。
- **示例**：
```
import re
str = '''sno:#1810101#,name:#李晓明#,age:#19#,major:#计算机#
sno:#1810102#,name:#马红#,age:#20#,major:#数学#'''
rlt1 = re.finditer(r'name:#([\s\S]*?)#[\s\S]*?major:#([\s\S]*?)#',str,re.I)
rlt2 = re.finditer(r'department:#([\s\S]*?)#',str,re.I)
for r in rlt1:
	print(r) 
	#返回的迭代器中每一个元素都是一个Match对象
	# <re.Match object;span=(14,45),match='name:#李晓明#,age:#19#,major:#计算机#'>
	# <re.Match object;span=(60,89),match='name:#马红#,age:#20#,major:#数学#'>
for r in rlt2:
	print(r) #无
```
## split、sub和subn
- **split函数**：将字符串按与正则表达式匹配的子串分割
- **语法格式**：`re.split(pattern,string,maxsplit=0,flags=0)` maxsplit为最大分割次数
- **示例**：
```
import re
str = 'sno:1810101,name:李晓明',age:19,major：'计算机'
rlt = re.split(r'\W+',str) #以非单词字符进行分割
print(rlt) #['sno','1810101','name','李晓明','age','19','major','计算机']
```
- **sub函数**：替换字符串中与正则表达式匹配的子串
- **语法格式**：`re.sub(pattern,repl,string,count=0,flags=0)` count为最大替换次数
- **示例**：
```
import re
html = '''<h3 class="c-title">'''
content=re.sub(r'<[^<]*>','',html) #去除字符串中所有的< >，匹配的字符串中间不能包括左尖括号
content= content.strip() #去除两边的空格
```
- **subn函数**：功能与sub函数相同，以==元组==的形式同时返回替换匹配字串后得到的**新字符串**和**替换的次数**
- **语法格式**：`re.subn(pattern,repl,string,count=0,flags=0)`
- **示例**：
```
import re
html = '''<h3 class="c-title">'''
content=re.subn(r'<[^<]*>','',html) 
print(content) #('',1) #替换了一次
```

# IO编程与异常
## os模块的使用
### 基础操作
- **使用os模块功能前**，通过`import os`将其导入
- **查看系统平台**：`os.name`查看当前操作系统的名字，Windows为字符串“nt”，Linux为“posix”
- **获取当前系统平台路径分隔符**：`os.sep` Windows以'\\\\'作为路径分隔符，Linux以'/'作为路径分隔符
- **获取当前工作目录**：`os.getcwd`
- **示例**：访问当前工作目录小的data子目录中的test.dat文件
	 1. **相对路径**：`'data'+os.sep_'test.dat'`或`data{sep}test.dat'.format(sep=os.sep)`
	 2. **绝对路径**：`os.getcwd()+os.sep+'data'+os.sep+'test.dat'`或`{cwd}{sep}data{sep}test.dat'.format(cwd=os.getcwd(),sep=os.sep)`
- **获取环境变量**：`os.environ[key]或os.getenv(key)` 查看键名为key的环境变量值
- **示例**：查看HOME环境变量的值 `os.environ['HOME']或os.getenv('HOME')`
- **获取文件和目录的列表**：`os.listdir(path='')` 默认为当前路径下的所有文件和目录的名字，返回值为path路径下所有文件和目录的名字组成的==列表==
- **示例**：
```
os.listdir() #获取当前路径下所有文件和目录名字组成的列表
os.listdir(os.getcwd()+os.sep+'DDLs') #获取当前路径的DLLs目录下所有文件和目录名字组成的列表
```
### 目录的创建和删除
#### 目录的创建
- **os.mkdir函数**：只能用于创建路径中的最后一个目录，即要创建的目录中出最后一个目录外都存在
- **语法格式**：`os.mkdir(path)`
- **os.makedirs函数**：依次创建路径中所有不存在的目录
- **语法格式**：`os.mkdir(path)`
- **示例**
```
os.mkdir(os.getcwd()+os.sep+'newdir') #在当前目录下创建一个newdir目录
os.makedirs(os.getcwd()+os.sep+'subdir1'+os.sep+'subdir2') #换成mkdir时会报错FileNotFoundError
```
- 如果**创建的目录已存在**，会报错FileExistsError
#### 目录的删除
- **os.rmdir函数**：删除指定路径的最后一层目录
- **语法格式**：`os.rmdir(path)`
- **示例**：`os.rmdir(os.getcwd()+os.sep+'newdir')` 删除当前目录下的newdir目录
- 只能==删除空目录==，删除非空目录时会报错OSError
- **os.removedirs函数**：删除指定路径的最后多层目录，只能==删除空目录==；从指定路径的最后一个目录开始逐层向前删除，直到指定路径中的==所有目录都被删除==或==遇到一个不为空的目录==
- **语法格式**：`os.removedirs(path)`
- **示例**：`os.removedirs(os.getcwd()+os.sep+'subdir1'+os.sep+'subdir2')`先删除当前目录的子目录subdir1(目录里只有一个空目录subdir2)下的subdir2目录，然后删除subdir1子目录，最后会因为当前目录不是空目录而停止删除操作
- 删除目录不存在时，执行os.rmdir和os.removedirs会报错FileNotFoundError
### 获取绝对路径、路径分离和连接
#### 获取指定相对路径的绝对路径
- **以当前工作目录下的DLLs的目录为例子**：
	 1. **相对路径**：`.\\DLLs` 或 `DLLs`
	 2. **绝对路径**：`D:\\Python\\Python37\\DLLs`
- **当前目录的上层目录**：`..`
- **os.path.abspath函数**：`os.path.abspath(path)` 获取path对应的绝对路径
- **示例**：
```
print(os.path.abspath('..')) #获得上层目录的绝对路径
print(os.path.abspath('DLLs'))
```
- 编写程序时，尽量使用相对路径，以保证程序的**可移植性**
#### 获取文件所在目录的路径
- **os.path.dirname函数**：返回path中去除文件名后的路径
- **语法格式**：`os.path.dirname(path)`
- **示例**：`print(os.path.dirname('D:\\Python\\Python37\\LICENSE.txt'))` D:\\Python\\Python37
#### 获取文件名
- **os.path.basename函数**：获取指定路径中的文件名
- **语法格式**：`os.path.basename(path)`
- **示例**：`print(os.path.basename('D:\\Python\\Python37\\LICENSE.txt'))` LICENSE.txt
#### 获取指定路径的目录名或文件名
- **os.path.split函数**：将路径分解成路径和目录/文件名两部分
- **语法格式**：`os.path.split(path)` 返回==元组==
- **示例**：`print(os.path.split(os.getcwd()+os.sep+'LICENSE.txt')) #('D:\\Python\\Python37','LICENSE.txt')` 
- 当指定的**路径中不包含文件名**，也会把路径分为两部分：==最后一个目录名==和==前面所有目录组成的文件名==
- **示例**：`print(os.path.split(os.getcwd())) #('D:\\Python','Python37')` 
#### 分离文件扩展名
- **os.path.splitext函数**：将扩展名从指定路径中分离出来
- **语法格式**：`os.path.splitext(path)` 返回==元组==（root，ext）
- **示例**：`print(os.path.splitext('D:\\Python\\Python37','LICENSE.txt')) #('D:\\Python\\Python37\\LICENSE','txt')` 
#### 路径连接
- **os.path.join函数**：将一个路径的多个组成部分用系统路径分隔符依次连接在一起
- **语法格式**：`os.path.join(path,*paths)` 返回==元组==
- **示例**：`print(os.path.join('D:\\Python','Python37','LICENSE.txt')) #D:\Python\Python37\LICENSE.txt)` 
### 条件判断
- **os.path.isfile函数**：判断指定的路径目标是否为*文件*
- **语法格式**：`os.path.isfile(path)`
- **os.path.isdir函数**：判断指定的路径目标是否为*目录*
- **语法格式**：`os.path.isdir(path)`
- **示例**：
```
dir = os.getcwd()
file = dir+os.sep+'LICENSE.txt'
print(str(os.path.isdir(dir))) #True
print(str(os.path.isdir(file))) #False

print(str(os.path.isfile(dir))) #False
print(str(os.path.isfile(file))) #True
```
- **os.path.exists函数**：判断指定路径是否存在
- **语法格式**：`os.path.exist(path)`
- **示例**：
```
path1 = os.getcwd()
path2 = path1+os.sep+'mytest'
print(str(os.path.exists(path1))) #True
print(str(os.path.exists(path2))) #False
```
- **os.path.isabs函数**：判断指定路径是否为绝对路径
- **语法格式**：`os.path.isabs(path)`
- **示例**：
```
print(str(os.path.isabs(..))) #False
print(str(os.path.exists(os.getcwd()))) #True
```
### 文件打开和关闭
- **open函数**：打开一个要进行读/写操作的文件
- **语法格式**：`open(filename,mode='r')` 默认打开方式为'r'(等同于'rt')
- **文件打开方式**：![[Pasted image 20240727155205.png]]![[Pasted image 20240727160534.png]]
- **示例**：`f=open('D:\\Python\\test.txt','w+')` 以w+方式打开文件，并将返回的文件对象赋给f
- **文件关闭**：使用open函数打开文件并完成读/写操作后，==必须使用文件对象的close方法将文件关闭==
- **示例**：
```
f=open('D:\\Python\\test.txt','w+')
print(f.closed) #False
f.close
print(f.closed) #True
```
- **with语句**：让系统在文件操作完毕后自动关闭文件
- **示例**：
```
with open('D:\\Python\\test.txt','w+') as f:
	pass #此处可以对文件对象做一系列的操作
print(f.closed) #True
```
### 文件对象的write和read方法
- **write方法**：可以将字符串写入文件中
- **语法格式**：`f.write(str)` 执行完毕后会返回==写入到文件中的字符数==
- **示例**：
```
charnum = 0
with open('D:\\Python\\test.txt','w+') as f:
	charnum += f.write('Python是一门流行的编程语言！\n') 向文件中写入字符串需要换行时，只能用换行符‘\n’,且换行符算一个字符数
	charnum += f.write('我喜欢学习Python语言！')
print(charnum) #32
```
- **read方法**：从文件中读取数据
- **语法格式**：`f.read(n=-1)` n指定要读取的字节数，默认为-1，表示读取文件中的所有数据
- **示例**：
```
with open('D:\\Python\\test.txt','r') as f:
	content = f.read() 
	content = f.read()
print(content1) 
#Python是一门流行的编程语言！
#我喜欢学习Python语言！
print(content2) # (空字符串)
```
- **注**：第一次调用read方法时，一次性把文件中的所有数据读取到了content1中，此时文件指针在刚读取的数据后（即文件尾），因此第二次调用read方法时，不会读取到任何数据，content2为一个空字符串
### 文件对象的readline、readlines和seek方法
- **readline方法**：从文件中==每一次读取一行数据==
- **语法格式**：`f.readline()`
- **示例**：
```
ls = []
with open('D:\\Python\\test.txt','r') as f:
	ls.append(f.readline())
	ls.append(f.readline())
print(ls) #['Python是一门流行的编程语言！\n','我喜欢学习Python语言！']
```
- **readlines方法**：从文件中==按行读取所有数据==
- **语法格式**：`f.readlines()`
- **示例**：
```
ls = []
with open('D:\\Python\\test.txt','r') as f:
	ls = f.readlines()
print(ls) #['Python是一门流行的编程语言！\n','我喜欢学习Python语言！']
```
- **seek方法**：==移动文件指针==，从而实现文件的随机读写
- **语法格式**：`f.seek(pos,whence=0)` pos为要移动的字节数；whence为参照位置，默认值==0代表以文件首作为参照位置，1和2分别表示当前文件指针位置和文件尾==，*无返回值*
```
with open('D:\\Python\\test.txt','r') as f:
	f.seek(6,0)
	print(f.readline()) #是一门流行的编程语言！
```
- **注**：以文本方式打开文件后，只支持以文件首作为参照位置移动指针；以二进制方式打开文件后，支持全部的三种参照位置
### 一维数据和二维数据
- **一维数据**（数轴）：数据元素的值==由一个因素唯一确定==
- **一维数据的存储**：
	- **有序存储**：列表 **示例**：成绩`data1D=[98,95,96]`
	- **无序存储**：集合
- **二维数据**（平面坐标系）：数据元素的值==由两个因素共同确定==
- **二维数据的存储**：二维列表
- **示例**：
```
data2D=[[90,98,87], #第一名学生的三门课程成绩
[76,45,86], #第二名学生的三门课程成绩
[76,85,98]] #第三名学生的三门课程成绩
```
### CSV操作一维、二维数据
- **CSV（Comma-Separated Values）**：国际通用的一维、二维数据存储格式，扩展名为.csv
- **CSV格式**：每行对应一个一维数据，一维数据的各数据元素间用英文半角逗号（,）分隔，==逗号不变不需要加额外的空格==；对于确实元素，要保留逗号
- **CSV文件的写操作**：csv模块的writer方法可生成一个writer对象，使用该对象可将数据以逗号分隔的形式写入CSV文件中
- **语法格式**：`csv.writer(csvfile)` csvfile为一个具有writer方法的对象，即文本文件等
- **注**：如将open函数返回的文件对象作为实参传给csvfile，则调用open函数打开文件时，必须加上关键字参数“`newline=''`”
- **writerow和writerows方法**：向CSV文件中写入数据
- **语法格式**：`writer.writerow(row)  writer.writerows(rows)`
- **CSV文件的读操作**：csv模块的writer方法可生成一个reader对象，使用该对象可将数据以逗号分隔的形式写入CSV文件中
- **语法格式**：`csv.reader(csvfile)` csvfile为一个==迭代器==
- **注**：如将open函数返回的文件对象既是*可迭代对象*，也是*迭代器*；如将open函数返回的文件对象作为实参传给csvfile，则调用open函数打开文件时，必须加上关键字参数“`newline=''`”
- **示例**：
```
import csv
data2D = [[90,98,87],
[70,89,92],
[95,78,81],
[98,90,95],
[65,72,70]]
with open('D:\\Python\\score.csv','w',newline='') as f:
	csvwriter = csv.writer(f)
	csvwriter.writerow(['语文','数学','英语'])
	csvwriter.writerows(data2D)
ls = []
with open('D:\\Python\\score.csv','r',newline='') as f:
	csvreader = csv.reader(f)
	for line in csvreader:
		ls2.append(line)
print(ls2) #[['语文','数学','英语'],['90','98','87'],['70','89','92'],['95','78','81'],['98','90','95'],['65','72','70']]
```
## 异常
### 异常的定义与分类
- **定义**：因程序运行时发生错误而产生的信号
- **分类**：语法错误和逻辑错误
- **常见逻辑错误**：![[Pasted image 20240728111015.png]]![[Pasted image 20240728111036.png]]
### 异常处理
#### try except
- **try except语句**：捕获异常并做异常处理
- **语法格式**：
```
try:
	try子句的语句块
except 异常类型1：
	异常类型1的处理语句块
except 异常类型2：
	异常类型2的处理语句块
...
except 异常类型N：
	异常类型N的处理语句块
```
- **except子句后的异常类型**：可以为多个异常类型组成的元组，如`except(TypeError,ZeroDivisionError):`;也可为空，如`except:` 表示捕获所有的异常
- **try except语句执行过程**：先执行try子句的语句块，没出现异常则except子句不被执行；出现对应的异常后，执行对应except子句的语句块，==try子句中未执行完的语句块不会被继续执行了==；如异常无法被任何except子句执行，程序会抛出异常并停止运行。
- **示例**：
```
for i in range(3):
	try:
		num = int(input())
		print(10/num)
	except ValueError:
		print('值错误！')
	except：
		print('其他异常！')
#输入：abc 输出：值错误！
#输入：0   输出：其他异常！
#输入：10  输出：1.0
```
#### else、finally和raise、
- **else**：==没有异常时==，在try子句执行结束后执行else自己
- **示例**：
```
for i in range(3):
	try:
		num = int(input())
		print(10/num)
	except ValueError:
		print('值错误！')
	except：
		print('其他异常！')
	else:
		print('else子句被执行!')
```
- **finally**：无论是否有异常都执行
- **示例**：
```
for i in range(3):
	try:
		num = int(input())
		print(10/num)
	except ValueError:
		print('值错误！')
	except：
		print('其他异常！')
	finally:
		print('finally子句被执行!')
```
- **raise**：人为产生异常
- **示例**：
```
for i in range(2):
	try:
		num = int(input())
		if num == 0:
			raise ValueError('输入的数字不能为0！')
		print(10/num)
	except ValueError as e:
		print('值错误:',e) #输入0时，会输出“值错误：输入的数字不能为0！”
```
#### 断言和自定义异常
- **assert**：判断一个条件是否成立，如果==成立==，则==继续执行后面的语句==；如果不成立，则会引发AssertionError异常，不再继续执行后面的语句
- **示例**：
```
for i in range(2):
	try:
		num = int(input())
		assert != 0
		print(10/num)
	except AssertionError:
		print('断言失败！')
```
- **自定义异常**：以BaseException类作为父类创建一个子类
- **示例**：
```
class ScoreError(BaseException):
	def __init__(self,msg):
		self.msg = msg
	def __str__(self):
		return self.msg
if __name__=='__main__':
	for i in range(2):
		try:
			score = int(input())
			if score<0 or score>100:
				raise ScoreError('输入成绩为%d，成绩应在0-100之间'%score)
			print('输入的成绩为%d'%score)
		except ScoreError as e:
			print('分数错误：',e)
# 输入：-1
# 输出：输入成绩为-1，成绩应再0-100之间
```