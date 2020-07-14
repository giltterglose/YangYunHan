# **python学习路径**

## 1.python入门：

### 安装相应软件

python首先进行环境搭建，在python官网上面先进行python下载以便搭建环境，搭建的环境会保存在下载下的python文档里面

下载官网：https://www.python.org/

下载最新版的python

可以使用idle或者pycharm软件

个人推荐pycharm，有社区版和专业版（要出钱），所以对于初学者来说，社区版就够了

## 2.字符串&print

### 2.1 print：字符串的输入

eg：print(‘Hello world’) (注意没有分号) 可以在控制台打印出显示的内容

用`print()`在括号中加上字符串，就可以向屏幕上输出指定的文字。比如输出`'hello, world'`，用代码实现如下：

```python
>>> print('hello, world')
```

`print()`函数也可以接受多个字符串，用逗号“,”隔开，就可以连成一串输出：

```python
>>> print('The quick brown fox', 'jumps over', 'the lazy dog')
The quick brown fox jumps over the lazy dog
```

`print()`也可以打印整数，或者计算结果：

```python
>>> print(300)
300
>>> print(100 + 200)
300
```

因此，我们可以把计算`100 + 200`的结果打印得更漂亮一点：

```python
>>> print('100 + 200 =', 100 + 200)
100 + 200 = 300
```

注意，对于`100 + 200`，Python解释器自动计算出结果`300`，但是，`'100 + 200 ='`是字符串而非数学公式，Python把它视为字符串，

### 2.2 字符串：用' '或" "包裹的内容

### 2.3 input：内容的读入

如果要让用户从电脑输入一些字符怎么办？Python提供了一个`input()`，可以让用户输入字符串，并存放到一个变量里。比如输入用户的名字：

```python
>>> name = input()
Michael
```

当你输入`name = input()`并按下回车后，Python交互式命令行就在等待你的输入了。这时，你可以输入任意字符，然后按回车后完成输入。

输入完成后，不会有任何提示，Python交互式命令行又回到`>>>`状态了。那我们刚才输入的内容到哪去了？答案是存放到`name`变量里了。可以直接输入`name`查看变量内容：

```python
>>> name
'Michael'
```

`input()`可以让你显示一个字符串来提示用户，于是我们把代码改成：

```python
name = input('please enter your name: ')
print('hello,', name)
```

再次运行这个程序，你会发现，程序一运行，会首先打印出`please enter your name:`，这样，用户就可以根据提示，输入名字后，得到`hello, xxx`的输出：

```python
C:\Workspace> python hello.py
please enter your name: Michael
hello, Michael
```

注意：input得到的是字符串，要想变成数字，得转化一下用函数（后面会说）

int()等函数

## 3.变量（难度很小）

### 3.1变量定义

与C语言、C++、Java类似，但是可以不用定义类型，中间用=连接；

2.变量具有可变性：

### 3.2基础数据类型

与C语言、C++、Java类似，分为整型，浮点数（由于小数点的位数可变，故称浮点数），布尔值

### 3.3运算符

与上述语言类似，但略有不同

不同点在于：

[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-So9QJ7Y0-1594436952552)(C:\Users\24552\AppData\Roaming\Typora\typora-user-images\image-20200707191544928.png)]

**注意：py不能使用++和--运算符了！！！！！！**

**在print里面使用加号，相当于字符串拼接，但是类型必须都是字符串，否则会报错！！**

解决办法：str() 把任何数据类型转换成字符串

## 4.布尔值和条件判断

### 4.1布尔：使用（True 和False）来判断

可以直接赋值，也可以用逻辑判断

常用逻辑运算符：== 、 >、   >=、  <、  <=、   !=

逻辑运算：and 和C/C++及Java里面 && 一样

​                   or 和C/C++及Java里面 || 一样

遵循括号优先原则

### 4.2 if条件判断：

**在 Python 中不会像 C 语言或者 Java 一样用{}区分代码块，而是用代码缩进来区分，相似缩进的代码被称为一个代码块，如图所示：** 

```python
character = '勇敢'
if character == '勇敢':
    print('你的性格是' + character) # 左侧缩进了4格
    print('格兰芬多！') # 左侧缩进了4格
print('下一位')
```

结尾有冒号，表示代码块的开始，后面是新代码块。

执行方法和C/C++，Java一样。

### 4.3 if-else

注意else后面一定要有冒号!!这条打五星！！

### 4.4 if-elif-else

可以减少if嵌套，减小时间复杂度。

```python
character = '无'
if character == '勇敢':
    print('格兰芬多!')
elif character == '忠诚':
    print('赫奇帕奇!')
elif character == '精明':
    print('拉文克劳!')
else:
    print('斯莱特林!')
print('下一位')
```



## 5.列表

### 5.1.定义：

Python 中的基础数据类型，我们总是使用一个变量等于一个值，这个值可以是整数、浮点数、字符串、布尔类型。如果我们想要一个变量等于一组值，我们就需要使用列表list。

列表一般表示有序组合。每个元素还可以是不同的类型。

还可以是多维列表。（列表嵌套列表）

```python
heroInfos = [['魏', '曹操', 160.3],['蜀', '刘备', 177.1],['吴', '周瑜', 188.6]]
print(heroInfos)
```



### 5.2 列表访问

索引值：和C/C++，Java一模一样。

越界问题：IndexError: list index out of range。

获得列表长度：len(list):字符串长度、数组长度。

```python
num = ['3', '.', '1', '4', '1', '5', '9', '2', '6', '5', '3', '5', '8', '9', '7', '9', '3', '2', '3', '8', '4', '6', '2', '6', '4', '3', '3', '8', '3', '2', '7', '9', '5', '0', '2', '8', '8', '4', '1', '9', '7', '1', '6', '9', '3', '9', '9', '3', '7', '5', '1', '0', '5', '8', '2', '0', '9', '7', '4', '9', '4', '4', '5', '9', '2']# 打印num的长度
print(len(num))
```

多列表访问：相当于二维数组访问方法。

```python
heroInfos = [['魏', '曹操', 160.3],['蜀', '刘备', 177.1],['吴', '周瑜', 188.6]]#打印第一个英雄的名称
print(heroInfos[0][1])
```

**倒序索引**：倒着数，倒数第一个为-1，倒数第二为-2

```python
heros = ['曹操', '夏侯惇', '典韦', '刘备', '关羽', '张飞', '诸葛亮']
print(heros[-1])
```

### 5.3 元素的添加（append、insert函数）

采用数组名.append(text)来操作。

```python
heros = ['牛魔', '妲己', '兰陵王']
heros.append('亚瑟')
print(heros)
```

插入函数：数组名.insert(索引值,text)

```python
heros = ['牛魔', '妲己', '兰陵王']
heros.insert(0, '亚瑟')
print(heros)
```

### 5.4 删除元素（pop函数）

数组名.pop()

```python
heros = ['牛魔', '妲己','亚瑟','兰陵王']
leave = heros.pop()
print('死亡英雄：' + leave)
print('存活英雄：' + str(heros))
```

在上面的案例中，我们没有传递 index 的值，所以是删除列表的最后一个元素。如果传递了 index，则是删除索引的值。

删除第一个元素，需要传入的 index 应该为 0。

**注意！！**

**在删除第一个元素后，后面的元素会自动迁移，在删除之前妲己、亚瑟、兰陵王的索引值为1，2，3，移动之后分别变成了0，1，2。**

### 5.5 元组--tuple

元组如下所示：

```python
heros = ('牛魔','妲己','亚瑟','兰陵王')
print(heros)
```

元组和列表的区别：

列表是动态的，长度可变，可以随意的增加、删减或改变元素。列表的存储空间略大于元组，性能略逊于元组。

元组是静态的，长度大小固定，不可以对元素进行增加、删减或者改变操作。元组相对于列表更加轻量级，性能稍优。

所以元组不能使用append 还有 insert 还有pop函数

元组所占空间小于列表。

**总结：在确定长度不可变时候用元组，不确定长度用列表**

## 6.循环

### 6.1 for循环

循环与C/C++语言，Java类似for while

for 循环打印遍历不同于C/C++，Java，格式为

for 变量（相当于迭代器）in 列表名称:

```python
heros = ['曹操','刘备','关羽','张飞','诸葛亮','周瑜','孙策','大乔','小乔']
for hero in heros:    
    print(hero)
print('结束')
```

但是python里面不支持打印索引，所以就引入range函数：

### 6.2 range

写法：

```python
for index in range(10):    
   print(index)
```

range用法

range(start,end,step)现在不用死记硬背，后面会有说明。

[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-wIIgX3MV-1594436952562)(C:\Users\24552\AppData\Roaming\Typora\typora-user-images\image-20200707191916761.png)]

倒叙遍历，步长为-1

```python
for i in range(9, -1, -1):
    print(i)
```

计算1~10的方法：

```python
sum = 0
for i in range(10):
    sum = sum + i
print(sum)
```

### 6.3 while循环

语法：while 条件判断:

例子1：

```python
sum = 0i = 1  # 这里的1是range的start
while i < 1000:    
    sum = sum + i    
    i = i + 2  # 这里的2其实就是range的步长了
print(sum)
```

例子2：

```python
i = 0
damage = 0  # 总伤害
while i < 7:  # 当i<7成立的时候，执行下面的代码块
    harm = 1000 + 250 * i  # 每次造成的伤害都在上一次的基础上加250
    print('妲己第' + str(i + 1) + '次造成了伤害：' +     str(harm))  # 字符串和数字相加时要将数字转为字符串，别忘了哦
    damage = damage + harm
    print('妲己造成的总伤害为：' + str(damage))
    i = i + 1  # 每次执行这个代码块，我们
```

### 6.4 break&continue

这个和C/C++一模一样。

### 6.5 for循环嵌套

```python
heroInfos = [['蜀', '刘备', 177.1], ['吴', '周瑜', 188.6], ['魏', '曹操', 160.3], ['蜀', '关羽', 212.4], ['蜀', '张飞', 188]]
for hero in heroInfos:    
    for message in hero:        
        print(message)
```

九九乘法表实例：

step1：for循环嵌套：

```python
for x in range(9):    
    for y in range(9):        
        print(str(x + 1) + '*' + str(y + 1))
```

但是由于print默认是会换行的，所以你会发现每行只有1个，怎么避免呢？

```python
print('之前', end=' ')
print('之后', end=' ')
```

end 表示打印之后的添加的字符串，默认是\n(换行符)，在这里我们将其改为了空格，所以两个 print 会打印在同一行

进一步优化：

```python
for x in range(9):    
    for y in range(9):        
        print(str(x + 1) + '*' + str(y + 1) + '=' + str((x + 1) * (y + 1)), end=' ')    
        print('')
```

但是优化以后你会发现，打印全部了，但是我们只要下三角

怎么处理呢？

step2：

y<=x:

```python
for x in range(9):    
    for y in range(x + 1):        
        print(str(x + 1) + '*' + str(y + 1) + '=' + str((x + 1) * (y + 1)), end=' ')    
        print('')
```

## 7.字典：

相当于C++和Java里面的map函数相当于key-value组合。

```python
heroInfo = {    
    'name': '刘备',    
    'state': '蜀',    
    'weapon': '雌雄双股剑',    
    'mount': '的卢',    
    'height': 177.1
}
print(heroInfo)
```



特点：

1.字典由大括号包裹，这个是区分列表的

2.字典由两列组成，左边的叫做Key(键)，右侧的叫做Value(值)

3.Key-Value中间用冒号：分割，Key-Value是成对出现的，我们称为键值对

### 7.1字典的访问

代码如下：

```python
heroInfo = {    
    'name': '刘备',    
    'state': '蜀',    
    'weapon': '雌雄双股剑',    
    'mount': '的卢',    
    'height': 177.1
}
print(heroInfo['weapon'])  # 访问武器
```

输入相对应的key值来访问其value值。

字典存储是无序的

若key值不存在，则会报错

判断key存在的方法： if ~ in 对象：

```python
if 'wife' in heroInfo:    
    print('wife在heroInfo中')
else:    
    print('wife不在heroInfo中')
```

### 7.2 键值对的性质：key/value

键值对里面的key只要是不可变数据就可以了（字符串，数值类型，布尔类型均可）由于元组不可变，所以元组可以作为key。

```python
info = {    
    0: 'A',    
    (0,1,2): 'B',    
    '1': 'C'
}
print(info)
```

### 7.3 字典的增改

修改方法：和字符串，列表一模一样

只需要指定key值就可以自动修改字典里面的值

```python
heroInfo = {
    'name': '关羽',
    'state': '蜀',
    'weapon': '青龙偃月刀',
    'mount': '可怜的小马',
    'height': 212.2
}

print('原来的坐骑：' + heroInfo['mount'])
heroInfo['mount'] = '赤兔'
print('新的坐骑：' + heroInfo['mount'])
```

如果字典里面不存在键值对，则自动添加

如果字典里面存在键值对，就在后面自动加上

```python
heroInfo = {
    'name':'关羽',
    'state':'蜀',
    'weapon':'青龙偃月刀',
    'mount':'赤兔',
    'height':212.2
}

print('原来的关羽小队：' + str(heroInfo))
heroInfo['newcomer'] = '两位嫂嫂'
print('现在的关羽小队：' + str(heroInfo))
```

### 7.4 字典的删除

采用函数del进行删除

```python
heroInfo={
    'name':'关羽',
    'state':'蜀',
    'weapon':'青龙偃月刀',
    'mount':'赤兔',
    'height':212.2,
    'newcomer':'两位嫂嫂'
}

print('原来的关羽小队：'+str(heroInfo))
del heroInfo['newcomer']
print('现在的关羽小队：'+str(heroInfo))
```

del 后面直接跟上内容就可以了，删除的是相对的对象

clear方法：把相应的字典全部清空

```python
heroInfo={
    'name':'关羽',
    'state':'蜀',
    'weapon':'青龙偃月刀',
    'mount':'赤兔',
    'height':212.2
}
print('原来的关羽信息:' + str(heroInfo))
heroInfo.clear()
print('新的关羽信息:' + str(heroInfo))
```

### 7.5 字典的遍历

for循环照样遍历

```python
heroInfo = {
    'name': '关羽',
    'state': '蜀',
    'weapon': '青龙偃月刀',
    'mount': '赤兔',
    'height': 212.2
}
for key in heroInfo:
    print(key+'：'+str(heroInfo[key]))
```

经过key值遍历，进行输出value的值

前面的key是代表字典里面的索引值

当要对列表里面的字典进行遍历时，注意在列表每一个子元素里面添加相对应的key值

因为dict的存储不是按照list的方式顺序排列，所以，迭代出的结果顺序很可能不一样。

默认情况下，dict迭代的是key。如果要迭代value，可以用`for value in d.values()`，如果要同时迭代key和value，可以用`for k, v in d.items()`。

### 7.6 集合Set

由于列表可以解决多个有序元素的问题，字典可以解决描述值与映射的问题

集合：是非重复的无序列表

我们可以使用set来解决元素重复的问题

```python
heros=['周瑜','孙策','小乔','孙策']
result = set(heros)
print('英雄'+str(result))
print('英雄个数：'+str(len(result)))
```

相当于set(集合名称)

set的特点：

1.集合表示方式为set(列表)

2.集合中的元素是不可重复的

3.集合中没有索引的概念，集合元素是无序的，因此集合也无法通过索引进行访问

4.集合的个数，也可以通过len()得到

5.集合通常用来表示成员间的关系及元素的去重等等

### 7.7 集合的遍历

和列表与字典一模一样

集合元素的增加：采用集合.add()来使用

集合元素的删除：采用集合.remove()来使用

由于集合无序且唯一，所以插入不需要像列表一样指定位置。

```python
heros = set(['周瑜', '孙策', '小乔', '孙策'])
heros.add('大乔')
print('add:'+str(heros))
heros.remove('周瑜')
print('remove:'+str(heros))
```

## 8.其他操作

### 8.1 字符串转换

可以采用int()来进行转换，例如int('123')

### 8.2 not in

由于in是用来判断元素是否在列表里面的关键字，那么not in则是判断元素是否不在列表里面

代码如下：

```python
hero = {
  'name': '赵云',
  'state': '蜀'
}

print('name' in hero)
print('weapon' not in hero)
```

### 8.3 排序问题

#### 8.3.1 冒泡排序

**思路：**

1.比较两个相邻元素，如果第一个比第二个大，则交换他们， 对每一对相邻元素作同样的工作，从开始第一对到结尾的最后一对。

代码如下：

```python
nums = [8, 6, 7, 9, 4, 5, 3, 1, 2]
for index in range(len(nums) - 1):

  # 如果底部元素>顶部元素，则交换
  if nums[index] > nums[index + 1]:
    # 交换元素
    temp = nums[index + 1]
    nums[index + 1] = nums[index]
    nums[index] = temp

print(nums[-1])
```

2.这步做完后，最后的元素会是最大的数。

3.针对所有的元素重复以上的步骤，除了最后一个。

4.持续每次对越来越少的元素重复上面的步骤，直到没有任何一对数字需要比较。

这个本质上是一个循环嵌套问题

```python
nums = [8, 6, 7, 9, 4, 5, 3, 1, 2]
for time in range(len(nums) - 1):
  # 此处表示循环次数，9个元素，循环8次可以找到最大的8个元素，及完成了排序
  for index in range(len(nums) - 1 - time):
    # 注意此处，我们减去time，因此每次顶部的元素已经找到了，不需要再次遍历了

    # 如果左边元素>右边元素，则交换
    if nums[index] > nums[index + 1]:
      # 交换元素
      temp = nums[index + 1]
      nums[index + 1] = nums[index]
      nums[index] = temp

print(nums)
```

#### 8.3.2 插入排序

**思路**

1.从第一个元素开始，放在有序列表中，该元素可以认为已经有序。

2.取出下一个元素，在已经排好序的元素序列中从左到右扫描。

3.如果该元素（待插入的元素）大于扫描到的元素，则将扫描移动到下一位。

4.直到该元素（待插入的元素）小于有序列表中的某个元素，则将该元素（待插入的元素）插入到列表中当前元素之前。

5.重复步骤2-4，指导待排序列表全部取出。

代码如下：

```python
nums = [8, 6, 7, 9, 4, 5, 3, 1, 2]
sorts = []
for item in nums:
  # 当有序列表为空时，插入一个元素
  if len(sorts) == 0:
    sorts.append(item)
  else:
    insertIndex = -1;
    for index in range(len(sorts)):
      # 遍历直到当前元素大于将插入的元素
      if sorts[index] > item:
        insertIndex = index
        break
    # 如果insertIndex = -1，也就是全部有序列表中都小于将插入的元素
    # 可以使用append插入到最后
    # 否则利用insert进行插入，并break停止查找
    if insertIndex == -1:
      sorts.append(item)
    else:
      sorts.insert(insertIndex, item)
print(sorts)
```

### 8.4 把字典变成列表

```python
for key in duration:
  phone = key
  sum = duration[key]
  newItem = {'phone': phone, 'sum': sum}
  # 当sortCalled为空的情况
  if len(sortCalled) == 0:
    sortCalled.append(newItem)
  else:
    insertIndex = -1
    for sortIndex in range(len(sortCalled)):
      if sortCalled[sortIndex]['sum'] < sum:
        insertIndex = sortIndex
        break
    if insertIndex == -1:
      sortCalled.append(newItem)
    else:
      sortCalled.insert(insertIndex, newItem)
```

## 9.python函数

### 9.1函数的概念

函数，相当于C/C++及Java里面俗称的方法

抽象也可以相当于函数

函数是一种代码的抽象形式，是一种组织好的，可以重复使用的，用来实现功能单一或相关联功能的代码段。

### 9.2内置函数

使用最为广泛：print() 用来打印

在进行字符串相加时：str() 转化成字符串

列表长度：len()

循环范围：range()

其实python有很多内置函数，由于太多，我就不一一列举，死记硬背没有用，所以给大家一个官网进行查询，后面遇到再慢慢解释

官网：https://docs.python.org/zh-cn/3/library/functions.html

#### min()函数

返回可迭代对象(在列表里面的元素)中最小的元素，或者返回两个及两个以上实参中最小的一个

#### abs()函数:

返回一个数的绝对值。 参数可以是一个整数或浮点数。 如果参数是一个复数，则返回它的模。 

#### sum()函数:

`sum`(*iterable*, */*, *start=0*)

从 *start* 开始自左向右对 *iterable* 的项求和并返回总计值。 *iterable* 的项通常为数字，而 start 值则不允许为字符串。

可以简化把自定义函数=内置函数也可以，例如：f = abs;

#### map()函数：

`map()`函数接收两个参数，一个是函数，一个是`Iterable`，`map`将传入的函数依次作用到序列的每个元素，并把结果作为新的`Iterator`返回。

map(function,Iterable)

不仅如此，`map()`作为高阶函数，事实上它把运算规则抽象了，因此，我们不但可以计算简单的f(x)=x2，还可以计算任意复杂的函数，例如转换成字符串等等。

```python
>>>def f(x):
...     return x * x
...
>>> r = map(f, [1, 2, 3, 4, 5, 6, 7, 8, 9])
>>> list(r)
[1, 4, 9, 16, 25, 36, 49, 64, 81]
```

**注意：在使用map时，要注意变成list来返回**

#### reduce()函数：

`reduce`把一个函数作用在一个序列`[x1, x2, x3, ...]`上，这个函数必须接收两个参数，`reduce`把结果继续和序列的下一个元素做累积计算

相当于reduce(function,Iterable)

```python
>>> from functools import reduce
>>> def add(x, y):
...     return x + y
...
>>> reduce(add, [1, 3, 5, 7, 9])
25
```

#### filter()函数：

Python内建的`filter()`函数用于过滤序列。

和`map()`类似，`filter()`也接收一个函数和一个序列。和`map()`不同的是，`filter()`把传入的函数依次作用于每个元素，然后根据返回值是`True`还是`False`决定保留还是丢弃该元素。

相当于fliter(judge,Iterable)方法

```python
def not_empty(s):
    return s and s.strip()

list(filter(not_empty, ['A', '', 'B', None, 'C', '  ']))
# 结果: ['A', 'B', 'C']
```

#### sorted()函数：

`sorted()`函数也是一个高阶函数，它还可以接收一个`key`函数来实现自定义的排序，例如按绝对值大小排序

```python
 sorted([36, 5, -12, 9, -21], key=abs)
```

对字符串排序，是按照ASCII的大小比较的，由于`'Z' < 'a'`，结果，大写字母`Z`会排在小写字母`a`的前面。

要进行反向排序，不必改动key函数，可以传入第三个参数`reverse=True`：

```python
>>> sorted(['bob', 'about', 'Zoo', 'Credit'],key=str.lower, reverse=True)
['Zoo', 'Credit', 'bob', 'about']
```



### 9.3 自定义函数

代码如下：

```python
def cMin(numbers):    
    minNumber = numbers[0]    
    for num in numbers:        
        if num < minNumber:            
            minNumber = num    
            return minNumber
        
   print(cMin([2, 3, 4, 1, 5, 7]))
```

1.函数开头的定义def
2.函数的名称，命名规则和变量-样，在这里是cMin
3.函数的参数，像之前的描述一样，参数也可以歧持多个
4.函数的内容部分，注意内容部分在单独一个代码块
5.函数的返回值，返回值也可以不定义，比如: print()



**return结束**

表示函数结束，立即返回调用者

代码如下：

```python
def cMin(numbers):
    if len(numbers) == 0: # 如果传入的列表为空，则直接返回
        return
    minNumber = numbers[0]
    for num in numbers:
        if num < minNumber:
            minNumber = num
    return minNumber

print(cMin([2, 3, 4, 1, 5, 7]))
```

 一旦执行到return时，函数执行完毕，并且返回结果，如果最后没有return则返回none

**多返回值**

示例：

```python
def convertToLatLon(address):
    # 省略中间转换逻辑

    # 最终得到的经纬度如下
    lon = '143.231'
    lat = '40.0592'

    # return返回多个值
    return lon, lat

lon, lat = convertToLatLon('杭州市西湖文化广场')
print('经度：' + lon)
print('纬度：' + lat)
```

由于部分情况下我们可能需要返回多个数值，我们只需要在数值之间画，就可以了。

元组经常可以用于函数返回值情况

### 9.4 默认参数

以range()函数为例：

range(index1,index2,index3):

index1:表示开始

index2:表示结束

index3:表示步长

相当于range(start,stop[,step])，[,step]符号说明step可有可无，如果不注明，则step默认是1，本质上就是step在range里面起作用

默认参数设置

def function(e=2):

参考案例：

```python
def cPow(num, exp = 2):
    index = 0
    result = 1
    while index < exp:
        result *= num
        index += 1
    return result

print(cPow(2))
```

我们在参数后面添加默认赋值条件，那么该参数如果没有传递则获取默认值

（因为参数传递从左到右，所以默认参数只能从最右边开始，否则就报错

以下方法是错误的

```python
def cPow(num = 2, exp):
```

### 9.5 动态参数

以min()函数为例：

原型是min(arg1,arg2,*args),args把剩下元素打包为元组

```python
def cPrint(*args):
    for arg in args:
        print(arg, end=' ')

cPrint('hello', 'you', 'ke', 'da')
```

### 9.6 递归

定义：自身不断循环自身

递归函数：一个函数在自身内部自己调用自己

实现方法案例：阶乘

```python
def fact(n):    # 加入递归条件    
    if n == 1:        
        return 1    # 把fact(n-1)的结果和n相乘，剩下的是交给fact(n-1)    
    return fact(n-1) * n
fact(10)
```

### 9.7 返回函数

不需要立刻求和，而是在后面的代码中，根据需要再计算怎么办？可以不返回求和的结果，而是返回求和的函数：

这样可以减少函数调用

```python
def lazy_sum(*args):
    def sum():
        ax = 0
        for n in args:
            ax = ax + n
        return ax
    return sum
```

当我们调用`lazy_sum()`时，返回的并不是求和结果，而是求和函数：

调用函数`f`时，才真正计算求和的结果：

```python
def it(*args):
    def power():
        total = 0
        for item in args:
            total += item**2
        return total
    return power()

f = it(1,3,5,7,9)
print(f)
```

结果是165

**当我们调用`lazy_sum()`时，每次调用都会返回一个新的函数，意思是不一样了**

**闭包**

定义：当一个函数返回了一个函数后，其内部的局部变量还被新函数引用

```python
def count():
    fs = []
    for i in range(1, 4):
        def f():
             return i*i
        fs.append(f)
    return fs

f1, f2, f3 = count()
```

你可能会认为会返回1，4，9 但是是9，9，9，原因就在于返回的函数引用了变量`i`，但它并非立刻执行。等到3个函数都返回时，它们所引用的变量`i`已经变成了`3`，因此最终结果为`9`。

**返回闭包时牢记一点：返回函数不要引用任何循环变量，或者后续会发生变化的变量。**

一定要引用循环变量怎么办？方法是再创建一个函数，用该函数的参数绑定循环变量当前的值，无论该循环变量后续如何更改，已绑定到函数参数的值不变：

```python
def count():
    def f(j):
        def g():
            return j*j
        return g
    fs = []
    for i in range(1, 4):
        fs.append(f(i)) # f(i)立刻被执行，因此i的当前值被传入f()
    return fs
```

返回就是1，4，9了

### 9.8 匿名函数

表示方法：lambda x: 语块

冒号前面的`x`表示函数参数。

匿名函数有个限制，就是只能有一个表达式，不用写`return`，返回值就是该表达式的结果。

用匿名函数有个好处，因为函数没有名字，不必担心函数名冲突。

同样，也可以把匿名函数作为返回值返回：

```python
def build(x, y):
    return lambda: x * x + y * y
```

**但是：Python对匿名函数的支持有限，只有一些简单的情况下可以使用匿名函数。**

### 9.9 装饰器

在函数调用前后自动打印日志，但又不希望修改`now()`函数的定义，这种在代码运行期间动态增加功能的方式，称之为“装饰器”（Decorator）

```python
def log(func):
    def wrapper(*args, **kw):
        print('call %s():' % func.__name__)
        return func(*args, **kw)
    return wrapper
```

观察上面的`log`，因为它是一个decorator，所以接受一个函数作为参数，并返回一个函数。我们要借助Python的@语法，把decorator置于函数的定义处：

调用`now()`函数，不仅会运行`now()`函数本身，还会在运行`now()`函数前打印一行日志：

```python
@log
def now():
    print('2015-3-25')
>>> now()
call now():
2015-3-25
```

把`@log`放到`now()`函数的定义处，相当于执行了语句：

```python
now = log(now)
```

不需要编写`wrapper.__name__ = func.__name__`这样的代码，Python内置的`functools.wraps`就是干这个事的，所以，一个完整的decorator的写法如下：

```python
import functools

def log(func):
    @functools.wraps(func)
    def wrapper(*args, **kw):
        print('call %s():' % func.__name__)
        return func(*args, **kw)
    return wrapper
```

### 9.10 偏函数

函数参数的时候，我们讲到，通过设定参数的默认值，可以降低函数调用的难度。而偏函数也可以做到这一点。

但`int()`函数还提供额外的`base`参数，默认值为`10`。如果传入`base`参数，就可以做N进制的转换：

```python
>>> int('12345', base=8)
5349
>>> int('12345', 16)
74565
```

假设要转换大量的二进制字符串，每次都传入`int(x, base=2)`非常麻烦，于是，我们想到，可以定义一个`int2()`的函数，默认把`base=2`传进去：

```python
def int2(x, base=2):
    return int(x, base)
>>> int2('1000000')
64
>>> int2('1010101')
85
```

`functools.partial`就是帮助我们创建一个偏函数的，不需要我们自己定义`int2()`，可以直接使用下面的代码创建一个新的函数`int2`：

```python
>>> import functools
>>> int2 = functools.partial(int, base=2)
>>> int2('1000000')
64
>>> int2('1010101')
85
```

最后，创建偏函数时，实际上可以接收函数对象、`*args`和`**kw`这3个参数，当传入：

```python
int2 = functools.partial(int, base=2)
```

实际上固定了int()函数的关键字参数`base`，也就是：

```python
int2('10010')
```

相当于：

```python
kw = { 'base': 2 }
int('10010', **kw)
```

```python
max2 = functools.partial(max, 10)
```

实际上会把`10`作为`*args`的一部分自动加到左边，也就是：

```python
max2(5, 6, 7)
```

相当于：

```python
args = (10, 5, 6, 7)
max(*args)
```

结果是10

## 10. 模块

模块是一个python文件，以.py结尾

可以更有逻辑组织模块，让代码更好用，更加易懂

可以定义函数，类，变量，也可以包含可执行代码

### 10.1 模块使用

我们想导入模块，可以采用import进行导入

使用方法：在主程序里面导入，使用模块名.函数/方法即可，例如：

```python
import cList
print(cList.cMax([2, 3, 4, 1, 5, 7]))
```

用.符号获取方法就好了

但是，只有在平级包下面（同一个文件夹下面）才可以使用。

### 10.2 导入具体的内容

采用from xxx（模块名称） import xxx（内部函数）

```python
from cList import cMax
print(cMax([2, 3, 4, 1, 5, 7]))
```

## 11.高级特性

### 11.1 切片

相当于在一个列表里面，取出其中一部分元素，由于你想一个个取太麻烦了，所以采用切片的方法来获取

```python
r = []
n = 3
for i in range(n):
    r.append(L[i])
 
>>> r
['Michael', 'Sarah', 'Tracy']
>>> L[0:3]
['Michael', 'Sarah', 'Tracy']
```

其中，`L[0:3]`表示，从索引`0`开始取，直到索引`3`为止，但**不包括索引`3`**。即索引`0`，`1`，`2`，正好是3个元素。如果第一个索引是`0`，还可以省略。

类似的，既然Python支持`L[-1]`取倒数第一个元素，那么它同样支持倒数切片：

代码如下：

```python
>>> L[-2:]
['Bob', 'Jack']
>>> L[-2:-1]
['Bob']
```

另外的，tuple（元组）还可以进行切片操作

### 11.2 列表生成式

要生成list `[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]`可以用`list(range(1, 11))`

```python
>>> list(range(1, 11))
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

但是，要生成别的方式大家第一时间肯定想到这样操作：

```python
>>> L = []
>>> for x in range(1, 11):
...    L.append(x * x)
...
>>> L
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

但是太麻烦了

所以我们有一种方法来进行生成，叫做列表生成式，例如：

```python
>>> [x * x for x in range(1, 11)]
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

写列表生成式时，把要生成的元素`x * x`放到前面，后面跟`for`循环，就可以把list创建出来。

当然，我们可以还在后面添加条件进行判断：

```python
>>> [x * x for x in range(1, 11) if x % 2 == 0]
[4, 16, 36, 64, 100]
```

还可以进行二重循环，生成全排列：

```python
>>> [m + n for m in 'ABC' for n in 'XYZ']
['AX', 'AY', 'AZ', 'BX', 'BY', 'BZ', 'CX', 'CY', 'CZ']
```

### 11.3 生成器generator

把列表生成式list（）变成tuple元组（）就可以了

```python
>>> L = [x * x for x in range(10)]
>>> L
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
>>> g = (x * x for x in range(10))
>>> g
<generator object <genexpr> at 0x1022ef630>
```

打印generator的方法，采用next（g）的方法。

但是，generator保存的是算法，每次调用`next(g)`，就计算出`g`的下一个元素的值，直到计算到最后一个元素，没有更多的元素时，抛出`StopIteration`的错误。

解决办法仍然是采用for xxx in yyy：

```python
>>> g = (x * x for x in range(10))
>>> for n in g:
...     print(n)
```

下面来看斐波那契数列的案例：

```python
def fib(max):
    n, a, b = 0, 0, 1
    while n < max:
        print(b)
        a, b = b, a + b
        n = n + 1
    return 'done'
```

赋值语句a,b=b,a+b 相当于

```
t = (b, a + b) # t是一个tuple
a = t[0]
b = t[1]
```

仔细观察，可以看出，`fib`函数实际上是定义了斐波拉契数列的推算规则，可以从第一个元素开始，推算出后续任意的元素，这种逻辑其实非常类似generator。

也就是说，上面的函数和generator仅一步之遥。要把`fib`函数变成generator，只需要把`print(b)`改为`yield b`就可以了：

```python
def fib(max):
    n, a, b = 0, 0, 1
    while n < max:
        yield b
        a, b = b, a + b
        n = n + 1
    return 'done'
```

最难理解的就是generator和函数的执行流程不一样。函数是顺序执行，遇到`return`语句或者最后一行函数语句就返回。而变成generator的函数，在每次调用`next()`的时候执行，遇到`yield`语句返回，再次执行时从上次返回的`yield`语句处继续执行。

generator，在执行过程中，遇到`yield`就中断，下次又继续执行，到最后一个的时候，再往下就会发生报错。

`fib`的例子，我们在循环过程中不断调用`yield`，就会不断中断。当然要给循环设置一个条件来退出循环，不然就会产生一个无限数列出来。

```python
>>> for n in fib(6):
...     print(n)
```

但是用`for`循环调用generator时，发现拿不到generator的`return`语句的返回值。如果想要拿到返回值，必须捕获`StopIteration`错误，返回值包含在`StopIteration`的`value`中：

```python
>>> g = fib(6)
>>> while True:
...     try:
...         x = next(g)
...         print('g:', x)
...     except StopIteration as e:
...         print('Generator return value:', e.value)
...         break
```

try except异常捕获后期会讲到这里可以了解一下昂。

### 11.4 可迭代对象与迭代器

可以直接作用于`for`循环的数据类型有以下几种：

一类是集合数据类型，如`list`、`tuple`、`dict`、`set`、`str`等；

一类是`generator`，包括生成器和带`yield`的generator function。

这些可以直接作用于`for`循环的对象统称为可迭代对象：`Iterable`。

可以使用`isinstance()`判断一个对象是否是`Iterable`对象：

```python
>>> from collections.abc import Iterable
>>> isinstance([], Iterable)
True
```

但是注意需要提前导包：from collections.abc import Iterable

isinstance用法：isinstance(内容,Iterable)

生成器不但可以作用于`for`循环，还可以被`next()`函数不断调用并返回下一个值，直到最后抛出`StopIteration`错误表示无法继续返回下一个值了。

可以被`next()`函数调用并不断返回下一个值的对象称为迭代器：`Iterator`。

可以使用`isinstance()`判断一个对象是否是`Iterator`对象：

注意提前导包：from collections.abc import Iterator

```python
>>> from collections.abc import Iterator
>>> isinstance((x for x in range(10)), Iterator)
True
```

生成器都是`Iterator`对象，但`list`、`dict`、`str`虽然是`Iterable`，却不是`Iterator`。

把`list`、`dict`、`str`等`Iterable`变成`Iterator`可以使用`iter()`函数：

```python
>>> isinstance(iter([]), Iterator)
True
>>> isinstance(iter('abc'), Iterator)
True
```

为什么`list`、`dict`、`str`等数据类型不是`Iterator`？

这是因为Python的`Iterator`对象表示的是一个数据流，Iterator对象可以被`next()`函数调用并不断返回下一个数据，直到没有数据时抛出`StopIteration`错误。可以把这个数据流看做是一个有序序列，但我们却不能提前知道序列的长度，只能不断通过`next()`函数实现按需计算下一个数据，所以`Iterator`的计算是惰性的，只有在需要返回下一个数据时它才会计算。

**总结**

1.凡是可作用于`for`循环的对象都是`Iterable`类型；

2.凡是可作用于`next()`函数的对象都是`Iterator`类型，它们表示一个惰性计算的序列；

3.集合数据类型如`list`、`dict`、`str`等是`Iterable`但不是`Iterator`，不过可以通过`iter()`函数获得一个`Iterator`对象。

4.Python的`for`循环本质上就是通过不断调用`next()`函数实现的

## 12.面向对象编程

### 12.1 相关概念

面向对象编程——Object Oriented Programming，简称OOP，是一种程序设计思想。OOP把对象作为程序的基本单元，一个对象包含了数据和操作数据的函数。

面向过程的程序设计把计算机程序视为一系列的命令集合，即一组函数的顺序执行。为了简化程序设计，面向过程把函数继续切分为子函数，即把大块函数通过切割成小块函数来降低系统的复杂度。

而面向对象的程序设计把计算机程序视为一组对象的集合，而每个对象都可以接收其他对象发过来的消息，并处理这些消息，计算机程序的执行就是一系列消息在各个对象之间传递。

采用面向对象的程序设计思想，我们首选思考的不是程序的执行流程，而是`Student`这种数据类型应该被视为一个对象，这个对象拥有`name`和`score`这两个属性（Property）。如果要打印一个学生的成绩，首先必须创建出这个学生对应的对象，然后，给对象发一个`print_score`消息，让对象自己把自己的数据打印出来。

```python
class Student(object):

    def __init__(self, name, score):
        self.name = name
        self.score = score

    def print_score(self):
        print('%s: %s' % (self.name, self.score))
```

给对象发消息实际上就是调用对象对应的关联函数，我们称之为对象的方法（Method）。

```python
bart = Student('Bart Simpson', 59)
lisa = Student('Lisa Simpson', 87)
bart.print_score()
lisa.print_score()
```

### 12.2 类和实例

面向对象最重要的概念就是类（Class）和实例（Instance），类是抽象的模板，比如Student类，而实例是根据类创建出来的一个个具体的“对象”，每个对象都拥有相同的方法，但各自的数据可能不同，定义类是通过`class`关键字。

`class`后面紧接着是类名，即`Student`，类名通常是大写开头的单词，紧接着是`(object)`，表示该类是从哪个类继承下来的，继承的概念我们后面再讲，通常，如果没有合适的继承类，就使用`object`类，这是所有类最终都会继承的类。

定义好了`Student`类，就可以根据`Student`类创建出`Student`的实例，创建实例是通过类名+()实现的

```python
>>> bart = Student()
>>> bart
<__main__.Student object at 0x10a67a590>
```

变量`bart`指向的就是一个`Student`的实例，后面的`0x10a67a590`是内存地址，每个object的地址都不一样，而`Student`本身则是一个类。

可以自由地给一个实例变量绑定属性，比如，给实例`bart`绑定一个`name`属性：

```python
>>> bart.name = 'Bart Simpson'
>>> bart.name
'Bart Simpson'
```

类可以起到模板的作用，因此，可以在创建实例的时候，把一些我们认为必须绑定的属性强制填写进去。通过定义一个特殊的`__init__`方法，在创建实例的时候，就把`name`，`score`等属性绑上去：

```python
class Student(object):

    def __init__(self, name, score):
        self.name = name
        self.score = score
```

 **注意：特殊方法“init”前后分别有两个下划线！！！**

`__init__`方法的第一个参数永远是`self`，表示创建的实例本身，因此，在`__init__`方法内部，就可以把各种属性绑定到`self`，因为`self`就指向创建的实例本身。

**有了`__init__`方法，在创建实例的时候，就不能传入空的参数了，必须传入与`__init__`方法匹配的参数，**但`self`不需要传，Python解释器自己会把实例变量传进去：

```python
>>> bart = Student('Bart Simpson', 59)
>>> bart.name
'Bart Simpson'
>>> bart.score
59
```

`Student`实例本身就拥有这些数据，要访问这些数据，就没有必要从外面的函数去访问，可以直接在`Student`类的内部定义访问数据的函数，这样，就把“数据”给封装起来了。这些封装数据的函数是和`Student`类本身是关联起来的，我们称之为类的方法：

```python
class Student(object):

    def __init__(self, name, score):
        self.name = name
        self.score = score

    def print_score(self):
        print('%s: %s' % (self.name, self.score))
```

### 12.3 访问限制

由于我们有了Student类，但是在外部还是可以修改Student里面的数据，所以为了保护数据，我们需要设置访问权限

要让内部属性不被外部访问，可以把属性的名称前加上两个下划线`__`，在Python中，实例的变量名如果以`__`开头，就变成了一个私有变量（private），只有内部可以访问，外部不能访问（不同于C++和Java语言）

```python
class Student(object):

    def __init__(self, name, score):
        self.__name = name
        self.__score = score

    def print_score(self):
        print('%s: %s' % (self.__name, self.__score))
```

这样已经无法从外部访问`实例变量.__name`和`实例变量.__score`了：

```python
>>> bart = Student('Bart Simpson', 59)
>>> bart.__name
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'Student' object has no attribute '__name'
```

如果外部代码要获取name和score，像C++和Java一样添加get方法

```python
class Student(object):
    ...

    def get_name(self):
        return self.__name

    def get_score(self):
        return self.__score
```

允许外部代码修改score，可以再给Student类增加`set_score`方法：

```python
class Student(object):
    ...

    def set_score(self, score):
        self.__score = score
```

在方法中，可以对参数做检查，避免传入无效的参数。

**需要注意的是，在Python中，变量名类似`__xxx__`的，也就是以双下划线开头，并且以双下划线结尾的，是特殊变量，特殊变量是可以直接访问的，不是private变量。**

你会看到以一个下划线开头的实例变量名，比如`_name`，这样的实例变量外部是可以访问的，但是仍然要视为一个私有变量

双下划线开头的实例变量，

不能直接访问`__name`是因为Python解释器对外把`__name`变量改成了`_Student__name`，所以，仍然可以通过`_Student__name`来访问`__name`变量：

```python
>>> bart._Student__name
'Bart Simpson'
```

但是强烈建议你不要这么干，因为不同版本的Python解释器可能会把`__name`改成不同的变量名。

最后注意下面的这种*错误写法*：

```python
>>> bart = Student('Bart Simpson', 59)
>>> bart.get_name()
'Bart Simpson'
>>> bart.__name = 'New Name' # 设置__name变量！
>>> bart.__name
'New Name'
```

表面上看，外部代码“成功”地设置了`__name`变量，但实际上这个`__name`变量和class内部的`__name`变量*不是*一个变量！内部的`__name`变量已经被Python解释器自动改成了`_Student__name`，而外部代码给`bart`新增了一个`__name`变量。不信试试：

```python
>>> bart.get_name() # get_name()内部返回self.__name
'Bart Simpson'
```

### 12.4 继承与多态

#### 12.4.1 继承

在OOP程序设计中，当我们定义一个class的时候，可以从某个现有的class继承，新的class称为子类（Subclass），而被继承的class称为基类、父类或超类（Base class、Super class）。

比如，我们已经编写了一个名为`Animal`的class，有一个`run()`方法可以直接打印：

```python
class Animal(object):
    def run(self):
        print('Animal is running...')
```

当我们需要编写`Dog`和`Cat`类时，就可以直接从`Animal`类继承：

```python
class Dog(Animal):
    pass

class Cat(Animal):
    pass
```

继承有什么好处？最大的好处是子类获得了父类的全部功能。由于`Animial`实现了`run()`方法，因此，`Dog`和`Cat`作为它的子类，什么事也没干，就自动拥有了`run()`方法：

```python
dog = Dog()
dog.run()

cat = Cat()
cat.run()
```

运行结果如下：

```
Animal is running...
Animal is running...
```

当然，也可以对子类增加一些方法，比如Dog类：

```python
class Dog(Animal):

    def run(self):
        print('Dog is running...')

    def eat(self):
        print('Eating meat...')
```

继承的第二个好处需要我们对代码做一点改进。你看到了，无论是`Dog`还是`Cat`，它们`run()`的时候，显示的都是`Animal is running...`，符合逻辑的做法是分别显示`Dog is running...`和`Cat is running...`，因此，对`Dog`和`Cat`类改进如下：

```python
class Dog(Animal):

    def run(self):
        print('Dog is running...')

class Cat(Animal):

    def run(self):
        print('Cat is running...')
```

再次运行，结果如下：

```python
Dog is running...
Cat is running...
```

#### 12.4.2 多态

当子类和父类都存在相同的`run()`方法时，我们说，子类的`run()`覆盖了父类的`run()`，在代码运行的时候，总是会调用子类的`run()`。这样，我们就获得了继承的另一个好处：多态。

什么是多态，我们首先要对数据类型再作一点说明。当我们定义一个class的时候，我们实际上就定义了一种数据类型。

```python
a = list() # a是list类型
b = Animal() # b是Animal类型
c = Dog() # c是Dog类型
```

判断一个变量是否是某个类型可以用`isinstance()`判断：

```python
>>> isinstance(a, list)
True
>>> isinstance(b, Animal)
True
>>> isinstance(c, Dog)
True
```

看来`a`、`b`、`c`确实对应着`list`、`Animal`、`Dog`这3种类型。

但是等等，试试：

```python
>>> isinstance(c, Animal)
True
```

看来`c`不仅仅是`Dog`，`c`还是`Animal`！

在继承关系中，如果一个实例的数据类型是某个子类，那它的数据类型也可以被看做是父类。但是，反过来就不行：

```python
>>> b = Animal()
>>> isinstance(b, Dog)
False
```

### 12.5 获取对象信息

当我们拿到一个对象的引用时，如何知道这个对象是什么类型、有哪些方法呢？

#### **12.5.1 使用type()**

首先，我们来判断对象类型，使用`type()`函数：

基本类型都可以用`type()`判断：

```python
>>> type(123)
<class 'int'>
>>> type('str')
<class 'str'>
>>> type(None)
<type(None) 'NoneType'>
```

如果一个变量指向函数或者类，也可以用`type()`判断：

```python
>>> type(abs)
<class 'builtin_function_or_method'>
>>> type(a)
<class '__main__.Animal'>
```

判断基本数据类型可以直接写`int`，`str`等，但如果要判断一个对象是否是函数怎么办？可以使用`types`模块中定义的常量：

```python
>>> import types
>>> def fn():
...     pass
```

#### 12.5.2 使用isinstance()

对于class的继承关系来说，使用`type()`就很不方便。我们要判断class的类型，可以使用`isinstance()`函数。

我们回顾上次的例子，如果继承关系是：

```
object -> Animal -> Dog -> Husky
```

那么，`isinstance()`就可以告诉我们，一个对象是否是某种类型。先创建3种类型的对象：

```python
>>> a = Animal()
>>> d = Dog()
>>> h = Husky()
```

然后，判断：

```python
>>> isinstance(h, Husky)
True
```

没有问题，因为`h`变量指向的就是Husky对象。

再判断：

```python
>>> isinstance(h, Dog)
True
```

`h`虽然自身是Husky类型，但由于Husky是从Dog继承下来的，所以，`h`也还是Dog类型。换句话说，`isinstance()`判断的是一个对象是否是该类型本身，或者位于该类型的父继承链上。

因此，我们可以确信，`h`还是Animal类型：

```python
>>> isinstance(h, Animal)
True
```

同理，实际类型是Dog的`d`也是Animal类型：

```python
>>> isinstance(d, Dog) and isinstance(d, Animal)
True
```

但是，`d`不是Husky类型：

```python
>>> isinstance(d, Husky)
False
```

能用`type()`判断的基本类型也可以用`isinstance()`判断：

```python
>>> isinstance('a', str)
True
>>> isinstance(123, int)
True
>>> isinstance(b'a', bytes)
True
```

**总是优先使用isinstance()判断类型，可以将指定类型及其子类“一网打尽”。**

#### 12.5.3 使用dir()

如果要获得一个对象的所有属性和方法，可以使用`dir()`函数，它返回一个包含字符串的list，比如，获得一个str对象的所有属性和方法：

类似`__xxx__`的属性和方法在Python中都是有特殊用途的，比如`__len__`方法返回长度。在Python中，如果你调用`len()`函数试图获取一个对象的长度，实际上，在`len()`函数内部，它自动去调用该对象的`__len__()`方法，所以，下面的代码是等价的：

```python
>>> len('ABC')
3
>>> 'ABC'.__len__()
3
```

我们自己写的类，如果也想用`len(myObj)`的话，就自己写一个`__len__()`方法：

```python
>>> class MyDog(object):
...     def __len__(self):
...         return 100
...
>>> dog = MyDog()
>>> len(dog)
100
```

### 12.6 实例属性与类属性

由于Python是动态语言，根据类创建的实例可以任意绑定属性。

给实例绑定属性的方法是通过实例变量，或者通过`self`变量：

```python
class Student(object):
    def __init__(self, name):
        self.name = name

s = Student('Bob')
s.score = 90
```

但是，如果`Student`类本身需要绑定一个属性呢？可以直接在class中定义属性，这种属性是类属性，归`Student`类所有：

```python
class Student(object):
    name = 'Student'
```

当我们定义了一个类属性后，这个属性虽然归类所有，但类的所有实例都可以访问到。来测试一下：

```python
>>> class Student(object):
...     name = 'Student'
...
>>> s = Student() # 创建实例s
>>> print(s.name) # 打印name属性，因为实例并没有name属性，所以会继续查找class的name属性
Student
>>> print(Student.name) # 打印类的name属性
Student
>>> s.name = 'Michael' # 给实例绑定name属性
>>> print(s.name) # 由于实例属性优先级比类属性高，因此，它会屏蔽掉类的name属性
Michael
>>> print(Student.name) # 但是类属性并未消失，用Student.name仍然可以访问
Student
>>> del s.name # 如果删除实例的name属性
>>> print(s.name) # 再次调用s.name，由于实例的name属性没有找到，类的name属性就显示出来了
Student
```

## 13.面向对象进阶

### 13.1 使用___slots___

当我们定义了一个class，创建了一个class的实例后，我们可以给该实例绑定任何属性和方法，这就是动态语言的灵活性。相当于我们可以往类里面添加属性，就是用对象去实例化。

```python
class Student(object):
    pass
#然后，尝试给实例绑定一个属性：
>>> s = Student()
>>> s.name = 'Michael' # 动态给实例绑定一个属性
>>> print(s.name)
Michael
#还可以尝试给实例绑定一个方法：
>>> def set_age(self, age): # 定义一个函数作为实例方法
...     self.age = age
...
>>> from types import MethodType#导入函数的方法
>>> s.set_age = MethodType(set_age, s) # 给实例绑定一个方法
>>> s.set_age(25) # 调用实例方法
>>> s.age # 测试结果
25
```

但是，给一个实例绑定的方法，对另一个实例是不起作用的，这是一个局限性

```python
>>> s2 = Student() # 创建新的实例
>>> s2.set_age(25) # 尝试调用方法
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'Student' object has no attribute 'set_age'
```

解决办法：为了给所有实例都绑定方法，可以给class绑定方法：

```python
>>> def set_score(self, score):
...     self.score = score
...
>>> Student.set_score = set_score
```

#### 使用__slots__

但是，如果我们想要限制实例的属性怎么办？比如，只允许对Student实例添加`name`和`age`属性。

为了达到限制的目的，Python允许在定义class的时候，定义一个特殊的`__slots__`变量，来限制该class实例能添加的属性：（相当于这个类只能添加这两个属性，多的会报错）

```python
class Student(object):
    __slots__ = ('name', 'age') # 用tuple定义允许绑定的属性名称
```

```python
>>> s = Student() # 创建新的实例
>>> s.name = 'Michael' # 绑定属性'name'
>>> s.age = 25 # 绑定属性'age'
>>> s.score = 99 # 绑定属性'score'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'Student' object has no attribute 'score'
```

由于`'score'`没有被放到`__slots__`中，所以不能绑定`score`属性，试图绑定`score`将得到`AttributeError`的错误。

使用`__slots__`要注意，`__slots__`定义的属性仅对当前类实例起作用，对继承的子类是不起作用的：

```python
>>> class GraduateStudent(Student):
...     pass
...
>>> g = GraduateStudent()
>>> g.score = 9999
```

除非在子类中也定义`__slots__`，这样，子类实例允许定义的属性就是自身的`__slots__`加上父类的`__slots__`。

### 13.2 使用@property

为了限制score的范围，可以通过一个`set_score()`方法来设置成绩，再通过一个`get_score()`来获取成绩，这样，在`set_score()`方法里，就可以检查参数：

```python
class Student(object):

    def get_score(self):
         return self._score

    def set_score(self, value):
        if not isinstance(value, int):
            raise ValueError('score must be an integer!')
        if value < 0 or value > 100:
            raise ValueError('score must between 0 ~ 100!')
        self._score = value
```

现在，对任意的Student实例进行操作，就不能随心所欲地设置score了。

至于关键字raise是什么，我们在后面章节会好好说的。

Python内置的`@property`装饰器就是负责**把一个方法变成属性调用的**：

```python
class Student(object):

    @property
    def score(self):
        return self._score

    @score.setter
    def score(self, value):
        if not isinstance(value, int):
            raise ValueError('score must be an integer!')
        if value < 0 or value > 100:
            raise ValueError('score must between 0 ~ 100!')
        self._score = value
```

把一个getter方法变成属性，只需要加上`@property`就可以了，此时，`@property`本身又创建了另一个装饰器`@score.setter`，负责把一个setter方法变成属性赋值

这个神奇的`@property`，我们在对实例属性操作的时候，就知道该属性很可能不是直接暴露的，而是通过getter和setter方法来实现的。

还可以定义只读属性，只定义getter方法，不定义setter方法就是一个只读属性：

```python
class Student(object):

    @property
    def birth(self):
        return self._birth

    @birth.setter
    def birth(self, value):
        self._birth = value

    @property
    def age(self):
        return 2015 - self._birth
```

上面的`birth`是可读写属性，而`age`就是一个*只读*属性，因为`age`可以根据`birth`和当前时间计算出来。

### 13.3 多重继承

相当于一个子类可以继承多个父类

回忆一下`Animal`类层次的设计，假设我们要实现以下4种动物：

- Dog - 狗狗；
- Bat - 蝙蝠；
- Parrot - 鹦鹉；
- Ostrich - 鸵鸟。

如果按照哺乳动物和鸟类归类，我们可以设计出这样的类的层次：

```ascii
                |     Animal    │
                └───────────────┘
                        │
           ┌────────────┴────────────┐
           │                         │
           ▼                         ▼
    ┌─────────────┐           ┌─────────────┐
    │   Mammal    │           │    Bird     │
    └─────────────┘           └─────────────┘
           │                         │
     ┌─────┴──────┐            ┌─────┴──────┐
     │            │            │            │
     ▼            ▼            ▼            ▼
┌─────────┐  ┌─────────┐  ┌─────────┐  ┌─────────┐
│   Dog   │  │   Bat   │  │ Parrot  │  │ Ostrich │
└─────────┘  └─────────┘  └─────────┘  └─────────┘
```

但是如果按照“能跑”和“能飞”来归类，我们就应该设计出这样的类的层次：

```ascii
                ┌───────────────┐
                │    Animal     │
                └───────────────┘
                        │
           ┌────────────┴────────────┐
           │                         │
           ▼                         ▼
    ┌─────────────┐           ┌─────────────┐
    │  Runnable   │           │   Flyable   │
    └─────────────┘           └─────────────┘
           │                         │
     ┌─────┴──────┐            ┌─────┴──────┐
     │            │            │            │
     ▼            ▼            ▼            ▼
┌─────────┐  ┌─────────┐  ┌─────────┐  ┌─────────┐
│   Dog   │  │ Ostrich │  │ Parrot  │  │   Bat   │
└─────────┘  └─────────┘  └─────────┘  └─────────┘
```

如果要把上面的两种分类都包含进来，我们就得设计更多的层次：

- 哺乳类：能跑的哺乳类，能飞的哺乳类；
- 鸟类：能跑的鸟类，能飞的鸟类。

这么一来，类的层次就复杂了：

```ascii
                ┌───────────────┐
                │    Animal     │
                └───────────────┘
                        │
           ┌────────────┴────────────┐
           │                         │
           ▼                         ▼
    ┌─────────────┐           ┌─────────────┐
    │   Mammal    │           │    Bird     │
    └─────────────┘           └─────────────┘
           │                         │
     ┌─────┴──────┐            ┌─────┴──────┐
     │            │            │            │
     ▼            ▼            ▼            ▼
┌─────────┐  ┌─────────┐  ┌─────────┐  ┌─────────┐
│  MRun   │  │  MFly   │  │  BRun   │  │  BFly   │
└─────────┘  └─────────┘  └─────────┘  └─────────┘
     │            │            │            │
     │            │            │            │
     ▼            ▼            ▼            ▼
┌─────────┐  ┌─────────┐  ┌─────────┐  ┌─────────┐
│   Dog   │  │   Bat   │  │ Ostrich │  │ Parrot  │
└─────────┘  └─────────┘  └─────────┘  └─────────┘
```

如果要再增加“宠物类”和“非宠物类”，这么搞下去，类的数量会呈指数增长，很明显这样设计是不行的。

正确的做法是采用多重继承。

首先，主要的类层次仍按照哺乳类和鸟类设计：

```
class Animal(object):
    pass

# 大类:
class Mammal(Animal):
    pass

class Bird(Animal):
    pass

# 各种动物:
class Dog(Mammal):
    pass

class Bat(Mammal):
    pass

class Parrot(Bird):
    pass

class Ostrich(Bird):
    pass
```

现在，我们要给动物再加上`Runnable`和`Flyable`的功能，只需要先定义好`Runnable`和`Flyable`的类：

```python
class Runnable(object):
    def run(self):
        print('Running...')

class Flyable(object):
    def fly(self):
        print('Flying...')
```

对于需要`Runnable`功能的动物，就多继承一个`Runnable`，例如`Dog`：

```python
class Dog(Mammal, Runnable):
    pass
```

对于需要`Flyable`功能的动物，就多继承一个`Flyable`，例如`Bat`：

```python
class Bat(Mammal, Flyable):
    pass
```

通过多重继承，一个子类就可以同时获得多个父类的所有功能。

**MixIn**

在设计类的继承关系时，通常，主线都是单一继承下来的，例如，`Ostrich`继承自`Bird`。但是，如果需要“混入”额外的功能，通过多重继承就可以实现，比如，让`Ostrich`除了继承自`Bird`外，再同时继承`Runnable`。这种设计通常称之为MixIn。

MixIn的目的就是给一个类增加多个功能，这样，在设计类的时候，我们优先考虑通过多重继承来组合多个MixIn的功能，而不是设计多层次的复杂的继承关系。

例如：

```python
class MyTCPServer(TCPServer, ForkingMixIn):
    pass
```

### 13.4 定制类（魔术方法）

看到类似`__slots__`这种形如`__xxx__`的变量或者函数名就要注意，这些在Python中是有特殊用途的。

`__slots__`我们已经知道怎么用了，`__len__()`方法我们也知道是为了能让class作用于`len()`函数。

除此之外，Python的class中还有许多这样有特殊用途的函数，可以帮助我们定制类。

定制类繁多，大家了解即可，不用刻意去记。

资源下载：https://www.liaoxuefeng.com/wiki/1016959663602400/1017590712115904

### 13.5 枚举类

当我们需要定义常量时，一个办法是用大写变量通过整数来定义，例如月份：

```
JAN = 1
FEB = 2
MAR = 3
...
NOV = 11
DEC = 12
```

好处是简单，缺点是类型是`int`，并且仍然是变量。

更好的方法是为这样的枚举类型定义一个class类型，然后，每个常量都是class的一个唯一实例。Python提供了`Enum`类来实现这个功能：

```python
from enum import Enum

Month = Enum('Month', ('Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'))
```

访问方法：

```python
for name, member in Month.__members__.items():
    print(name, '=>', member, ',', member.value)
```

这样我们就获得了`Month`类型的枚举类，可以直接使用`Month.Jan`来引用一个常量，

如果需要更精确地控制枚举类型，可以从`Enum`派生出自定义类：

```python
from enum import Enum, unique

@unique
class Weekday(Enum):
    Sun = 0 # Sun的value被设定为0
    Mon = 1
    Tue = 2
    Wed = 3
    Thu = 4
    Fri = 5
    Sat = 6
```

`@unique`装饰器可以帮助我们检查保证没有重复值。

访问这些枚举类型可以有若干种方法：

```python
>>> day1 = Weekday.Mon
>>> print(day1)
Weekday.Mon
>>> print(Weekday.Tue)
Weekday.Tue
>>> print(Weekday['Tue'])
Weekday.Tue
>>> print(Weekday.Tue.value)
2
>>> print(day1 == Weekday.Mon)
True
>>> print(day1 == Weekday.Tue)
False
>>> print(Weekday(1))
Weekday.Mon
>>> print(day1 == Weekday(1))
True
>>> Weekday(7)
Traceback (most recent call last):
  ...
ValueError: 7 is not a valid Weekday
>>> for name, member in Weekday.__members__.items():
...     print(name, '=>', member)
...
Sun => Weekday.Sun
Mon => Weekday.Mon
Tue => Weekday.Tue
Wed => Weekday.Wed
Thu => Weekday.Thu
Fri => Weekday.Fri
Sat => Weekday.Sat
```

name是key，member是value

## 14.异常、调试与测试

### 14.1 异常

在程序运行过程中，总会遇到各种各样的错误，我们程序员就是在不断处理产生的bug，bug处理方法在前面也出现过，只是没有刻意强调，所以我们就要来看如何处理bug。

所以高级语言通常都内置了一套`try...except...finally...`的错误处理机制，Python也不例外。但是在C++与Java里面是try...catch，但是性质一模一样

#### 14.1.1 try

让我们用一个例子来看看`try`的机制：

```python
try:
    print('try...')
    r = 10 / 0
    print('result:', r)
except ZeroDivisionError as e:
    print('except:', e)
finally:
    print('finally...')
print('END')
```

当我们认为某些代码可能会出错时，就可以用`try`来运行这段代码，如果执行出错，则后续代码不会继续执行，而是直接跳转至错误处理代码，即`except`语句块，执行完`except`后，如果有`finally`语句块，则执行`finally`语句块，至此，执行完毕。

没有错误发生，所以`except`语句块不会被执行，但是`finally`如果有，则一定会被执行（可以没有`finally`语句）。

你还可以猜测，错误应该有很多种类，如果发生了不同类型的错误，应该由不同的`except`语句块处理。没错，可以有多个`except`来捕获不同类型的错误：

```python
try:
    print('try...')
    r = 10 / int('a')
    print('result:', r)
except ValueError as e:
    print('ValueError:', e)
except ZeroDivisionError as e:
    print('ZeroDivisionError:', e)
finally:
    print('finally...')
print('END')
```

`int()`函数可能会抛出`ValueError`，所以我们用一个`except`捕获`ValueError`，用另一个`except`捕获`ZeroDivisionError`。

此外，如果没有错误发生，可以在`except`语句块后面加一个`else`，当没有错误发生时，会自动执行`else`语句：

```python
try:
    print('try...')
    r = 10 / int('2')
    print('result:', r)
except ValueError as e:
    print('ValueError:', e)
except ZeroDivisionError as e:
    print('ZeroDivisionError:', e)
else:
    print('no error!')
finally:
    print('finally...')
print('END')
```

此时的你会发现，错误处理可以采用as关键字来弄

Python的错误其实也是class，所有的错误类型都继承自`BaseException`，所以在使用`except`时需要注意的是，它不但捕获该类型的错误，还把其子类也“一网打尽”。比如：

```python
try:
    foo()
except ValueError as e:
    print('ValueError')
except UnicodeError as e:
    print('UnicodeError')
```

第二个`except`永远也捕获不到`UnicodeError`，因为`UnicodeError`是`ValueError`的子类，如果有，也被第一个`except`给捕获了。

**调用栈：就是出错了他会一级一级地向上抛出。出错的时候，一定要分析错误的调用栈信息，才能定位错误的位置。**

#### 14.1.2 错误记录

观看文档我们发现，原来我们产生的错误BaseException下面一个子类叫Exception

如果实在是不知道怎么写，就写Exception来处理就完了。

如果不捕获错误，自然可以让Python解释器来打印出错误堆栈，但程序也被结束了。既然我们能捕获错误，就可以把错误堆栈打印出来，然后分析错误原因，同时，让程序继续执行下去。

Python内置的`logging`模块可以非常容易地记录错误信息：

```python
# err_logging.py

import logging

def foo(s):
    return 10 / int(s)

def bar(s):
    return foo(s) * 2

def main():
    try:
        bar('0')
    except Exception as e:
        logging.exception(e)

main()
print('END')
```

结果如下：

```python
$ python3 err_logging.py
ERROR:root:division by zero
Traceback (most recent call last):
  File "err_logging.py", line 13, in main
    bar('0')
  File "err_logging.py", line 9, in bar
    return foo(s) * 2
  File "err_logging.py", line 6, in foo
    return 10 / int(s)
ZeroDivisionError: division by zero
END
```

#### 14.1.3 抛出错误

在Java与C++语言里面常用throw或者throws关键字进行抛出

如果要抛出错误，首先根据需要，可以定义一个错误的class，选择好继承关系，然后，用`raise`语句抛出一个错误的实例：

```python
# err_raise.py
class FooError(ValueError):
    pass

def foo(s):
    n = int(s)
    if n==0:
        raise FooError('invalid value: %s' % s)
    return 10 / n

foo('0')
```

但是自定义错误注意函数首字母大写。我们可以知道自己错误处理机制

最后，我们来看另一种错误处理的方式：

```python
# err_reraise.py

def foo(s):
    n = int(s)
    if n==0:
        raise ValueError('invalid value: %s' % s)
    return 10 / n

def bar():
    try:
        foo('0')
    except ValueError as e:
        print('ValueError!')
        raise

bar()
```

在`bar()`函数中，我们明明已经捕获了错误，但是，打印一个`ValueError!`后，又把错误通过`raise`语句抛出去了，这不有病么？

其实这种错误处理方式不但没病，而且相当常见。捕获错误目的只是记录一下，便于后续追踪。但是，由于当前函数不知道应该怎么处理该错误，所以，最恰当的方式是继续往上抛，让顶层调用者去处理。好比一个员工处理不了一个问题时，就把问题抛给他的老板，如果他的老板也处理不了，就一直往上抛，最终会抛给CEO去处理。

`raise`语句如果不带参数，就会把当前错误原样抛出。此外，在`except`中`raise`一个Error，还可以把一种类型的错误转化成另一种类型

只要是合理的转换逻辑就可以，但是，决不应该把一个`IOError`转换成毫不相干的`ValueError`。

### 14.2 调试

#### 14.2.1 断言

因为用print打印错误以后，会导致运行结果也会包含很多垃圾信息。凡是用`print()`来辅助查看的地方，都可以用断言（assert）来替代：

```
def foo(s):
    n = int(s)
    assert n != 0, 'n is zero!'
    return 10 / n

def main():
    foo('0')
```

`assert`的意思是，表达式`n != 0`应该是`True`，否则，根据程序运行的逻辑，后面的代码肯定会出错。

如果断言失败，`assert`语句本身就会抛出`AssertionError`：

```python
$ python err.py
Traceback (most recent call last):
  ...
AssertionError: n is zero!
```

程序中如果到处充斥着`assert`，和`print()`相比也好不到哪去。不过，启动Python解释器时可以用`-O`参数来关闭`assert`：

**断言的开关“-O”是英文大写字母O，不是数字0。**

#### 14.2.2 logging

把`print()`替换为`logging`是第3种方式，和`assert`比，`logging`不会抛出错误，而且可以输出到文件：

```
import logging

s = '0'
n = int(s)
logging.info('n = %d' % n)
print(10 / n)
```

`logging.info()`就可以输出一段文本。运行，发现除了`ZeroDivisionError`，没有任何信息。怎么回事？

别急，在`import logging`之后添加一行配置再试试：

```python
import logging
logging.basicConfig(level=logging.INFO)
```

看到输出了：

```
$ python err.py
INFO:root:n = 0
Traceback (most recent call last):
  File "err.py", line 8, in <module>
    print(10 / n)
ZeroDivisionError: division by zero
```

这就是`logging`的好处，它允许你指定记录信息的级别，有`debug`，`info`，`warning`，`error`等几个级别，当我们指定`level=INFO`时，`logging.debug`就不起作用了。同理，指定`level=WARNING`后，`debug`和`info`就不起作用了。这样一来，你可以放心地输出不同级别的信息，也不用删除，最后统一控制输出哪个级别的信息。

#### 14.2.3 pdb

第4种方式是启动Python的调试器pdb，让程序以单步方式运行，可以随时查看运行状态。我们先准备好程序：

```python
# err.py
s = '0'
n = int(s)
print(10 / n)
```

然后启动：

```
$ python -m pdb err.py
> /Users/michael/Github/learn-python3/samples/debug/err.py(2)<module>()
-> s = '0'
```

以参数`-m pdb`启动后，pdb定位到下一步要执行的代码`-> s = '0'`。输入命令`l`来查看代码：

```
(Pdb) l
  1     # err.py
  2  -> s = '0'
  3     n = int(s)
  4     print(10 / n)
```

输入命令`n`可以单步执行代码：

```
(Pdb) n
> /Users/michael/Github/learn-python3/samples/debug/err.py(3)<module>()
-> n = int(s)
(Pdb) n
> /Users/michael/Github/learn-python3/samples/debug/err.py(4)<module>()
-> print(10 / n)
```

任何时候都可以输入命令`p 变量名`来查看变量：

```
(Pdb) p s
'0'
(Pdb) p n
0
```

输入命令`q`结束调试，退出程序：

```
(Pdb) q
```

这种通过pdb在命令行调试的方法理论上是万能的，但实在是太麻烦了，如果有一千行代码，要运行到第999行得敲多少命令啊。还好，我们还有另一种调试方法。

#### 14.2.4 pdb.set_trace()

这个方法也是用pdb，但是不需要单步执行，我们只需要`import pdb`，然后，在可能出错的地方放一个`pdb.set_trace()`，就可以设置一个断点：

```python
# err.py
import pdb

s = '0'
n = int(s)
pdb.set_trace() # 运行到这里会自动暂停
print(10 / n)
```

运行代码，程序会自动在`pdb.set_trace()`暂停并进入pdb调试环境，可以用命令`p`查看变量，或者用命令`c`继续运行：

```
$ python err.py 
> /Users/michael/Github/learn-python3/samples/debug/err.py(7)<module>()
-> print(10 / n)
(Pdb) p n
0
(Pdb) c
Traceback (most recent call last):
  File "err.py", line 7, in <module>
    print(10 / n)
ZeroDivisionError: division by zero
```

这个方式比直接启动pdb单步调试效率要高很多，但也高不到哪去。

### 14.3 单元测试

把测试用例放到一个测试模块里，就是一个完整的单元测试。

为了编写单元测试，我们需要引入Python自带的`unittest`模块，编写`mydict_test.py`如下：

```python
import unittest

from mydict import Dict

class TestDict(unittest.TestCase):

    def test_init(self):
        d = Dict(a=1, b='test')
        self.assertEqual(d.a, 1)
        self.assertEqual(d.b, 'test')
        self.assertTrue(isinstance(d, dict))

    def test_key(self):
        d = Dict()
        d['key'] = 'value'
        self.assertEqual(d.key, 'value')

    def test_attr(self):
        d = Dict()
        d.key = 'value'
        self.assertTrue('key' in d)
        self.assertEqual(d['key'], 'value')

    def test_keyerror(self):
        d = Dict()
        with self.assertRaises(KeyError):
            value = d['empty']

    def test_attrerror(self):
        d = Dict()
        with self.assertRaises(AttributeError):
            value = d.empty
```

编写单元测试时，我们需要编写一个测试类，从`unittest.TestCase`继承。

以`test`开头的方法就是测试方法，不以`test`开头的方法不被认为是测试方法，测试的时候不会被执行。

对每一类测试都需要编写一个`test_xxx()`方法。由于`unittest.TestCase`提供了很多内置的条件判断，我们只需要调用这些方法就可以断言输出是否是我们所期望的。最常用的断言就是`assertEqual()`

#### 14.3.1 运行单元测试

一旦编写好单元测试，我们就可以运行单元测试。最简单的运行方式是在`mydict_test.py`的最后加上两行代码：

```
if __name__ == '__main__':
    unittest.main()
```

这样就可以把`mydict_test.py`当做正常的python脚本运行：

```
$ python mydict_test.py
```

另一种方法是在命令行通过参数`-m unittest`直接运行单元测试：

```
$ python -m unittest mydict_test
.....
----------------------------------------------------------------------
Ran 5 tests in 0.000s

OK
```

这是推荐的做法，因为这样可以一次批量运行很多单元测试，并且，有很多工具可以自动来运行这些单元测试。

#### 14.3.2 setUp与tearDown

可以在单元测试中编写两个特殊的`setUp()`和`tearDown()`方法。这两个方法会分别在每调用一个测试方法的前后分别被执行。

`setUp()`和`tearDown()`方法有什么用呢？设想你的测试需要启动一个数据库，这时，就可以在`setUp()`方法中连接数据库，在`tearDown()`方法中关闭数据库，这样，不必在每个测试方法中重复相同的代码. 

## 15. IO编程

IO在计算机中指Input/Output，也就是输入和输出。由于程序和运行时数据是在内存中驻留，由CPU这个超快的计算核心来执行，涉及到数据交换的地方，通常是磁盘、网络等，就需要IO接口。

IO编程中，Stream（流）是一个很重要的概念，可以把流想象成一个水管，数据就是水管里的水，但是只能单向流动。Input Stream就是数据从外面（磁盘、网络）流进内存，Output Stream就是数据从内存流到外面去。

操作IO的能力都是由操作系统提供的，每一种编程语言都会把操作系统提供的低级C接口封装起来方便使用，Python也不例外。我们后面会详细讨论Python的IO编程接口。

### 15.1 文件读写

#### 15.1.1 读文件

要以读文件的模式打开一个文件对象，使用Python内置的`open()`函数，传入文件名和标示符：

```python
>>> f = open('/Users/michael/test.txt', 'r')
```

标示符'r'表示读，这样，我们就成功地打开了一个文件。

如果文件不存在，`open()`函数就会抛出一个`IOError`的错误。

如果文件打开成功，接下来，调用`read()`方法可以一次读取文件的全部内容，Python把内容读到内存，用一个`str`对象表示：

```python
>>> f.read()
'Hello, world!'
```

最后一步是调用`close()`方法关闭文件。文件使用完毕后必须关闭，因为文件对象会占用操作系统的资源，并且操作系统同一时间能打开的文件数量也是有限的：

```python
>>> f.close()
```

由于文件读写时都有可能产生`IOError`，一旦出错，后面的`f.close()`就不会调用。所以，为了保证无论是否出错都能正确地关闭文件，我们可以使用`try ... finally`来实现：

```python
try:
    f = open('/path/to/file', 'r')
    print(f.read())
finally:
    if f:
        f.close()
```

但是每次都这么写实在太繁琐，所以，Python引入了`with`语句来自动帮我们调用`close()`方法：

```python
with open('/path/to/file', 'r') as f:
    print(f.read())
```

这和前面的`try ... finally`是一样的，但是代码更佳简洁，并且不必调用`f.close()`方法。

调用`read()`会一次性读取文件的全部内容，如果文件有10G，内存就爆了，所以，要保险起见，可以反复调用`read(size)`方法，每次最多读取size个字节的内容。另外，调用`readline()`可以每次读取一行内容，调用`readlines()`一次读取所有内容并按行返回`list`。

#### 15.1.2 二进制文件

前面讲的默认都是读取文本文件，并且是UTF-8编码的文本文件。要读取二进制文件，比如图片、视频等等，用`'rb'`模式打开文件即可：

```python
>>> f = open('/Users/michael/test.jpg', 'rb')
>>> f.read()
b'\xff\xd8\xff\xe1\x00\x18Exif\x00\x00...' # 十六进制表示的字节
```

#### 15.1.3 字符编码

要读取非UTF-8编码的文本文件，需要给`open()`函数传入`encoding`参数，例如，读取GBK编码的文件：

```python
>>> f = open('/Users/michael/gbk.txt', 'r', encoding='gbk')
>>> f.read()
'测试'
```

遇到有些编码不规范的文件，你可能会遇到`UnicodeDecodeError`，因为在文本文件中可能夹杂了一些非法编码的字符。遇到这种情况，`open()`函数还接收一个`errors`参数，表示如果遇到编码错误后如何处理。最简单的方式是直接忽略：

```python
>>> f = open('/Users/michael/gbk.txt', 'r', encoding='gbk', errors='ignore')
```

#### 15.1.4 写文件

写文件和读文件是一样的，唯一区别是调用`open()`函数时，传入标识符`'w'`或者`'wb'`表示写文本文件或写二进制文件：

```python
>>> f = open('/Users/michael/test.txt', 'w')
>>> f.write('Hello, world!')
>>> f.close()
```

你可以反复调用`write()`来写入文件，但是务必要调用`f.close()`来关闭文件。当我们写文件时，操作系统往往不会立刻把数据写入磁盘，而是放到内存缓存起来，空闲的时候再慢慢写入。只有调用`close()`方法时，操作系统才保证把没有写入的数据全部写入磁盘。忘记调用`close()`的后果是数据可能只写了一部分到磁盘，剩下的丢失了。所以，还是用`with`语句来得保险：

```python
with open('/Users/michael/test.txt', 'w') as f:
    f.write('Hello, world!')
```

要写入特定编码的文本文件，请给`open()`函数传入`encoding`参数，将字符串自动转换成指定编码。

细心的童鞋会发现，以`'w'`模式写入文件时，如果文件已存在，会直接覆盖（相当于删掉后新写入一个文件）。如果我们希望追加到文件末尾怎么办？可以传入`'a'`以追加（append）模式写入。

```python
with open('/Users/michael/test.txt', 'a') as f:
    f.write('Hello, world!')
```

### 15.2 StringIO与ByteIO

#### 15.2.1 StringIO

StringIO顾名思义就是在内存中读写str。

要把str写入StringIO，我们需要先创建一个StringIO，然后，像文件一样写入即可：

```python
>>> from io import StringIO
>>> f = StringIO()
>>> f.write('hello')
5
>>> f.write(' ')
1
>>> f.write('world!')
6
>>> print(f.getvalue())
hello world!
```

`getvalue()`方法用于获得写入后的str。

要读取StringIO，可以用一个str初始化StringIO，然后，像读文件一样读取：

```python
>>> from io import StringIO
>>> f = StringIO('Hello!\nHi!\nGoodbye!')
>>> while True:
...     s = f.readline()
...     if s == '':
...         break
...     print(s.strip())
...
Hello!
Hi!
Goodbye!
```

#### 15.2.2 BytesIO

StringIO操作的只能是str，如果要操作二进制数据，就需要使用BytesIO。

BytesIO实现了在内存中读写bytes，我们创建一个BytesIO，然后写入一些bytes：

```python
>>> from io import BytesIO
>>> f = BytesIO()
>>> f.write('中文'.encode('utf-8'))
6
>>> print(f.getvalue())
b'\xe4\xb8\xad\xe6\x96\x87'
```

请注意，写入的不是str，而是经过UTF-8编码的bytes。

和StringIO类似，可以用一个bytes初始化BytesIO，然后，像读文件一样读取：

```python
>>> from io import BytesIO
>>> f = BytesIO(b'\xe4\xb8\xad\xe6\x96\x87')
>>> f.read()
b'\xe4\xb8\xad\xe6\x96\x87'
```

### 15.3 文件操作

ile', 'r')
    print(f.read())
finally:
    if f:
        f.close()
```

但是每次都这么写实在太繁琐，所以，Python引入了`with`语句来自动帮我们调用`close()`方法：

```python
with open('/path/to/file', 'r') as f:
    print(f.read())
```

这和前面的`try ... finally`是一样的，但是代码更佳简洁，并且不必调用`f.close()`方法。

调用`read()`会一次性读取文件的全部内容，如果文件有10G，内存就爆了，所以，要保险起见，可以反复调用`read(size)`方法，每次最多读取size个字节的内容。另外，调用`readline()`可以每次读取一行内容，调用`readlines()`一次读取所有内容并按行返回`list`。

#### 15.1.2 二进制文件

前面讲的默认都是读取文本文件，并且是UTF-8编码的文本文件。要读取二进制文件，比如图片、视频等等，用`'rb'`模式打开文件即可：

```python
>>> f = open('/Users/michael/test.jpg', 'rb')
>>> f.read()
b'\xff\xd8\xff\xe1\x00\x18Exif\x00\x00...' # 十六进制表示的字节
```

#### 15.1.3 字符编码

要读取非UTF-8编码的文本文件，需要给`open()`函数传入`encoding`参数，例如，读取GBK编码的文件：

```python
>>> f = open('/Users/michael/gbk.txt', 'r', encoding='gbk')
>>> f.read()
'测试'
```

遇到有些编码不规范的文件，你可能会遇到`UnicodeDecodeError`，因为在文本文件中可能夹杂了一些非法编码的字符。遇到这种情况，`open()`函数还接收一个`errors`参数，表示如果遇到编码错误后如何处理。最简单的方式是直接忽略：

```python
>>> f = open('/Users/michael/gbk.txt', 'r', encoding='gbk', errors='ignore')
```

#### 15.1.4 写文件

写文件和读文件是一样的，唯一区别是调用`open()`函数时，传入标识符`'w'`或者`'wb'`表示写文本文件或写二进制文件：

```python
>>> f = open('/Users/michael/test.txt', 'w')
>>> f.write('Hello, world!')
>>> f.close()
```

你可以反复调用`write()`来写入文件，但是务必要调用`f.close()`来关闭文件。当我们写文件时，操作系统往往不会立刻把数据写入磁盘，而是放到内存缓存起来，空闲的时候再慢慢写入。只有调用`close()`方法时，操作系统才保证把没有写入的数据全部写入磁盘。忘记调用`close()`的后果是数据可能只写了一部分到磁盘，剩下的丢失了。所以，还是用`with`语句来得保险：

```python
with open('/Users/michael/test.txt', 'w') as f:
    f.write('Hello, world!')
```

要写入特定编码的文本文件，请给`open()`函数传入`encoding`参数，将字符串自动转换成指定编码。

细心的童鞋会发现，以`'w'`模式写入文件时，如果文件已存在，会直接覆盖（相当于删掉后新写入一个文件）。如果我们希望追加到文件末尾怎么办？可以传入`'a'`以追加（append）模式写入。

```python
with open('/Users/michael/test.txt', 'a') as f:
    f.write('Hello, world!')
```

### 15.2 StringIO与ByteIO

#### 15.2.1 StringIO

StringIO顾名思义就是在内存中读写str。

要把str写入StringIO，我们需要先创建一个StringIO，然后，像文件一样写入即可：

```python
>>> from io import StringIO
>>> f = StringIO()
>>> f.write('hello')
5
>>> f.write(' ')
1
>>> f.write('world!')
6
>>> print(f.getvalue())
hello world!
```

`getvalue()`方法用于获得写入后的str。

要读取StringIO，可以用一个str初始化StringIO，然后，像读文件一样读取：

```python
>>> from io import StringIO
>>> f = StringIO('Hello!\nHi!\nGoodbye!')
>>> while True:
...     s = f.readline()
...     if s == '':
...         break
...     print(s.strip())
...
Hello!
Hi!
Goodbye!
```

#### 15.2.2 BytesIO

StringIO操作的只能是str，如果要操作二进制数据，就需要使用BytesIO。

BytesIO实现了在内存中读写bytes，我们创建一个BytesIO，然后写入一些bytes：

```python
>>> from io import BytesIO
>>> f = BytesIO()
>>> f.write('中文'.encode('utf-8'))
6
>>> print(f.getvalue())
b'\xe4\xb8\xad\xe6\x96\x87'
```

请注意，写入的不是str，而是经过UTF-8编码的bytes。

和StringIO类似，可以用一个bytes初始化BytesIO，然后，像读文件一样读取：

```python
>>> from io import BytesIO
>>> f = BytesIO(b'\xe4\xb8\xad\xe6\x96\x87')
>>> f.read()
b'\xe4\xb8\xad\xe6\x96\x87'
```

### 15.3 文件操作

详情见此：https://www.liaoxuefeng.com/wiki/1016959663602400/1017623135437088
