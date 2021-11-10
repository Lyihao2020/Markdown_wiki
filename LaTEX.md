## <font face = '楷体'>写在之前：</font>

###<font face  = '楷体'>由于学习大学物理，高等数学，模电等一些课程需要写笔记来记录当天所学的知识，所以我先后采用了纸质笔记和电子笔记两种方法，两种记录均有优缺点，但对于我个人来说，电子笔记明显效率更高。但无奈于在电脑上的电子笔记不美观，所以需要写这一篇<font color=#blue> LATEX 语法</font>讲解来巩固自己的基础知识，愿与大家共勉</font>

## <font face = '楷体'>基础篇</font>

### 一、符号

MathJax与LaTeX最大的不同就是支持Unicode字符...废话当年还没UTF呢, 不过能输入和能正常显示还是有点距离的...

简单地说,有些符号比如乘法在LaTeX中必须写成 a \times b但是现在可以直接打 a×b

```latex
运算符号: ＋－×(\times)÷(\div)±(\pm) 负正(\mp) 点乘 \dot
不等号: ≠(\ne或\neq或\not=) 大于>大于等于≥(\ge)小于等于≤(\le)恒等\equiv. 否定加\not.
约等于: 约等于≈ (\approx波浪\dot=等号加点) 近似不能用~,必须用\sim
a\timesb
```

点击编辑器的选项亦可, 但是**能记命令就不用很麻烦的去点了**...
$$
x\pm a \\ 
x\mp a \\	 
x \dot b \\ 
x · b 	\\
x \times b \\
x\dot{B} 	\\
x \ne b	\\
x\not=b \\
x\ge b \\
x\le b \\
x\approx b	\\
a \sim b \\
$$
反斜杠 ![[公式]](https://www.zhihu.com/equation?tex=\text{\\}) 称为命令,括号 ![[公式]](https://www.zhihu.com/equation?tex=\texttt{\{+\}+})被称为界定符, 用作消除歧义.

分数使用\frac{a}{b}, ![[公式]](https://www.zhihu.com/equation?tex=\frac{a}{b}) ,不引起歧义可以省略括号比如\frac12, ![[公式]](https://www.zhihu.com/equation?tex=\frac12) ,不过不推荐这么写.
$$
\frac{A}{B} \\
\frac 1 2
$$

<hr/>

###  <font face = '楷体'>函数</font>

函数在前面加一个 \ 符号即可, 比如\sin(x), ![[公式]](https://www.zhihu.com/equation?tex=\sin(x))

使用^上标如 a^x , ![[公式]](https://www.zhihu.com/equation?tex=a^x) 使用 _ 下标如 \log_a(x), ![[公式]](https://www.zhihu.com/equation?tex=\log_a(x)) .

开根号\sqrt{a}, ![[公式]](https://www.zhihu.com/equation?tex=\sqrt{a}) 开高次根\sqrt[n]{a}, ![[公式]](https://www.zhihu.com/equation?tex=\sqrt[n]{a}) ,其他写法 \root n \of a, ![[公式]](https://www.zhihu.com/equation?tex=\root+n+\of+a) .

绝对值|x|, ![[公式]](https://www.zhihu.com/equation?tex=|x|) 回车上面那个符号.

大括号\{ \},因为大括号现在是界定符,要输入就要用命令,同理反斜杠是\\.

**按照标准**,自然底数需要写成 \mathrm{e}^x, ![[公式]](https://www.zhihu.com/equation?tex=+\mathrm{e}^x) ,但一般偷懒写 e^x即可, ![[公式]](https://www.zhihu.com/equation?tex=+e^x) .

你有函数就加个\试一试能不能正体,不行的话用下面的方法.

比如光学里有个函数叫菲涅尔S函数, 没法自动正体, 那么可以这样写\operatorname{FresnelS} , ![[公式]](https://www.zhihu.com/equation?tex=\operatorname{FresnelS}(v)) ,可以偷懒写成\text{FresnelS}.
$$
\sin(x) \\
\cos(x) \\
\arctan(x) \\
a^x	\\
a_x \\
\sqrt{a}	\\
\sqrt[n]{a}	\\
\root n\of a	\\
\|x\|		\\
|x|			\\
\mathrm{e}^x	\\
\operatorname{FresnelS(v)}	\\
\text{FresnelS(v)}
$$


<hr/>

###<font face='楷体'>微积分</font>

微积分使用比较特殊的符号规则,看上去差不多但是已经重载过了,或者叫宏.

极限	$\textstyle{\lim}_{x\to0}f(x)$,	

求和    $\displaystyle\sum_{n=1}^\infty a_n$

求和重载Sigma $\Sigma_{n=0}^\infty a_n$

虽然\sum和\Sigma一模一样,但是行为完全不同,这就是重载.

求积 prod $\prod_{n=1}^\infty a_n$ $\pi_{n=1}^\infty a_n$

求积一样的\sum改\prod即可 ![[公式]](https://www.zhihu.com/equation?tex=\prod_{n%3D1}^\infty+a_n) ,\prod和\Pi长得一样.

有时候可以看到这种: ![[公式]](https://www.zhihu.com/equation?tex=\textstyle+f(x)+%3D+\textstyle+\sum_{i%3D0}^{n}+\frac{a_i}{1%2Bx})

> 呀,这个作者搞错了吧,他写的\Sigma
>
> $\Sigma_{n=0}^\infty a_n$, 唉,好像不大一样?

不不,他写的没错,还是\sum_{n=1}^\infty a_n,但是style不同.

![[公式]](https://www.zhihu.com/equation?tex=\begin{array}{ll}+\texttt{\displaystyle}+%26+\displaystyle+f(x)+%3D+\sum_{i%3D0}^{n}+\frac{a_i}{1%2Bx}+\\+\texttt{\textstyle}+%26+\textstyle+f(x)+%3D+\sum_{i%3D0}^{n}+\frac{a_i}{1%2Bx}+\\+\texttt{\scriptstyle}+%26+\scriptstyle+f(x)+%3D+\sum_{i%3D0}^{n}+\frac{a_i}{1%2Bx}+\\+\texttt{\scriptscriptstyle}+%26+\scriptscriptstyle+f(x)+%3D+\sum_{i%3D0}^{n}+\frac{a_i}{1%2Bx}+\end{array})

style有四种,大多数网站区分前两种, **除了知乎**所有公式前都加\displaystyle.

求导标准写法**f^\prime(x)**, ![[公式]](https://www.zhihu.com/equation?tex=f^\prime(x)) ,但是我都是偷懒写f'(x)的... 	$f^\prime(x)$

微分标准写法**\frac{\mathrm{d}^n}{\mathrm{d}\,x^n}f(x)**, ![[公式]](https://www.zhihu.com/equation?tex=\frac{\mathrm{d}^n}{\mathrm{d}x^n}f(x)) ,但我偷懒省略\mathrm. $\frac{\mathrm{d}^n}{\mathrm{d}x^n}f_x$

偏微分标准写法,**\frac{\partial^n}{\partial x^n}f(x)**, ![[公式]](https://www.zhihu.com/equation?tex=\frac{\partial+^n}{\partial+x^n}f(x)) ,这个没法偷懒了...

$\frac{\partial^n}{\partial{x}^n}f(x)$

积分标准写法**\int_a^b f(x)\,\mathrm{d}x**, ![[公式]](https://www.zhihu.com/equation?tex=\int_a^b+f(x)\%2C\mathrm{d}x) ,当然偷懒省略\,\mathrm了咯...

$\int_a^b f(x) \mathrm{d}x$

二重积分**\iint f(x,y)\,\mathrm{d}x\,\mathrm{d}y**, ![[公式]](https://www.zhihu.com/equation?tex=\iint+f(x%2Cy)\%2C\mathrm{d}x\%2C\mathrm{d}y) ,偷懒同上...

$\iint f(x,y)\mathrm{d}x\mathrm{d}y$

三重积分,\iiint,四重积分\iiiint,五重积分反正不是\iiiiint,五重以上就用\idotsint, ![[公式]](https://www.zhihu.com/equation?tex=\idotsint) .

曲线曲面积分,**\oint_{C}f(x)\, \mathrm{d}x + g(y)\, \mathrm{d}y**, ![[公式]](https://www.zhihu.com/equation?tex=\oint_{C}f(x)\%2C+\mathrm{d}x+%2B+g(y)\%2C+\mathrm{d}y) ,偷懒同上.

$\oint_c f(x)\mathrm{d}x+g(y)\mathrm{d}y$

交集**\bigcap_{i=1}^\infty p_i**, ![[公式]](https://www.zhihu.com/equation?tex=\bigcap_{i%3D1}^\infty+p_i)  并集**\bigcup_{i=1}^\infty p_i**, ![[公式]](https://www.zhihu.com/equation?tex=\bigcup_{i%3D1}^\infty+p_i) .

$\bigcap_{i=1}^\infty p_i$

$\bigcup_{i=1}^\infty p_i$

------

###<font face = '楷体'>矩阵</font>

```text
\begin{matrix} 
 1&2\\
 3&4\\ 
\end{matrix}
```

![[公式]](https://www.zhihu.com/equation?tex=\begin{matrix}+1%262\\+3%264\\+\end{matrix}) ,要括号的话怎么办呢? 一种方法是使用自适应括号.
$$
\left[\begin{matrix}
 1&2&3&4 \\
 2&3&4&5 \\
 3&4&5&6 \\
\end{matrix}
\right]
$$


```text
\left[\begin{array}{cc|c}
  1&2&3\\
\hline
  4&5&6\\
\end{array}\right]
```

![[公式]](https://www.zhihu.com/equation?tex=\left[\begin{array}{cc|c}+1%262%263\\+\hline+4%265%266\\+\end{array}\right])
$$
\left[\begin{array}{c|c|cc}
		1&2&3&4 \\
		\hline
		2&3&4&5 \\
\end{array}
\right]
$$
array可以用来画表

当然这种常用的肯定封装好了.

![[公式]](https://www.zhihu.com/equation?tex=\begin{array}{lc}+\texttt{smallmatrix}%26\bigl(\begin{smallmatrix}+a+%26+b+\\+c+%26+d+\end{smallmatrix}\bigr)\\+\texttt{matrix}+%26\begin{matrix}+1%262\\3%264\\+\end{matrix}+\\+\texttt{pmatrix}%26\begin{pmatrix}1%262\\3%264\\+\end{pmatrix}\\+\texttt{bmatrix}%26\begin{bmatrix}1%262\\3%264\\+\end{bmatrix}\\+\texttt{Bmatrix}%26\begin{Bmatrix}1%262\\3%264\\+\end{Bmatrix}\\+\texttt{vmatrix}%26\begin{vmatrix}1%262\\3%264\\+\end{vmatrix}\\+\texttt{Vmatrix}%26\begin{Vmatrix}1%262\\3%264\\+\end{Vmatrix}\\+\end{array})
$$
\begin{Vmatrix}
	1&2&3\\
	3&4&5\\
\end{Vmatrix}
$$


向量用\vec,\vec可以作用在一个或两个字母上

```text
\texttt{\vec}&\vec{x}\ \mathrm{or}\ \vec{AB}\\
```

$$
\text{\\vec}\quad\vec{x}\quad \mathrm{or} \quad\vec{AB} \\
$$



```text
\begin{cases}
 a_1x+b_1y+c_1z=\frac{p_1}{q_1} \\[2ex] 
 a_2x+b_2y+c_2z=\frac{p_2}{q_2} \\[2ex] 
 a_3x+b_3y+c_3z=\frac{p_3}{q_3} \\[2ex] 
\end{cases}
```

$$
\begin{cases}
	\quad a_1x+ \quad b_1x + \quad c_1z = \quad\frac{p_1}{q_1} \\[2ex]
	\quad a_2x+ \quad b_2x + \quad c_2z = \quad\frac{p_2}{q_2} \\[2ex]
	\quad a_3x+ \quad b_3x + \quad c_3z = \quad\frac{p_3}{q_3} \\[2ex]
\end{cases}
$$



大括号可以用case, **后面[2ex] 用于调整间距.**

当然用自适应括号也行, \left\{ XXX \right. 注意有个点, 加点表示什么也不显示.

<hr/>

组合符号:\binom{k}{1}, ![[公式]](https://www.zhihu.com/equation?tex=\binom{k}{1}) ,当然你不知道用矩阵打也是可以的...我干过...

$\binom1 2$ 

连分式: 

```text
x = a_0 + \cfrac{1^2}{a_1
        + \cfrac{2^2}{a_2
        + \cfrac{3^2}{a_3 
        + \cfrac{4^4}{a_4 + \cdots}}}}
```

$$
x = a_0 + \cfrac{1^2}{a_1
					+ \cfrac{2^2}{a_2
					+ \cfrac{3^2}{a_3
					+ \cfrac{4^2}{a_4
					+ \dots}
					}}}
$$

我不怎么喜欢这么写, 有点像Lisp, 在没有自动括号补全的情况下少打一个会很开心.

注意这种情况下要写\cfrac,不然会挤在一起

还有很多符号可以\dfrac,\dbinom,\tfrac,\tbinom,分别表示\displaystyle和\textstyle

```text
x = a_0 + \frac{1^2}{a_1+}
          \frac{2^2}{a_2+}
          \frac{3^2}{a_3+} 
          \frac{4^4}{a_4+} \cdots
```

![[公式]](https://www.zhihu.com/equation?tex=x+%3D+a_0+%2B+\frac{1^2}{a_1%2B}+\frac{2^2}{a_2%2B}+\frac{3^2}{a_3+%2B}+\frac{4^4}{a_4+%2B}+\cdots)

应该推广这种写法...还省空间不是...

```text
\underset{j=1}{\overset{\infty}{\LARGE\mathrm K}}\frac{a_j}{b_j}
```

很有趣的一个事情, \sum到底是怎么重载的? 就是这样, 

$\underset{j=1}{\overset{\infty}{\LARGE\mathrm K}}\frac{a_j}{b_j}$

更多测试参考:[知乎公式编辑器测试](https://zhuanlan.zhihu.com/p/31232001)

------

你也许会想,**这么多命令怎么记得住?**

当然记不住, 我又不是最强大脑,但我也不是高中生了, 没人考我记忆力.

忘记说明用不到, 说明不重要, 每天都用的命令是不会忘的.

偶尔遇到现在也不用查手册, 现在不有手写识别嘛

[http://webdemo.myscript.com/views/math.html#](https://link.zhihu.com/?target=http%3A//webdemo.myscript.com/views/math.html%23)

![img](https://pic3.zhimg.com/50/v2-5c7700389266155b68c78bb7a80506e8_720w.jpg?source=1940ef5c)![img](https://pic3.zhimg.com/80/v2-5c7700389266155b68c78bb7a80506e8_1440w.jpg?source=1940ef5c)

哦对了, Mathtype 这种玩意儿少用, 复制出来的代码毫无可读性,严重不符合标准.

何况有个合适的IDE打TeX比Mathtype快多了, 允许你用快捷键还是比你快...

------

## 进阶篇

### <font face='楷体'>占位符</font>

回忆下积分的写法,\int_a^b f(x)\,\mathrm{d}x,其中\,称为占位符,用来调节间隔使公式更美观. 空格必须使用占位符否则不算...当然\text{   空格   } 有效但是这是错误用法...

1. 占位符以一个大写M为标准, 标为\quad
2. \qquad 那就是双空格
3. \, 相当于 3/18个 \quad
4. \: 相当于 4/18个 \quad
5. \; 相当于 5/18个 \quad
6. \  相当于 6/18个 \quad
7. \! 相当于-3/18个 \quad

###<font face='楷体'>字体字号</font>

MathJax支持以下九种字体![[公式]](https://www.zhihu.com/equation?tex=\begin{array}{ll|l}+\texttt{"normal"}+%26\texttt{}+%26+ABCDEFGHIJKLMNOPQRSTUVWXYZ\\+\texttt{"blackboard"}+%26\texttt{\mathbb}+%26\mathbb{ABCDEFGHIJKLMNOPQRSTUVWXYZ}\\+\texttt{"boldface"}+%26\texttt{\mathbf}+%26\mathbf{ABCDEFGHIJKLMNOPQRSTUVWXYZ}\\+\texttt{"typewriter"}+%26\texttt{\mathtt}+%26\mathtt{ABCDEFGHIJKLMNOPQRSTUVWXYZ}\\+\texttt{"roman"}+%26\texttt{\mathrm}+%26\mathrm{ABCDEFGHIJKLMNOPQRSTUVWXYZ}\\+\texttt{"sans-serif"}+%26\texttt{\mathsf}+%26\mathsf{ABCDEFGHIJKLMNOPQRSTUVWXYZ}\\+\texttt{"calligraphic"}%26\texttt{\mathcal}+%26\mathcal{ABCDEFGHIJKLMNOPQRSTUVWXYZ}\\+\texttt{"script"}+%26\texttt{\mathscr}+%26\mathscr{ABCDEFGHIJKLMNOPQRSTUVWXYZ}\\+\texttt{"fraktur"}+%26\texttt{\mathfrak}%26\mathfrak{ABCDEFGHIJKLMNOPQRSTUVWXYZ}\\+\end{array})

正常不填就行, 强制转换的话那就是 ![[公式]](https://www.zhihu.com/equation?tex=\texttt{\mathnormal})

$\mathfrak{ AAAAAA}$

$\mathbf{ABCDEFG}$

这个是AmsLaTeX里的, 其他字体可以试试\unicode

```text
\unicode[Garamond]{x41} \unicode[Arial]{x41} 
```

![[公式]](https://www.zhihu.com/equation?tex=\unicode[Garamond]{x41}+\unicode[Arial]{x41}+) ,$\unicode[Garamond]{x41}$

这不是标准里的, 这个和浏览器有关, 还和知乎开了什么css-family有关...

字号,字号从大到小依次为:

```text
\Huge\huge\LARGE\Large\large\normalsize\small\footnotesize\scriptsize\tiny
```

暂时不可以用\fontsize ![[公式]](https://www.zhihu.com/equation?tex=\fontsize{15pt}{22pt})

###<font face='楷体'>颜色</font>

啊,到了大家最关心的颜色环节了.

其实就是 \color{色调}表达式 ,比如标题就是\color{blue}{颜色}, ![[公式]](https://www.zhihu.com/equation?tex=\color{blue}{颜色})

内置的颜色列表应该是:[知乎「插入公式」诀窍](https://zhuanlan.zhihu.com/p/31188118) 列举的这些

![[公式]](https://www.zhihu.com/equation?tex=\begin{array}{|lc|}+\hline+\verb%2B\color{black}{黑色}%2B+%26+\color{black}{黑色}+\\+\verb%2B\color{gray}{灰色}%2B+%26+\color{gray}{灰色}+\\+\verb%2B\color{silver}{银色}%2B+%26+\color{silver}{银色}+\\+\verb%2B\color{white}{白色}%2B+%26+\color{white}{白色}+\\+\hline+\verb%2B\color{maroon}{栗色}%2B+%26+\color{maroon}{栗色}+\\+\verb%2B\color{red}{红色}%2B+%26+\color{red}{红色}+\\+\verb%2B\color{fuchsia}{桃红}%2B+%26+\color{fuchsia}{桃红}+\\+\verb%2B\color{pink}{粉红}%2B+%26+\color{pink}{粉红}+\\+\verb%2B\color{orange}{橙色}%2B+%26+\color{orange}{橙色}+\\+\verb%2B\color{yellow}{黄色}%2B+%26+\color{yellow}{黄色}+\\+\verb%2B\color{lime}{青柠}%2B+%26+\color{lime}{青柠}+\\+\verb%2B\color{green}{绿色}%2B+%26+\color{green}{绿色}+\\+\verb%2B\color{cyan}{青色}%2B+%26+\color{cyan}{青色}+\\+\verb%2B\color{teal}{靛青}%2B+%26+\color{teal}{靛青}+\\+\verb%2B\color{blue}{蓝色}%2B+%26+\color{blue}{蓝色}+\\+\verb%2B\color{navy}{海蓝}%2B+%26+\color{navy}{海蓝}+\\+\verb%2B\color{purple}{紫色}%2B+%26+\color{purple}{紫色}+\\+\hline+\end{array})

这张表是用MathJax画的哦...

$\color{red}{\oint_{n=1}f(x)\mathrm{d}x}$

支持16位色代码\color{#A00}{\texttt{#A00}}, ![[公式]](https://www.zhihu.com/equation?tex=\color{%23A00}{\texttt{%23A00}})

支持256位色\color{#00A000}{\texttt{#00A000}}, ![[公式]](https://www.zhihu.com/equation?tex=\color{%2300A000}{\texttt{%2300A000}})

不支持带透明通道颜色代码 #0000A000

不支持**标准的实值颜色代码**{\color[rgb]{1, 0, 0} \texttt{red}},知乎你开包开少了吧...

本来的话背景色一般该写成\pagecolor{色调},但是好像也不接受...

好吧,那就**\bbox[颜色]{表达式}**,一样可以,\bbox[pink,2pt]{f(x)}, ![[公式]](https://www.zhihu.com/equation?tex=\bbox[pink%2C2pt]{f(x)})

\bbox还可以用来加框

```text
\bbox[#EFF,5px,border:2px solid red]
{e^x=\lim_{n\to\infty} \left( 1+\frac{x}{n} \right)^n\qquad (1)}\\
```

![[公式]](https://www.zhihu.com/equation?tex=\bbox[%23EFF%2C5px%2Cborder%3A2px+solid+red]+{e^x%3D\lim_{n\to\infty}+\left(+1%2B\frac{x}{n}+\right)^n\qquad+(1)}\\)

- ![[公式]](https://www.zhihu.com/equation?tex=\color{blue}{环境})

知乎把宏取消掉了,那这个没啥好讲了

说个万能对齐环境 align

```text
\begin{align}
f(x) & = (m+n)^2 \\
     & = m^2+2mn+n^2 \\
\end{align}
```

![[公式]](https://www.zhihu.com/equation?tex=\begin{align}+f(x)+%26+%3D+(m%2Bn)^2+\\+%26+%3D+m^2%2B2mn%2Bn^2+\\+\end{align})

你**不知道用什么**对齐那就用align(你知道就用专门的那个)

可以模拟一切对齐case,array,alignat等等的对齐

直接在需要对齐处加&即可

更多环境参考 [Share Latex](https://link.zhihu.com/?target=https%3A//cn.sharelatex.com/learn/Learn_LaTeX_in_30_minutes)

- ![[公式]](https://www.zhihu.com/equation?tex=\color{blue}{宏})

宏说白了就是替换

可是知乎上礼拜把宏取消掉了

宏也是最精彩最难的部分...

有宏的话我甚至能画出图来

宏有多强一门语言就有多强

强到极值这门语言强到了极点

我们统称这样的语言为Lisp

















