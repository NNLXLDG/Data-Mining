# Python网络爬虫

## 1 爬虫基础
### 1.1 爬虫的分类
网络爬虫可分为：**通用网络爬虫、聚焦网络爬虫、增量式网络爬虫、深网网络爬虫等**。实际使用中，通常是这几类的组合体。
1. 通用网络爬虫：爬取海量数据，主要由初始URL集合，URL队列等模块构成。
2. 聚焦网络爬虫：爬取特定的信息。
3. 深层网络爬虫：爬取深度网页中的信息。

### 1.2 爬虫的流程
网络爬虫的基本工作流程为：
1. 获取初始URL集合。
2. 通过爬虫代码向网页服务器发送请求，获取响应数据。
3. 解析响应数据，确定数据所在的位置。
4. 提取数据。
5. 实现数据的清洗和筛选。
6. 将清洗后的数据保存至本地或数据库当中。

### 1.3 HTTP基本原理
Web服务器的工作原理可以概括为以下4个步骤：
1. 客户端通过TCP/IP协议建立到服务器的TCP连接。
2. 客户端向服务器发送HTTP请求。请求服务器里的资源文档，常用的请求方式有：GET、POST、PUT、DELETE、HEAD、OPTIONS、TRACE、CONNECT。
3. 服务器向客户端返回HTTP响应，响应包括状态行、响应头、响应体。由客户端解释HTML文档，并显示在浏览器上。


### 1.4 网页的基本结构
Web网页主要由**HTML、CSS、JavaScript**三部分组成。
1. HTML：超文本标记语言，是网页的骨架，负责网页内容的组织和结构。主要用于实现Web页面中的各种组件。
2. CSS：层叠样式表，是网页的样式，负责网页的显示效果。主要用于实现Web页面中组件位置，文字颜色等其他样式。
3. JavaScript：脚本语言，是网页的行为，负责网页的交互效果。主要用于实现Web页面中组件的动态效果。


### 1.5 标记语言和编程语言
| 特性   | 标记语言                | 编程语言                |
|--------|------------------------|-------------------------|
| 目的   | 描述内容和结构         | 描述计算过程和逻辑      |
| 功能   | 声明“这是什么”（静态） | 命令计算机“怎么做”（动态） |
| 过程   | 定义状态               | 执行指令、算法、控制流程 |
| 结果   | 生成一个文档（如网页、PDF） | 创建一个可以运行的程序、软件或功能 |
| 例子   | HTML, XML, Markdown    | Python, Java, C++       |

### 1.6 CSS如何改变样式
CSS提供了三个信息，分别是**选择器、属性、值**。通过选择器选中HTML元素，然后为该元素设置属性和值，从而改变其样式。

**（1）属性选择器**

通过属性来选择标签，这些属性既可以是标准属性（HTML中默认该有的属性，如input标签的type属性），也可以是自定义属性。

在HTML中，通过各种各样的属性，可以给元素增加很多附加信息。例如，在一个HTML页面中，插入了多个`<p>`标签， 并为每一个`<p>`标签设定了如字体大小、颜色等属性。

```html
<p color=“red”>这是一个段落。</p>
<p font=“fontsize”>这是另一个段落。</p>
```        

在HTML中为标签添加属性之后，可以在CSS中使用标签选择器选择对应的标签来改变样式。在使用属性选择器时，需要申明属性与属性值。申明方式如下：

```css
[属性名=属性值] {
    属性:值;
}
```
例如：意思是，选择所有`<p>`标签中，属性color的值为red的标签，并将其字体颜色设置为红色，字体大小设置为20px。

```css    
[p color=“red”] {
    color: red;
    font-size: 20px;
}
```

**（2）ID和Class选择器**

ID和Class选择器是CSS中最常用的选择器。ID选择器用于选择具有特定ID属性的HTML元素，而Class选择器用于选择具有特定Class属性的HTML元素。

ID选择器使用`#`符号，Class选择器使用`.`符号。例如：

```html
<p id="unique">这是一个唯一的段落。</p>
<p class="common">这是一个常见的段落。</p>
<p class="common">这是另一个常见的段落。</p>
``` 
在一个网页中，ID属性的值必须是唯一的，而Class属性的值可以重复使用。   

```css
#unique {
    color: blue;
    font-size: 18px;
}
.common {
    color: green;
    font-size: 16px;
}
```

### 1.7 JavaScript如何实现交互
JavaScript通过操作DOM（文档对象模型）来实现网页的交互效果。

**什么是DOM？**

HTML 是静态的源代码。DOM 是浏览器根据 HTML 创建的、动态的、可编程的对象模型。DOM 独立于语言，虽然最常与 JavaScript 搭配使用，但任何支持 DOM 接口的编程语言（如 Python, Java）都可以操作它。所有现代网页的动态效果、数据交互、用户体验都建立在 JavaScript 操作 DOM 的基础之上。


通常情况下，在Web页面中使用JavaScript有两种方法，一种是直接在页面中嵌入JavaScript代码，另一种是链接外部JavaScript文件。下面分别对两种方法进行介绍。

**（1）直接在页面中嵌入JavaScript代码**

在HTML文档中使用`<script>...</script>`标签将JavaScript代码嵌入HTML文档中。可以有多个`<script>...</script>`标签，它们会按照它们出现的顺序执行。`<script>`常用属性如下：

|属性值       | 描述  |
| --------- | --------- |
|language/type（主流） | 设置所使用的脚本语言及版本
| src | 引入的外部脚本文件路径
|defer | 延迟加载脚本|

在html文档中嵌入JavaScript代码的例子如下：
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
</head>
<body>
	
<h1>我的第一个页面</h1>
<p>我的第一个段落。</p>
<script language="javascript" >
window.alert(5 + 6);
</script>
	
</body>
</html>
```

**（2）链接外部JavaScript脚本**
另一种方法是引入外部脚本文件，即使用`<script>`标签引入外部脚本文件。

在Web页面中链接外部脚本文件的语法如下：
```html
<script src="外部脚本文件路径"></script>
```
在外部JavaScript文件中，不需要将脚本代码用`<script>`和`</script>`标签包裹起来。


## 2 搭建网络爬虫开发环境

## 3 网络请求urllib模块

### 3.1 了解urllib模块
在Python3中，urllib和urllib2模块的功能被组合，并合并到一个名为urllib的模块中。

urllib模块中包含多个功能的子模块，具体内容如下：
+ urllib.request：用于打开和读取URL，实现基本的HTTP请求功能
+ urllib.error：用于处理urllib.request模块中抛出的异常
+ urllib.parse：用于解析URL
+ urllib.robotparser：用于解析robots.txt文件，判断网站是否允许爬虫

### 3.2 发送网络请求
urllib.request模块中包含一个urlopen()方法，实现最基本的HTTP请求，返回一个HTTPResponse对象。
```python
response = urllib.request.urlopen('http://www.baidu.com',data=None,[timeout,]*,cafile=None,capath=None,cadefault=True,context=None)
```
其中参数含义如下：
1. url：请求的URL
2. data：该参数默认为None，如果是None，则表示请求方式为GET，否则为POST。在发送POST请求时，data需要以字典形式的数据传递给该参数。并需要将字典类型的参数值转换成字节类型的数据才可以实现POST请求。
3. timeout：请求超时时间，默认为None，表示没有超时时间限制。以秒为单位。
4. cafile、capath：指定一组HTTPS请求受信任的CA证书，cafile指定包含CA证书的单个文件，capath指定包含CA证书的目录。
5. cadefault：指定默认的CA证书，默认为None。
6. context：指定SSL选项的实例。

### 3.3 发送GET请求
在使用urlopen()方法实现一个网络请求时，所返回的是一个“http.client.HTTPResponse”对象，该对象包含HTTP响应的元数据，比如响应头、响应状态码、响应内容等等。

示例如下：
```python
import urllib.request
url = 'https://www.baidu.com'
response = urllib.request.urlopen(url)
print(response.status)
print(response.getheaders())
print(response.read().decode('utf-8'))
```


### 3.4 发送POST请求
urlopen()方法在默认的情况下是发送GET请求，如果需要发送POST请求，可以为其设置data参数，该参数是bytes类型，所以需要使用bytes()方法转换成bytes类型。
```python
import urllib.request
import urllib.parse
url = 'https://www.baidu.com'
data = bytes(urllib.parse.urlencode({'word':'hello'}), encoding='utf8')
response = urllib.request.urlopen(url, data=data)
print(response.read().decode('utf-8'))
```

### 3.5 请求超时
urlopen()方法会等待响应，如果响应时间过长，可能会导致程序假死。为了避免这种情况，可以使用timeout参数设置超时时间。
```python
import urllib.request
response = urllib.request.urlopen(url, timeout=0.1)
print(response.read().decode('utf-8'))
```

如果遇到了超时异常，爬虫程序将在此处停止。所以在实际开发中开发者需要对超时异常进行捕获，并重新发起请求。使用 try...except 语句处理超时异常。

示例代码如下：
```python
import urllib.request
import urllib.error
import socket
url='http://www.baidu.com'
try:
    response = urllib.request.urlopen(url, timeout=0.1)
    print(response.read().decode('utf-8'))
except urllib.error.URLError as e:
    if isinstance(e.reason, socket.timeout):
        print('TIME OUT')
```

### 3.6 设置请求头
urlopen()方法能够发送一个最基本的网络请求，但是，还需要再在请求中添加如Headers、Cookies、代理IP等内容，这样才能更好地模拟一个浏览器所发送的网络请求。Request类则可以构建一个多种功能的请求对象，其语法格式如下：
```python
urllib.request.Request(url, data=None, headers={}, origin_req_host=None, unverifiable=False, method=None)
```
其中各个参数含义如下：
1. url：请求的URL
2. data：该参数默认为None，如果是None，则表示请求方式为GET，否则为POST。在发送POST请求时，data需要以字典形式的数据传递给该参数。并需要将字典类型的参数值转换成字节类型的数据才可以实现POST请求。
3. headers：设置请求头部信息，该参数为字典类型。添加请求头信息最常见的用法就是修改User-Agent字段，模拟浏览器发送请求。例如：
```python
headers = {
    'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.36'
}
```    
4. origin_req_host：表示请求的主机名或者IP。
5. unverifiable：表示请求是否可以被验证，默认为False。
6. method：表示请求的方法，默认为GET请求，可以设置为GET、POST等。


设置请求头参数是为了模拟浏览器向网页后台发送网络请求，可以避免服务器的反爬措施。使用urlopen()方法发送网络请求时，其本身没有设置请求头参数，所以向测试地址发送请求时，返回的信息中headers将显示默认值。

所以需要在浏览器中找到一个有效的请求头信息。再通过Request类的headers参数设置请求头信息。示例代码如下：
```python
import urllib.request
import urllib.parse
url = 'http://httpbin.org/get'

headers = {
    'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.36'
}

data = bytes(urllib.parse.urlencode({'word': 'hello'}), encoding='utf-8')

request = urllib.request.Request(url=url, data=data,headers=headers,method='POST')

response = urllib.request.urlopen(request)
print(response.read().decode('utf-8'))
```

### 3.7 获取与设置Cookie




## 4.网络请求urllib3模块

## 5.网络请求requests模块


