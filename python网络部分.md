# python网络部分

## 1.基本概念

### 1.1 协议

网络协议的简称，是通信计算机双方必须共同遵守的同一组约定。只有遵守了计算机才能相互通信。

HTTP / HTTPS协议：

协议的相关内容在此：https://www.youkeda.com/post/detail/3d57607fa6364d1fb755153b54c1e536

### 1.2 URL

地址栏输入的地址叫做URL，也就是网址，叫做**统一资源定位器**

组成方式：

[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-a6NWrw7e-1594478631571)(C:\Users\24552\Downloads\py2-1-2.png)]

URL的格式,就像逛校园,先根据门牌号(域名)找到校园，跟门卫出示了学生证(协议)，顺着路/大楼/层/教室号(路径)走到了教室，告诉老师你的姓名(参数)，老师就可以给你传授知识啦。

### 1.3 其他补充内容

#### 1.3.1 端口号

你们肯定在复制链接的时候看到这些了叭：

https://www.douban.com:443/gallery/topic/116390/?from= hot_ topic_note&sort=new
域名后的: 443表示网站的端口号。HTTP协议默认的端口号是80HTTPS协议默认的端口号是「443
默认的端口号在URL中是可以省略的，其它的端口号就必须要写明了。

上网浏览时，大多数情况下看不到端口号，但是大家在开发过程中可能经常会用到不同的端口号，以8000
8080最常见，这些端口号必须写明。

#### 1.3.2 路径情况

##### 1.3.2.1 相对路径

只输入部分来体现

##### 1.3.2.2 默认路径

我们在.上网时，仅输入了https://www.douban.com或https://www.douban.com/都能打开豆瓣首页，并没有输入路径啊。
实际上，没有输入路径时，表示请求网站的默认页面，那么服务器就会返回一-个默认页面给浏览器。至于具体默认页面是什么页面，是由服务器决定的，通常服务器默认的页面是首页。

### 1.4 TCP/IP简介

因为互联网协议包含了上百种协议标准，但是最重要的两个协议是TCP和IP协议，所以，大家把互联网的协议简称TCP/IP协议。

通信的时候，双方必须知道对方的标识，好比发邮件必须知道对方的邮件地址。互联网上每个计算机的唯一标识就是IP地址，类似`123.123.123.123`。如果一台计算机同时接入到两个或更多的网络，比如路由器，它就会有两个或多个IP地址，所以，IP地址对应的实际上是计算机的网络接口，通常是网卡。

IP协议负责把数据从一台计算机通过网络发送到另一台计算机。

IP地址实际上是一个32位整数（称为IPv4），以字符串表示的IP地址如`192.168.0.1`实际上是把32位整数按8位分组后的数字表示，目的是便于阅读。

IPv6地址实际上是一个128位整数，它是目前使用的IPv4的升级版，以字符串表示类似于`2001:0db8:85a3:0042:1000:8a2e:0370:7334`。

TCP协议则是建立在IP协议之上的。TCP协议负责在两台计算机之间建立可靠连接，保证数据包按顺序到达。TCP协议会通过握手建立连接，然后，对每个IP包编号，确保对方按顺序收到，如果包丢掉了，就自动重发。

许多常用的更高级的协议都是建立在TCP协议基础上的，比如用于浏览器的HTTP协议、发送邮件的SMTP协议等。

一个TCP报文除了包含要传输的数据外，还包含源IP地址和目标IP地址，源端口和目标端口。

现在我们基本上了解了网络相关基础知识，现在我们可以进入网络编程了。

## 2.网络编程的开始

### 2.1 相关库的导入

我们在开始前需要导入一个库叫做request库

导入方法，在自己的console（控制台）里面输入命令：

```
pip install requests
```

具体方法见：https://jingyan.baidu.com/article/ce09321b94a1272bfe858f5a.html

request装好以后，使用方法如下：

get方法：

```python
# 引用requests库
import requests

# 调用get方法获取指定网址的返回结果
result = requests.get('https://www.ustc.edu.cn/')
result = requests.get('http://ip.taobao.com/service/getIpInfo.php', params={'ip': '117.89.35.58', 'format': 'json'})
```

为了获取指定网址的内容，采用的方式就是GET请求。
import requests 语句表示依赖了http库 。这个是固定用法。
result = requests.get('https: / /www.ustc.edu.cn/')
语句表示将目标URL当做字符串参数传递给requests.get()方法，用result变量引用请求的结果。

### 2.2 API

API全称Application Programming Interface， 应用程序接口，API- -般是指一-些预先定义的函数，目的是可以为开发人员快速访问某一程序，而无需了解和访问源码，或理解它内部工作机制的细节。

简单的讲，API可以快速调用某个程序。

如果想要了解更多的API，可以进入下面链接：

https://www.youkeda.com/post/detail/9c8a4060b7044cb6a1d396f38883d669

### 2.3 调用API

API本质上就是一个URL，只是返回内容有明显区别，没有大量多余的字符串，API返回的内容统称为数据。数据是什么，我们后面慢慢说。

### 2.4 get请求

详情见2.1部分

后面的数据是params类型。

### 2.5 有参数的get请求

有一个URL（统一资源定位器）：http://ip.taobao.com/service/getIpInfo.php?ip=117.89.35.58&format=json

拆解成地址与参数两部分：

#### 2.5.1 API地址

包含了从协议到路径的URL| 的前面一段:
http:/ /ip. taobao. com/ service/getIpInfo. php

#### 2.5.2 API参数

就是URL的参数部分:

| 参数名 | 参数值       |
| ------ | ------------ |
| ip     | 117.89.35.58 |
| format | json         |


API调用：

```python
import requests

result = requests.get('http://ip.taobao.com/service/getIpInfo.php', params={'ip': '117.89.35.58', 'format': 'json'})
```

params的作用：调用API时，传入一批API参数

API地址与API参数相互配套，不同API参数可能不一样

### 2.6 post表单数据

post方法不难，只需要把get方法变成post也就可以了

```python
result = requests.post(
    'https://accounts.douban.com/login', 
    #data也是一个字典
    data={
        'form_email': 'abc@example.com', 'form_password': '123456'
        }
    )
```

post方法第一个参数传进去的是网址，第二个是待交的数据。

后面的数据是data类型。

### 2.7 post json数据

和post一样，只不过是参数的data变成json

我们可以把data与params提前在外面先写好，再进行传入，这样代码会更加简洁。

```python
params = {'name': '张飞', 'secondName': '翼德'}
result=requests.post('https://www.fastmock.site/mock/3d95acf3f26358ef032d8a23bfdead99/api/posts', json=params)
```

### 2.8 JSON

JSON(JavaScript Object Notation, JS 对象简谱) 是一种轻量级的数据交换格式。它基于 ECMAScript (欧洲计算机协会制定的js规范)的一个子集，采用完全独立于编程语言的文本格式来存储和表示数据。简洁和清晰的层次结构使得 JSON 成为理想的数据交换语言。

Python中的json和字典的写法是一样的，json是一种通用数据格式，可以在Java、Python、JavaScript之间通信，而字典不可以，因此在Python语言中，json数据与dict字典以及对象之间的转化，是必不可少的操作。

关羽json，大家可以参照一下链接进行。

https://www.youkeda.com/post/detail/34aece36847a4355a1ef8948f47b1ad7

## 3.Response对象

### 3.1 Response - 网页

上面我们通过的get方法，返回值是Response对象，最主要的是两个数据：http状态码，以及具体响应的内容。

#### http状态码

状态码是使用一个数字直观反映本次请求的状况。

HTTP 响应状态代码指示特定 [HTTP](https://developer.mozilla.org/zh-cn/HTTP) 请求是否已成功完成。响应分为五类：信息响应(`100`–`199`)，成功响应(`200`–`299`)，重定向(`300`–`399`)，客户端错误(`400`–`499`)和服务器错误 (`500`–`599`)

200：表示请求成功了。

301:  资源（网页等）被永久转移到其它URL

404:  请求的资源（网页等）不存在

500:  内部服务器错误

获得状态码的语句

```
response.status_code
```

响应的具体内容，文本访问

```
response.text
```

### 3.2 Response文件

上面3.1我们访问了网页，实际上，response不仅仅可以请求网页、API，也可以访问图片与excel等。

但是访问图片和excel等内容的时候，不能用text了，要用：

```
response.content
```

type方法可以看数据类型，上面返回的是字节数content返回字节。

### 3.3 Response-json

我们在实际操作里面，会经常调用API，而很多API返回内容都是json格式的

其实，requests库里面Response对象对json有更友好的支持，使用如下：

```python
response.json()
```

可以把API返回的json格式的结果，换成字典的形式。

**有圆括号！！！！**

我们母大不仅要学会调用API，关键在于解析！！欲知后事如何，请看下集分解。

### 3.4 字典的解析

用json()进行调用，得到的是很多东西与数据。

json可能解析出很多东西，但是我们可以格式化：

可以这么看：http://www.ab173.com/json/jsonviewernew.php

在里面复制好解析的内容，点击格式化即可。

### 3.5 列表的解析

在json()后面加['名称/键值']来找到列表元素

我们后面有可能还加上相应索引来说是哪一个

```python
response.json()['result'][0]['channellist'][0]['name']
```

## 4.header（消息头）

判断一个信息是否来自一个真实的浏览器，需要从http消息头Header里面取得User-Agent信息以后才能判断

### 4.1 User-Agent

这个可以帮忙白嫖一些资源的

#### 4.1.1 HTTP header

HTTP的消息头是HTTP协议的一项重要内容，作用是在发起请求时除了参数以外，还可以附加更多的信息

关于header，想要详细指导可以看下面：https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Headers

但是header不在URL里面，被隐藏了，所以看不到。

#### 4.1.2 User-Agent

这个的目的是在指定URL发送请求时，告诉服务端当前用户浏览器类型、版本，甚至操作系统、CPU等非隐私的数据信息。

关于本部分详细，可以看看这里：https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Headers/User-Agent

所以关于爬虫我们可以在请求码里面加上User-Agent的消息，就可以成功访问了

写法：可以看文档

其实使用就在get(url,headers)里面，headers就是User-Agent码

```python
import requests

url = 'https://www.douban.com/'

headers = {'User-Agent': 'Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/535.1 (KHTML, like Gecko) Chrome/14.0.835.163 Safari/535.1'}

response = requests.get(url, headers=headers)

print('API调用结果：')
print(response.text)
```



### 4.2 Referer（防盗链处理）

在实际情况里面，有更严格的检查：图片防盗链

浏览器在请求页面里面的图片或其他时时，会自动在header里面加一个Referer信息表示请求的来源。由于使用了不同的网站请求，所以就拒绝访问这个图片。

所以图片或其他会访问不了。

**解决方法**

需要把referer使用的信息设置为图片原始使用网站

要想打印出最终响应的URL，可以采用requests请求后的response对象，可以采用

```
response.url
```

### 4.3 Host（客户端环境验证处理）

Host表示当前请求的域名，含义与作用很广泛。

想要好好学的可以看以下链接：https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Headers/Host

host也是字典的一个字段

host的值是一个域名并且不带协议头

## 5. 文件的问题：下载与读写

### 5.1 文件的下载

#### 5.1.1 文本文件的写入

写入字符串语句：

```python
# 打开一个文件
fo = open("foo.txt", "w")
# 写入内容
fo.write("www.runoob.com!\nVery good site!")
# 关闭文件
fo.close()
```

open()函数自定义，第二个参数表示性质

w表示文件重新写入

#### 5.1.2 写入二进制文件

```python
# 打开一个文件
fo = open("china-city-list.xlsx", "wb")
fo.write(response.content)
fo.close()
```

注意结尾第二个参数是wb，是重写二进制内容

### 5.2 图片下载

与excel一模一样，以二进制文件读入即可。

### 5.3 excel解析

需要提前安装库

安装库方法：

调用excel库：由于excel是多sheet模式，每一个sheet是一个表格，表格分为行和列

解析数据路径是sheet->行->列

解析方法如下：

```python
import xlrd

## 必须先打开 excel 文件
x1 = xlrd.open_workbook('xzq_201907.xlsx')
## 按位置读取第一个 sheet，
## sheet_by_index()方法获取到 sheet 对象，参数是位置坐标
s1 = x1.sheet_by_index(0)
## sheet 总行数
rows = s1.nrows
## sheet 总列数
cols = s1.ncols

## 取得第一个 sheet 的第一行的第一列的单元格值
## cell() 方法获取到表格单元格对象，参数是位置坐标
## .value 取得表示单元格的值
first = s1.cell(0, 0).value
## 取得第一个 sheet 的最后一行的最后一列的单元格
last = s1.cell(rows-1, cols-1).value
```

首先导入包 xlrd，在pycharm里面可以直接下载

打开方式：x1=xlrd.open_workbook()

获取行列：先用s1 = x1.sheet_by_index(0),得到excel对象

​                   获取行：rows = s1.nrow

​                   获取列：cols = s1.ncol

获取单元格表值：s1.cell(x-1,y-1).value;

## 6. cookie & session

### 6.1 cookie

由于登录信息会存放在cookie里面

怎么寻找呢？

在谷歌浏览器的开发者工具里面找到network选项，找mine，如果没有，就找与浏览器地址栏相同的url请求

然后找到cookie的值就可以了，放在cookie.txt文件里面

最后我们要转换成字典类型

字符串划分，以split('txt')为例进行划分

```python
def readCookie():
  # 打开保存的cookies内容文件
  f = open('cookie.txt', 'r')
  # 初始化cookies字典变量
  cookies = {}
  # 按照分号 ; 进行划分读取
  for line in f.read().split(';'):
    # 其设置为1就会把字符串拆分成2份
    name, value = line.strip().split('=', 1)
    # 为字典cookies添加内容
    cookies[name] = value

  return cookies

```

怎么一行行读取呢？

我们可以采用f.read()来读文件

split()则是按照一定的次序读取划分，后面带参数就是划分为n+1份strip()是去掉空格的。

### 6.2 session

由于cookie的弊端是cookie存放在客户端的浏览，是临时的，登录以后还想以登录状态与服务器通信，比较麻烦

session可以解决

session用法比cookie还简单

先调用 session - requests.Session()

再用session来发送请求

可以用get，也可以用post，参数都与requests.get() and requests.post()一模一样

### 6.3 复用session

很简单，再一次后面调用就可以了。

## 7. SMTP与邮件

### 7.1 SMTP协议

SMTP协议：是一个简单的基于文本的邮件传输协议，可以在这个协议上面指定一条邮件信息和多个邮件接收者。

发送邮件：

我们要提前在QQ邮箱里面开启SMTP服务。

可能在里面要提前写写验证，，会有授权码，保存它！！！

### 7.2 smtplib 和 Email

发送邮件以前，要用到smtplib和email两个库，但是这个是python提前就自带的，不需要提前安装

#### 1.引入库

```python
import smtplib
from email.mime.text import MIMEText
from email.header import Header
```

固定用法，不用背，复制粘贴即可

#### 2.配置邮件

```python
## 发送者的邮箱
sender = 'xxx@xxx.com'
## 邮件接收，可以有多个，可以是其它邮箱地址
receivers = ['xxx@xxx.com']  

## 邮件普通文本内容
mailContent = 'Hello World'
message = MIMEText(mailContent, 'plain', 'utf-8')
## 发送人名称
message['From'] = Header("优课达", 'utf-8')
## 收件人名称
message['To'] =  Header("测试邮件", 'utf-8')
## 邮件标题
message['Subject'] = Header('这是测试邮件', 'utf-8')
```

为了防止烫烫烫，我们采用utf-8编码格式

关于码表，大家可以打开这个链接：https://www.cnblogs.com/csguo/p/7402034.html

如果发送网页邮件，就把plain改成html

#### 3.邮箱配置

```python
## 邮箱的 SMTP 服务
mailHost = "smtp.xxxx.com"
## 用户名
mailUser = "xxx@xxx.com"
## 授权码
mailPass = ""
```

pass是授权码

#### 4.发送邮件

```python
try:
  ## 连接邮箱。465 为 SMTP 端口号
  smtpObj = smtplib.SMTP_SSL(mailHost, 465)
  ## 授权认证
  smtpObj.login(mailUser,mailPass)
  ## 发送邮件
  smtpObj.sendmail(sender, receivers, message.as_string())
  print("邮件发送成功")
except smtplib.SMTPException:
  print("Error: 无法发送邮件")
```

固定用法，发送失败要阅读相关帮助s文档。

表，大家可以打开这个链接：https://www.cnblogs.com/csguo/p/7402034.html

如果发送网页邮件，就把plain改成html

#### 3.邮箱配置

```python
## 邮箱的 SMTP 服务
mailHost = "smtp.xxxx.com"
## 用户名
mailUser = "xxx@xxx.com"
## 授权码
mailPass = ""
```

pass是授权码

#### 4.发送邮件

```python
try:
  ## 连接邮箱。465 为 SMTP 端口号
  smtpObj = smtplib.SMTP_SSL(mailHost, 465)
  ## 授权认证
  smtpObj.login(mailUser,mailPass)
  ## 发送邮件
  smtpObj.sendmail(sender, receivers, message.as_string())
  print("邮件发送成功")
except smtplib.SMTPException:
  print("Error: 无法发送邮件")
```

固定用法，发送失败要阅读相关帮助s文档。
