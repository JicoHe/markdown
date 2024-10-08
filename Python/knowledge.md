### **集合的元素**
 ```
 在Python中，集合（Set）是一种无序且元素唯一的数据结构。集合中的元素可以是任何不可变的数据类型，包括整数、浮点数、字符串、元组等。具体来说，集合可以包含以下类型的元素：
 1. 整数：例如 `{1, 2, 3}`
 2. 浮点数：例如 `{2.5, 3.14, 1.0}`
 3. 字符串：例如 `{"apple", "banana", "orange"}`
 4. 元组：例如 `{(1, 2), ('a', 'b', 'c')}`
 5. 其他不可变类型的对象
 需要注意的是，集合本身是可变的，但集合中的元素必须是不可变的，这样才能保证集合的唯一性和无序性。
列表（List）不是集合（Set）的元素。因为集合要求其中的元素必须是不可变的，而列表是可变的数据结构，它的元素可以随时添加、删除或修改。因此，不能将列表作为集合的元素。
 
 如果需要将列表中的元素存储到集合中，可以先将列表转换为元组，因为元组是不可变的，然后再将元组添加
 到集合中。例如：
																		python
	my_list = [1, 2, 3]
	my_set = set(tuple(my_list))
 这样就可以将列表 `my_list` 中的元素 `[1, 2, 3]` 转换为元组 `(1, 2, 3)`，然后存储在集合
 `my_set` 中。
```

### **__ init __方法**
```
	__init__就是其中一种函数，叫做[构造函数]

 python
	def __init__(self,...):
	    代码块
每次创建类的实例对象时，__init__函数就会自动被调用，无论它里面有什么样的变量、计算，统统会自动调用。
理解__init__函数需要搞清楚以下三点：

> 1.带有两个下划线开头的函数是声明该属性为私有,不能在类地外部被使用或直接访问。  
> 2.init函数（方法）支持带参数的类的初始化 ，也可为声明该类的属性  
> 3.init函数（方法）的第一个参数必须是 self（self为习惯用法，也可以用别的名字），后续参数则可 以自由指定，和定义函数没有任何区别。

```text
# 不带参数
class Sample:
    def __init__(self):
        print("自动调用构造方法")
        # 定义了一个实例属性
        self.name = "小明"


test = Sample()
print(test.name)

# 输出结果
自动调用构造方法
小明

如上，在创建 test这个对象时，隐式调用了手动创建的__init__()构造方法

构造函数__init__为什么会存在？

顾名思义，就像房子必须有地基、框架、大梁一样，是房子的基础，实例对象也需要有的构造的基础，这就是构造函数的作用，给实例对象最原始的属性。

所以综上，构造方法__init__用于创建实例对象时使用，每当创建一个类的实例对象时，Python解释器都会自动调用它，用来初始化对象的某些属性。
```


### 变量
- 变量视为你可以赋值的标签，而不是箱子 
- 可通过(,)运算符进行分隔进行分别赋值，比如x,y,z = 1,2,3。x,y,z分别被赋值为1,2,3。
__数据类型__
1. string字符串，可以用单引号（‘’）或者双引号（“”）
	- _f-string_:组合两个字符串，f"string1 {字符串变量}"
2. 数字
	- 让数据容易读用 ( _ )分隔数字，不影响输出
3. 常量：变量表达式所有字母都是**大写**

### 方法（method）
- 每个方法后面都要有一组括号（）(parentheses)
__种类__
1. **title()**
	- 将字符串的每一个单词首字母成大写,其余字母小写
	- 不需要带额外条件
2. **upper()和lower()**
	- upper为全部字母大写
	- lower为全部字母小写，适用于储存数据
3. **strip()、lstrip()和rstrip()**
	- 消除字符串的、左侧的或右侧的空白字符
4. **append()**
	- 添加元素到列表末端
5. **insert(index, value)**
	- 插入值到列表对应索引
6. **pop(index)**
	- 会把列表中*第index的*变量移除并且将得到的被除变量储存到新的地方，为空值时则是最后一个值
7. **remove()**
	- 在括号里输入你要删掉的值并且可以使用这个值，但是注意⚠️，只会删去第一个值，如果有重复的需要遍历删除。
8. sort()
	- 永久将列表的字符串按字母表排序
	- （）中填写reverse  = true ， 则逆字母表排序
9. sorted()
	- 短暂复制一份按字母排序的字符串列表
	- 用法：sorted(变量)
10. reverse()
	- 将列表元素倒过来
11. get()
	- 解决字典中不存在对应key的错误字典.get('key', value)
12. items()
	- 在字典中使用返回一个key-value pair的数组由key和value组成，与遍历使用
13. keys()
	- 不需要遍历value的时候
	- 与之对应的是values()
14. values()
	- 只遍历字典的value
15. split()
	- 拆分字符串的文本单词
### 基本函数
1. len()
	- 给出列表的长度
2. renge()
	- range(6)代表从0到5
	- 也可以用来构建数字列表：num = list(range(1, 6))
	- range(2, 11, 2)表示从2开始以n的步长增加
3. min(), max(), sum()
	- 寻找数列的最大值、最小值与和
4. input()
	- 读取用户的输入并转化成字符（⚠️输入数字也会变成字符）
	- 括号里面可以添加其他的东西，比如字符串一起引用
5. int()
	- 读取用户输入整型数字并转化成整型搭配input使用：int(input())
6. float()
	- 转换数字字符成浮点数，用法与上面类似
### 函数的定义
1. 结构：
```python
def function_name (parameters参数)
	statement
function_name(arguments)
```
- 提供的形参可以有多个要一一按照顺序对应
- 或者通过关键词对应：`paramater1:'value'`
- 如果提供的参数不够，则为默认参数，给默认参数赋值时，将该参数放在后面。其中可选择的参数可以对形参进行赋值空
2. 通过函数返回值：经过处理后返回一个值，或者返回一个字典
- 返回字典可选内容时：初始参数为None，且在函数内if判断是否有，有则补充
```python
def function_name (parameter1, parameter2, parameter_optional=None)
	statement
	if parameter_optional:
		dictionaty['key_optional'] = parameter_optional
function_name(arguments)
```
3. 传递**列表**给函数
4. 修改列表：函数内部可以永久的修改列表的元素，因此为了避免将原有列表修改，可以传递一份列表的拷贝(List_name[:])
5. 处理不知道接受多少个argument的情况：函数的parameter设为元组（**tuple**)接受多个变量
```python
# 处理不知道函数接受多少个argument的情况  
def make_pizza(*toppings):  
    print(toppings)  
# 建立了一个元组topping，可以接受多个变量  
make_pizza('pepperoni')  
make_pizza('green peppers', 'mushrooms', 'extra cheese')
"""如果要考虑多个参数，那要遵循顺序"""
def make_pizza(size, *topping)
```
6. 处理不知道什么种类的的arg，用接受**键值对**的方式去进行，接收到的parameter是可变字典：
```python
def build_profile(first, last, **user_info):  
    user_info['first_name'] = first  
    user_info['last_name'] = last  
    return user_info  
  
user_profile = build_profile('albert', 'einstein',  
                             location='princeton',  
                             field='physics')  
print(user_profile)
# 显示的结果：
{'location': 'princeton', 'field': 'physics',
 'first_name': 'albert', 'last_name': 'einstein'}
```


### 运算符
1. 点运算符(.)
	- 在变量后用(.)来连接方法，将方法在变量上起作用
2. 转义字符
	- 退格：输入一个tab(\\t)
	- 换行：新开一行(\\n)
3. 算数运算符
	- 加减乘除：+ -  * /
		1. 整数相除会得到浮点数
		2. 浮点数和整数之间运算得到浮点数
	- 数的次方：a ** b表示a的b次方
	- 取模运算：%取余，返回余数
4. 条件运算符
	- == !=：等于与不等于

### 列表list
- 有**顺序的动态的**数据 collection
- 用中括号（[ ]）定义,内部元素用逗号(commas)分隔
- 访问元素则在列表中括号内部填索引号（0为开头与数组类似），注意在中括号内输入-n，则访问倒数第n个值，-1即为最后一个值。
2. **用法**
	- 修改：通过重新赋值的方法
	- 添加：append可以将新元素放到列表末端
	- 插入：用index方法
	- 删除：可以用del语句(已经知道对应位置)del 变量[]
3. 切片slice
	- list[m : n]将m到n-1的元素保留
	- [m:]从m+1切切到尾
	- [:n]从开始切到第n个
	- [-n:]得到倒数的n个
4. 通过切片来复制：list2=list1[:]，得到两个单独的列表，如果是list2=list1是代表两个都是同一个列表，不是单独的。
5. 不可改变的列表：元组tuple()，
	- 用括号（）来括起元素
	- 如果只有一个元素也需要用，分隔（a，）
	- 可以对整个元组重新赋值，但不能单独修改

### 语句(statement)
1. del删除语句
	- 将列表元素删除
2. for循环
	**结构**：for *var* in *mounts*: statement
	建议：for item in list_of_items:
3. 列表推导式List comprehension
	- 从一个列表名开始
	- 定义列表的变量值表达式
	- 启用循环来赋予表达式的数字来获得变量
	- 用[]中括号括上
4. if条件语句
	- 结构：
	```python
	if 表达式:
		statement
	else:
	or
	if conditional_test:
		do something
	else
	```
	- 使用方法时去判断，不会影响原先变量
	- 多重变量时用and表同时成立，or其中一个成立
	- 对于列表内是否有一个特定的值，表达式用**in 或者 not in**
	- if组会每个都进行，elif和else不会每个语句都进行
5. while循环（只要不满足特定条件就会停止）
```python
while expression:
	statement
	expression_change
```
  1. 将while和列表一起使用:
	- 移动列表的物品到另一个列表：通过中间变量，将原列表用pop方法弄出后添加到新列表
	- 删除特定的元素：while 元素 in lists：用remove方法
  2. 与字典一起使用：
	通过字典储存玩家的输入
  3. 使用**break**跳出循环，**continue**跳过本次循环
6. import语句(需要在程序开头填写)
	1. 可以从其他文件中调用函数
	- 整个使用时`import module`，也可以加`as alias`方便使用，用点运算符连接文件和函数：`module_name.function_name`
	- 引用特定的函数：`from module_name inport function_0, function_1, function_2`使用时直接使用函数就可以，也可以在function_name后加`as alias`方便使用
	- 引用全部的函数：`from module import *`
	2. 导入类 `from module import class`
### 旗帜flag
对于循环，如果面对多钟情况不执行，可以用Flag去标记任何情况
用法：Flag = True / False
while True: 会一直进行。

### 字典（dictionary）
与C语言中的结构体类似
- 定义：**字典 = {'key1':value1, 'key2':value2}**
- 使用：**字典[‘key’]**
字典是动态的结构，可以添加新的key
- 方式：**字典['new key'] = value**
- 因此可以从空字典开始：**字典{}**
- 修改字典对应key的value结构与上面相同
- 删除：用del语句：del 字典[‘key’]
定义时可跨行，用花括号的时候
另外，可以通过for遍历整个字典
```python
for key, value in dictionary.items():
	print(f'\nkey: {key}')
	print(f'value: {value}')
```
当不需要遍历value时，可用keys()方法
```python
for key in dictionary.keys():
	print(f'\nkey: {key}')
```
或者for遍历默认遍历key
```python
for key in dictionary:
	print(f'\nkey: {key}')
```
同样的可以使用values()方法进行遍历
```python
for value in dictionary.values():
	print(f'value: {value}')
```
为了避免出现重复的内容用set()将字典转换成集合，集合中的元素是不可变且不重复的
```python
for value in set(dictionary.values()):
	print(f'value: {value}')
```
遍历时可以通过sorted(dictionary)方法进行按字母排序遍历
- **nesting：将字典作为列表的元素**
```python
# A List in a Dictionary 及其用法  
# Store information about a pizza being ordered.  
pizza = {  
    'crust': 'thick',  
    'toppings': ['mushrooms', 'extra cheese'],  
}  
# Summarize the order.  
print(f"You ordered a {pizza['crust']}-crust pizza "  
      "with the following toppings:")  
# 通过遍历使用字典中的列表
for topping in pizza['toppings']:  
    print("\t" + topping)
```
- **还有字典中的字典**
善用items（）方法拆分，去得到字典中的字典，使用get方法确保不会出问题

### 🌟🌟类（类似模版） classes
面向对象编程
在类中创建物体时，物体将具备类的所有特性，叫实例化instantiation，构建出一个新的实例instanse
可以将类储存在module中，用import语句调用
- **在类里面的函数被称为方法。用点连接符使用函数。**
1. `__init__()`方法：此方法中的双下划线不能缺.
2. 定义一个类的方法时，括号内部第一位必须是`self`，代表使用方法时，将类的所有特性传递给实例。`self parameter = value`。
3. 可以对特性初始化一个值，`__init__()`方法的定义中
4. 改变特性的值有三种方法：
- 实例直接修改：`instance.attribute = value`
- 通过方法修改：在类中定义一个赋值的方法：```
```python
def update_odometer(self, mileage):  
    self.odometer_reading += mileage
```
- 对值进行加减：和上面类似
5. **继承**
如果要创建一个新的类，可以从原有的类中继承，类的种类就有父类和子类。继承的时候会多次用到`__init__`方法.  
格式：```
```python
class child_class(parent_class)
	def __init__(self, attribute_1...)
		super().__init__(attribute_1...)
		self.new_attribute = value
		...
```
- super函数的作用是调用父类中`__init__()`方法，来给子类的实例提供父类的性质，然后在此下面添加新的属性。  
- 此外你也可以定义新的方法去覆盖父类的方法。
- 当类的方法和特性过长时，可以将类细分成小类，配合使用，其中属性的值缺一不可
```python
class ATTRIBUTE:
	def __init__(self, new_attribute=value)
		self.new_attribute = new_attribute

	def method(self)
		statement

# 原有的类
class child_class(parent_class)
	def __init__(self, attribute_1...)
		super().__init__(attribute_1...)
		# 创建了ATTRIBUTE的实例
		self.attribute = ATTRIBUTE()
		...
```
使用时：`instance.attribute.method()`

### 文件的读取与使用
1. 读取文件
	1. 打开文件：`with open('file') as file_object`  
		- open函数的作用是用一个物体去代替文件
		- with的作用是读取文件后关闭文件
		- 可以用 / 去输入要读取文件的路径
		- 你也可以将open()内的地址作为一个变量，在外面设置。
		- 读取的文件装转换成**字符串**
	2. 将文件读取道内存中：`contents = file_object.read()`用到read()方法读取整个内容，同时==会返回一行空行==，解决问题是加一个rstrip()方法去消掉字符串右侧的物体
	3. 通过读取每一行的形式
	```python
	for line in file_object:
		statement  # 这样会按行读取，而不是read()方法的整个读取
```
	4. 做行的列表
		原因是想要再次访问文件的信息在with的外面
		解决：通过使用==readlines()==方法
		```python
with open('pi_digits.txt') as file_object:  
    lines = file_object.readlines()  
  
for line in lines:  
    print(line.rstrip())
```
	5. 使用文本的内容
2. 写入文件
write()覆盖
```python
filename = '...'
with open(filename, 'w') as file_object:  
    file_object.write('I love programming.!')
```
- `'w'`表示以读写模式打开文件
- `write()`方法为写入什么内容，以**覆盖**的形式
- 只能写入**字符串**，如果要写入数字，用`str()`函数转换

append添加
```python
filename = '...'
with open(filename, 'a') as file_object:  
    file_object.write('I love programming.!')
```
- 'a'`表示以添加模式打开文件，在文章末尾加入

匹配文本编辑形式：在地址后添加`encoding=''`
3. 预测
是处理会产生错误的情况，用`try-except`词块：
```python
try:  
    print(5/0)  
except ZeroDivisionError:  
    print("You can't Division by zero")
else:
	statement...
```
常见情况有：
- `ZeroDivisionError`
- `FileNoFoundError`
4. 分析文本
拆分文本单词：split()方法
处理多个文件
忽略错误：在except里用==`pass`==
5. 