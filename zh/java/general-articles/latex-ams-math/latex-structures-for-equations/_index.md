---
translation: true
template: /templates/_template-java.md
linktitle: 乳胶方程对齐和显示
title: 2. 乳胶方程的显示和对齐
weight: 10
url: /java/latex-structures-for-equations/
keywords: AMS-LATEX，AMSMATH，AMSMATH选项，乳胶方程对齐，Leqno，Eqno，Fleqn，乳胶方程式标签，乳胶方程标签，乳胶对齐方程
description: 这是对带有AMS-LATEX软件包排版乳胶方程的介绍，并提供了一些示例及其解释。乳胶对齐方程。
lastmod: "2025-06-10"
---

{{<section overview>}}


* amsmath *软件包包含许多用于键入显示的数学公式的环境定义。它们可以通过材料线的数量(单个或多个)以及对齐点的数量进行分类。

> 在本节中，我们将以以下方式使用术语“方程式”：指代数学显示中“逻辑上”不同的部分，该部分通常编号以供参考，并带有标签（例如，用括号中的数字表示）。此类标签也称为“标签”。

以下列表包含最受欢迎的显示环境。在适当的情况下，他们出演了没有方程式标记的形式。

||
| --- | --- | --- |
| `equation` | `方程*|一行，一个等式|
| `多线| `多线*|一个未对齐的多线方程，一个方程编号|
| ``聚会| `收集*|几个方程式没有对准|
| `align` | `对齐*|具有多个对齐方式的几个方程式|
| `flalign` | `flalign*`|几个方程式：水平扩散的形式的“ Align” |
| `split` | |多线方程中的简单对齐|

本章中的所有示例均为排本，右侧的数学材料和方程编号(标签)。为了可视化定位，我们在表示左右边缘以及中心线的输出中呈现蓝色垂直线。在乳胶源代码中，我们使用``％-----...`评论对文档序言中应与应放置在体内的行中放置的单独行。


```tex
\usepackage[leqno]{amsmath}
% -------------------------------------------------------------------------------
\begin{equation} (a-b)^2 = a^2-2ab+b^2 \end{equation}
\[ \cos2\eta = \cos^2\eta-\sin^2\eta \]
```

![Leqno](/tex/images/java/tutorial/latex-ams-math-2-1.png)

如果要将数学从左边边缘定位为固定的缩进，而不是以文本列为中心，则可以使用“ Fleqn”选项。您可以通过设置橡胶长度“ \ Mathindent”的值来指定序言中缩进的大小。它的默认值与一级列表的缩进相同。如果您对此值感到满意，则可以跳过设置“ \ Mathindent”长度。


```tex
\usepackage[fleqn,reqno]{amsmath}
\setlength\mathindent{0.2in}
% -------------------------------------------------------------------------------
\begin{equation} (a-b)^2 = a^2-2ab+b^2 \end{equation}
\[ \cos2\eta = \cos^2\eta-\sin^2\eta \]
```

![勒克尼，雷克诺](/tex/images/java/tutorial/latex-ams-math-2-2.png)

这里无需在此处传递“ reqno”选项(默认值为默认值)，但是它覆盖了文档类设置，因此等式编号被强制到正确的情况下。

在标准乳胶中，`＆`和`\\'用于显示对齐中的列和行分离。它们使用的细节在“ AMSMATH”环境中发生了变化。

## 2.1. 与标准乳胶的比较

一些多行显示环境允许您对齐公式的某些部分。与标准 LaTeX 环境 `eqnarray` 和 `eqnarray*` 相比，`amsmath` 包中定义的结构提供了一种略有不同且更简单的标记对齐点的方法。在标准 LaTeX 中，`eqnarray*` 类似于以 `{rcl}` 为前缀的 `array` 环境，这意味着需要两个 `&` 字符来指示两个对齐点。在 `amsmath` 包中，等效结构只有一个对齐点（就好像 `array` 有一个 `{rl}` 前缀），因此您只需在需要对齐的符号（通常是关系）左侧放置一个 `&` 字符即可。

`eqnarray` 环境会根据 `array` 的参数设置在对齐点处产生额外的空间。同时，`amsmath` 结构会提供固定的间距。下一个示例清楚地说明了两者的区别。同一个等式分别使用 `equation`、`align` 和 `eqnarray` 环境进行排版。


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
x^2 + y^2 = z^2
\end{equation}
\begin{align}
x^2 + y^2 &= z^2 \\
x^3 + y^3 &< z^3
\end{align}
\begin{eqnarray}
x^2 + y^2 &=& z^2 \\
x^3 + y^3 &<& z^3
\end{eqnarray}
```

![与标准乳胶相比](/tex/images/java/tutorial/latex-ams-math-2-3.png)

与标准 LATEX 一样，`amsmath` 显示中的行以 `\\` 标记（或环境结束）。由于数学显示中的换行通常需要深入了解公式的结构，因此通常认为这超出了当今软件的能力。

## 2.2. 一行的单个方程式

`equation` 环境可以生成单个方程式。系统会根据所使用的选项自动生成一个标签，并将其放置在最左侧或最右侧。`equation*` 环境可以生成相同的方程式，但不包含标签。标准 LaTeX 也包含 `equation`，但没有 `equation*`，因为后者与标准显示的数学环境类似。

一个值得注意的事实是，标签的存在不会影响内容的定位。如果一行在一行上没有足够的空间，则标签将向上或向下移动：当方程式标签在左侧时，到上一行，当标签在右侧时，到下一行。


```tex
\usepackage[leqno]{amsmath}
% -------------------------------------------------------------------------------
\begin{equation*}
n^2 + m^2 = k^2
\end{equation*}
\begin{equation}
n^p + m^p \neq k^p \qquad p > 2
\end{equation}
```

![一条线上的一个平衡](/tex/images/java/tutorial/latex-ams-math-2-4.png)

## 2.3. 在几行上的单个方程式无对准

`equation` 环境的一个变体是 `multline` 环境。它仅用于无法在一行中显示的公式。必须使用 `\\` 字符标记换行符，因为换行符无法自动找到。

`multline` 的第一行将与左边距的缩进对齐，最后一行与右边距的相同缩进对齐。`\multlinegap` 的长度值定义了此缩进的大小。

除第一行和最后一行之外的每一行都会在显示宽度内单独居中（除非使用了 `fleqn` 选项）。但是，如果您在一行中添加 `\shoveleft` 或 `\shoveright` 命令，该行将被强制向左或向右对齐。

“多线环境”具有一个单个标签，因为它在逻辑上是一个方程。因此，无法通过使用`\tag`或`\notag`更改单个线路。如果使用`reqno`/`leqno`选项时，将标签(如果存在)放在最后/第一行上的齐平/左/向左。


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{multline}
\text{First line of a multline} \\
\text{Centered Middle line} \\
\shoveright{\text{A right Middle}} \\
\text{Another centered Middle} \\
\text{Yet another centered Middle} \\
\shoveleft{\text{A left Middle}} \\
\text{Last line of the multline}
\end{multline}
```

![几行的单个平衡](/tex/images/java/tutorial/latex-ams-math-2-5.png)

下一个示例展示了 `\multlinegap` 如何影响结果。在第一种情况下，"*dy*" 对齐，看起来像是方程式第一行缺少了一个标签。当 `\multlinegap` 设置为 `0` 时，第二行左侧的空格不会因为标签而发生变化，而第一行则移到了左边距，这清楚地表明这是一个单独的方程式。


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{multline} \tag{2}
\sum_{t \in \mathbf{T}} \int_a^t \biggl\lbrace \int_a^t f(t - x)^2 \, g(y)^2 \,dx \biggr\rbrace \,dy \\
= \sum_{t \notin \mathbf{T}} \int_t^a \biggl\lbrace g(y)^2 \int_t^a f(x)^2 \,dx \biggr\rbrace \,dy
\end{multline}
\setlength\multlinegap{0pt}
\begin{multline} \tag{2}
\sum_{t \in \mathbf{T}} \int_a^t \biggl\lbrace \int_a^t f(t - x)^2 \, g(y)^2 \,dx \biggr\rbrace \,dy \\
= \sum_{t \notin \mathbf{T}} \int_t^a \biggl\lbrace g(y)^2 \int_t^a f(x)^2 \,dx \biggr\rbrace \,dy
\end{multline}
```

![\ multlineGap效果](/tex/images/java/tutorial/latex-ams-math-2-6.png)

## 2.4. 单个方程式在几行与对齐方式上

当你需要对齐单个多行方程式时，`split` 环境可以为你提供帮助。只需在每行上使用一个 `&` 字符来标记对齐点即可。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
\begin{split}
(a + b)^4 &= (a + b)^2 (a + b)^2 \\
          &= (a^2 + 2ab + b^2)(a^2 + 2ab + b^2) \\
          &= a^4 + 4a^3b + 6a^2b^2 + 4ab^3 + b^4
\end{split}
\end{equation}
```

![一个简单对齐的单一平衡](/tex/images/java/tutorial/latex-ams-math-2-7.png)

`split` 本身不会创建公式标签（因此不需要带星号的变体），因为它始终用作单个公式的内容。为此，您可以将其放入外部环境。

默认情况下，该标签（以及 `split` 之外的公式的任何部分）在 `split` 环境材质的总高度上垂直居中。此行为对应于 `centertags` 选项。当您指定 `tbtags` 选项时，如果标签位于右侧，则放置在 `split` 的最后一行；如果标签位于左侧，则放置在第一行。


```tex
\usepackage[tbtags]{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
\begin{split}
(a - b)^3 &= (a - b) (a - b)^2 \\
          &= (a - b)(a^2 - 2ab + b^2) \\
          &= a^3 - 3a^2b + 3ab^2 - b^3
\end{split}
\end{equation}
```

![一个简单对准的单个平衡和最后一行的标签](/tex/images/java/tutorial/latex-ams-math-2-8.png)

## 2.5. 方程组无对准

当您需要将两个或多个方程式放入单个显示中而不对齐方程式之间，则可以使用“聚集”环境。它还分别将每个方程式中心在显示宽度内，并在需要的情况下用单独的标签安装。从逻辑上讲，“聚集”的每一行都是一个方程。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
(a + b)^2 = a^2 + 2ab + b^2 \\
(a + b) \cdot (a - b) = a^2 - b^2
\end{gather}
```

![方程组无对准](/tex/images/java/tutorial/latex-ams-math-2-9.png)

您可能需要隐藏某一行的公式编号。答案是使用`\notag`命令，将其放在逻辑行中。`gather`环境根本不标记公式。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
D(a,r) \equiv \{ z \in \mathbf{C} \colon |z - a| < r \} \notag \\
\operatorname{seg} (a, r) \equiv \{ z \in \mathbf{C} \colon \Im z < \Im a, \ |z - a| < r \} \\
C (E, \theta, r) \equiv \bigcup_{e \in E} c (e, \theta, r)
\end{gather}
```

![具有标签的方程组](/tex/images/java/tutorial/latex-ams-math-2-10.png)

## 2.6. 简单对齐的方程组

当你需要在单个显示中排版多个公式并使其垂直对齐时，`align` 环境可以帮你解决这个问题。最简单的情况下，你可以在每行上使用一个 `&` 来标记对齐点。


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align}
(a - b)^3 &= (a - b) (a - b)^2 \\
          &= (a - b)(a^2 - 2ab + b^2) \\
          &= a^3 - 3a^2b + 3ab^2 - b^3
\end{align}
\begin{align}
x^2 + y^2 &= 1 \\
        y &= \sqrt{1-x^2}
\end{align}
```

![简单对齐的方程组](/tex/images/java/tutorial/latex-ams-math-2-11.png)

## 2.7. 多个路线

`align` 环境可以定义多个对齐点。布局包含所需数量的列对，类似于带有 `{rlrl...}` 类似前导码的 `array`。假设它由 *n* 个这样的 `rl` 列对组成，则每行 `&` 的数量将为 *2n - 1*：每个列对内有一个 `&` 符号用于对齐，从而得到 *n* 个；另外 *n - 1* 个 `&` 符号用于分隔列对。

`align`环境将材料均匀地散布在显示宽度上。如果有额外的空间，则在相邻的列对和两个显示边距之间平均分布。


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
This example has two column-pairs.
\begin{align} \text{Compare }
x^2 + y^2 &= 1 &                      x^3 + y^3 &= 1 \\
x              &= \sqrt {1-y^2}   &           x &= \sqrt[3]{1-y^3}
\end{align}
This example has three column-pairs.
\begin{align}
     x &= y        &        X &= Y      &   a &= b+c \\
    x' &= y'       &       X' &= Y'     &  a' &= b \\
x + x' &= y + y'   &   X + X' &= Y + Y' & a'b &= c'b
\end{align}
```

![多个路线](/tex/images/java/tutorial/latex-ams-math-2-12.png)

`flalign`的布局相似，但是边缘没有空间。在下一个示例中，您可以看到由于此事实(而公式(2)仍然没有)，等式(3)适合单行。


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
This example has two column-pairs.
\begin{flalign} \text{Compare }
x^2 + y^2 &= 1               &   x^3 + y^3 &= 1 \\
        x &= \sqrt {1-y^2}   &           x &= \sqrt[3]{1-y^3}
\end{flalign}
This example has three column-pairs.
\begin{flalign}
     x &= y        &        X  &= Y        &     a &= b+c \\
    x' &= y'       &       X'  &= Y'       &    a' &= b \\
x + x' &= y + y'   &   X + X'  &= Y + Y'   &   a'b &= c'b
\end{flalign}
```

![flalign](/tex/images/java/tutorial/latex-ams-math-2-13.png)

在这两种情况下，都可以通过更改 `\minalignsep` 来设置列对之间的最小间距。默认值为 `10pt`，可以使用 `\renewcommand` 进行更改，因为它是一个宏命令，而不是长度参数。下一个示例演示了更改 `\minalignsep` 的效果。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
This example has two column-pairs.
\renewcommand\minalignsep{0pt}
\begin{align} \text{Compare }
x^2 + y^2 &= 1               &   x^3 + y^3 &= 1 \\
        x &= \sqrt {1-y^2}   &           x &= \sqrt[3]{1-y^3}
\end{align}
This example has three column-pairs.
\renewcommand\minalignsep{15pt}
\begin{flalign}
     x &= y        &        X  &= Y        &     a &= b+c \\
    x' &= y'       &       X'  &= Y'       &    a' &= b \\
x + x' &= y + y'   &   X + X'  &= Y + Y'   &   a'b &= c'b
\end{flalign}
```

![\ minalignsep效应](/tex/images/java/tutorial/latex-ams-math-2-14.png)

下一个示例演示了 `align` 的一个非常常见的用法。请注意，在数学材料中使用 `\text` 来生成普通文本。


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align}
     x &= y        &&   \text{by hypothesis} \\
    x' &= y'       &&   \text{by definition} \\
x + x' &= y + y'   &&   \text{by Axiom 1}
\end{align}
```

![\文本的使用](/tex/images/java/tutorial/latex-ams-math-2-15.png)

## 2.8. 中断显示：`\ InterText`

您可能想在显示对齐的行间插入一小段文本。这可以通过 `\intertext` 命令完成。务必确保所有对齐属性不受文本影响，同时文本本身将排版为设置为显示宽度的普通段落。如果您直接结束显示，然后在文本后开始新的显示，对齐将不起作用。此命令必须始终紧跟 `\\` 或 `\\*` 命令。


``` tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align}
A_1 &= N_O (\lambda ; \Omega') - \phi ( \lambda ; \Omega') \\
A_2 &= \phi (\lambda ; \Omega') \phi (\lambda ; \Omega) \\
\intertext{and finally}
A_3 &= \mathcal{N} (\lambda ; \omega)
\end{align}
```

![\ intertext命令](/tex/images/java/tutorial/latex-ams-math-2-16.png)

> “最后”这两个词超出了对齐范围，位于左边距，但所有三个等式都是对齐的。

## 2.9. 方程编号和标签

在乳胶中，方程式通常会自动生成，它们本质上是乳胶计数器“方程式”的印刷表示。这是由乳胶在三个步骤中完成的：设置“方程”计数器的值；格式化标签；并以正确的位置打印。

前两个步骤紧密链接，因为仅当自动打印相应的标签时，“方程”计数器值才增加。让我们看一下既有出演和未经标记的表单的展示环境。只有未星级的形式会更改“方程”计数器的值，因为它会自动标记每个逻辑方程，而星级形式则没有。

当您需要在未加星号的形式中抑制某个逻辑等式的标签设置时，可以在 `\\` *之前* 添加 `\notag`（或 `\nonumber`）。您也可以使用 `\tag` 命令在 `\\` *之前* 添加，将默认标签替换为您自己设计的标签。此命令的参数可以是任意排版在括号中的普通文本，作为该等式的标签。

请注意，使用 `\tag` 时，计数器值的递增也会被抑制。这意味着默认标签设置仅在视觉上与 `\tag{\theequation}` 相同；它们并不等效。加星号的形式 `\tag*` 会排版其参数中的文本，而无需使用括号（并且不会使用任何其他可能添加到特定文档类的内容）。


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align}
x^2+y^2 &= z^2 \label{eq:A} \\
x^3+y^3 &= z^3 \notag \\
x^4+y^4 &= r^4 \tag{$*$} \\
x^5+y^5 &= r^5 \tag*{$*$} \\
x^6+y^6 &= r^6 \tag{\ref{eq:A}$'$} \\
A_1 &= N_0 (\lambda ; \Omega') - \phi ( \lambda ; \Omega') \\
A_2 &= \phi (\lambda ; \Omega') \, \phi (\lambda ; \Omega) \tag*{ALSO (\theequation)} \\
A_3 &= \mathcal{N} (\lambda ; \omega)
\end{align}
```

![\ tag，\ tag*，\ notag，\ label和\ ref](/tex/images/java/tutorial/latex-ams-math-2-17.png)

> 请注意如何使用 `\label` 和 `\ref` 命令为方程式提供某种“相对编号”。

## 2.10. 从属编号序列

* amsmath *软件包还支持所谓的“方程式子数字”。 `subequations`环境产生形式(2a)，(2b)，(2c)等形式的标签。该编号方案基于两个普通的乳胶计数器：`parentequination`and`equation`。 `subequations`环境中的所有标记方程都使用此方案。

以下示例表明可以在一定程度上重新定义该标签，但是请注意，`\equ`的重新定义必须放入`subequations`环境中。


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{subequations} \label{eq:1}
\begin{align}
           f &= g \label{eq:1A} \\
          f' &= g' \label{eq:1B} \\
\mathcal{L}f &= \mathcal{L}g \label{eq:1C}
\end{align}
\end{subequations}

\begin{subequations} \label{eq:2}
\renewcommand\theequation{\theparentequation\roman{equation}}
\begin{align}
           f &= g \label{eq:2A} \\
          f' &= g' \label{eq:2B} \\
\mathcal{L}f &= \mathcal{L}g + K \label{eq:2C}
\end{align}
\end{subequations}
Note the relationship between~\eqref{eq:1}
and~\eqref{eq:2}: only~\ref{eq:1C} and~\ref{eq:2C} differ.
```

![从属编号序列](/tex/images/java/tutorial/latex-ams-math-2-18.png)

> `subequations` 环境必须出现在其影响的显示*之外*。它也不应该嵌套在其自身中。每次使用此环境时，“主”方程计数器都会递增。在 `subequations` 环境中，但位于任何单个（逻辑）方程之外的 `\label` 命令将生成指向父级数字的 `\ref`（例如，指向 2 而不是 2i）。

## 2.11. 重置方程计数器

通常的做法是，在章节或章节内使用类似 (1.1), (1.2), ..., (2.1), (2.2), ... 的标签对公式进行编号。`amsmath` 包提供了一种简单的方法，即使用 `\numberwithin` 声明来实现。

例如，要获取包含章节编号的公式标签，并自动重置每个章节的公式计数器，请在序言中添加以下声明：`\numberwithin{equation}{section}`。

## 附录A.用aspose.tex api渲染乳胶方程

现在，我们将研究Aspose.TeX API允许您将乳胶方程作为独立数字的方式。

假设您需要将方程式作为栅格图像获得，以便可以在某些非TEX出版物(例如网页)中使用它。使用aspose.tex api，您可以按以下方式执行以下操作：


```csharp
string equation = @"\begin{equation} (a-b)^2 = a^2-2ab+b^2 \end{equation}
\[ \cos2\eta = \cos^2\eta-\sin^2\eta \]";
Aspose.TeX.Features.PngMathRendererOptions options = new Aspose.TeX.Features.PngMathRendererOptions();
using (Stream stream = File.Open("your-file-name-and-path", FileMode.Create))
{
    new Aspose.TeX.Features.PngMathRenderer().Render(equation, stream, options, out System.Drawing.SizeF size);
    // Below is the short version for rendering with SVG
    // new Aspose.TeX.Features.SvgMathRenderer().Render(equation, stream, new Aspose.TeX.Features.SvgMathRendererOptions(), out System.Drawing.SizeF size);
}
```

如您所见，API还能够将乳胶方程转换为SVG文件。这就是使用aspose.tex进行.net的一个示例。以下是Java版本的等效代码。


```java
String equation = "\\begin{equation} (a-b)^2 = a^2-2ab+b^2 \\end{equation}\r\n" +
		"\\[ \\cos2\\eta = \\cos^2\\eta-\\sin^2\\eta \\]";
Size2D size = new Size2D.Float();
com.aspose.tex.PngMathRendererOptions options = new com.aspose.tex.PngMathRendererOptions();
final OutputStream stream = new FileOutputStream(Helper.getOutputFile(Path.combine(getCurrentPath(), "doc.png")));
try
{
    new com.aspose.tex.PngMathRenderer().render(equation, stream, options, size);
}
finally {
    stream.close();
}
```

您可以在文章中找到有关使用[Aspose.TeX for .NET](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/)或[Aspose.TeX for Java]渲染乳胶数学公式的文章中使用渲染器选项的详细信息(20)。但是其中一个对我们来说很重要。使用此选项，您可以指定您需要获得所需结果的乳胶文档序言。 (以后，我们将仅介绍源代码的C＃版本。)


```csharp
// The preamble for the very first example on this page
options.Preamble = @"\usepackage[leqno]{amsmath}";
```

当您需要在范围较窄的区域中布置方程式时，您也可以使用此选项，默认情况下定义了textwidth。您有两个选择实现此目标的选择：


```csharp
// The preamble for the 2.7 examples
options.Preamble = @"\usepackage[textwidth=232pt]{geometry}
\usepackage{amsmath}";
// or
options.Preamble = @"\usepackage{amsmath}
\setlength{\textwidth}{232pt}";
```

在aspose.tex api中，默认情况下使用以下序言，因此，除非您需要将选项传递给`amsmath`软件包或更改默认值`\ textwidth`或其他内容，否则无需在renderer's Options中指定序言：


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

## 附录B.用Aspose latex方程渲染乳胶方程Web应用程序

还有[乳胶方程编辑器Web应用程序](https://products.aspose.app/tex/equation-editor)，它允许您编辑和查看乳胶方程。您可以在文本字段中输入方程式，然后单击 *视图 *按钮以查看结果。或者，您可以使用字段上方的控制面板来通过选择子表达类别，然后进行子表达，然后编辑参数(如果有)来构建方程。您可以在 *公式 *字段下方找到序言和其他选项。