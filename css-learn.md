CSS：层叠样式表：定义如何显示 html元素





样式定义的优先级：

内联样式》内部样式表》外部样式表》浏览器缺省设置



css语法：

selector

{

​	declaration1；declaration2；‘……

}

也就是选择器加声明；





selector{property：value}

例如：

h1{ color：red；font-size：14px；}



![image-20200602113839838](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20200602113839838.png)



颜色值的不同写法：

p{color:#ff0000}

p{color:#f00}

p{color:rgb(255,0,0);}

p{color:rgb(100%,0%,0%)}百分号表示的时候就算是0也要加%





如果值是若干的单词，就要给值加引号

p{font-family:"sans serif";}



CSS对大小写不敏感



css可以对选择器分组：

h1,h2,h3,h4,h5,h6{

color:green

}



CSS存在继承：

例如：

body{

font-family:vendana,sans-serif;

}

那么所有body的子元素（p td ul ol li dl dt） 都会显示verdana字体

如果不想使用继承的样式，那就要去单独设定



id选择器：

用#来指定特定id的样式

#red {color:red;}那么id为red的元素的颜色就是红色



id选择器与派生选择器：

#label  p{

font-style:italic;

text-align: right;

}

那么这个样式只会作用于id为label 的元素中的p元素



类选择器；用.来表示

例如： .center {

text-align: center

}

那么所有拥有center类的html元素均为居中



类选择器也可以用作派生选择器：

. label td

{

color:red;

background:black;

}

也就是所有的含有label类的元素中的td元素都应用这个样式

























