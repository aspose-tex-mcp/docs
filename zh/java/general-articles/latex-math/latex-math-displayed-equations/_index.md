---
translation: true
template: /templates/_template-java.md
linktitle: 显示公式
title: 9. 显示公式
weight: 90
url: /java/latex-math-displayed-equations/
keywords: latex、latex 数学公式、latex 数学、latex 数学公式显示、latex 数学方程式显示、latex 数学方程式数组、latex 数学公式显示对齐方式
description: 了解如何使用 LaTeX 提供的命令，以大尺寸或大量公式的方式显示数学公式。
lastmod: "2026-04-21"
---

{{<section overview>}}

到目前为止我们已经讨论了如何处理单个公式；但是显示公式往往涉及一大堆不同的公式，或一个巨大的公式的不同部分，如何让它们相互对齐常常是个挑战。幸运的是，大型显示通常可以归纳为几种简单的模式。

### 9.1. 单行显示

显示公式经常包含普通文本。我们已经[讨论](/tex/{{lang.url-fragment}}java/latex-math-fine-points/#82-non-italic-letters)了如何在不离开数学模式的情况下在公式中使用罗马体，但将文本放入显示中的最佳方式是把它放进 `\hbox`。实际上甚至不需要任何数学。要排版

![没有任何数学的显示文本](/tex/images/java/tutorial/latex-math-9-1.png)

可以写 `$\hbox{Displayed text}$`。下面是一个更有意思的例子：

![数学显示中的文本](/tex/images/java/tutorial/latex-math-9-2.png)

在这种情况下，公式和文本的组合方式如下：

```tex
$\X_n=X_k \qquad\hbox{if and only if}\qquad
     Y_n=Y_k \quad\hbox{and}\quad Z_n=Z_k.$
```

如你所见，`\qquad` 出现在 “if and only if” 两侧，而单个 `\quad` 包围 “and”；这强调了 *Y* 与 *Z* 部分相对于 *X* 部分更紧密地关联在一起。

再来看下面的显示：

![数学显示中的文本](/tex/images/java/tutorial/latex-math-9-3.png)

一种写法是

```tex
$Y_n=X_n\bmod p \quad\hbox{and}\quad z_n=X_n\bmod q
    \qquad\hbox{for all }n\ge0.$
```

但更好的写法是（见第二行）

```tex
$Y_n=X_n\bmod p \quad\hbox{and}\quad z_n=X_n\bmod q
    \qquad\hbox{for all $n\ge0$.}$
```

是的，这里是数学模式嵌套在水平模式中，再嵌套在显示数学模式中，但这种写法比第一种更自然。

现在来谈谈公式编号——出现在显示公式侧边的小标签。如果你键入

```tex
$<formula>\eqno<formula>$
```

TeX 会显示第一个公式，并在右侧边距放置一个公式编号（第二个公式）。例如，

```tex
$x^2-y^2 = (x+y)(x-y).\eqno(15)$
```

会产生

![右侧的公式编号](/tex/images/java/tutorial/latex-math-9-4.png)

你也可以使用 `\leqno` 在左侧边距得到公式编号。例如，

```tex
$x^2-y^2 = (x+y)(x-y).\leqno(15)$
```

会产生

![左侧的公式编号](/tex/images/java/tutorial/latex-math-9-5.png)

请注意，无论编号出现在左侧还是右侧，都必须把编号放在第二个位置。

显示公式始终居中显示，无论是否有公式编号。但是当公式很大时，TeX 会确保编号不与公式本身冲突；公式编号甚至可能单独占一行。

LaTeX 还提供了 `equation` 环境来自动给公式编号。例如，键入

```tex
\begin{equation}
  f(x)=(x+a)(x+b)
\end{equation}
```

会得到

![equation 环境的使用](/tex/images/java/tutorial/latex-math-9-6.png)

也可以使用 `\label` 和 `\ref` 给公式加标签并引用。例如，

```tex
\begin{equation} \label{eq:someequation}
  f(x)=(x+a)(x+b)
\end{equation}
这引用方程 \ref{eq:someequation}。
```

会产生

![带标签和引用的 equation 环境](/tex/images/java/tutorial/latex-math-9-7.png)

### 9.2. 多行显示

有时一个显示公式不适合单行模式（即使带或不带公式编号）。LaTeX 为其余的大多数情况提供了专门的命令。

多行显示通常包括几条必须在等号（`=`）处对齐的公式，例如

![使用 array 环境排版的多行公式](/tex/images/java/tutorial/latex-math-9-8.png)

推荐的做法是使用 LaTeX 提供的 `array` 环境：

```tex
$\begin{array}{rl}
  X_1+\cdots+\X_p&=m,\\
  Y_1+\cdots+\Y_q&=n.}
\end{array}$
```

该环境帮助你将公式表示为一个多列（这里是两列）的矩形数组。每一行包含一个单独的公式，行之间使用 `\\`（换行）分隔。每个公式的左、右两侧分别用 `&` 符号分开。最后一行不必以 `\\` 结束。环境还有一个参数用于指定每列的对齐方式。在本例中，`rl` 表示左侧部分右对齐，右侧部分左对齐。

LaTeX 还提供了 `eqnarray*` 环境，工作方式类似，但如果要让等式两侧正确对齐，需要两个对齐点，而且不幸的是间距会偏离数学排版的常规。下面的代码

```tex
\begin{eqnarray*}
  X_1+\cdots+X_p&=&m,\\
  Y_1+\cdots+Y_q&=&n.
\end{eqnarray*}
```

产生如下输出：

![使用 eqnarray* 环境排版的多行公式](/tex/images/java/tutorial/latex-math-9-9.png)

LaTeX 的 `eqnarray` 环境会产生相同的效果，只是会自动给每个公式加编号。

在 `array` 环境中可以放任意数量的公式；一般模式如下：

```tex
\begin{array}{rl}
  <left-hand side_1>&<right-hand side_1>\\
  <left-hand side_2>&<right-hand side_2>\\
  …
  <left-hand side_n>&<right-hand side_n>
\end{array}
```

其中每个 `<right-hand side>` 之前的符号即为对齐点。

`array` 环境的结果是一个垂直居中的盒子，这使得下面的排版变得很容易：

![在同一显示中呈现的两组公式](/tex/images/java/tutorial/latex-math-9-10.png)

只需在同一行使用两次 `array` 环境：

```tex
$\left\{
  \begin{array}{rl}
    \alpha&=f(z)\\ \beta&=f(z^2)\\ \gamma&=f(z^3)
  \end{array}
\right\}\qquad\left\{
  \begin{array}{rl}
    x&=\alpha^2-\beta\\ y&=2\gamma
  \end{array}
\right\}.$
```

更复杂的情况是你有若干对齐的公式并且每条公式都有编号，或者部分行有编号、部分行没有编号：

![右侧带标签的任意编号公式数组](/tex/images/java/tutorial/latex-math-9-11.png)

遗憾的是，即使使用 `eqnarray*`（尽管间距不理想），也无法在多行显示中手动指定公式编号。只能依赖 `amsmath` 包来实现。因此，推荐的做法是：

```tex
%% Preamble
\usepackage{amsmath}
%% Body
\begin{align}
  (x+y)(x-y)&=x^2-xy+xy-y^2 \notag \\
            &=x^2-y^2; \tag4\\
  (x+y)^2   &=x^2+2xy+y^2. \tag5
\end{align}
```

如果在 `align` 环境的某一行既不写 `\tag` 也不写 `\notag`，该行的公式编号会自动使用内部计数器的当前值。

如果在加载 `amsmath` 包时使用 `leqno` 选项，公式编号会出现在左侧边距。例如：

```tex
%% Preamble
\usepackage[leqno]{amsmath}
%% Body
\begin{align}
  (x+y)(x-y)&=x^2-xy+xy-y^2 \notag \\
            &=x^2-y^2; \tag4\\
  (x+y)^2   &=x^2+2xy+y^2. \tag5
\end{align}
```

会产生

![左侧带标签的任意编号公式数组](/tex/images/java/tutorial/latex-math-9-12.png)

要了解使用 `amsmath` 包的更多排版技巧，请参阅这些[文章](/tex/{{lang.url-fragment}}java/what-is-ams-latex/)。

### 9.3. 长公式

现在来讨论当公式太长以至于放不下一行时该怎么办。例如，下面的公式

![导致行溢出的缩小长公式](/tex/images/java/tutorial/latex-math-9-13.png)

必须拆分。TeX 已经把 `+`、`-` 两侧的空格压到几乎为零，但仍然出现了行溢出。

我们尝试在 `+7` 之前拆分该公式。使用 `array` 环境会在等号右侧留下过多空间：

```tex
$\begin{array}{rl}
  \sigma(2^{34}-1,2^{35},1)&=-3+(2^{34}-1)/2^{35}+2^{35}\!/(2^{34}-1) \\
                   &\qquad{}+7/2^{35}(2^{34}-1)-\sigma(2^{35},2^{34}-1,1)
\end{array}$
```

因此最好再次使用 `amsmath` 包。这一次使用 `align*` 环境（因为不需要公式编号）：

```tex
%% Preamble
\usepackage{amsmath}
%% Body
\begin{align*}
  \sigma(2^{34}-1,2^{35},1)&=-3+(2^{34}-1)/2^{35}+2^{35}\!/(2^{34}-1) \\
                   &\qquad+7/2^{35}(2^{34}-1)-\sigma(2^{35},2^{34}-1,1).
\end{align*}$
```

得到

![使用 align* 环境拆分的长公式](/tex/images/java/tutorial/latex-math-9-14.png)

思路是把一个长的单行公式当成两行公式来处理，第二行使用 `\qquad` 使其相对于第一行的等号向右适当偏移。

实际上，要决定如何把长的显示公式换行并不容易；TeX 并不会尝试自动换行，因为没有一套规则能够覆盖所有情况。手稿的作者往往是最好的判断者，因为换行位置取决于数学阐述的细微因素。例如，常常需要强调公式中隐藏的对称性或结构，而这需要对公式的内部含义有深入的理解。

尽管如此，仍然可以给出一些经验法则：

a) 虽然段落中的公式总是在二元运算符或关系符 **之后** 换行，显示公式则总是在二元运算符或关系符 **之前** 换行。这就是为什么我们在前面的例子中没有把第一行写成 `(2^{34}-1)+`，而是写成 `(2^{34}-1`，第二行以 `+` 开头。

b) 当在二元运算符处换行时，第二行应当至少向右移动两个 quad，使其相对于第一行中包含该二元运算符的最内层子公式向右偏移。例如，要在下面的公式中把 `<formula_1>` 与 `<formula_2>` 之间的加号处换行：

```tex
$\sum_{0<k<n}\left(<formula_1>+<formula_2>\right)$
```

几乎必须让第二行的加号位于对应的左大括号（`\left(`）的右侧。

在前面的例子中，需要特别注意把 `\left` 和 `\right` 成对使用：不能在一行只出现 `\left`，另一行只出现 `\right`。此外，两行的分隔符大小应保持一致，通常需要手动指定分隔符的尺寸，例如：

```tex
%% Preamble
\usepackage{amsmath}
%% Body
\begin{align*}
  \sum_{0<k<n}\biggl(&<formula_1>\\
    &\qquad+<formula_2>\biggr)
\end{align*}
```

这里的 `&` 标记并不是出现在等号上，而是标记对齐点。

另一种拆分长公式的方式叫做 **双行形式**（two-line form）。思路是把公式的前半部分几乎左对齐，后半部分几乎右对齐，“几乎左/右对齐”指的是相距一个 quad。例如，前面讨论的长 sigma 公式的双行形式如下所示：

![公式的双行形式](/tex/images/java/tutorial/latex-math-9-15.png)

实现方法如下：

```tex
$\displaylines{\quad\sigma(2^{34}-1,2^{35},1)
  =-3+(2^{34}-1)/2^{35}+2^{35}\!/(2^{34}-1)\hfill{}\cr
\hfill{}+7/2^{35}(2^{34}-1)-\sigma(2^{35},2^{34}-1,1).\quad\cr}$
```

在第二行的开头额外加入 `{}`，以让 TeX 将 `+` 识别为二元运算符。双行形式特别适用于左侧很长的等式，此时换行通常就在等号前面进行。
