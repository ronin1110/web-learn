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











