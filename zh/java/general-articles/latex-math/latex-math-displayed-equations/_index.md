---
translation: true
template: /templates/_template-java.md
linktitle:  显示的方程式
title: 9. 显示的方程式|乳胶手册
weight: 90
url: /java/latex-math-displayed-equations/
keywords: 乳胶，乳胶数学公式，乳胶数学，乳胶数学显示公式，乳胶数学显示方程，乳胶数学方程式阵列，乳胶数学显示对齐
description: 了解使用乳胶提供的命令来显示大尺寸或大量公式的数学公式的方法。
lastmod: "2025-06-10"
---

{{<section overview>}}

到现在为止，我们已经讨论了如何处理单个公式。但是显示器通常涉及一堆不同的公式或巨大公式的不同部分，将它们放置以使它们彼此正确排列可能是一个挑战。幸运的是，大显示通常属于一些简单的模式。

### 9.1. 单行显示

显示的方程式通常包含普通文本。我们已经[讨论](/tex/{{lang.url-fragment}}java/latex-math-fine-points/#82-non-italic-letters)如何在不离开数学模式的情况下将罗马类型进入公式，但是将文本放入显示屏中的最佳方法是将其放入“ \ hbox”中。实际上，甚至根本不需要任何数学。键入设置

![完全没有数学显示文字](/tex/images/java/tutorial/latex-math-9-1.png)

您可以说`$$ \ hbox {显示的文本} $$`。但这是一个更有趣的例子：

![数学显示中的文字](/tex/images/java/tutorial/latex-math-9-2.png)

在这种情况下，公式和文本的组合如下：


```tex
$$\X_n=X_k \qquad\hbox{if and only if}\qquad
     Y_n=Y_k \quad\hbox{and}\quad Z_n=Z_k.$$
```

如您所见，`\ qquad`出现在“ if and If”周围，但单个\ quad“围绕”和“”；这对显示器的 *y*和 * z *部分与彼此的相关性更紧密地相关的事实表达了一个重点。 

让我们看以下显示：

![数学显示中的文字](/tex/images/java/tutorial/latex-math-9-3.png)

可以指定的一种方法是


```tex
$$Y_n=X_n\bmod p \quad\hbox{and}\quad z_n=X_n\bmod q
    \qquad\hbox{for all }n\ge0.$$
```

但是更好的方法是(请参阅第二行)


```tex
$$Y_n=X_n\bmod p \quad\hbox{and}\quad z_n=X_n\bmod q
    \qquad\hbox{for all $n\ge0$.}$$
```

是的，这是显示数学模式内水平模式内的数学模式，但是该解决方案看起来比第一个解决方案更自然。

现在，让我们转到方程式，那些出现在显示屏侧面的小标签。如果您输入


```tex
$$<formula>\eqno<formula>$$
```

TEX将显示第一个公式，它还将在右侧边距放置一个方程号(第二公式)。例如，


```tex
$$x^2-y^2 = (x+y)(x-y).\eqno(15)$$
```

会产生

![右边的方程编号](/tex/images/java/tutorial/latex-math-9-4.png)

您还可以使用`\ leqno`在左侧边缘获取方程编号。例如，

```tex
$$x^2-y^2 = (x+y)(x-y).\leqno(15)$$
```

会产生

![左边的方程式](/tex/images/java/tutorial/latex-math-9-5.png)

请注意，即使要出现在左侧，您始终将方程式编号第二。

不管方程数的存在如何，显示的方程式都集中。但是，当公式很大时，Tex确保它不会干扰其数字。方程式甚至可以单独放在线上。

乳胶还提供了方程环境​​，可以自动编号您的方程式。例如，打字

```tex
\begin{equation}
  f(x)=(x+a)(x+b)
\end{equation}
```

结果

![方程环境的使用](/tex/images/java/tutorial/latex-math-9-6.png)

也可以使用`\label`和 `\ref`标记和参考方程。例如，

```tex
\begin{equation} \label{eq:someequation}
  f(x)=(x+a)(x+b)
\end{equation}
this references equation \ref{eq:someequation}.
```

结果

![使用标签和参考的方程环境的使用](/tex/images/java/tutorial/latex-math-9-7.png)

### 9.2. 多行显示

有时，显示可能不符合具有或没有方程式的单行公式的简单模式。乳胶为其余大多数情况提供了特殊命令。

多行显示通常包含几个方程，应通过其“ =”符号排列的几个方程，如

![带有数组环境的多行方程排序](/tex/images/java/tutorial/latex-math-9-8.png)

此类显示的推荐方法是使用乳胶提供的“数组”环境：

```tex
$$\begin{array}{rl}
  X_1+\cdots+\X_p&=m,\\
  Y_1+\cdots+\Y_q&=n.}
\end{array}$$
```

此环境可以帮助您表示方程为多列(在这种情况下为两列)矩形数组。该行包含由`\\`(是newline)命令隔开的单个方程式。每个方程式的左侧和右侧由'＆'符号隔开。不需要最后一行以`\\'结束。环境还具有指定每列中的对齐方式的参数。在示例中，适当的值为“ rl”，这意味着方程式的左侧将右侧齐平，而右侧则将左侧齐平。

乳胶还提供了``eqnarray``环境的工作原理，但是要使方程式的两侧正确对齐，它需要两个对齐点，不幸的是，间距在某种程度上脱离了数学键入惯例。以下代码

```tex
\begin{eqnarray*}
  X_1+\cdots+X_p&=&m,\\
  Y_1+\cdots+Y_q&=&n.
\end{eqnarray*}
```

产生以下输出：

![带有eqnarray*环境的多行方程排序](/tex/images/java/tutorial/latex-math-9-9.png)

乳胶的“ eqnarray”环境产生相同的结果，除了它会自动编号方程。

“数组”环境中可以有任何数量的方程式；一般模式是

```tex
\begin{array}{rl}
  <left-hand side_1>&<right-hand side_1>\\
  <left-hand side_2>&<right-hand side_2>\\
  ...
  <left-hand side_n>&<right-hand side_n>
\end{array}
```

每个``<右侧>''从要对齐的符号开始。

“数组”环境的结果是一个垂直中心的框。这使得获得这样的公式很容易

![一个显示中的两组方程](/tex/images/java/tutorial/latex-math-9-10.png)

您只需两次使用“数组”环境：

```tex
$$\left\{
  \begin{array}{rl}
    \alpha&=f(z)\\ \beta&=f(z^2)\\ \gamma&=f(z^3)
  \end{array}
\right\}\qquad\left\{
  \begin{array}{rl}
    x&=\alpha^2-\beta\\ y&=2\gamma
  \end{array}
\right\}.$$
```

当您具有几个具有几个方程式的对齐方程时，就会发生下一个复杂性。或某些线可能被编号，而其他行则没有：

![任意编号的方程数阵列在右侧带有标签](/tex/images/java/tutorial/latex-math-9-11.png)

不幸的是，即使使用`eqnarray`环境(其间距不正确)，也无法在多行显示中手动指定方程编号。只有`amsmath`软件包可以 
帮助。因此，获得上述结果的推荐方法是输入：

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

如果您在“ Align”环境的行上同时省略`\ tag`和`\ notag`，则将使用存储在相应的内部计数器中的当前值自动生成方程编号。

如果将`amsmath`软件包加载为``leqno``选项，则方程式将出现在左侧边缘。因此

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
生产

![任意编号的方程式数组，左侧有标签](/tex/images/java/tutorial/latex-math-9-12.png)

要了解有关使用`amsmath`软件包的功能排列数学公式的更多信息，请参见这些[文章](/tex/{{lang.url-fragment}}java/what-is-ams-latex/)。

### 9.3. 长公式

现在，让我们讨论当公式太长以至于不适合单行时该怎么办。例如，假设您遇到方程式

![缩减长度配方，使线路过时](/tex/images/java/tutorial/latex-math-9-13.png)

您必须以某种方式将其分解； Tex通过将“+”和“  - ”标志旁边的空间缩小到零的空间来挤在一起，尽力将所有东西挤在一起，但线路仍然充满了。

让我们尝试在“ +7”之前打破该方程式。如果您使用与多行方程相同的方式，则“数组”环境给'='的右侧留出太多空间：

```tex
$$\begin{array}{rl}
  \sigma(2^{34}-1,2^{35},1)&=-3+(2^{34}-1)/2^{35}+2^{35}\!/(2^{34}-1) \\
                   &\qquad{}+7/2^{35}(2^{34}-1)-\sigma(2^{35},2^{34}-1,1)
\end{array}$$
```

因此，最好再次使用`amsmath`软件包。但是这次，您应该使用`align`阵列，因为不需要方程编号：

```tex
%% Preamble
\usepackage{amsmath}
%% Body
\begin{align*}
  \sigma(2^{34}-1,2^{35},1)&=-3+(2^{34}-1)/2^{35}+2^{35}\!/(2^{34}-1) \\
                   &\qquad+7/2^{35}(2^{34}-1)-\sigma(2^{35},2^{34}-1,1).
\end{align*}$$
```

这会产生

![使用对齐*环境分解了长配方](/tex/images/java/tutorial/latex-math-9-14.png)

这个想法是使用第二行上的`\ qquad`将长的单行公式视为两行公式，以便公式的第二部分在第一行的'='符号的右侧很好地显示。
实际上，决定如何将长期显示的公式分解为线条并不是一件容易的事。 Tex永远不会尝试这样做，因为没有一套规则真的足够了。数学手稿的作者通常是该怎么做的最好的法官，因为休息位置取决于数学解释的微妙因素。例如，通常需要强调一些基于公式的对称或其他结构，并且这些事情需要对该公式中的确切理解有深入的了解。

然而，有可能陈述一些关于如何在显示屏中处理长公式的经验法则，因为有一些原则是最好的数学排版倾向于遵循：

a) 尽管段落中的公式总是在 *二进制操作和关系后打破*，但显示的公式总是在 *二进制操作和关系之前打破*。这就是为什么我们没有以`(2^{34} -1)+`结束上一个示例的第一行;我们用`(2^{34} -1`结束了它，并以``+''开始了第二行。

b) 当二进制操作之前打破方程式时，第二行应至少在最内部的子形式的右侧至少启动两个四边形，其中包含二进制操作在第一行开始。例如，如果您想休息

```tex
$$\sum_{0<k<n}\left(<formula_1>+<formula_2>\right)$$
```

在 `<formula_1>` 和 `<formula_2>` 之间的加号处，几乎必须让第二行的加号出现在与 `\left(` 对应的大左括号的右侧。

在仅考虑的示例中，需要特别注意将公式分为两行，因为不能隔离地使用`\ weft`和`\ right``\ right`。此外，即使它们以不同的线路出现，您也希望两个定界符具有相同的大小。最好的解决方案通常是自己选择定界符的大小；例如，您可以输入

```tex
%% Preamble
\usepackage{amsmath}
%% Body
\begin{align*}
  \sum_{0<k<n}\biggl(&<formula_1>\\
    &\qquad+<formula_2>\biggr)
\end{align*}
```

如果`\ bigg`定界符是最好的。请注意，在此示例中，``＆'标记都不会出现在``='''符号上，它们只是标记了一个对齐点。

有另一种破坏长公式的方法，有时称为 *两行 *表单。这个想法是将公式的第一部分几乎左侧齐平，然后将第二部分几乎向右齐平，在那里“几乎齐平”的意思是“一个四轮”。因此，前面考虑的长Sigma方程的两行形式是

![方程式的两行形式](/tex/images/java/tutorial/latex-math-9-15.png)

为了获得这一两行效果，只需键入：

```tex
$$\displaylines{\quad\sigma(2^{34}-1,2^{35},1)
  =-3+(2^{34}-1)/2^{35}+2^{35}\!/(2^{34}-1)\hfill{}\cr
\hfill{}+7/2^{35}(2^{34}-1)-\sigma(2^{35},2^{34}-1,1).\quad\cr}$$
```

在这里的第二行上键入了一个额外的`{}`，以便Tex知道'+'是二进制操作。对于左侧长的方程式，特别建议使用两行形式。在这种情况下，休息通常是在=符号之前。