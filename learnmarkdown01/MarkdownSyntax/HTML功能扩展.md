[TOC]



## 三.Markdown的HTML扩展

## 一.居中

**语法格式一：**

```html
<center>内容</center> 
```

**语法格式二：**

```html
<p align=center>内容</p> 
或
<div align=center>内容</div>
```

*效果如下*

<center>内容</center>

<p align=center>内容</p>

<div align=center>内容</div>

---

## 二.字体颜色、大小、字体类型

使用font标签以及其三个属性，下面代码的效果便是第3个标题

**格式**

```html
<font color="" size=6 face="">字体颜色、大小、字体类型</font
```

*效果如下*

<font face="黑体" size=6 color=red>我是一条单身狗</font>

---

##三、图片

**格式一**

```html
![alt 属性文本](图片地址 "可选标题")
```

**格式二**

```html
<img src="url" width="400" height="400" alt="" title="" style="zoom:50%;"/>
```

其中，

- src：该图片的网址
- **alt：是图片没有加载成功时，显示的文字**
- title：该图片的标题
- **style：设置缩放**

---

##四、空白行

虽然说markdown能回车换行，但是没办法做到n个空白行，而且。换行的办法就比较多了，因为别忘了，markdown是支持HTML标签的：

1. **使用块标签，撑开一行，如p、div**

```html
<p></p>
或
<div></div> 
```

2. **简单点的方法，就直接使用 br 标签**

```html
内容1<br/><br/>内容2
```

*效果如下：*

<p></p>

或

<div></div>

或

<br></br>

或

/*上面有三个换行 */

---

## 五.表格宽度的设置(看不到效果)

***一个比较简单粗暴的方法自然是加一段空格符*** 	`&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  `

***一个更加优雅的方法则是使用空的 `<img>` 标签。***

例1:

```html
| a | b | c |
|---|---|---|
| 1 |  &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | 3 | 
```

*效果如下*	

| a    | b                                  | c    |
| ---- | ---------------------------------- | ---- |
| 1    | &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | 3    |

例2:

```html
| a | b | c |
|---|---|---|
| 1 |<img width=200/>| 3 | 
```
*效果如下（好像出现了点问题)*

| a    | b                | c    |
| ---- | ---------------- | ---- |
| 1    | <img width=200/> | 3    |

---

## 六.长文本需要指定列宽，控制换行（看不到效果)

**第一种方法**可以使用 `<div style="width:[长度]">[单元格文本]</div>` 的形式，长度单位可以是 `pt` , `px`, `cm`等。比如：

```html
**默认**

| a | b | d |
|---|---|---|
| 1 | very very very very very long long long long long text | 3 |

**使用后效果**

| a | b | d |
|---|---|---|
| 1 | <div style="width: 150pt">very very very very very lonng long long long long text</div>| 3 |
```

***效果如下***

**默认**

| a    | b                                                      | d    |
| ---- | ------------------------------------------------------ | ---- |
| 1    | very very very very very long long long long long text | 3    |

**使用后效果**

| a    | b                                                            | d    |
| ---- | ------------------------------------------------------------ | ---- |
| 1    | <div style="width: 150pt">very very very very very lonng long long long long text</div> | 3    |

**第二种方法**可以从外部定义一个 「Style」来指定各列的列宽

```css
first-of-type ：选择的 p 元素是其父元素的第一个 p 元素

nth-of-type(2) ：指定每个p元素匹配同类型中的第2个同级兄弟元素

nth-of-type(3) ：指定每个p元素匹配同类型中的第3个同级兄弟元素

示例：修改选择的p元素匹配同类型中的第2个同级兄弟元素的背景色
p:nth-of-type(2)
{
	background:#ff0000;  //red
}

```



```html
<style>
table th:first-of-type {
    width: 4cm;
}
table th:nth-of-type(2) {
    width: 150pt;
}
table th:nth-of-type(3) {
    width: 8em;
}
</style>

| a | b | c |
|---|---|---|
| 列宽 = 3 cm| 列宽 = 5 cm| 列宽 = 8em |
```

**效果如下：


| a           | b           | c          |
| ----------- | ----------- | ---------- |
| 列宽 = 3 cm | 列宽 = 5 cm | 列宽 = 8em |

*****当然你可以把单位改成 `%` 这样就相当于按照所占行宽的比例来分配列宽***

```css
<style>
table th:first-of-type {
    width: 20%;
}
table th:nth-of-type(2) {
    width: 30%;
}
table th:nth-of-type(3) {
    width: 50%;
}
</style>

| a | b | c |
|---|---|---|
| 列宽 = 10% 行宽| 列宽 = 30% 行宽 |列宽 = 60% 行宽 |
```

***效果如下：***


| a               | b               | c               |
| --------------- | --------------- | --------------- |
| 列宽 = 10% 行宽 | 列宽 = 30% 行宽 | 列宽 = 60% 行宽 |

---

## 七.文字缩写(显示出错)

`文字缩写`使用`HTML <abbr> 标签`，如下所示：

```html
<abbr title="Hyper Text Markup Language">HTML</abbr> 是一种标记语言
```

效果如下：

<abbr title="Hyper Text Markup Language">HTML</abbr> 是一种标记语言

---

## 八.注脚

***使用注脚也是分两步，一是定义注脚，二是使用注脚。***

定义注脚的语法如下：

```text
[^注脚名称]:注脚内容
```

中括号内有一个`上尖括号^`，后边紧跟`注脚名称`，中括号后边是一个`冒号:`，再后边是`注脚内容`。一般`注脚定义`会被显示在文档的最后，多个`注脚定义`不能写在同一行。

使用注脚时，只需要在`需要注解的文字`后边加上`[^注脚名称]`即可，如下：

```text
这是一个注脚示例[^注脚名称]
```

完整示例：

```text
注脚示例[^note]
注脚示例二[^note2]

[^note]:这是注脚示例内容        
[^note2]:这是注脚示例内容2
```

效果如下：

注脚示例[^note]
注脚示例二[^note2]

[^note]:这是注脚示例内容        
[^note2]:这是注脚示例内容2

---

## 九.思维导图

[Markmap](https://link.zhihu.com/?target=https%3A//markmap.js.org/) 是一个支持 **Markdown** 语法的思维导图工具，通过**Markmap**，你可以使用**Markdown** 语法来生成思维导图。

**Markmap** 开源免费，简单易用。你可以在[这里](https://link.zhihu.com/?target=https%3A//markmap.js.org/repl) 将你写的**Markdown** 文档转换为思维导图。

在**Markmap** 中支持的**Markdown** 符号有：

- 标题符号**#**
- 无须列表符号**-**
- 分隔符**---**
- 超级链接符号**[]()** 和**<>**
- 文字修饰，例如**加粗**，**斜体**，**删除线**
- 代码块，包括**行内代码块**和**多行代码块**

你可以将如下**Markdown** 文档在[这里](https://link.zhihu.com/?target=https%3A//markmap.js.org/repl) 转换为思维导图：

~~~text
# Markmap 支持

## 标题符号

- 一级标题
- 二级标题
- 三级标题

## 无序列表

- 列表1
- 列表2

## 分隔符

- 第一部分
---
- 第二部分
--- 
- 第三部分
- 第四部分

## 超级链接

- <https://www.google.com>
- [Google](https://www.google.com)

## 文字修饰

- *斜体*
- **加粗**
- ~~删除线~~

## 代码块

- `单行代码块`
- 
```shell
多行代码块1
多行代码块2
多行代码块3
```
~~~

[其效果展示在网页Markmap中](https://link.zhihu.com/?target=https%3A//markmap.js.org/repl)

