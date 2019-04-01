---
layout: _post
title: web学习记录
date: 2019-03-31 20:27:14
tags:
categories:
- Web前端技术
---

## Web 前端技术概览
  由于在项目中需要用到 Web 前端的相关知识，自己对这一块恰好又是有些了解但从未系统的去学习过，于是写一篇文章来记录，一般来说，一个前端工程师需要掌握的基础技能有：
  
  1. HTML 
  2. CSS
  3. Javascipt

这三个知识点是前端工程师需要掌握的最基础的技能，当我们不考虑开发速度，不考虑效果等等，理论上，只有掌握了这三个点，就完全可以开发出任意网页.

当然，已经 9102 年了，已经很少有人再利用原始的 html/css/js 来做 Web 前端开发了，通常会借助一些成功的框架帮助web 开发，例如： 

  1. jQuery
  2. Angular
  3. React 
  4. Vue

本文将从 html/css/javascript 讲起，但不会做过多的赘述，用最快的速度精简的路径直通主流框架，进击实战。

## HTML
### 什么是 HTML
HTML 是用来描述网页的一种语言。

 * HTML 指的是超文本标记语言 (Hyper Text Markup Language)
 * HTML 不是一种编程语言，而是一种标记语言 (markup language)
 * 标记语言是一套标记标签 (markup tag)
 * HTML 使用标记标签来描述网页

### 编译工具（IDE）
用来编写前端的 IDE 十分简便，入门阶段，我们用 Macdown，Sublime Text3，甚至说是记事本，都可以用来编写 HTML。

### Hello World
好了，废话不多说，直接上代码，学习任何一门语言或框架都是从 hello world 开始的，这是一个夹杂着程序员专有浪漫的美丽启程。

好了，我们进入一个目录，创建一个 HiWeb 目录并进入，再创建一个 Hello.html 文件, 利用 IDE 或文本编辑器打开。
编写如下代码：

```
<html>
<body>

<h1> 我的第一个标题 </h1>
<p> Hello World! </p>

</body>

</html>
```

例子解释：
* `<html> 与 </html> 之间文本描述网页`
* `<body> 与 </body> 之间的文本用来显示可见内容`
* `<h1> 与 </h1> 之间的文本一级标题`
* `<p> 与 </p> 之间文本显示段位`

### 基础标签

标题标签

```
<h1>一级标题</h1>
<h2>二级标题</h2>
<h3>三级标题</h3>
<h4>四级标题</h4>
```

注释

```
<!-- 注释的标签是这样玩的 -->
```

段落注释

```
<!-- 

<p>段落注释</p

-->

```


分割线标签

`<hr />`

折行标签

`<br />`

段落标签

```
<p>这是一个段落</p>
<p>这是另一个段落</p>
```

a标签

```
<a href="https://www.taobao.com"> 这是一个链接标签 </a>
```

图片标签

```
<img src="./resource/photo/onepiece.jpg" width="200" height="200">

```

注：图片标签的宽高，均是用属性的形式进行设置


### 元素
所有从开始标签到结束标签的代码，都是元素

`<p> 元素：标签从开始到结束的所有代码 ，元素可以嵌套</p>`

元素语法

* HTML 元素以开始标签起始
* HTML 元素以结束标签结束
* 元素的内容是开始标签到结束标签的所有内容
* 有些 HTML 元素具有空内容
* 空元素可以在开始标签中关闭
* 大多数 HTML 标签可拥有属性

元素使用注意事项

1. 不要忘记结束标签
2. 空标签的结束标签是在开始标签后加斜杠，例如换行标签 `<br />`
3. 标签小写规范，理论上标签不会敏感大小写，但 W3C 推送使用小写

### 属性

a 标签中的 href 就是属性

`<a href="http://www.w3school.com.cn">This is a link</a>`

属性的实例

`<h1 align="center"> 使用居中属性 </h1>`

属性使用注意事项

1. 属性和属性值同样是不敏感大小写的，但 W3C 推荐使用小写


参考手册

[完整的 HTML 参考手册](http://www.w3school.com.cn/tags/index.asp)

[HTML 全局属性手册](http://www.w3school.com.cn/tags/index.asp)


### 样式

HTML 提供了一种改变元素样式的属性，style，例如我们想要改变元素的背景颜色，我们可以这样

`<p style="background: yellow;" > 这是一个有待改变的段落</p>`

[CSS教程](http://www.w3school.com.cn/css/index.asp) 中包括了样式的全部用法

避免使用废弃的标签

```
<center>
<font> 和 <basefont>
<s> 和 <strike>
<u>
```

避免使用废弃的属性
```
align
bgcolor
color
```

实例1：改变背景色

`<p style="background: yellow;" > 这是一个有待改变的段落</p>`

实例2：改变字体及颜色

`<p style="font-size: 30;color: cyan"> 这是一个要改变字体颜色大小的段落</p>`

实例3：改变字体对齐

`<p style="text-align: center;"> 这是一个要被对齐段落</p>`

### 格式化

格式化不想做过多的赘述，可以参考[格式化](http://www.w3school.com.cn/html/html_formatting.asp)

### 引用

`<p>我们通过 q 标签可以：<q>为一段问题加入引号 <br /> 换行好像也行</q></p>`

### 代码 

利用 code 标签，可以满足代码格式的示例展示

```
<code>
	var person = {
	   name = "索隆",
	   profession = “剑客”,
	   aims = “世界第一的大剑豪”
	}
</code>
```

但是，展示出来会发现，这并不是我们要的现象，并不会展示出代码的格式，于是我们要利用 pre 标签，定义预格式文本

```
<code>
<pre>
var person = {
	name = "索隆",
	profession = “剑客”,
	aims = “世界第一的大剑豪”
}
</pre>
</code>

```

利用 samp 元素定义计算机输出

```
<samp>
demo.example.com login: Apr 12 09:10:17
Linux 2.6.10-grsec+gg3+e+fhs6b+nfs+gr0501+++p3+c4a+gr2b-reslog-v6.189
</samp>
```

当然，如果想实现换行的格式，利用 pre 就可以了。

HTML 还提供了 var 标签来定义变量，可以用来展示数学公式

```
<p>HTML 还可以用来展示数学公式，很有意思!!</p>
<p>例如，爱因斯坦公示</p>
<p><var>E</var> = <var>m</var> <var>c</var> <sup>2</sup></s></p>

```

### 列表

无序列表

```
<ul>
	<li>Coffee</li>
	<li>Milk</li>
	<li>Tea</li>
</ul>
```
有序列表

```
<ol>
	<li>Coffee</li>
	<li>Milk</li>
	<li>Tea</li>
</ol>
```

定义列表

```
<dl>
	<dt>Coffee</dt>
	<dd>Black hot drink</dd>
	<dt>Milk</dt>
	<dd>White cold drink</dd>
</dl>
```

### 块（div 和 span）
前面学写了这么多，感觉终于算是步入正轨了。div 和 span 是 html 非常重要的一环，配合 class 和 id 的使用，对于编写动态页面以及 HTML 结构化都有着重要的作用。

**div**

我们可以把 div 就理解成一个块，HTML 会为 div 内置一个换行符号，在一个我们为一个块内定义的属性，在整个块内所有的元素都会生成，配合 class 和 id，在实际的 web 开发中，非常常用。

```
<div style="color: red" class="news" id="">
	<h3>这是一个标题</h3>
	<p>这是一个段落</p>

</div>
```

**span**

span 通常用来定义和区分行内元素，和 div 一样，在实际 web 开发中，配合 class 和 id 的使用非常常用

```
<p class="label"> 段落段落 <span class="focus">我们不一样～不一样～</span></p>
```

class 和 id 通常会用于获取 CSS 的样式，JS 的调用标识，具体使用，在 CSS 和 JS 全部讲完后，具体展示

div 和 span 都支持 [全局属性](http://www.w3school.com.cn/tags/html_ref_standardattributes.asp) 和 [事件属性](http://www.w3school.com.cn/tags/html_ref_eventattributes.asp)

**class与CSS的示例**
利用莎士比亚的《短诗十八行》，展示下如何利用 class 获取组合样式

```
<!DOCTYPE html>
<html>
<head>
	<title>I have a dream</title>

	<style>
	.label {
    background-color: gray;
    color:white;
    margin:20px;
    padding:20px;
	} 

	.subTitle {
		align: right;
		color: yellow;
		font-size: 30;
	}
	</style>
</head>
<body>


<div class="label">
	<h2> Sonnet 18 </h2>	
	<p>  BY <span class="subTitle">WILLIAM SHAKESPEARE</span> </p>
	<pre>
	<p>
		Shall I compare thee to a summer’s day?
		Thou art more lovely and more temperate:
		Rough winds do shake the darling buds of May,
		And summer’s lease hath all too short a date;
		Sometime too hot the eye of heaven shines,
		And often is his gold complexion dimm'd;
		And every fair from fair sometime declines,
		By chance or nature’s changing course untrimm'd;
		But thy eternal summer shall not fade,
		Nor lose possession of that fair thou ow’st;
		Nor shall death brag thou wander’st in his shade,
		When in eternal lines to time thou grow’st:
   		So long as men can breathe or eyes can see,
   		So long lives this, and this gives life to thee.
	</p>
	</pre>
	
</div>

</body>
</html>
```

### 脚本 （Script）

JavaScript 脚本将会使网页更加具有动态性和交互性，如下代码将会在浏览器输入 Hello World

```
document.write("Hello World!")
</script>

```

### 头部（Header）

header 元素是所有头部元素的容器。header 内的元素包含脚本，指定样式表，提供元信息等
以下标签都可以添加到 head 部分：`<title>、<base>、<link>、<meta>、<script> 以及 <style>。`

通过一个简化的 HTML 文档，体现 header

```
<!DOCTYPE html>
<html>
<head>
	<title>我是一个标题</title>
	<base href="https://www.baidu.com" />
	<link rel="stylesheet" type="text/css" href="/resource/css/xxxx.css">
	<style type="text/css">
		body {
			background-color: yellow
		}
	</style>
	<meta charset="utf-8" name="desciption" content="这是一个数据页面">
	<script type="text/javascript">/xxxx/xxxx.js</script>

</head>
<body>


</body>
</html>
```

以上的知识点，足够我们作为一个前端开发工程师的必备条件，但是仍有一些基础的知识点需要掌握

* [HTML字符实体](http://www.w3school.com.cn/html/html_entities.asp)
* [URL](http://www.w3school.com.cn/html/html_url.asp)
* [URL 编码](http://www.w3school.com.cn/html/html_urlencode.asp)
* [HTML 颜色](http://www.w3school.com.cn/html/html_colors.asp)
* [HTML 颜色列表](http://www.w3school.com.cn/html/html_colornames.asp)
* [HTML 文档类型](http://www.w3school.com.cn/html/html_doctype.asp)
* [HTML 速查手册](http://www.w3school.com.cn/html/html_quick.asp)

## JavaScript 
之所以在学习完 html 后，直接跳入 JavaScript，是个人认为想快速进行 Web 开发，JavaScript 会比 CSS 更加需要优先掌握，而且在实际的开发过程，又会有很多的样式封装，例如 bootstrap 等，所以先行学习 JavaScript。

但是 JavaScript 章节也不会停留太久，目前也很少有人用纯 JavaScript 进行 Web 开发，通常都会使用 jQuery 或 vue 框架，所以这个章节，对于有开发经验的人，可以快速的过一遍 JavaScript 的基础语法，然后直接进入 jQuery 的学习。

对于没有开发经验同学，还是需要详细的学习下 [JavaScript](http://www.w3school.com.cn/js/index.asp)

### 学习规划
#### 重点，因为这些是和其他语言差距较大的部分
1. 语法
2. 变量
3. 数据类型
4. 对象
5. 函数

#### 看一下就好，因为都差不多
1. 注释
2. 运算符/比较符号
3. if...else/switch/
4. for/while
5. break/continue

#### 重中之重
1. 事件响应
2. 捕捉 html 元素
3. 逐层捕捉 html 
3. 改变/插入 html 元素
4. 网络请求
5. jQuery 库


### 语法
JavaScript 需要些分号
JavaScript 对大小写敏感。
用花括号区分代码块
空格用来提高可读性

### 变量
用 var 来标记变量

### 数据类型

数字

```
var pi=3.14;
```

字符串

```
var name="Bill Gates";
var answer='Yes I am!';
```

Bool

```
var x = true;
var y = false;

```

数组

```
var cars = new Array();
cars[0]="Audi";
cars[1]="BMW";
cars[2]="Volvo";

或

var cars=new Array("Audi","BMW","Volvo");

或
var cars=["Audi","BMW","Volvo"];

或

var cars=[];
cars[0]="Audi";
cars[1]="BMW";
cars[2]="Volvo";

```

### 对象

```
var person = {
	name : '魏晓堃'
	age : 26
	id : 88888888888
};

var name = person.name;
var age = age["age"]
```

### 函数

无参无返回

```
function myFun() {
	...
	
	code 
	...
}
```

有参无返回

```
funcation myFun(name, id) {
	...
	code
	...
}
```

有参有返回

```
funcation myFun(name, id) {

	var value = ....
	
	...
	code
	...
	
	return value;
}
```

### 运算符
算数运算符

```
+
-
*
/
%
++ 
--
```

赋值运算符

```
=
+=
-=
*=
/=
%=
```

字符串可以通过 + 号拼接

```
var a = 5 + 5;
var a = '5' + '5';
var a = 5 + '5';
```
比较运算符

```
==
=== （全等，数据类型和值都必须完全相同）
!=
>
<
>=
<=
```

逻辑运算符

```
&&
||
!
```

条件运算符（三位运算符）
```
var value = (name == '瞬间移动帅不帅？') ？ "帅" : "不帅";
```

### if

```
if () {

} else if () {

} else {

}

```

### Switch
```
switch(n)
{
case 1:
  执行代码块 1
  break;
case 2:
  执行代码块 2
  break;
default:
  n 与 case 1 和 case 2 不同时执行的代码
}
```

### for 

```
for (var i = 0; i < 10; i++) {
	...
}
```


### while

```
while (条件)
  {
  需要执行的代码
  }
```

### break/continue

break：跳出全部循环
continue：跳出单个循环
return：跳出当前方法


到此，已经已经学会了 JavaScript 与法，我们可以不利用 document 的方法捕捉 html 元素，我们要用 jQuery 的方式 去完成上文提到的 **重中之重** 的规划

## jQuery

jQuery是一个JavaScript函数库。
jQuery是一个轻量级的"写的少，做的多"的JavaScript库。

### 重中之重
1. 事件响应
2. 捕捉 html 元素
3. 逐层捕捉 html 
3. 改变/插入 html 元素
4. 网络请求（Ajax）

### 安装
[点这里](http://jquery.com/download/) 下载 jquery，在本地进行进入，也可以直接下载进行引入

```
<!DOCTYPE html>
<html>
<head>
	<title>jQuery Demo</title>
	<script src="https://cdn.staticfile.org/jquery/1.10.2/jquery.min.js"></script>
	<!-- <script src="jquery-1.10.2.min.js"></script> -->
</head>
<body>

</body>
</html>
```






























 
