# web-learn

date:2020.5.20:

DOCTYPE声明了文档类型

<html>与</html>描述了文档类型

<body></body>可视化网页内容

'<h1></h1>'标题使用

’<p></p>‘段落显示





HTML：Hyper  Text  MarKup Language(超文本标记语言)

​			不是编程语言，是标记语言；

​			标记语言是一套标记标签

​			标记标签来描述网页

​			html文档也叫做web页面

*<标签>内容</标签>*



html元素：包含开始和结束标签

’<p>this is a pargraph</p>‘



标题<h1></h1>表示

段落<p></p>表示

链接<a href="www.baidu.com">……</a>

<img src="C:/Users/LENOVO/Pictures" width="111" height="232">图片

<br />换行



html元素以开始标签开始以结束标签结束

元素内容在开始标签与结束标签中间

属性：

​	class：为html元素定个意思一个或者多个类名（类名来源于css文件）

​	id：定义元素唯一id

​	style：规定语速行内样式

​	title：描述元素的额外信息

​	

属性为元素提供附加信息



<hr color="red" />标签：创建水平线hr元素用来分割内容

<html> 定义html文档

<body>定义文档主体

<h1>标题
    <h6> 定义html标题

<hr />定义水平线

<!--……-->



html中的style属性作用：提供一种改变所有html‘元素的样式的通用方法。

例：

```
<body style="background-color: yellow;font-size: 40px;">

</body>

```

text-align规定元素中的文本的水平对齐方式



文本格式标签：

<b>粗体

<big>大号字体

<em>着重字体

<i>斜体

<small>小号字体

<strong>加重

<sub>定义下标

<sup>上标

<ins>插入

<del>删除字



用于短的引用：

用<q></q>标签来表示

长的引用用<blockquote>来表示</blockquote>

缩略词的引用：

<abbr title="world health origanization">who</abbr>

<address>
    editor<br>
    visit us at:<br>
    111111.com<br>
    包括一些文档或文章的联系方式
</address>



<cite>

html site 元素定义著作的标题

</cite>



<bdo dir="rtl">
    "<bdo>"定义双向流覆盖

</bdo>





计算机代码元素：

通常，HTML 使用*可变*的字母尺寸，以及可变的字母间距。

在显示*计算机代码*示例时，并不需要如此。

<kdb>, <sample>, 以及 <code> 元素全都支持固定的字母尺寸和间距。



<var>var定义数学变量</var>



 <!--注释>





css样式：

外部样式：

<head>
    <link rel="stylesheet" type="text/css" href="mystyle.css"
</head>

内部样式表：

<head>
    <style type="text/css">
        body {background-color:red}
        p {margin-left:20px}
    </style>
</head>



内联样式：

<p style=" color: red;margin-left :20px">
    内联样式示例
</p>









html链接：

<a href="www.baidu.com" taget= "_blank">

百度的链接

</a>



链接的一些属性：

name属性等于id

用于定义锚的名称：

<a name="warnings">

提示

</a>

在其他地方就可以通过warning来访问到了



同一个网页中：

<a href="#warnings">

转到同网页的warning

</a>

不同网页中：

<a href="test.html#warings"

不同网页要加上网页地址

</a>



图像：



<img>标签 是空标签所以没有闭合标签 只有属性

src属性：值是指向图像的url地址

alt属性： 替换文本：用于图片没有加载的时候显示



<map name="image" id="image"></map>

<map>标签 ：定义图像地图 可以点击一张图片的不同区域 链接到不同地址



<table>
    table标签用来显示表格
    <tr>tr标签显示行
    <td>td标签用来显示列</td>
    </tr>
</table>

。。。。。。





列表：

有序无序和定义列表：

无序列表用ul标签标示

<ul>
    <li>
    每个项用li表示，有个小点</li>
    <li>
    可使用图片，段落，换行符，图片还有链接</li>
</ul>



有序列表用ol表示

<ol>
    <li>
        内容同无序
    </li>
    <li>
    coffee
    </li>
    <li>
    ...</li>
</ol>



自定义列表：

用dl标签开始

自定义列表项以dt开始

列表项定义以dd开始

<dl>
    <dt>coffee</dt>
    <dd>Black hot drink</dd>
    <dt>milk</dt>
    <dd>white cold drink</dd>
</dl>



块：

html元素一般包括块级元素（换行）与内联函数（不换行）

div元素是块级元素，用于组合其他元素的容器

相对应的span内联元素用以文本容器，组合行内元素





布局：

div元素布局通过css给样式

html5语义元素：

header： 页眉

nav：导航链接的容器

section：文章中的节

article：定义独立的自包含的文章

aside：文章之外的内容

footer：页脚

details：定义额外的细节

summary：定义details的标题





框架：frameset

同一个页面显示多个不同的网页

用frameset标签标示：

rows/columns的值定义每行或者裂占的比例



内联框架：

用于在网页内显示网页：

<iframe src="https://www.baidu.com" >
</iframe>





网页背景颜色：

<body bgcolor="#000000">

<body bgcolor="rgb(0,0,0)">

<body bgcolor="black">



背景：

<body background="xxx.gif">

<body background="url">



html的文件路径：

绝对路径：完整的url

相对路径：相对于当前页面的文件

尽量使用相对路径





html头部元素

用head表示：其中可以包含的脚本，样式表，提供元信息等等

可包含<title><base><link><script><style>



base标签规定了页面所有的链接规定的默认地址或者默认目标（target）

link元素一般用以链接样式表

style标签可以规定样式

meta元素定义关于html的元数据





统一资源定位器

http不加密

https安全超文本传输协议，网页加密

ftp 文件传输协议

file  本机文件





html url编码：

url只能用ascii字符集来通过英特网进行发送

之外的字符会通过%及其随后的两位十六进制数来替代为有效的ascii格式



html颜色

三原色：RGB不同的值组成不同的颜色

color HEX：#000000->#ffffff

color RGB：rgb（0,0,0）->rgb(255,255,255)







xhtml标准：

语法规则：

属性小写，属性值加引号，属性简写禁止；







html表单：

form元素：用于收集用户输入

表单元素：

input 元素：text  定义常规文本输入

​		·			 radio：定义单选按钮输入

​					 submit： 定义提交按钮（提交表单）



文本输入：

<input type="text">

<input type="radio" values="nmsl">

<input type="submit" values="提交">

action属性是在提交表单时执行的动作

如果省略，默认当前的页面为

指定的页面。



method属性：

规定提交表单时所用到的get和post方发（http）

<form action="....." method="GET/POSt">
    !!!!!!!!

</form>

name属性：

想要正确的提交每个提交的字段，必须有一个name属性。没有就不会提交。



fileset标签足额表单的相关属性

legend元素为fileset元素定义标题



form标签的属性：accept-charset 规定提交表单中的使用的字符集

action 向何处提交表单

autocomplete 默认自动完成表单

enctype 提交数据的编码 默认url

method属性：规定提交表单时所用到的get和post方发（http）

name 标示： 名称

target ：默认的目标地址





html的表单元素：

<input>元素 有不同类型 可有多种形态

<select> 
    <option  value="shabi">
 	 shabi 元素 下拉列表
    </option>
    <option  value="shabi">
  	shabi 
    </option>
    <option  value="shabi">
  	 shabi 
    </option>
</select>



<textarea rows="5" cols="5">
    文本域
</textarea>
<button type="button">表单按钮组件







html5新增的表单元素

datalist元素

keygen元素

output元素







html5中的输入类型

输入限制：

| disabled  | 规定输入字段应该被禁用。           |
| --------- | ---------------------------------- |
| max       | 规定输入字段的最大值。             |
| maxlength | 规定输入字段的最大字符数。         |
| min       | 规定输入字段的最小值。             |
| pattern   | 规定通过其检查输入值的正则表达式。 |
| readonly  | 规定输入字段为只读（无法修改）。   |
| required  | 规定输入字段是必需的（必需填写）。 |
| size      | 规定输入字段的宽度（以字符计）。   |
| step      | 规定输入字段的合法数字间隔。       |
| value     | 规定输入字段的默认值。             |

<input type="number">:输入数字值的字段



<input type="date"> 输入日期

<input type="color">颜色

<input type="range">一定范围内的值

<input type="month">允许输入年份和月份

<input type="week">允许输入周和年

<input type="time">允许选择时间（无时区

<input type="datetime">有时区

……………………



input属性：

value 规定初始值

readonly 输入字段为只读

disabled 规定输入字段是禁用的（不可用不可点击）

size属性规定了字段的尺寸（文本框长度几个字符）

maxlength 输入字段最大长度

html5中：

autocomplete 表单或者输入字段是否自动完成（开启后 基于之前的输入有提示）

novalida属性属于<form>属性 提交表单时不进行验证

autofocus属性属于booleam属性  如果设置 加载input元素时就会自元素动获得焦点

form属性规定input元素所属的一个或者多个表单



formaction属性：

​				规定了当提交表单时处理该输入空间的URL

​				覆盖了<form>元素的action属性

​				适用于type=“submit”以及type=“image”



formenctype 属性:

​			formenctype 属性规定当把表单数据（form-data）提交至服务器时如何对其进行编码（仅针对 method="post" 的表单）。

​			formenctype 属性覆盖 <form> 元素的 enctype 属性。

​			formenctype 属性适用于 type="submit" 以及 type="image"。



formmethod 属性

​			formmethod 属性定义用以向 action URL 发送表单数据（form-data）的 HTTP 方法。

​			formmethod 属性覆盖 <form> 元素的 method 属性。

​			formmethod 属性适用于 type="submit" 以及 type="image"。





height和 width属性：规定了<input>属性的高度和宽度

min和max属性：规定输入的最大最小值（适用于部分type）

multiple属性：允许用户在<input>输入一个以上的值

placeholder属性：用于输入提示

required属性： 在提交表单时必须填写的字段

step属性：合法数字间隔：





![image-20200601100458749](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20200601100458749.png)



html5中新的元素：

<article>
    定义文档内的文章
</article>

<aside>
    定义页面内容之外的内容
</aside>
<bdi>定义

与其他文本不同的文本方向

<details>
    定义用户可查看或者隐藏的细节
</details>

<dialog>
        定义对话框或者窗口
</dialog>

<figure>
    定义自包含的内容，比如图示，图表，照片，代码等
</figure>

<footer>
    定义页脚
</footer>
header>
    定义页眉
</header>

<main>
    文章主要内容
</main>
<mark >

强调

</mark>



<menuitem>

菜单项

<meter>

定义已知范围内的标尺测量

<nav>
    导航链接	
</nav>

<progress>

​	定义任务进度

<rt>

​	定义字符的发音

<summary>

​	定义<details>的可见标题

<time>定义时间



article section yu div的差异

在html5中差异很小；

section表示已的是相关元素的块

article表示相关元素的自包含块

div表示子元素的块





代码约定：

元素名小写 

关闭所有的html元素

 关闭空的html元素<br/>

小写属性名

属性值加引号

始终给图像加alt属性  还有图像尺寸

title元素是必须的





html5中的canvas

在网页上绘制图形

canvas利用的是javascript在网页上绘制

canvas是元素



htnl5中的SVG

SVG 指可伸缩矢量图形 (Scalable Vector Graphics

svg使用xml格式定义的图形

放大缩小时图形质量不会丢失

svg是www的标准



svg的优势：

可通过文本编辑器来创建或者修改

svg可被搜索。索引。脚本化 压缩

可伸缩 高质量打印

放大不降画质







html多媒体：



object元素是支持html插件：

embed元素的含义是外部（非html）内容的容器

audio元素用来播放音频





用雅虎的音频播放器来播放音频：

必须添加代码：

```
<script type="text/javascript" src="http://mediaplayer.yahoo.com/js"></script>
```





可以用超链接来链接音频

```
<a href="song.mp3">Play the sound</a>
```





html视频：

embed标签：嵌入视频

video标签：

- 您必须把视频转换为很多不同的格式

- video 元素无法通过 HTML 4 和 XHTML 验证。

- embed 元素无法通过 HTML 4 和 XHTML 验证。

超链接跳转到视频





html5的拖放：任何元素斗士可以拖放的



一个拖拽的过程：

```html
<!DOCTYPE HTML>
<html>
<head>
<script>
function allowDrop(ev) {
    ev.preventDefault();
}

function drag(ev) {
    ev.dataTransfer.setData("text", ev.target.id);
}

function drop(ev) {
    ev.preventDefault();
    var data = ev.dataTransfer.getData("text");
    ev.target.appendChild(document.getElementById(data));
}
</script>
</head>
<body>

<div id="div1" ondrop="drop(event)" ondragover="allowDrop(event)"></div>

<img id="drag1" src="img_logo.gif" draggable="true" ondragstart="drag(event)" width="336" height="69">

</body>
</html>
```

首先把元素设置为可拖放：draggable=“true”

拖放的内容：ondragstart与setdata（）

​	ondragstart属性调用一个drag（event）函数，规定拖动什么数据。

dataTransfer.setData()设置数据的数据类型与值

```
function drag(ev) {
    ev.dataTransfer.setData("text", ev.target.id);
}
```

数据类型是text  值是对象的id



拖到何处     ondragover事件，阻止元素的默认打开方式（允许放入到元素中）；

这个任务由ondragover事件的event.preventDefault()方法完成；













