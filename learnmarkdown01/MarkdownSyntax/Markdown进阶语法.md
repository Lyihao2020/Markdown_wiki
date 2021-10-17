****

本节目录(可实现跳转)

[TOC]

---

##二、Markdown纯文本进阶语法

上面的语法其实基本的写一些东西已经足够用了，但有时候还想要文档看起来更炫一些，这时候需要一些用于排版的进阶语法，实际上，***这里用的就是HTML的标签来实现了***。

##1. 更改字体、大小、颜色

***语法***

```html
<font face="黑体">我是黑体字</font>
<font face="微软雅黑">我是微软雅黑</font>
<font face="STCAIYUN">我是华文彩云</font>
<font color=red>我是红色</font>
<font color=#008000>我是绿色</font>
<font color=Blue>我是蓝色</font>
<font size=5>我是尺寸</font>
<font face="黑体" color=green size=5>我是黑体，绿色，尺寸为5</font>
```

**效果如下：**

<font face="黑体">我是黑体字</font>
<font face="微软雅黑">我是微软雅黑</font>
<font face="STCAIYUN">我是华文彩云</font>
<font color=red>我是红色</font>
<font color=#008000>我是绿色</font>
<font color=Blue>我是蓝色</font>
<font size=5>我是尺寸</font>
<font face="黑体" color=green size=5>我是黑体，绿色，尺寸为5</font>

<font face="STCAIYUN" color=red size=5>我是一条单身狗</font>

---

## 2.为文字添加背景色

由于 style 标签和标签的 style 属性不被支持，所以这里只能是借助 table, tr, td 等表格标签的 bgcolor 属性来实现背景色。故这里对于文字背景色的设置，只是将那一整行看作一个表格，更改了那个格子的背景色（bgcolor）。 语法：

```html
<table><tr><td bgcolor=yellow>背景色yellow</td></tr></table>
```

效果如下：

<table><tr><td bgcolor=yellow>背景色yellow</td></tr></table>

---

## 3.设置文字居中

**语法**

```html
<center>居中</center>
<p align="left">左对齐</p>
<p align="right">右对齐</p>
```

**效果如下：**

<center>居中</center>
<p align="left">左对齐</p>
<p align="right">右对齐</p>

---

## 4.加入上下标

**使用HTML中下标下标的语法即可, 语法：**

```html
H<sub>2</sub>O  CO<sub>2</sub>
爆米<sup>TM</sup>
H~2~O 下标
y^2=4	上标
```

效果如下：

H<sub>2</sub>O  CO<sub>2</sub>

爆米<sup>TM</sup>

H~2~O
y^2=4

---

## 5.超链接

***Markdown 支持两种形式的链接语法： 行内式和参考式两种形式***

不管是哪一种，链接文字都是用 [方括号] 来标记。

###行内式链接

要建立一个**行内式**的链接，只要在方块括号后面紧接着圆括号并插入网址链接即可，注意方括号和圆括号之间一定不能有空格，如果你还想要加上链接的 title 文字，只要在网址后面，用双引号把 title 文字包起来即可，例如：

```html
This is [baidu](www.baidu.com) inline link.

[This link](www.baidu.com) has orinted to Baidu.
```

效果如下：

This is [baidu](www.baidu.com) inline link.

[This link](www.baidu.com) has orinted to Baidu.

***注：如果想要在新页面中打开的话可以用html语言的a标签代替***

```
<a href="https://www.baidu.com" target="_blank">超链接名</a>
```

示例如下：

<a href="https://www.baidu.com" target="_blank">超链接名</a>

###参考式链接

在链接文字的括号后面再接上另一个方括号，而在第二个方括号里面要填入用以辨识链接的标记：

```
This is [an example][id] reference-style link.
[id]: http://example.com/  "Optional Title Here"
//接着，在文件的任意处，你可以把这个标记的链接内容定义出来:
//链接内容的形式为： 方括号（前面可以选择性地加上至多三个空格来缩进），里面输入链接文字,接着一个冒号,接着一个以上的空格或制表符,接着链接的网址,选择性地接着 title 内容，可以用单引号、双引号或是括弧包着 链接网址也可以用尖括号包起来：[id]: <http://example.com/> "Optional Title Here"
```

This is [an example][id] reference-style link.

[id]: http://example.com/  "Optional Title Here"

***链接辨别标签可以有字母、数字、空白和标点符号，但是并不区分大小写。***

链接的定义可以放在文件中的任何一个地方，我比较偏好直接放在链接出现段落的后面，你也可以把它放在文件最后面，就像是注解一样。

此外，用这个方法还可以将图片转化为base64编码保存在.md文件中，这将在插入图片中介绍。

下面是一个参考式链接的范例：

```
I get 10 times more traffic from [Google] [1] than from
[Yahoo] [2] or [MSN] [3].

  [1]: http://google.com/        "Google"
  [2]: http://search.yahoo.com/  "Yahoo Search"
  [3]: http://search.msn.com/    "MSN Search"
```

***还可以直接用链接名称的方式写：***

```
I get 10 times more traffic from [Google][] than from
[Yahoo][] or [MSN][].

  [google]: http://google.com/        "Google"
  [yahoo]:  http://search.yahoo.com/  "Yahoo Search"
  [msn]:    http://search.msn.com/    "MSN Search"
```

*要知道，**参考式的链接其实重点不在于它比较好写，而是它比较好读**。 使用 Markdown 的参考式链接，可以让文件更像是浏览器最后产生的结果，让你可以把一些标记相关的元数据移到段落文字之外，你就可以增加链接而不让文章的阅读感觉被打断。*

---

## 6.自动链接

除了上面的超链接方式，Markdown 还支持以比较简短的**自动链接形式来处理网址和电子邮件信箱，只要是用尖括号包起来， Markdown 就会自动把它转成链接** 语法：

```
<https://www.baidu.com>
```

效果如下：

<https://www.baidu.com>

---

## 7.插入图片

很明显地，要在纯文字应用中设计一个「自然」的语法来插入图片是有一定难度的。 Markdown 使用一种和链接很相似的语法来标记图片，同样也允许两种样式： **行内式**和**参考式**。

###**行内式**

图片语法看起来像是：

```text
![Alt pic](/path/to/img.jpg)

![Alt pic](/path/to/img.jpg "Optional title")
```

详细叙述如下： *一个惊叹号 !* 接着一个方括号，里面放上图片的替代文字 * 接着一个普通括号，里面放上图片的网址或本地路径（可以是相对路径或绝对路径），最后还可以用引号包住并加上 选择性的 '标题' 文字。

### **参考式**

图片语法则长得像这样：

```text
![Alt pic][id]
```

「id」是图片参考的名称，图片参考的定义方式则和连结参考一样：

```text
[id]: url/to/image  "Optional title attribute"
```

**但是在这里有两个很大的问题：** 1. 如果使用本地路径插入本地图片，不灵活不好分享，本地图片的路径更改或丢失都会造成markdown文件调不出图。 2. 插入网络图片，则非常依赖网络，如果是本地图片，还需要先上传到网络服务器上。

###**使用HTML <img> 标签**

`Markdown` 中支持`HTML <img> 标签` 来显示图片，当然也可以使用`HTML 属性`，来调节`图片大小`等：

```text
<img src="图片地址">
```



### 关于在markdown中保存图片

### 1. 将本地图片上传到github

首先在github中新建一个repo，然后git clone下来，然后把你想要的图片放到这个文件夹中然后上传，然后到GitHub中找到这个图片查看地址，在markdown中引用就好了。

这种方法的**优点**就在于插入式很灵活，github没有墙，你的文章上传到各个平台，图片也都基本不会丢失或找不到，但**缺点**就在于图片的管理很不方便，图片一旦多起来，你的本地仓库将会变得很大，而且你的文章可能涉及很多方面，管理也不方便，不过，也算是一个比较理想的解决方案。

### 2. 把图片存入markdown文件

1. 用base64转码工具把图片转成一段字符串
2. 把字符串填到基础格式中链接的那个位置。
3. 由于图片转成base64编码，会非常的大，一般至少都要上千行，这个时候会发现插入的这一长串字符串会把整个文章分割开，非常影响编写文章时的体验。这时候就可以用**参考式**，把大段的base64字符串放在文章末尾，然后在文章中通过一个id来调用，文章就不会被分割的这么乱了。

这种方式需要先将图片转换成`base64 编码` 格式，然后将图片内容放入`Markdown` 文档中（所以，如果图片很大的话，`Markdown` 文档也会变得很大），最后再引用图片。

***语法如下（描述文字可不写），`第一行`为图片的引用，`第二行`为图片的声明（一般可写在文档的最后）：***

```text
![描述图片的文字][图片声明]
[图片声明]:图片base64 编码内容
```

例如：

```html
![描述][base64str]
[base64str]:data:image/png;base64,iVBORw0......
```

这种方法的**优点**就是图片真的是不会丢啊，相当于直接将图片编码嵌入到文档中，但**缺点**也是显而易见的，就是base64编码实在是太长了啊，太长了，虽然可以放到文章结尾，但还是太长了，所以目前我还没找到更好的解决方法。

---

## 8.调整图片格式

图片位置——居左/居中/居右

利用markdown在编写文档时插入图片是**默认靠左**，有些时候将图片设置为居中时可以更加的美观，这时就需要在图片的信息前边添加如下语句：

```text
<div align=center>![Alt pic] (http:...)

如果想将图片位于右侧，只需要将center改为right
```

- 设置图片大小

```text
<img src="http:..." width = "100" height = "100" div align=right />
```

如上格式，在图片的最后添加 **width = “100” height = “100”，就可以设置图片的大小**。也可以在后边输入百分比为多少，如 width = 20% height = 20%， 当然，如果你使用的是base64编码，可以直接将编码放到上面放链接的引号里，也可以设置图片大小。

---

## 9.LaTeX 公式(仍然需要学习)

Markdown还有一大优势就是可以支持 LaTeX 的公式。 \$ 表示行内公式 \$$ 表示整行公式 访问 [MathJax](https://link.zhihu.com/?target=https%3A//math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference) 参考更多使用方法。

这里说一个常用的，很多时候，我们在做笔记时候，需要画箭头，然后在箭头上需要写字，这里就可以用LaTeX公式来实现：

```text
$ X\stackrel{F}{\longrightarrow}Y $
$$ X\stackrel{F}{\longrightarrow}Y $$
```

效果如下：

 $ X\stackrel{F}{\longrightarrow}Y $

---

$$
 X\stackrel{F}{\longrightarrow}Y 
$$

打开Typora选择数学模块

- 点击“段落”—>“公式块”
- 快捷键Ctrl+Shift+m
- `“$$”+回车`

---

## 10.内容目录

Markdown还有一个很方便的功能，就是可以根据标题自动生成目录。 

在段落中填写 `[TOC]` 以显示全文内容的目录结构，**语法：**

```text
[TOC]

## 我是标题一

这是标题一下的正文

## 我是标题二

这是标题二下的正文

### 我是标题二下的子标题
这是标题二下的子标题的正文

## 我是标题三
这是标题三下的正文
```

效果如下：

[TOC]

---

##11.表情

Typora语法支持添加emoji表情，输入不同的符号码（两个冒号包围的字符）可以显示出不同的表情。

```text
以:开始，然后输入表情的英文单词,以：结尾，将直接输入该表情.例如：
:smile
:cry
:happy
```

效果如下:

:smile:

---

|    代码库    | 链接                                                         |
| :----------: | ------------------------------------------------------------ |
|   MarkDown   | [https://github.com/younghz/Markdown](https://github.com/younghz/Markdown "Markdown") |
| MarkDownCopy | [https://github.com/younghz/Markdown](https://github.com/younghz/Markdown "Markdown") |


关于其它扩展语法可参见具体工具的使用说明。

