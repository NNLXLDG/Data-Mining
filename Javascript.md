# JavaScript

## 1.为什么学习 JavaScript?

JavaScript 是 web 开发人员必须学习的 3 门语言中的一门：
+ HTML 定义了网页的内容
+ CSS 描述了网页的布局
+ JavaScript 控制了网页的行为

## 2.JavaScript 是脚本语言

+ JavaScript 是一种轻量级的编程语言。
+ JavaScript 是可插入 HTML 页面的编程代码。
+ JavaScript 插入 HTML 页面后，可由所有的现代浏览器执行。

## 3.JavaScript 用法
+ HTML 中的 Javascript 脚本代码必须位于 `<script>`与 `</script>`标签之间。
+ Javascript 脚本代码可被放置在 HTML 页面的 `<body>` 和 `<head>` 部分中。
+ 也可以把脚本代码放在外部 .js 文件中。外部 .js 文件必须位于 `<script>` 标签内，并且 `src` 属性指定外部文件的位置。

## 4.JavaScript 输出
JavaScript 没有任何打印或者输出的函数。可以通过不同的方式来输出数据：
+ 使用 window.alert() 弹出警告框。
+ 使用 document.write() 方法将内容写到 HTML 文档中。
+ 使用 innerHTML 写入到 HTML 元素。
+ 使用 console.log() 写入到浏览器的控制台。

### 4.1 window.alert()
弹出警告框来显示数据
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
<script>
window.alert(5 + 6);
</script>
	
</body>
</html>
```

### 4.2 操作HTML元素
如需从 JavaScript 访问某个 HTML 元素，您可以使用 document.getElementById(id) 方法。
请使用 `id` 属性来标识 HTML 元素，并 innerHTML 来获取或插入元素内容：

```html
<!DOCTYPE html>
<html>
<head> 
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
</head>
<body>
	
<h1>我的第一个 Web 页面</h1>
<p id="demo">我的第一个段落。</p>
<script>
document.getElementById("demo").innerHTML="段落已修改。";
</script>
	
</body>
</html>
```
以上 JavaScript 语句（在` <script> `标签中）可以在 web 浏览器中执行：
document.getElementById("demo") 是使用 id 属性来查找 HTML 元素的 JavaScript 代码 。
innerHTML = "段落已修改。" 是用于修改元素的 HTML 内容(innerHTML)的 JavaScript 代码。


### 4.3 document.write()
使用 document.write() 可以向文档写入内容。
```html
<!DOCTYPE html>
<html>
<head> 
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
</head>
<body>
	
<h1>我的第一个 Web 页面</h1>
<p>我的第一个段落。</p>
<script>
document.write(Date());
</script>
	
</body>
</html>
```
如果在文档已完成加载后执行 document.write，整个 HTML 页面将被覆盖。例如：
```html
<!DOCTYPE html>
<html>
<body>

<h1>我的第一个 Web 页面</h1>

<p>我的第一个段落。</p>

<button onclick="myFunction()">点我</button>

<script>
function myFunction() {
    document.write(Date());
}
</script>

</body>
</html>
```

### 4.4 写到控制台
可以使用 console.log() 方法在浏览器中显示 JavaScript 值。浏览器中使用 F12 来启用调试模式， 在调试窗口中点击 "Console" 菜单。
```html
<!DOCTYPE html>
<html>
<body>
<h1>我的第一个 Web 页面</h1>
<script>
a = 5;
b = 6;
c = a + b;
console.log(c);
</script>

</body>
</html>
```

## 5.JavaScript 语法
JavaScript 是一个脚本语言。它是一个轻量级，但功能强大的编程语言。


### 5.1 JavaScript 字面量
在编程语言中，一般固定值称为字面量，如 3.14。

+ 数字（Number）字面量 可以是整数或者是小数，或者是科学计数(e)。
+ 字符串（String）字面量 可以使用单引号或双引号。
+ 表达式字面量用于计算。
+ 数组（Array）字面量 定义一个数组：
[40, 100, 1, 5, 25, 10]
+ 对象（Object）字面量 定义一个对象：
{firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"}
+ 函数（Function）字面量 定义一个函数：
function myFunction(a, b) { return a * b;}

### 5.2 JavaScript 变量

JavaScript 使用关键字 var 来定义变量， 使用等号来为变量赋值：
```javascript
var x, lengthx = 5
length = 6
```
变量可以通过变量名访问。在指令式语言中，变量通常是可变的。字面量是一个恒定的值。变量是一个**名称**。字面量是一个**值**。


### 5.3 JavaScript 操作符
avaScript使用 算术运算符 来计算值:
```python
(5 + 6) * 10
```

JavaScript使用赋值运算符给变量赋值：
```javascript
x = 5
y = 6
z = (x + y) * 10
```


### 5.4 JavaScript 语句
语句是用分号分隔。


### 5.5 JavaScript 关键字
JavaScript 关键字用于标识要执行的操作。和其他任何编程语言一样，JavaScript 保留了一些关键字为自己所用。



### 5.6 JavaScript 注释
不是所有的 JavaScript 语句都是"命令"。双斜杠 // 后的内容将会被浏览器忽略。


### 5.7 JavaScript 函数
JavaScript 语句可以写在函数内，函数可以重复引用：

引用一个函数 = 调用函数(执行函数内的语句)。
```python
function myFunction(a, b) {
   	return a * b;         
                     
// 返回 a 乘以 b 的结果
}
```


### 5.8 JavaScript 字母大小写
JavaScript 对大小写是敏感的。当编写 JavaScript 语句时，请留意是否关闭大小写切换键。

函数 getElementById 与 getElementbyID 是不同的。同样，变量 myVariable 与 MyVariable 也是不同的。


## 6 JavaScript 语句
JavaScript 语句是发给浏览器的命令。这些命令的作用是告诉浏览器要做的事情。下面的 JavaScript 语句向 id="demo" 的 HTML 元素输出文本 "你好 Dolly" ：

```javascript
document.getElementById("demo").innerHTML = "你好 Dolly";
```

### 6.1 分号 

分号用于分隔 JavaScript 语句。通常我们在每条可执行的语句结尾添加分号。使用分号的另一用处是在一行中编写多条语句。

```javascript
a = 5;
b = 6;
c = a + b;
```
可以写成:
```javascript
a = 5;b = 6;c = a + b;
```

您也可能看到不带有分号的案例。在 JavaScript 中，用分号来结束语句是可选的。


### 6.2 JavaScript 代码
JavaScript 代码是 JavaScript 语句的序列。浏览器按照编写顺序依次执行每条语句。

本例向网页输出一个标题和两个段落：
```javascript
document.getElementById("demo").innerHTML="你好 Dolly";
document.getElementById("myDIV").innerHTML="你最近怎么样?";
```

### 6.3 JavaScript 代码块
JavaScript 可以分批地组合起来。代码块以左花括号开始，以右花括号结束。代码块的作用是一并地执行语句序列。

本例向网页输出一个标题和两个段落：
```javascript
function myFunction()
{
    document.getElementById("demo").innerHTML="你好Dolly";
    document.getElementById("myDIV").innerHTML="你最近怎么样?";
}
```


### 6.4 JavaScript 语句标识符
JavaScript 语句通常以一个 语句标识符 为开始，并执行该语句。语句标识符是保留关键字不能作为变量名使用。

下表列出了 JavaScript 语句标识符 (关键字) ：
| 语句    | 描述    |
|---|---|
| break    | 用于跳出循环。    |
| catch    | 语句块，在 try 语句块执行出错时执行 catch 语句块。    |
| continue    | 跳过循环中的一个迭代。    |
| do ... while   | 执行一个语句块，在条件语句为 true 时继续执行该语句块。    |
| for    | 在条件语句为 true 时，可以将代码块执行指定的次数。    |
| for ... in    | 用于遍历数组或者对象的属性（对数组或者对象的属性进行循环操作）。    |
| function    | 定义一个函数    |
| if ... else    | 用于基于不同的条件来执行不同的动作。    |
| return    | 返回结果，并退出函数    |
| switch    | 用于基于不同的条件来执行不同的动作。    |
| throw    | 抛出（生成）错误。    |
| try    | 实现错误处理，与 catch 一同使用。    |
| var    | 声明一个变量。    |
| while    | 当条件语句为 true 时，执行语句块。    |

JavaScript 是脚本语言，浏览器会在读取代码时，逐行地执行脚本代码。而对于传统编程来说，会在执行前对所有代码进行编译。






















































