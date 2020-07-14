# python里面的正则表达式

## 1. 正则表达式基础

### 1.1 定义

是对一段文字进行文本检索，进一步替换与提取操作，不是编程语言，是一种通用的逻辑公式。

其支持Java，JavaScript，python等语言。

python里面已经内置了正则表达式，只要调用re库即可。

```python
import re
```

正则表达式在一般情况下写成‘\\\w\\\\.’形式，但是python写成r‘\\w\\.’

其中r让反斜杠不再表示转义字符

### 1.2 回车，换行，制表符

换行符：\n，计算机识别就在于此

回车符：在Windows里面 回车换行\r\n，其他操作系统\n，Windows回车符：\r，在正则表达式里面，\r表示回车符

制表符：tab键产生。

键宽固定：一个字符宽度，由于操作系统不一样，宽度可能不一样

\t在正则表达式里面表示制表符。

\f表示换页符，\v表示垂直制表符。

### 1.3 空白符与非空白符

空白符：\s匹配任何空白字符，包括空格、制表符、换页符等等（注意s要小写）

非空白符：\S（注意S大写）匹配任何非空白字符。

### 1.4 开头与结尾

字符串开头：^表示字符串的开头，eg：^\\+86表示字符串开头必须是以+86开头

字符串结尾：$表示字符串的结尾，eg：\\+86$表示字符串结尾必须是以+86结尾

判断是否以某个字符开头用^,判断是否以某个字符结尾用$

由于+表示一个表达式，\\+不是表达式，是他本身

### 1.5 单词、数字与点

单词字符：\\w，w小写，匹配包括下划线在内的任何一个单词字符，但是+ - * / 都不是

\W ,W大写匹配非单词字符

数字：\d，小写，匹配一个数字字符

\D，大写，匹配一个非数字字符

点表达式：.也是表达式，匹配除换行符以外（\\n、\\r）以外的任何单个字符，包括制表符\\t

## 2. 特殊字符

### 2.1 原义字符

正则表达式前面加一个反斜杠\，表示字符原义。

### 2.2 逻辑‘或’条件

逻辑或：|和or判断一模一样

### 2.3 子表达式

子表达式：为了精确描述其中一部分规则，通常把多个表达式组合起来，作为部分逻辑作用，放在()里面。

### 2.4 中括号表达式

可以表示区间范围：

[a-z]所有的小写字母

[A-Z]所有的大写字母

[0-9]数字

这个比固定范围表达式更加灵活，范围可以调整

可以表示可枚举的范围：

[a4j7]等价于a|4|j|7 表示可以匹配到中括号里面任意一个字符

混合[0,5-9],表示0 5 6 7 8 9

[2,4]**枚举数字要用逗号隔开**

排除范围，其实字符^在中括号里面表示非的范围

### 2.5 限定符表达式

**一般限定符**

？表示前面的子表达式可以出现零次或者一次

eg：go?d 可以匹配gd或者god，但是不能匹配good

+不是运算符，前面子表达式一次或多次（大于等于1次）

eg：go+d 不可以匹配gd，可以匹配god，也可以匹配good

*匹配前面的子表达式任意次

go*d可以匹配gd，god，也可以匹配good

**范围限定符**

在{}里面进行使用

{n}表示确定的n次

{n，}至少匹配n次

{n，m}匹配n到m次

上限到几次：{0，n}最多n次

### 2.6 贪婪匹配与非贪婪匹配

贪婪模式：尽量检索最多的结果，一般限定符与范围限定符默认都是

```python
import re

text = "I thought a thought. But the thought I thought wasn't the thought I thought I thought."

regex = r'thought(.+)thought'
matchObj = re.search(regex, text)

if matchObj:
  print(matchObj.group())
```

非贪婪模式：在范围限定符后面加上？即可

```python
import re

text = "I thought a thought. But the thought I thought wasn't the thought I thought I thought."

regex = r'thought(.+?)thought'
matchObj = re.search(regex, text)

if matchObj:
  print(matchObj.group())
```

## 3. 常用函数（必须判断match存在吗）

```python
if match：
```

### 3.1 单次检索

#### 3.1.1 检索第一个结果

检测文本，并且返回第一个结果，也就是文本里面是否包含至少一个正则表达式要求的内容

我们可以调用python库里面re里面的search()可以执行，第一个参数是正则表达式，第二个参数是字符串

#### 3.1.2 开头检索

match()方法只检测开头，只返回一个结果。

也就是说，使用match以后，可以不用考虑^开头符号了

#### 3.1.3 检索结果对象

无论是match还是search，都会返回结果对象，调用方法：group()可以获取匹配内容

如果没有则返回None

### 3.2 索引方法

起始位置：调用start()方法，取得匹配的第一个字符位置

结束位置：调查检索返回对象end()方法，左侧从1开始，取得末字符位置

起始与结束方法：span()方法，返回元组

### 3.3 全量搜索

#### 3.3.1 所有结果列表

findall()方法，查找所有内容

```python
re.findall(regex, text)
```

第一个参数是正则表达式，第二个是文本

返回的不是对象了，是字符串列表

```python
import re
 
line = 'I love dogs cats and others'
 
regex = r'\w+\s'

matchStrs = re.findall(regex, line)

print(matchStrs)

for matchStr in matchStrs :
  print(matchStr)
```

#### 3.3.1 所有结果迭代器

finditer()方法：

```python
import re
 
line = 'I love dogs cats and others'
 
regex = r'\w+\s'

matchObjs = re.finditer(regex, line)

for matchObj in matchObjs :
  print(matchObj.group() + ' start=' + str(matchObj.start()) + ' end=' + str(matchObj.end()))
```

返回的是一个包含检索结果的迭代器，可以进行遍历可以调用group，start，end，span方法

总结：取得简单匹配的用findall，如果要用更多的操作用finditer；

### 3.4 替换方法

re库提供了sub()方法，用于替换匹配内容

re.sub(正则表达式，替换后，源文本）源文本是被替换的串

指定替换次数：re.sub(正则表达式，替换后，源文本，次数）不写默认全部替换。

### 3.5 预编译

compile（正则表达式）

返回pattern对象，由于大量引用正则表达式会造成资源的浪费。

pattern 返回后的对象可以调用以前的函数

```python
import re

text = "2019-11-23"

## 替换所有的非数字的字符，兼容性好
regex = r'\D'
## 编译一次
pattern = re.compile(regex)

matchObjs = pattern.findall(text)
print(matchObjs)

targetText = pattern.sub('/', text)
print('日期：' + targetText)

```

### 3.6 分组

我们把子表达式称为组，获取每一个子表达式的匹配结果过程称为分组。

我们在前面的函数里面都可以调用来分组：

#### 3.6.1 整体结果

可以group方法进行，得到的就是整个表达式检索的结果。

```python
import re

text = "当前时间：2019-11-05 19:05:30 列车很快就要进站了，请旅客朋友们做好准备。"

## 获取被非单词字符分隔的时间数字
regex = r'(\d+)\W(\d+)'
pattern = re.compile(regex)
matchObj = pattern.search(text)

if matchObj:
  print("group() = " + matchObj.group())
else:
  print(无匹配内容)

```

#### 3.6.2 指定分组与所有分组

在group()括号里面加数字得到检索结果，1，2，3……正无穷大，参数从1开始，若参数没有，则默认是0，就是获取全部表达式。

所有分组：groups()注意多了一个s，相当于返回一个小组字符串的元组，元组里面可以用索引来访问groups()[index]相当于group(index+1)。

```python
import re

text = "当前时间：2019-11-05 19:05:30 列车很快就要进站了，请旅客朋友们做好准备。"

## 获取被非单词字符分隔的时间数字
regex = r'(\d+)\W(\d+)'
pattern = re.compile(regex)
matchObj = pattern.search(text)

if matchObj:
  print("groups() = " + str(matchObj.groups()))
  print("groups()[0] = " + matchObj.groups()[0])
  print("group(1) = " + matchObj.group(1))
else:
  print(无匹配内容)

```

注意：groups返回的是一个元组，不可以直接打印，要用str函数来弄

## 4 爬取基础

我们在前面三章里面介绍了正则表达式用法，要想好好学，还得玩真的

### 4.1 网页爬取

抓取网页信息：在前面网络编程里面也说过，抓取网页信息，先调用requests库，再调用get方法进行调用。

新闻链接的提取：在<<aa>>标签里面有。由于一个前端代码里面有很多这样的对子，我们要找最近的成对的。

### 4.2 链接的提取与标题

我们发现有乱码了，解决办法：用对象名.encoding='utf-8'

网址提取：a 里面href属性的值

标题提取：><中间内容

### 4.3 爬取代码：

```python
import re
import requests

## 抓取页面
response = requests.get('https://news.sina.com.cn/')
response.encoding = 'utf-8'
content = response.text

## 扫描 <a>xxx</a> 标签，这是新闻链接
aTagRegex = r"<a.+?/a>"
aTagPattern = re.compile(aTagRegex);

## 网址正则表达式
linkRegex = r"href=\"(.+?)\""
linkPattern = re.compile(linkRegex);

## 标题正则表达式
titleRegex = r">(.+)<"
titlePattern = re.compile(titleRegex);

matchs = aTagPattern.findall(content)

allNews={}
for matchStr in matchs:
  ## 解析网址
  matchLinkObj = linkPattern.search(matchStr)
  ## 解析标题
  matchTitleObj = titlePattern.search(matchStr)
  allNews[matchLinkObj]=matchTitleObj
  
print(allNews)
```

## 5 综合实例

我们在学完了一定理论基础上，我们进行了百度与哔哩哔哩的的爬取

源代码如下：

百度：

```python
import re
import requests

response = requests.get('https://news.baidu.com/')
response.encoding = 'utf-8'
contents = response.text

regex1 = r"<a.+?/a>"
pattern = re.compile(regex1)

regex2 = r"href=\"(.+?)\""
link = re.compile(regex2)

regex3 = r">(.+?)<"
title = re.compile(regex3)

matches = pattern.findall(contents)

items={}
for item in matches:
    linkObj = link.search(item)
    titleObj = title.search(item)
    items[linkObj] = titleObj

for key in items:
    print('链接：'+ str(key) + '标题' + str(items[key]))
```

哔哩哔哩：

```python
import re
import requests

target = requests.get('https://www.bilibili.com/')
target.encoding = 'utf-8'
texts = target.text

regex1 = r"<a.+?/a>"
resources = re.compile(regex1)

regex2 = r"href=\"(.+?)\""
link = re.compile(regex2)

regex3 = r">(.+?)<"
title = re.compile(regex3)

matches = resources.findall(texts)

resource = {}
for match in matches:
    linfKey = link.search(match)
    titleKey = title.search(match)
    resource[linfKey]=titleKey

for key in resource:
    print('链接：'+str(key)+'标题：'+ str(resource[key]))
```

案例分析：我们采用了知识点有：正则表达式，网络部分，还有基本语法：

正则表达式：由于我们要进行网络关键字搜索，所以使用正则表达式就可以减轻负担。正则表达式我们先预处理，就可以减少资源浪费，提高效率。我们正则表达式理论基础上，我们采用findall进行全盘搜索，方便遍历查找

网络部分：我们采用get方法进行资源调用，为了防止乱码，要改变字符形式：“utf-8”可以，获取相关资源采用text方法。

最后采用遍历的方法进行遍历
