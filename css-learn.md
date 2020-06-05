# CSS：层叠样式表：定义如何显示 html元素





样式定义的优先级：

内联样式》内部样式表》外部样式表》浏览器缺省设置



# css语法：

selector

{

​	declaration1；declaration2；‘……

}

也就是选择器加声明；





selector{property：value}

例如：

h1{ color：red；font-size：14px；}



![image-20200602113839838](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20200602113839838.png)



## 颜色值的不同写法：

p{color:#ff0000}

p{color:#f00}

p{color:rgb(255,0,0);}

p{color:rgb(100%,0%,0%)}百分号表示的时候就算是0也要加%





如果值是若干的单词，就要给值加引号

p{font-family:"sans serif";}



## CSS对大小写不敏感



## css可以对选择器分组：

h1,h2,h3,h4,h5,h6{

color:green

}



## CSS存在继承：

例如：

body{

font-family:vendana,sans-serif;

}

那么所有body的子元素（p td ul ol li dl dt） 都会显示verdana字体

如果不想使用继承的样式，那就要去单独设定



## id选择器：

用#来指定特定id的样式

#red {color:red;}那么id为red的元素的颜色就是红色



## id选择器与派生选择器：

#label  p{

font-style:italic;

text-align: right;

}

那么这个样式只会作用于id为label 的元素中的p元素



## 类选择器；用.来表示

例如： .center {

text-align: center

}

那么所有拥有center类的html元素均为居中



## 类选择器也可以用作派生选择器：

. label td

{

color:red;

background:black;

}

也就是所有的含有label类的元素中的td元素都应用这个样式



## 属性选择器：[]表示

例如：

[title]

{

color:red;

}

那么所有拥有title的属性的元素都会应用这个样式







CSS选择器参考手册

| [[*attribute*\]](https://www.w3school.com.cn/cssref/selector_attribute.asp) | 用于选取带有指定属性的元素。                                 |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [[*attribute*=*value*\]](https://www.w3school.com.cn/cssref/selector_attribute_value.asp) | 用于选取带有指定属性和值的元素。                             |
| [[*attribute*~=*value*\]](https://www.w3school.com.cn/cssref/selector_attribute_value_contain.asp) | 用于选取属性值中包含指定词汇的元素。                         |
| [[*attribute*\|=*value*\]](https://www.w3school.com.cn/cssref/selector_attribute_value_start.asp) | 用于选取带有以指定值开头的属性值的元素，该值必须是整个单词。 |
| [[*attribute*^=*value*\]](https://www.w3school.com.cn/cssref/selector_attr_begin.asp) | 匹配属性值以指定值开头的每个元素。                           |
| [[*attribute*$=*value*\]](https://www.w3school.com.cn/cssref/selector_attr_end.asp) | 匹配属性值以指定值结尾的每个元素。                           |
|                                                              |                                                              |
|                                                              |                                                              |







三种插入样式表的方法:

外部样式表;

```html
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
```





内部样式表：

```html
<head>
    <style>
        hr {color:red;}
        p{margin-left:20px;}
        body{background-image:url("images/background.jpg")}
    </style>
    
</head>
```





内联样式：

```html
<p style="color: sienna; margin-left:20px">
    this is a paragraph
</p>
```



样式继承的原则：谁更具体，继承谁







# CSS的背景：

​	用background-color属性可以为元素设置背景色；（默认的值是transparent  透明的意思）

## 	背景图片：

背景图片：

## 用background-image属性。值是一个url的地址。



## 背景重复：

对背景进行平铺：background-repeat属性 值：repeat-x和repeat-y表示在水平方向上重复。no-repeat 表示不允许图片重复。



## 背景定位：

用到backgroung-position 属性：

属性值可以是一些关键词：center bottom left right center

​	或者用百分比



关键词一般成对出现：一个表示水平 一个表示垂直   例如top right  表示右上对齐



、

| center | center center                  |
| ------ | ------------------------------ |
| top    | top center 或 center top       |
| bottom | bottom center 或 center bottom |
| right  | right center 或 center right   |
| left   | left center 或 center left     |





## 百分比：

百分比数值同时作用于元素和图像，也就是说50%，50%的含义是把图像的50%50%的点与元素的50%50%点对齐。



## 长度值：

作用基准是图像左上角



## 背景关联：





解决因为图像与文旦改长度不同的原因导致的背景图像的滚动：我们用到了background-attachment：fixed

属性值的默认是scroll  也就是默认滚动

fixed表示不在再滚动







# CSS文本：

## 缩进文本：text-index属性

值的选项：

### 使用负值：

可以实现使第一行位于元素的左边悬挂；小心第一行出现在屏幕外的情况：通过设置外边距或者内边距避免

```html
p {text-indent: -5em; padding-left: 5em;}
```

### 使用百分比值

百分比的缩进是相对于父元素的长度的；

### 继承：

text-index的属性可被继承：

## 水平对齐：text-align属性

### left：左对齐；right：右对齐；center：居中

### text-align：center与<CENTER>

两者不一样 center只会影响文本；<CENTER>影响元素，会把整个元素居中

### 两端对齐：justify属性：





## 字间隔：word-spacing属性

默认值是0；

可以是正负值，正：拉远；负值：拉近

## 字母间隔;letter-spaceing属性

修改的是字符或者字母之间的间隔；

## 字符转换：text-transform属性；

none；不作处理

uppercase；全大写

lowercase；全小写

capitalize;单个单词首字母大写



## 文本装饰：text-decoration属性：

none；

underline

overline

line-through

blink文本闪烁



text-decoration 值会替换而不是累积起来

也就是不会继承父元素中的text-decoration属性  而是会替换





## 处理空白符：white-space

影响对空格，换行和tab字符的处理

值：

normal：会合并空白字符 ；

pre：空白符不会被忽略

nowrap：防止换行

pre-wrap与pre-line：css2.1时加入：pre-wrap保留空白符但会正确换行

​																pre-line合并空白符保留换行



## 总结：

| 值       | 空白符 | 换行符 | 自动换行 |
| :------- | :----- | :----- | :------- |
| pre-line | 合并   | 保留   | 允许     |
| normal   | 合并   | 忽略   | 允许     |
| nowrap   | 合并   | 忽略   | 不允许   |
| pre      | 保留   | 保留   | 不允许   |
| pre-wrap | 保留   | 保留   | 允许     |

## 

## 文本方向：drection属性

ltr和rtl：从左到右与从右到左





## 总结：

| 属性                                                         | 描述                                                        |
| :----------------------------------------------------------- | :---------------------------------------------------------- |
| [color](https://www.w3school.com.cn/cssref/pr_text_color.asp) | 设置文本颜色                                                |
| [direction](https://www.w3school.com.cn/cssref/pr_text_direction.asp) | 设置文本方向。                                              |
| [line-height](https://www.w3school.com.cn/cssref/pr_dim_line-height.asp) | 设置行高。                                                  |
| [letter-spacing](https://www.w3school.com.cn/cssref/pr_text_letter-spacing.asp) | 设置字符间距。                                              |
| [text-align](https://www.w3school.com.cn/cssref/pr_text_text-align.asp) | 对齐元素中的文本。                                          |
| [text-decoration](https://www.w3school.com.cn/cssref/pr_text_text-decoration.asp) | 向文本添加修饰。                                            |
| [text-indent](https://www.w3school.com.cn/cssref/pr_text_text-indent.asp) | 缩进元素中文本的首行。                                      |
| text-shadow                                                  | 设置文本阴影。CSS2 包含该属性，但是 CSS2.1 没有保留该属性。 |
| [text-transform](https://www.w3school.com.cn/cssref/pr_text_text-transform.asp) | 控制元素中的字母。                                          |
| unicode-bidi                                                 | 设置文本方向。                                              |
| [white-space](https://www.w3school.com.cn/cssref/pr_text_white-space.asp) | 设置元素中空白的处理方式。                                  |
| [word-spacing](https://www.w3school.com.cn/cssref/pr_text_word-spacing.asp) | 设置字间距。                                                |

# css字体

## css字体系列：

通用字体系列;Serif或者Monospace

特定字体系列：Times或者Courier

Css的5种通用字体系列

## 指定字体系列：font-family属性

### 使用通用字体系列：

### body{font-family: sans-serif}

### 指定字体系列：

h1 {font-family: georgia;}



## 字体风格：font-style

值：normal：文本正常显示

italic：斜体

oblique：倾斜



italic与oblique基本一样只有几个字母不同



## 字体变形：font-variant

用以设置**小型大写字母**

## 字体加粗：font-weight

100-900对应9个级别

100对应最细的字体；

400等价于normal

700等价于bold

## 字体大小：font-size

绝对值：

- 将文本这定位指定大小
- 不允许用户所在浏览器更改文本大小
- 在确定了输出的物理尺寸时十分有用

相对大小：

- 相对周围元素来设定大小
- 允许用户浏览器更改大小

### 字体单位

em单位与px单位

在默认的情况下1em=16px；

当然em基于的是父元素的font-size，如果父元素的font-size=20px

那么1em=20px；

## 总结：

| 属性                                                         | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [font](https://www.w3school.com.cn/cssref/pr_font_font.asp)  | 简写属性。作用是把所有针对字体的属性设置在一个声明中。       |
| [font-family](https://www.w3school.com.cn/cssref/pr_font_font-family.asp) | 设置字体系列。                                               |
| [font-size](https://www.w3school.com.cn/cssref/pr_font_font-size.asp) | 设置字体的尺寸。                                             |
| [font-size-adjust](https://www.w3school.com.cn/cssref/pr_font_font-size-adjust.asp) | 当首选字体不可用时，对替换字体进行智能缩放。（CSS2.1 已删除该属性。） |
| [font-stretch](https://www.w3school.com.cn/cssref/pr_font_font-stretch.asp) | 对字体进行水平拉伸。（CSS2.1 已删除该属性。）                |
| [font-style](https://www.w3school.com.cn/cssref/pr_font_font-style.asp) | 设置字体风格。                                               |
| [font-variant](https://www.w3school.com.cn/cssref/pr_font_font-variant.asp) | 以小型大写字体或者正常字体显示文本。                         |
| [font-weight](https://www.w3school.com.cn/cssref/pr_font_weight.asp) | 设置字体的粗细。                                             |

# css链接：

## 设置链接的样式：

- a：link：没有被访问过的 不同的链接
- a：visited：已访问过的链接
- a：hover：鼠标位于链接上方
- a：active：鼠标被点击的时候

## 背景色：background-color

例如a:link{background-color：#ffffff}





# css列表：

## 列表类型 ：list-style-type

值：例如ul {list-style-type：square }把列表项标志设置为方块



## 列表项图像：list-style-image

值：图片的url   ：

ul li{ list-style-image：url（xxx.gif）}  

## 列表项的位置：list-style-position

## 简写列表样式：list-style

例如：li{ list-syle：url（example.gif）square inside }



## 总结：

| 属性                                                         | 描述                                                 |
| :----------------------------------------------------------- | :--------------------------------------------------- |
| [list-style](https://www.w3school.com.cn/cssref/pr_list-style.asp) | 简写属性。用于把所有用于列表的属性设置于一个声明中。 |
| [list-style-image](https://www.w3school.com.cn/cssref/pr_list-style-image.asp) | 将图象设置为列表项标志。                             |
| [list-style-position](https://www.w3school.com.cn/cssref/pr_list-style-position.asp) | 设置列表中列表项标志的位置。                         |
| [list-style-type](https://www.w3school.com.cn/cssref/pr_list-style-type.asp) | 设置列表项标志的类型。                               |
| marker-offset                                                |                                                      |

# css表格：

## 表格边框：border属性

table，th，td

{

border:1px soild blue

}

## 折叠边框;border-collapse属性

table{

border-collapse:collapse

}

就是当table与th都有边框的时候，合并边框

## 表格宽度与高度：width属性与height属性

例如

table{

width:100%;

}

th{

height:50px;

}

## 表格文本对齐：text-align与vertical属性

text-align：水平对齐方式；

vertical-align：垂直对齐属性



## 表格内边距：padding属性

用来设置th与td与外边框的距离：



## 表格的颜色：

边框颜色：border：green

文本与背景颜色：th{background-color:green;

color:red}

## 总结：

| 属性                                                         | 描述                                 |
| :----------------------------------------------------------- | :----------------------------------- |
| [border-collapse](https://www.w3school.com.cn/cssref/pr_tab_border-collapse.asp) | 设置是否把表格边框合并为单一的边框。 |
| [border-spacing](https://www.w3school.com.cn/cssref/pr_tab_border-spacing.asp) | 设置分隔单元格边框的距离。           |
| [caption-side](https://www.w3school.com.cn/cssref/pr_tab_caption-side.asp) | 设置表格标题的位置。                 |
| [empty-cells](https://www.w3school.com.cn/cssref/pr_tab_empty-cells.asp) | 设置是否显示表格中的空单元格。       |
| [table-layout](https://www.w3school.com.cn/cssref/pr_tab_table-layout.asp) | 设置显示单元、行和列的算法。         |

# css轮廓：

## 总结：

| 属性                                                         | 描述                             | CSS  |
| :----------------------------------------------------------- | :------------------------------- | ---- |
| [outline](https://www.w3school.com.cn/cssref/pr_outline.asp) | 在一个声明中设置所有的轮廓属性。 | 2    |
| [outline-color](https://www.w3school.com.cn/cssref/pr_outline-color.asp) | 设置轮廓的颜色。                 | 2    |
| [outline-style](https://www.w3school.com.cn/cssref/pr_outline-style.asp) | 设置轮廓的样式。                 | 2    |
| [outline-width](https://www.w3school.com.cn/cssref/pr_outline-width.asp) | 设置轮廓的宽度。                 |      |

# CSS框模型概述：

![CSS 框模型](https://www.w3school.com.cn/i/ct_boxmodel.gif)

**百分比的数值相对于的是父容器的宽度。上上下边距相对于的也是宽度；**

## css内边距属性：

| 属性                                                         | 描述                                                 |
| :----------------------------------------------------------- | :--------------------------------------------------- |
| [padding](https://www.w3school.com.cn/cssref/pr_padding.asp) | 简写属性。作用是在一个声明中设置元素的所内边距属性。 |
| [padding-bottom](https://www.w3school.com.cn/cssref/pr_padding-bottom.asp) | 设置元素的下内边距。                                 |
| [padding-left](https://www.w3school.com.cn/cssref/pr_padding-left.asp) | 设置元素的左内边距。                                 |
| [padding-right](https://www.w3school.com.cn/cssref/pr_padding-right.asp) | 设置元素的右内边距。                                 |
| [padding-top](https://www.w3school.com.cn/cssref/pr_padding-top.asp) | 设置元素的上内边距。                                 |

## css边框:允许规定样式、宽度、颜色。

### 边框位于背景之上：也就是背景包括了边框、内边距、与元素（css2.1规定）

### 边框的样式：

border-style：outset等10个非inherit样式

可以同时定义多个样式：

例如：

p.aside {border-style: solid dotted dashed double;}

为类名为aside的段落定义了四种样式：实线上边框；点线右边框；虚线下边框；双线下边框。

顺序为上右下左；设置内边距时 也是这个顺序；

### 定义单边样式：

- [border-top-style](https://www.w3school.com.cn/cssref/pr_border-top_style.asp)
- [border-right-style](https://www.w3school.com.cn/cssref/pr_border-right_style.asp)
- [border-bottom-style](https://www.w3school.com.cn/cssref/pr_border-bottom_style.asp)
- [border-left-style](https://www.w3school.com.cn/cssref/pr_border-left_style.asp)

```
p {border-style: solid solid solid none;}
p {border-style: solid; border-left-style: none;}
```

上述两种方法相等。（注意先后顺序  会覆盖）

## 边框宽度：

border-width：可以是指定长度值也可以是三个关键字之一（thin medium thick）

### 单边宽度设置：

```
p {border-style: solid; border-width: 15px 5px 15px 5px;}
```

顺序还是上右下左

- [border-top-width](https://www.w3school.com.cn/cssref/pr_border-top_width.asp)
- [border-right-width](https://www.w3school.com.cn/cssref/pr_border-right_width.asp)
- [border-bottom-width](https://www.w3school.com.cn/cssref/pr_border-bottom_width.asp)
- [border-left-width](https://www.w3school.com.cn/cssref/pr_border-left_width.asp)

如果没有声明边框样式：那边框就不会显示：

相当于border-style：none

none的值意味着没有边框。

**因此，如果您希望边框出现，就必须声明一个边框样式。**



边框颜色border-color：十六进制或者rgb

默认的边框颜色是元素本身的前景色。如果没有为边框声明颜色，它将与元素的文本颜色相同。另一方面，如果元素没有任何文本，假设它是一个表格，其中只包含图像，那么该表的边框颜色就是其父元素的文本颜色（因为 color 可以继承）

### 定义单边颜色：



- [border-top-color](https://www.w3school.com.cn/cssref/pr_border-top_color.asp)
- [border-right-color](https://www.w3school.com.cn/cssref/pr_border-right_color.asp)
- [border-bottom-color](https://www.w3school.com.cn/cssref/pr_border-bottom_color.asp)
- [border-left-color](https://www.w3school.com.cn/cssref/pr_border-left_color.asp)

## 总结：

| 属性                                                         | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [border](https://www.w3school.com.cn/cssref/pr_border.asp)   | 简写属性，用于把针对四个边的属性设置在一个声明。             |
| [border-style](https://www.w3school.com.cn/cssref/pr_border-style.asp) | 用于设置元素所有边框的样式，或者单独地为各边设置边框样式。   |
| [border-width](https://www.w3school.com.cn/cssref/pr_border-width.asp) | 简写属性，用于为元素的所有边框设置宽度，或者单独地为各边边框设置宽度。 |
| [border-color](https://www.w3school.com.cn/cssref/pr_border-color.asp) | 简写属性，设置元素的所有边框中可见部分的颜色，或为 4 个边分别设置颜色。 |
| [border-bottom](https://www.w3school.com.cn/cssref/pr_border-bottom.asp) | 简写属性，用于把下边框的所有属性设置到一个声明中。           |
| [border-bottom-color](https://www.w3school.com.cn/cssref/pr_border-bottom_color.asp) | 设置元素的下边框的颜色。                                     |
| [border-bottom-style](https://www.w3school.com.cn/cssref/pr_border-bottom_style.asp) | 设置元素的下边框的样式。                                     |
| [border-bottom-width](https://www.w3school.com.cn/cssref/pr_border-bottom_width.asp) | 设置元素的下边框的宽度。                                     |
| [border-left](https://www.w3school.com.cn/cssref/pr_border-left.asp) | 简写属性，用于把左边框的所有属性设置到一个声明中。           |
| [border-left-color](https://www.w3school.com.cn/cssref/pr_border-left_color.asp) | 设置元素的左边框的颜色。                                     |
| [border-left-style](https://www.w3school.com.cn/cssref/pr_border-left_style.asp) | 设置元素的左边框的样式。                                     |
| [border-left-width](https://www.w3school.com.cn/cssref/pr_border-left_width.asp) | 设置元素的左边框的宽度。                                     |
| [border-right](https://www.w3school.com.cn/cssref/pr_border-right.asp) | 简写属性，用于把右边框的所有属性设置到一个声明中。           |
| [border-right-color](https://www.w3school.com.cn/cssref/pr_border-right_color.asp) | 设置元素的右边框的颜色。                                     |
| [border-right-style](https://www.w3school.com.cn/cssref/pr_border-right_style.asp) | 设置元素的右边框的样式。                                     |
| [border-right-width](https://www.w3school.com.cn/cssref/pr_border-right_width.asp) | 设置元素的右边框的宽度。                                     |
| [border-top](https://www.w3school.com.cn/cssref/pr_border-top.asp) | 简写属性，用于把上边框的所有属性设置到一个声明中。           |
| [border-top-color](https://www.w3school.com.cn/cssref/pr_border-top_color.asp) | 设置元素的上边框的颜色。                                     |
| [border-top-style](https://www.w3school.com.cn/cssref/pr_border-top_style.asp) | 设置元素的上边框的样式。                                     |
| [border-top-width](https://www.w3school.com.cn/cssref/pr_border-top_width.asp) | 设置元素的上边框的宽度。                                     |