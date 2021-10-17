[TOC]



##一.Markdown纯文本基本语法

##1.标题{#here}

Markdown 支持两种标题的语法，类 Setext 和类 atx 形式。 类 Setext 形式是用底线的形式，

利用 **= （最高阶标题）**和**- （第二阶标题）**，例如：

This is an H1
======

This is an H2
------
```

效果如下：

This is an H1
======

This is an H2
------

P.S. 	任何数量的 = 和 - 都可以有效果
```
> 这里需要注意一点，由于分割线也是 “----”， 因此在使用分割线时，一定要空一行，不然会把上方的文字识别为第二阶标题。原因会在后面的段落和换行中说到。

效果如下：（三个-）

---

类 Atx 形式则是在行首插入 1 到 6 个 # ，对应到标题 1 到 6 阶，例如：

# this is H1

## this is H2
### this is H3
......
###### this is H6
**效果不再展示，但要注意的是，标准语法一般在 # 后跟个空格再写文字，不然可能会无法识别**

##2.字体

***Markdown 使用星号（）和底线（_）作为标记强调字词的符号***，你可以随便用你喜欢的样式，唯一的限制是，你用什么符号开启标签，就要用什么符号结束。但个人感觉写中文时还是（*）比较好用，因为它不区分全角半角，不用切换输入法。 举个栗子🌰：

```html
**这是加粗**
__这也是加粗__
*这是倾斜*
_这也是倾斜_
***这是加粗倾斜***
~~这是加删除线~~
<u>文字下划线使用HTML u 标签</u>
==高亮==
```

效果如下：

**这是加粗**
__这也是加粗__
*这是倾斜*
_这也是倾斜_
***这是加粗倾斜***

~~这是加删除线~~

<u>文字下划线使用HTML u 标签</u>

==高亮==

---

注意：

1.强调也可以直接插在文字中间，但是如果你的 * 和 _ 两边都有空白的话，它们就只会被当成普通的符号。 

2.如果要在文字前后直接插入普通的星号或底线，你可以用反斜线 \ 。

3.使用 control + B 也可以使字体加粗

---



## 3.分割线

你可以在一行中用三个以上的星号、减号、底线来建立一个分隔线，行内不能有其他东西。你也可以在星号或是减号中间插入空格。下面每种写法都可以建立分隔线：

```
* * *
***
**********
- - -
_________________
```

效果如下：

* * *
***
**********

- - -
_________________



## 4.引用

在引用的文字前加**>**即可。 在 Markdown 文件中建立一个区块引用，那会看起来像是你自己先断好行，然后在每行的最前面加上**>**：

```
> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
> Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
> 
> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
> id sem consectetuer libero luctus adipiscing.
```

效果如下：

> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
> Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
>
> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
> id sem consectetuer libero luctus adipiscing.

***Markdown 也允许你偷懒只在整个段落的第一行最前面加上 > ：***

*例如：*

```
> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
id sem consectetuer libero luctus adipiscing.
```

效果如下：

> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
> Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
> id sem consectetuer libero luctus adipiscing.

***重要：区块引用可以嵌套（例如：引用内的引用），只要根据层次加上不同数量的 >  ， 引用的区块内也可以使用其他的 Markdown 语法，包括标题、列表、代码区块等 ：***

举个栗子🌰：

```
># This is the first level of quoting.
>
> > ## This is nested blockquote.
>
> > > > ### Back to the first level.
```

效果如下：

># This is the first level of quoting.
>
>> ##This is nested blockquote.
>
>> > > ###Back to the first level.



## 5.列表

Markdown 支持有序列表和无序列表。 **无序列表使用星号、加号或是减号作为列表标记**。 示例：

```
- 列表内容
+ 列表内容
* 列表内容

注意：- + * 跟内容之间都要有一个空格
```

效果如下:

- 列表内容
+ 列表内容

* 列表内容

**有序列表则使用数字接着一个英文句点作为标记。 示例：**

```
1. 列表内容
2. 列表内容
3. 列表内容

注意：序号跟内容之间要有空格
```

效果如下：

1. 列表内容
2. 列表内容
3. 列表内容

> ***空格是关键哦***

> ***很重要的一点是，你在列表标记上使用的数字并不会影响输出的 HTML 结果。***

```
你的标记写成：
1.  Bird
1.  McHale
1.  Parish

甚至：

8. Bird
1. McHale
4. Parish

效果都一样。
```

效果如下：

1.  Bird
1.  McHale
1.  Parish

---

8. Bird
1. McHale
4. Parish 

> ***注意第二个排序是 8 · 9 · 10 ，效果都一样，只按第一个数字来排序，因此第一个最好是 1***

> ***列表可以嵌套，上一级和下一级之间敲三个空格即可。***

例如：

```
* 一级无序列表内容

   * 二级无序列表内容
   * 二级无序列表内容
   * 二级无序列表内容
```

效果如下：

* 一级无序列表内容

   * 二级无序列表内容
   * 二级无序列表内容
   * 二级无序列表内容

> ***要让列表看起来更漂亮，你可以把内容用固定的缩进整理好：***

```
*   Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
    Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
    viverra nec, fringilla in, laoreet vitae, risus.
*   Donec sit amet nisl. Aliquam semper ipsum sit amet velit.
    Suspendisse id sem consectetuer libero luctus adipiscing
```

偷懒的写法也可以：

```
*   Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
viverra nec, fringilla in, laoreet vitae, risus.
*   Donec sit amet nisl. Aliquam semper ipsum sit amet velit.
Suspendisse id sem consectetuer libero luctus adipiscing.
```

两种效果都一样，如下：

*   Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
    Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
    viverra nec, fringilla in, laoreet vitae, risus.
*   Donec sit amet nisl. Aliquam semper ipsum sit amet velit.
    Suspendisse id sem consectetuer libero luctus adipiscing

***列表项目可以包含多个段落，每个项目下的段落都必须缩进 4 个空格或是 1 个制表符（对齐更加美观）：***

```
1.  This is a list item with two paragraphs. Lorem ipsum dolor
    sit amet, consectetuer adipiscing elit. Aliquam hendrerit
    mi posuere lectus.

		Vestibulum enim wisi, viverra nec, fringilla in, laoreet
    vitae, risus. Donec sit amet nisl. Aliquam semper ipsum
    sit amet velit.

2.  Suspendisse id sem consectetuer libero luctus adipiscing.
```

效果如下：

1.  This is a list item with two paragraphs. Lorem ipsum dolor
    sit amet, consectetuer adipiscing elit. Aliquam hendrerit
    mi posuere lectus.

		Vestibulum enim wisi, viverra nec, fringilla in, laoreet
    //这里代码框里的是用 两个 tab 造出来的，如果只是单纯的对齐，而不是tab，那么将没有黑框
    
    vitae, risus. Donec sit amet nisl. Aliquam semper ipsum
    sit amet velit.
    
2.  Suspendisse id sem consectetuer libero luctus adipiscing.

***如果你每行都有缩进，看起来会看好很多，当然，再次地，如果你很懒惰，Markdown 也允许：***

```
*   This is a list item with two paragraphs.

    This is the second paragraph in the list item. You're
only required to indent the first line. Lorem ipsum dolor
sit amet, consectetuer adipiscing elit.

*   Another item in the same list.
```

效果如下：

*   This is a list item with two paragraphs.

    This is the second paragraph in the list item. You're
only required to indent the first line. Lorem ipsum dolor
sit amet, consectetuer adipiscing elit.

*   Another item in the same list.

*** 此外：如果要在列表项目内放进引用，那 > 就需要缩进，如果要放代码区块的话，该区块就需要缩进两次，也就是 8 个空格或是 2 个制表符。***

```
1.	> 使用tab缩进
2.		```
```

效果如下：
1.	> 使用tab缩进
2.		```markdown



## 6.表格

示例：

```markdown
表头|表头|表头
---|:--:|---:
1|2|3
4|5|6

表头|表头|表头
---|---|---
1|2|3
4|5|6

**第二行分割表头和内容。**
- 有一个就行，为了对齐，多加了几个
文字默认居左
-两边加：表示文字居中
-右边加：表示文字居右
注：原生的语法两边都要用 | 包起来。此处省略
```

效果如下：

| 表头 | 表头 | 表头 |
| ---- | :--: | ---: |
| 1    |  2   |    3 |
| 4    |  5   |    6 |

| 表头 | 表头 | 表头 |
| ---- | ---- | ---- |
| 1    | 2    | 3    |
| 4    | 5    | 6    |



## 7.代码

在Markdown中加入代码块有两种方式： 

***第一种，只要简单地缩进 4 个空格或是 1 个制表符就可以***，

```
这是一个普通段落：

    这是一个代码区块。

(当然，前面要有一个空行和前面的文字分隔开)
```

效果如下：

这是一个普通段落：

    这是一个代码区块。

***第二种方法似乎是更为常用， 单行代码代码之间分别用一个反引号包起来即可***

```text
这里有一句代码`代码内容`。
```

效果如下：

		这里有一句代码`代码内容`。

***代码块：代码之间分别用三个反引号包起来，且两边的反引号单独占一行***

***在上面的 ``` 后面注明你的代码类型，可以产生相应的代码高亮***

~~~text
```c
	#include<studio.h>
	int main(){
	return 0;
	}
```
\ 是为了防止转译，实际是没有的。
~~~

效果如下：

```c
	#include<studio.h>
	int main(){
	return 0;
	}
```

***代码高亮消除符号***

~~~
	#include<studio.h>
	int main(){
	return 0;
	} //用～～～造出代码框
~~~

---

## 8.段落和换行

一个 Markdown 段落是由一个或多个连续的文本行组成，它的前后要有一个以上的空行（**空行的定义是显示上看起来像是空的，便会被视为空行。比方说，若某一行只包含空格和制表符，则该行也会被视为空行**）。**普通段落不该用空格或制表符来缩进**。 **我们在两个不同的文字块之间，一定要空行以示区分，不然就会被归入同一文字块中。** Markdown 允许段落内的强迫换行（插入换行符）。 **如果想要空一行，在插入处先按入两个以上的空格然后回车**，即可。

但有时也可以使用标记来强制空行和空格，比如需要首行缩进的时候：

**格式：**

```
&ensp;：输入一个空格
&nbsp;：输入一个空格
&emsp;：输入两个空格
```

**注意：**不要忘记分号

示例：

&&emsp;&emsp;&emsp;积土成山，风雨兴焉；积水成渊，...   //&后面有个四个空格

---

## 9.代办列表

`待办列表` 可以表示任务的处理状态，`-[]`表示`待办`状态，`-[X]` 表示`已办`状态：

```text
- [ ] 待办任务1
- [ ] 待办任务2
- [x] 已办任务
```

其效果如下：

- [ ] 待办任务1
- [ ] 待办任务2
- [x] 已办任务

**需要注意的是，有些网站可能不支持`待办列表`**

---

## 10.使用锚点

使用`锚点`，首先是先`定义锚点`，然后再`引用锚点`。

`定义锚点`是在一个`标题` 的后边加上`{#锚点名称}`，如下：

```text
### 这是一个锚点{#here}
```

然后使用如下格式`使用锚点`，`中括号`内是`锚点描述`，`小括号`内是`锚点名称`：

```text
跳转到[锚点](#here)
```

***显示效果以标题一为例***

跳转到[标题一](#here)

---

##11.段落

按换行键[Enter]建立新的一行,***按`Shift`+`Enter`可以创建一个比段落间距更小的行间距***。可在行尾插入打断线，禁止向后插入

```text
打断线<br/>后面的内容将自动换行
```

---

### 常用快捷键

- 加粗： `Ctrl + B`
- 撤销： `Ctrl + Z`
- 字体倾斜 ：`Ctrl+I`
- 下划线：`Ctrl+U`
- 多级标题： `Ctrl + 1~6`
- 有序列表：`Ctrl + Shift + [`
- 无序列表：`Ctrl + Shift + ]`
- 降级快捷键 ：`Tab`
- 升级快捷键：`Shift + Tab`
- 插入链接： `Ctrl + K`
- 插入公式： `Ctrl + Shift + M`
- 行内代码： `Ctrl + Shift + K`
- 插入图片： `Ctrl + Shift + I`
- 返回Typora顶部：`Ctrl+Home`
- 返回Typora底部 ：`Ctrl+End`
- 创建表格 ：`Ctrl+T`
- 选中某句话 ：`Ctrl+L`
- 选中某个单词 ：`Ctrl+D`
- 选中相同格式的文字 ：`Ctrl+E`
- 搜索: `Ctrl+F`
- 搜索并替换 ：`Ctrl+H`
- 删除线 ：`Alt+Shift+5`
- 引用 ：`Ctrl+Shift+Q`
- 生成目录：`[TOC]+Enter`
- 打开源码模式：`control + /`

注：一些实体符号需要在实体符号之前加” \ ”才能够显示
