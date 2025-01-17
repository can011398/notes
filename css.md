# id

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

文本的颜色

* 颜色属性被用来设置文字的颜色

  示例如下：

  ~~~css
  body {color:red;}
  h1 {color:#00ff00;}
  h2 {color:rgb(255,0,0);}
  ~~~

文本的对齐方式

* 文本排列属性是用来设置文本左右的水平对齐方式。

* 文本居中或对齐到左或右,两端对齐。

* 当text-align设置为"justify"，每一行被展开为宽度相等，左，右外边距是对齐（如杂志和报纸）

  ~~~css
  h1 {text-align:center;}
  p.date {text-align:right;}
  p.main {text-align:justify;}
  ~~~

文本修饰

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

文本转换

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

  文本缩进

  * 用来指定文本的第一行的缩进。

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

