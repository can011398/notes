### id

id在css中是唯一的；

id选择器可以为标有特定ID的html元素指定特定的样式。

css中id选择器以“#”来定义

例如：

~~~<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
<style>
#para1
{
	text-align:center;
	color:red;
} 
</style>
</head>

<body>
<p id="para1">Hello World!</p>
<p>这个段落不受该样式的影响。</p>
</body>
</html>
~~~

在这串代码中使用了#来定义了para1元素的样式

通过使用来改变html的表现效果

### class

在css中我学习了id，而class和id的效果差不多，区别在于，class可以在多个元素中使用，以一个点.号显示：

~~~html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
<link rel="stylesheet" herf="styles.css">
</head>

<body>
<h1 class="center">标题居中</h1>
<p class="center">段落居中。</p> 
</body>
</html>
~~~

~~~css
.center {
    text-align: center;
}
~~~

在这串代码中，<link>元素通常用于链接外部资源

rel属性：

定义了当前文档与被链接文档之间的关系。这个属性可以取不同的值，用来指定链接资源的类型和目的。

* rel="stylesheet":表示链接的是一个样式表（css文件）。
* rel =“icon":表示被链接的资源是一个图标文件，用于在浏览器，书签栏或其他地方显示该网站的图标。
* rel=“preload”：表示加载一个资源，这有利于提高页面的性能，浏览器可以提前下载一些重要的资源，如字体，脚本，图像，等等，以便在有需要的时候可以更快的使用它们。

herf属性：

* herf指定了链接资源的位置。对于<link>元素，它通常是一个文件的url，可以是相对路径，或绝对路径

### css

css规则主要由两个主要的部分构成：选择器，以及一条或多条声明：

例如

~~~css
h1{color:blue;font-size:12px}
/*h1是选择器，color和font-size属性，blue和12px是值
每条声明由一个属性和一个值组成*/
~~~

css的声明是以;来结尾，用大括号{}括起来；

注释要以/**/来包裹

### 样式表

插入样式表的方法有三种

1. 外部样式表

2. 内部样式表

3. 内联样式表

   这三种方法在html里讲解

接下来要讲的是多重样式

#### 多重样式

如果某些属性在不同的样式表中被同样的选择器定义，那么属性值将从更具体的样式表中被继承过来。

例如，外部样式表有针对h3选择器的三个属性：

~~~css
h3
{
    color:red;
    text-align:left;
    font-size:8pt;
}
~~~

而内部样式表拥有针对h3选择器的两个属性：

~~~css
h3
{
    text-align:right;
    font-size:20pt;
}
~~~

假如拥有内部样式表的这个页面同时与外部样式表链接，那么 h3 得到的样式是：

~~~css
color:red;
text-align:right;
font-size:20pt;
~~~

即颜色属性将被继承于外部样式表，而文字排列（text-alignment）和字体尺寸（font-size）会被内部样式表中的规则取代。

* 多重样式优先级

  （内联样式）Inline style > （内部样式）Internal style sheet >（外部样式）External style sheet > 浏览器默认样式

### css背景

css属性定义背景效果：

* background-color:背景颜色

  在不同的选择器里可以设置不同的颜色

  ~~~HTML
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8"> 
  <title>菜鸟教程(runoob.com)</title> 
  <style>
  h1
  {
  	background-color:#6495ed;
  }
  p
  {
  	background-color:#e0ffff;
  }
  div
  {
  	background-color:#b0c4de;
  }
  </style>
  </head>
  
  <body>
  
  <h1>CSS background-color 实例!</h1>
  <div>
  该文本插入在 div 元素中。
  <p>该段落有自己的背景颜色。</p>
  我们仍然在同一个 div 中。
  </div>
  
  </body>
  </html>
  ~~~

  

* Background-image：背景图像

  默认情况下，背景图像进行平铺<重复>显示，以覆盖整个元素实体,一些条件下并不协调，而使用background-repeat可以实现在某一方向定向重复

* background-repeat：repeat-x在x轴上重复，repeat-y；在y轴上重复，不重复使用no-repeat。

* background-attachment:背景图像是否固定或者随着页面的其余部分滚动

* background-position:设置背景图像的起始位置。

### 文本

#### 文本的颜色

* 颜色属性被用来设置文字的颜色

  示例如下：

  ~~~css
  body {color:red;}
  h1 {color:#00ff00;}
  h2 {color:rgb(255,0,0);}
  ~~~

#### 文本的对齐方式

* 文本排列属性是用来设置文本左右的水平对齐方式。

* 文本居中或对齐到左或右,两端对齐。

* 当text-align设置为"justify"，每一行被展开为宽度相等，左，右外边距是对齐（如杂志和报纸）

  ~~~css
  h1 {text-align:center;}
  p.date {text-align:right;}
  p.main {text-align:justify;}
  ~~~

#### 文本修饰

text-decoration属性用来设置或删除文本的装饰

以下是实例：

~~~html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
<style>
h1 {text-decoration:overline;}
h2 {text-decoration:line-through;}
h3 {text-decoration:underline;}
</style>
</head>

<body>
<h1>This is heading 1</h1>
<h2>This is heading 2</h2>
<h3>This is heading 3</h3>
</body>

</html>
~~~

h1删除线在文字上；h2在文字中；h3在文字下；

a {text-decoration:none;}删除下划线

#### 文本转换

* 文本转换属性是用来指定在一个文本中的大写和小写字母。

  可用于所有字句变成大写或小写字母，或每个单词的首字母大写。

  实例

  ~~~html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8"> 
  <title>菜鸟教程(runoob.com)</title> 
  <style>
  p.uppercase {text-transform:uppercase;}
  p.lowercase {text-transform:lowercase;}
  p.capitalize {text-transform:capitalize;}
  </style>
  </head>
  
  <body>
  <p class="uppercase">This is some text.</p>
  <p class="lowercase">This is some text.</p>
  <p class="capitalize">This is some text.</p>
  </body>
  </html>
  ~~~

  其中

  ~~~css
  p.uppercase {text-transform:uppercase;}/*全转换为大写*/
  p.lowercase {text-transform:lowercase;}/*全转化为小写*/
  p.capitalize {text-transform:capitalize;}/*只转化每个单词的第一个字母*/
  ~~~

  #### 文本缩进

  用来指定文本的第一行的缩进。

  ~~~html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8"> 
  <title>菜鸟教程(runoob.com)</title> 
  <style>
  p {text-indent:50px;}
  </style>
  </head>
  <body>
  
  <p>In my younger and more vulnerable years my father gave me some advice that I've been turning over in my mind ever since. 'Whenever you feel like criticizing anyone,' he told me, 'just remember that all the people in this world haven't had the advantages that you've had.'</p>
  
  </body>
  </html>
  ~~~

  用法：p{text-indent:50px}

  | 属性                                                         | 描述                     |
  | :----------------------------------------------------------- | :----------------------- |
  | [color](https://www.runoob.com/cssref/pr-text-color.html)    | 设置文本颜色             |
  | [direction](https://www.runoob.com/cssref/pr-text-direction.html) | 设置文本方向。           |
  | [letter-spacing](https://www.runoob.com/cssref/pr-text-letter-spacing.html) | 设置字符间距             |
  | [line-height](https://www.runoob.com/cssref/pr-dim-line-height.html) | 设置行高                 |
  | [text-align](https://www.runoob.com/cssref/pr-text-text-align.html) | 对齐元素中的文本         |
  | [text-decoration](https://www.runoob.com/cssref/pr-text-text-decoration.html) | 向文本添加修饰           |
  | [text-indent](https://www.runoob.com/cssref/pr-text-text-indent.html) | 缩进元素中文本的首行     |
  | [text-shadow](https://www.runoob.com/cssref/css3-pr-text-shadow.html) | 设置文本阴影             |
  | [text-transform](https://www.runoob.com/cssref/pr-text-text-transform.html) | 控制元素中的字母         |
  | [unicode-bidi](https://www.runoob.com/cssref/pr-text-unicode-bidi.html) | 设置或返回文本是否被重写 |
  | [vertical-align](https://www.runoob.com/cssref/pr-pos-vertical-align.html) | 设置元素的垂直对齐       |
  | [white-space](https://www.runoob.com/cssref/pr-text-white-space.html) | 设置元素中空白的处理方式 |
  | [word-spacing](https://www.runoob.com/cssref/pr-text-word-spacing.html) | 设置字间距               |

### 字体

#### 字体类型

在css字型，有两种类型的字体系列名称：

* 通用字体系列和特定字体系列

  |serif             |字体中字符在行的末端有额外的装饰

  |sans-serif    |没有额外的装饰

  |Monospace|所有等宽字符具有相同的宽度

  在html里

  ~~~html
  <font face="Serif" color=red></font>
  ~~~

  可以改变末端颜色

#### 字体系列

font-family 属性设置文本的字体系列。

font-family 属性应该设置几个字体名称作为一种"后备"机制，如果浏览器不支持第一种字体，他将尝试下一种字体。如果字体系列的名称超过一个字，它必须用引号，如Font Family："宋体"。

多个字体系列是用一个逗号分隔指明：

~~~html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title>
<style>
p.serif{font-family:"Times New Roman",Times,serif;}
p.sansserif{font-family:Arial,Helvetica,sans-serif;}
</style>
</head>

<body>
<h1>CSS font-family</h1>
<p class="serif">这一段的字体是 Times New Roman </p>
<p class="sansserif">这一段的字体是 Arial.</p>

</body>
</html>
~~~

#### 字体样式

字体样式属性有三个值

* 正常
* 斜体
* 倾斜的文字

~~~html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title>
<style>
p.normal {font-style:normal;}
p.italic {font-style:italic;}
p.oblique {font-style:oblique;}
</style>
</head>

<body>
<p class="normal">这是一个段落,正常。</p>
<p class="italic">这是一个段落,斜体。</p>
<p class="oblique">这是一个段落,斜体。</p>
</body>

</html>
~~~

#### 字体大小

font-size设置文本大小

字体大小的值可以是绝对或相对的大小。

绝对大小：

- 设置一个指定大小的文本
- 不允许用户在所有浏览器中改变文本大小
- 确定了输出的物理尺寸时绝对大小很有用

相对大小：

- 相对于周围的元素来设置大小
- 允许用户在浏览器中改变文字大小

   如果不指定一个字体大小，默认16像素

> 16px=1em

em和px的用法一样

~~~css
/*px:*/
h1 {font-size:40px;}
h2 {font-size:30px;}
p {font-size:14px;}
/*em*/
h1 {font-size:2.5em;} 
h2 {font-size:1.875em;} 
p {font-size:0.875em;} 
~~~

还可以用百分比和em结合

~~~css
body {font-size:100%;}
h1 {font-size:2.5em;}
h2 {font-size:1.875em;}
p {font-size:0.875em;}
~~~

### 链接

链接的样式可以用任何css属性（例如颜色，背景，字体）来确定

~~~css
a:link {color:#000000;}      /* 未访问链接*/
a:visited {color:#00FF00;}  /* 已访问链接 */
a:hover {color:#FF00FF;}  /* 鼠标移动到链接上 */
a:active {color:#0000FF;}  /* 鼠标点击时 */
~~~

不同行为不同颜色

- a:link - 正常，未访问过的链接
- a:visited - 用户已访问过的链接
- a:hover - 当用户鼠标放在链接上时
- a:active - 链接被点击的那一刻

这里的a是html的<a>元素，即超链接元素。常用于创建网页上的链接，可以将用户引导至另一个网页、文件或同一页面的不同位置

当开始这些设置时，要注意顺序

- a:hover 必须跟在 a:link 和 a:visited后面
- a:active 必须跟在 a:hover后面

链接下面一般会有下划线，此刻，学的text-decoration出现作用了

~~~html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
<style>
a:link {color:#000000;}      /* 未访问链接*/
a:visited {color:#00FF00;}  /* 已访问链接 */
a:hover {color:#FF00FF;}  /* 鼠标移动到链接上 */
a:active {color:#0000FF;}  /* 鼠标点击时 */
</style>
</head>
<body>
<p><b><a href="/css/" target="_blank">这是一个链接</a></b></p>
<p><b>注意：</b> a:hover 必须在 a:link 和 a:visited 之后，需要严格按顺序才能看到效果。</p>
<p><b>注意：</b> a:active 必须在 a:hover 之后。</p>
</body>
</html>
~~~

~~~html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
<style>
a:link {text-decoration:none;}    /* unvisited link */
a:visited {text-decoration:none;} /* visited link */
a:hover {text-decoration:underline;}   /* mouse over link */
a:active {text-decoration:underline;}  /* selected link */
</style>
</head>

<body>
<p><b><a href="/css/" target="_blank">这是一个链接</a></b></p>
<p><b>注意:</b> hover必须在:link和 a:visited之后定义才有效.</p>
<p><b>注意:</b>active必须在hover之后定义是有效的.</p>
</body>
</html>
~~~

这是对比。

#### 背景颜色

背景颜色属性指定链接背景色

~~~css
a:link {background-color:#B2FF99;}
a:visited {background-color:#FFFF85;}
a:hover {background-color:#FF704D;}
a:active {background-color:#FF704D;}
~~~

### 边框

#### 边框样式：border-style

none: 默认无边框

dotted: 定义一个点线边框

dashed: 定义一个虚线边框

solid: 定义实线边框

double: 定义两个边框。 两个边框的宽度和 border-width 的值相同

groove: 定义3D沟槽边框。效果取决于边框的颜色值

ridge: 定义3D脊边框。效果取决于边框的颜色值

inset:定义一个3D的嵌入边框。效果取决于边框的颜色值

outset: 定义一个3D突出边框。 效果取决于边框的颜色值

~~~html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
<style>
p.none {border-style:none;}
p.dotted {border-style:dotted;}
p.dashed {border-style:dashed;}
p.solid {border-style:solid;}
p.double {border-style:double;}
p.groove {border-style:groove;}
p.ridge {border-style:ridge;}
p.inset {border-style:inset;}
p.outset {border-style:outset;}
p.hidden {border-style:hidden;}
p.mix {border-style: dotted dashed solid double;}
</style>
</head>

<body>
<p class="none">无边框。</p>
<p class="dotted">虚线边框。</p>
<p class="dashed">虚线边框。</p>
<p class="solid">实线边框。</p>
<p class="double">双边框。</p>
<p class="groove"> 凹槽边框。</p>
<p class="ridge">垄状边框。</p>
<p class="inset">嵌入边框。</p>
<p class="outset">外凸边框。</p>
<p class="hidden">隐藏边框。</p>
<p class="mix">混合边框</p>
</body>

</html>
~~~

#### 边框宽度：border-width

指定宽度有两种方法：

1. 可以指定长度值
2. 可以使用三个关键字之一，即thick，medium（默认值）和thin。

注意：CSS 没有定义 3 个关键字的具体宽度，所以一个用户可能把 thick 、medium 和 thin 分别设置为等于 5px、3px 和 2px，而另一个用户则分别设置为 3px、2px 和 1px。所以尽量不要使用

~~~css
p.one
{
    border-style:solid;
    border-width:5px;
}
p.two
{
    border-style:solid;
    border-width:medium;
}
~~~

#### 边框颜色：border-color

- name - 指定颜色的名称，如 "red"
- RGB - 指定 RGB 值, 如 "rgb(255,0,0)"
- Hex - 指定16进制值, 如 "#ff0000"

还可以设置边框的颜色为"transparent"（透明的）。

使用方法：

~~~css
p.one
{
    border-style:solid;
    border-color:red;
}
p.two
{
    border-style:solid;
    border-color:#98bf21;
}
~~~

注意：不能单独使用border-color，必须先用border-style设计样式

#### 单独设置各边边框

~~~css
p
{
    border-top-style:dotted;/*dotte:点状*/
    border-right-style:solid;/*solid:实线*/
    border-bottom-style:double;/*double:两条平行线*/
    border-left-style:dashed;/*dashed:一系列短横线*/
}
~~~

border-style属性可以有1-4个值：

- border-style:dotted solid double dashed;
  - 上边框是 dotted
  - 右边框是 solid
  - 底边框是 double
  - 左边框是 dashed
- border-style:dotted solid double;
  - 上边框是 dotted
  - 左、右边框是 solid
  - 底边框是 double
- border-style:dotted solid;
  - 上、底边框是 dotted
  - 右、左边框是 solid
- border-style:dotted;
  - 四面边框是 dotted

应该是连用法，简化使用

#### 边框简写

## 边框-简写属性

可以在"border"属性中设置：

- border-width
- border-style (required)
- border-color

~~~css
border:5px solid red;
~~~

一次性写多个多个属性
