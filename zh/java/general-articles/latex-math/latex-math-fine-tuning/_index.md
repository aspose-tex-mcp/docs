---
translation: true
template: /templates/_template-java.md
linktitle: 数学公式微调
title: 8. 数学公式微调
weight: 80
url: /java/latex-math-fine-points/
keywords: LaTeX、LaTeX 数学公式、LaTeX 数学、LaTeX 数学微调、LaTeX 数学标点符号、LaTeX 数学运算符、LaTeX 数学字体样式、LaTeX 数学间距、LaTeX 数学换行、LaTeX 数学矩阵
description: 学习数学输入的精细技巧，并通过涉及数学公式中各种对象的示例进行讲解。
lastmod: "2026-02-24"
---

{{<section overview>}}

我们已经讨论了构造数学公式所需的大部分工具。但仍有一些细节可以帮助你排版出真正漂亮的公式，这些公式能够提升你所编写的书籍和论文的整体外观与可读性。

### 8.1. 标点

一般规则是：当公式后面紧跟句号、逗号、分号、冒号、问号、感叹号等标点时，**在行内公式**应把标点放在公式后面；**在行间公式**则应把标点放在 `$` 前面。例如，

```tex
If $x<0$, we have shown that $y=f(x).$
```

因此，你不应该写成下面的形式

```tex
for $x = a, b$, or $c$.
```

正确的写法应是

```tex
for $x = a$, $b$, $c$.
```

在第一种情况中，TeX 会把 `$x = a, b$` 视为一个整体公式，从而在逗号和 `b` 之间插入一个细空格。这个空格与逗号后面 `c` 之间的空格不同，因为单词之间的空格总是比细空格要大。这样看的效果很差，而在第二种写法中，空格看起来更合适。

同样重要的是，TeX 永远不会在逗号后面的空格处换行，因为在公式中逗号后换行通常是不正确的，例如在等式 `$x = f(x, a)$` 中。于是，段落换行的可能性被抑制，导致排版文档的外观更差。换句话说，如果标点符号在语言上属于句子而不是公式本身，则应把它放在 `$` 之外。

### 8.2. 非斜体字母

诸如 `log` 之类的常用数学函数总是以罗马体（Roman）显示。将此类对象放入公式的最佳方式是使用下面的命令：

![Math function and named operator commands](/tex/images/java/tutorial/latex-math-8-1.png)

以下示例演示了部分命令的用法：

![Using math function and named operator commands](/tex/images/java/tutorial/latex-math-8-2.png)

后面的两个展示公式表明，某些命令会被 TeX 当作带上下限的大运算符（如求和符号）处理。而 `\max` 的下标不会像 `\log` 那样被视为普通下标。当在显示样式中把下标或上标附着在 `\det`、`\gcd`、`\inf`、`\lim`、`\liminf`、`\limsup`、`\max`、`\min`、`\Pr`、`\sup` 上时，它们会自动变成上下限形式。

如果需要对常用但未列出的函数或运算符使用罗马体，你可以轻松地自行定义命令。假设你想定义一个带上下限的运算符 `\oper`，可以在导言区加入如下定义：

```tex
\def\oper{\mathop{\rm oper}}
```

![Using a custom operator commands](/tex/images/java/tutorial/latex-math-8-3.png)

如果你的运算符不需要上下限，则可以使用下面的定义：

```tex
\def\oper{\mathop{\rm oper}\nolimits}
```

若仅需一次性使用罗马体，直接切换到 `\rm` 更简便：

![Switching to Roman type with \rm command](/tex/images/java/tutorial/latex-math-8-4.png)

请注意最后一种情况中使用了 `\ `（反斜杠空格）。如果没有它们，普通的空格会被忽略，`lower order terms` 会被排成 “lowerorderterms”。

单词 `mod` 同样通常以罗马体显示，但它有两种不同的用法。`\bmod` 用于二元运算 “mod”，而 `\pmod` 用于出现在括号内、位于公式末尾的 “mod”。  

![Using \pmod and \bmod](/tex/images/java/tutorial/latex-math-8-5.png)

`\pmod` 会自行插入括号；括号中的内容除非是单个符号，否则应使用大括号括起来。

你也可以通过 `\rm` 获得其他字体样式。例如，`\bf` 用于加粗：

![Switching to boldface with \bf](/tex/images/java/tutorial/latex-math-8-6.png)

可以看到 `+` 与 `=` 仍保持罗马体。`\rm`、`\bf` 等命令只影响大写字母 `A`‑`Z`、小写字母 `a`‑`z`、数字 `0`‑`9`、大写希腊字母 `\Gamma`‑`\Omega`，以及诸如 `\hat`、`\tilde` 的数学重音。此例中没有使用大括号，因为这些命令本身已经限定了作用范围。

`\cal` 也可以在公式中使用，以获得大写字母的“书法体”：

![Switching to the calligrafic style with \cal](/tex/images/java/tutorial/latex-math-8-7.png)

> 这只对字母 `A`‑`Z` 有效；对小写或希腊字母使用 `\cal` 会得到奇怪的结果。

还有 `\mit`，代表 “数学斜体”。它会影响大写希腊字母：

![Italic Greek capitals](/tex/images/java/tutorial/latex-math-8-8.png)

当 `\mit` 生效时，普通字母 `A`‑`Z`、`a`‑`z` 仍保持斜体，因为它们本来就来自数学斜体字体。相反，大写希腊字母和数学重音不受 `\rm` 影响，因为它们本来就来自罗马体。

使用 LaTeX 时，你也可以输入 `\it` 或 `\tt` 来在公式中得到文本斜体或打字机体。你可能会好奇为何同时提供 `\mit` 与 `\it`。答案是：`\mit` 是 “数学斜体”（通常更适合公式），`\it` 是 “文本斜体”（通常更适合正文）。

![Math italic and text italic](/tex/images/java/tutorial/latex-math-8-9.png)

数学斜体字母更宽，间距也不同。这在大多数公式中效果更好，但在需要在数学模式下输入像 *different* 这样的斜体单词时会出现问题。宽斜体 `*f*` 在公式中通常是期望的，但在正文中则不合适。因此，若公式中需要出现真正的斜体单词，最好使用 `\it`。这通常不是传统数学的情形，而是在排版计算机程序时的常见需求：

![Text italic in typesetting programs](/tex/images/java/tutorial/latex-math-8-10.png)

第二个示例展示了使用短下划线来分割标识符名称的效果。

### 8.3. 公式之间的间距

当一个显示块中包含多个公式时常会出现这种情况；例如，一个等式后可能跟随一个侧条件：

![A equation accompanied by a side condition](/tex/images/java/tutorial/latex-math-8-11.png)

这时需要告诉 TeX 在逗号后应留多少空格，否则常规写法会把东西挤在一起。可以这样写：

```tex
$F_{n}=F_{n-1}+F_{n-2},\qquad n\ge2$.
```

`\qquad` 表示 “双四分宽”（double quad），其中 “quad” 是印刷行业约定的一段空白。`\quad` 相当于水平方向上的一个四分宽。若希望的间距不同于常规，需要显式使用 `\quad`、`\qquad` 等命令。

传统的 quad 是一个正方形的空白字符，宽高各 1 em——大约相当于大写字母 M 的大小；而 LaTeX 中的 quad 本身没有高度。

在段落文字中，公式最好用词语而不是仅仅用逗号分隔。如果实在没有文字可插入，至少应在公式之间留出一定空白。例如比较：

```tex
The Fibonacci numbers satisfy $F_{n}=F_{n-1}+F_{n-2}$, $n\ge2$.
```

和

```tex
The Fibonacci numbers satisfy $F_{n}=F_{n-1}+F_{n-2}$, \ $n\ge2$.
```

两者的排版效果如图所示：

![Setting the right spacing between formulas](/tex/images/java/tutorial/latex-math-8-12.png)

这里的 `\ ` 提供了一个可视的分隔，部分弥补了不佳的排版风格。

### 8.4. 公式内部的间距

我们已经看到 TeX 会自动为数学公式加上合适的间距，使其在大多数情况下看起来不错。但由于可能的公式组合极其庞大，且 TeX 的间距规则相对简单，实际使用中仍会出现例外。因此，需要能够在必要时使用细粒度的间距控制，而不是仅依赖 `\ `、`\quad`、`\qquad` 这类“大块”间距。

TeX 在公式中使用的基本间距单位有 *细空格*（thin space）、*中空格*（medium space）和 *粗空格*（thick space）。这些间距会自动插入，但你也可以随时使用下面的命令自行添加：

![Basic elements of space](/tex/images/java/tutorial/latex-math-8-13.png)

涉及微积分的公式在 `dx`、`dy`、`d` 等前面加入一个额外的细空格效果最佳；然而 TeX 并不会自动完成此操作。以下示例演示了如何告知 TeX 这些需求：

![The examples of proper spacing within formulas involving calculus](/tex/images/java/tutorial/latex-math-8-14.png)

请注意，在倒数第二个公式的斜杠 `/` 后并不需要 `\,`；在最后一个示例中也不需要 `\,`，因为 *dt* 单独出现在分式的分子中，这样可以在视觉上将其与其余部分分离。

当物理单位出现在公式中时，应使用罗马体并在前面的内容后加一个细空格：

![The examples of proper spacing within formulas with physical units](/tex/images/java/tutorial/latex-math-8-15.png)

在感叹号（阶乘符号）后面，如果下一个字符是字母、数字或左分界符，也应插入细空格：

![The examples of proper spacing within formulas with factorial operation](/tex/images/java/tutorial/latex-math-8-16.png)

除此之外，你偶尔会遇到符号过于密集或空白过多的情况，这往往是由某些不幸的形状组合导致的。恰当地使用 `\,` 或 `\!` 可以适度拉开或拉紧间距，使读者不会因排版问题而分心。根号和多重积分常常需要这种微调。下面给出一些典型情形的示例：

![The examples of proper spacing in cases of certain shape combinations](/tex/images/java/tutorial/latex-math-8-17.png)

当公式中出现竖线 `|` 或 `\|` 时，TeX 有时会把它们当作普通符号而非分界符，导致间距不正确。考虑下面的公式：

![The examples of proper spacing in formulas with vertical bars](/tex/images/java/tutorial/latex-math-8-18.png)

在第一个例子中，间距错误是因为 TeX 误以为加号在计算 `|` 与 `*x*` 的和。第二个例子使用了 `\left` 与 `\right`，使 TeX 正确识别分界符。第三个例子表明，对其他分界符不需要额外修正，因为 TeX 能自行判断它们是左界还是右界。

### 8.5. 省略号

省略号可以用两种不同高度的点来表示。传统上会区分这两种情况。一般情况下，下面的写法是正确的：

![Properly set ellipses](/tex/images/java/tutorial/latex-math-8-19.png)

而下面的写法则不正确：

![Improperly set ellipses](/tex/images/java/tutorial/latex-math-8-20.png)

原则是：想要三个低位点时使用 `\ldots`，想要三个竖直居中的点时使用 `\cdots`。通常在 `+`、`-`、乘号之间，以及 `=`、“≤”、子集符号或其他类似关系之间使用 `\cdots`；在逗号之间以及完全没有符号相邻时使用低位点：

![Uses of ellipses](/tex/images/java/tutorial/latex-math-8-21.png)

但有一种特殊情况：当 `\ldots` 或 `\cdots` 出现在公式结尾或紧邻右分界符时，默认的间距不合适，这时需要再加一个细空格。例如：

![Setting proper spaces after ellipses at the end of a formula](/tex/images/java/tutorial/latex-math-8-22.png)

第一句可以这样输入：

```tex
Prove that $(1-x)^{-1}=1+x+x^2+\cdots\,$.
```

如果没有 `\,`，句号会紧贴在 `\cdots` 后面。

第二句的写法如下：

```tex
Clearly $a_i<b_i$ for $i=1$,~2, $\ldots\,$,~$n$.
```

请注意这里使用了连字符（`~`），它可以防止不良的换行。此类省略号在某些数学写作中非常常见，LaTeX 因此提供了 `\dots` 宏，等价于 `$\ldots\,$`，用于统一的省略号排版。

### 8.6. 自动换行

当段落中出现公式时，TeX 可能需要在行间进行换行。它仅会在关系符号或二元运算符后进行换行，且该符号必须处于公式的最外层（即未被 `{...}` 包裹）。例如：

```tex
$f(x,y) = x^2-y^2 = (x+y)(x-y)$
```

如果这段代码位于普通文字中，TeX 可能会在等号后换行（优先）或在减号、加号等处换行（紧急情况下）。但它绝不会在逗号处换行，因为逗号后不应出现换行。

如果你不希望在此示例中除等号之外的任何位置换行，可以这样写：

```tex
$f(x,y) = {x^2-y^2} = {(x+y)(x-y)}$
```

额外的大括号会“冻结”子公式，使其成为不可拆分的盒子。除非 TeX 真正把公式断得很糟，否则通常不必担心这类情况。

若希望在公式的外层某处允许换行，可以使用 `\allowbreak`。例如，当下面的公式出现在段落文字中时：

```tex
$(x_1,\ldots,x_m,\allowbreak y_1,\ldots,y_n)$
```

TeX 将允许它在 `\allowbreak` 处断开：

![A formula broken at the \allowbreak](/tex/images/java/tutorial/latex-math-8-23.png)

### 8.7. 大括号

符号 `{` 与 `}` 在多种记号中都有使用，LaTeX 提供了一些命令帮助你处理涉及大括号的公式。

最常见的情形是用大括号表示一个集合。例如，`{a, b, c}` 表示包含元素 *a*、*b*、*c* 的集合：

![A set of three elements](/tex/images/java/tutorial/latex-math-8-24.png)

集合也可以使用“元素 | 条件” 或 “元素 : 条件” 的形式。例如，所有大于 5 的对象 *x* 可以写成：

![Another notation for sets](/tex/images/java/tutorial/latex-math-8-25.png)

这两种写法等价；前者需要使用 `\mid` 来得到竖线，而后者只需冒号，冒号会被视为二元运算符。

当分界符需要放大时，使用 `\bigl`、`\bigm` 与 `\bigr`：

![Using larger delimiters in indication of a set](/tex/images/java/tutorial/latex-math-8-26.png)

更大的分界符可以使用 `\Big`、`\bigg` 或 `\Bigg`。

在展示公式中，大括号还可以表示多种情况的选择。例如下面左侧的大括号表示若干分支：

![\cases construction](/tex/images/java/tutorial/latex-math-8-27.png)

可以使用 `\case`（实际为 `\cases`）来实现：

```tex
$|x|=\case{x,&if $x\ge0$;\cr
            -x,&otherwise.\cr}$
```

每个分支由 `&` 分隔，`&` 在构建表格结构时扮演特殊角色。`&` 左侧是隐式包在 `$...$` 中的数学公式，右侧是普通文本。因此第二行的 `-x` 以数学模式排版，而 `otherwise` 则以水平模式排版。`&` 前后的空格会被忽略。分支数量可以任意，通常只有两个。每个分支结束后必须使用 `\cr`。

如果需要在展示公式的上方或下方加上水平的大括号，可使用 `\overbrace` 或 `\underbrace`。这些命令被视为大运算符（如 `\sum`），因此可以像对待上下限一样添加上、下标：

![\overbrace and \underbrace](/tex/images/java/tutorial/latex-math-8-28.png)

### 8.8. 矩阵

矩阵是数学公式中常见的对象，它们实际上是按行列排列的公式矩阵。LaTeX 提供了 `\matrix` 命令来处理最常用的矩阵类型。

例如，要排版下面的矩阵：

![An example of a matrix](/tex/images/java/tutorial/latex-math-8-29.png)

只需键入：

```tex
$A=\left(\matrix{x-\lambda&1&0\cr
                  0&x-\lambda&1\cr
                  0&0&x-\lambda\cr}\right).$
```

这与前面的 `\cases` 构造非常相似：每行以 `\cr` 结束，列之间用 `&` 分隔。不过，与 `\cases` 不同，矩阵需要自行在外部加上 `\left` 与 `\right` 分界符。由于圆括号最常使用，你也可以使用 `\pmatrix` 让 LaTeX 自动加上圆括号：

```tex
$\pmatrix{x-\lambda&...&x-\lambda\cr}.$
```

矩阵的每个条目默认在其列内居中显示，列宽会根据内容自动扩展，列间有一个 quad 的间距。若希望某个条目左/右对齐，可在其前后加入 `\hfill`。

矩阵中的每个条目都是独立排版的，采用文本样式的数学公式。例如，在某一条目中使用 `\rm` 不会影响其他条目。写成 `{\\rm x&y}` 是非法的。

矩阵常用省略号表示省略的行或列。除了 `\ldots`，LaTeX 还提供了垂直省略号 `\vdots` 与对角省略号 `\ddots`。例如下面的矩阵：

![A matrix as a general pattern with ellipses](/tex/images/java/tutorial/latex-math-8-30.png)

对应的代码是：

```tex
$A=\pmatrix{a_{11}&a_{12}&\ldots&a_{1n}\cr
             a_{21}&a_{22}&\ldots&a_{2n}\cr
             \vdots&\vdots&\ddots&\vdots\cr
             a_{m1}&a_{m2}&\ldots&a_{mn}\cr}$
```

有时矩阵的顶部和左侧会附加标签，以标示行和列。这时可以使用 LaTeX 中的专用宏 `\bordermatrix`。例如下面的展示：

![A bordered matrix](/tex/images/java/tutorial/latex-math-8-31.png)

对应代码如下：

```tex
$M=\bordermatrix{&C&I&C'\cr
                C&1&0&0\cr
                I&b&1-b&0\cr
                C'&0&a&1-a\cr}$
```

第一行给出上方标签，位于左、右大括号的上方；第一列给出左侧标签，左对齐紧贴矩阵本体。第一行第一列交叉处通常为空白。和 `\pmatrix` 一样，`\bordermatrix` 也会自行加上圆括号。

把矩阵直接放入段落文字中通常并不推荐，因为矩阵往往太大，适合单独显示。不过若真的需要在行内使用小矩阵，可以使用 `\choose` 或 `\atop`：

![Examples of setting small matrices for use in text](/tex/images/java/tutorial/latex-math-8-32.png)

需要注意的是，`\matrix` 宏本身并不会生成像上面那样的“小矩阵”。
