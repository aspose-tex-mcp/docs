---
translation: true
template: /templates/_template-java.md
linktitle: LaTeX 方程对齐与显示
title: 2. LaTeX 方程的显示与对齐
weight: 10
url: /java/latex-structures-for-equations/
keywords: ams-latex、amsmath、amsmath 选项、latex 方程对齐、leqno、eqno、fleqn、latex 方程标签、latex 方程标记、latex 方程对齐
description: 这是关于使用 AMS‑LATEX 包排版 LaTeX 方程的介绍，并提供一些示例及其解释。LaTeX 对齐方程。
lastmod: "2026-02-19"
---

{{<section overview>}}

*amsmath* 包包含了许多用于排版显示数学公式的环境定义。它们可以按素材行数（单行或多行）以及对齐点的数量进行分类。

> 在本节中，我们将 *equation* 一词用于以下含义：指代一个 **逻辑上** 独立的数学显示部分，通常会编号以供引用，并且会有标签（例如，用括号括起的编号）。此类标签也称为 *tags*。

下面的列表包含了最常用的显示环境。适当情况下，它们还有不带标签的星号形式。

||
|---|---|---|
| `equation` | `equation*` | 单行，单个方程 |
| `multline` | `multline*` | 单个未对齐的多行方程，只有一个方程编号 |
| `gather` | `gather` | 多个方程，未对齐 |
| `align` | `align*` | 多个方程，具有多个对齐点 |
| `flalign` | `flalign*` | 多个方程：`align` 的水平展开形式 |
| `split` | | 在多行方程内部的简单对齐 |

本章中的所有示例均采用数学素材居中、方程编号（标签）位于右侧的排版方式。为便于观察定位，我们在输出中展示了表示左、右边距以及中心线的蓝色垂直线。在 LaTeX 源代码中，我们使用 `% -----...` 注释来区分应放在文档前言（preamble）中的行和应放在正文（body）中的行。

```tex
\usepackage[leqno]{amsmath}
% -------------------------------------------------------------------------------
\begin{equation} (a-b)^2 = a^2-2ab+b^2 \end{equation}
\[ \cos2\eta = \cos^2\eta-\sin^2\eta \]
```

![leqno](/tex/images/java/tutorial/latex-ams-math-2-1.png)

如果希望将数学公式相对于左边距固定缩进，而不是在文本栏居中显示，可使用 `fleqn` 选项。可以在前言中通过设置弹性长度 `\mathindent` 的值来指定缩进大小。其默认值与一级列表的缩进相同。如果你对该默认值满意，可以省略对 `\mathindent` 长度的设置。

```tex
\usepackage[fleqn,reqno]{amsmath}
\setlength\mathindent{0.2in}
% -------------------------------------------------------------------------------
\begin{equation} (a-b)^2 = a^2-2ab+b^2 \end{equation}
\[ \cos2\eta = \cos^2\eta-\sin^2\eta \]
```

![fleqn,reqno](/tex/images/java/tutorial/latex-ams-math-2-2.png)

这里其实不需要再显式传递 `reqno` 选项（因为它是默认值），但它会覆盖文档类的设置，使得方程编号始终强制位于右侧，无论发生何种情况。

在标准 LaTeX 中，`&` 和 `\\` 用于显示对齐中的列分隔和换行分隔。它们在 `amsmath` 环境中的用法细节有所变化。

## 2.1. 与标准 LaTeX 的比较

一些多行显示环境允许对公式的部分进行对齐。相比标准 LaTeX 环境 `eqnarray` 和 `eqnarray*`，`amsmath` 包中定义的结构提供了一种稍有不同且更简洁的标记对齐点的方式。在标准 LaTeX 中，`eqnarray*` 类似于前置 `{rcl}` 的 `array` 环境，这意味着需要两个 `&` 字符来指示两个对齐点。而在 `amsmath` 包中，等价结构只需要一个对齐点（相当于 `array` 使用 `{rl}` 前置），因此只需在应对齐的符号（通常是关系符）左侧放置一个 `&`。

`eqnarray` 环境会根据 `array` 的参数设置在对齐点处产生额外的间距。`amsmath` 结构则始终提供固定的间距。下面的示例清晰地展示了两者的差异。同一公式分别使用 `equation`、`align` 和 `eqnarray` 环境排版。

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

![Amsmath compared to standard LaTeX](/tex/images/java/tutorial/latex-ams-math-2-3.png)

注意，`eqnarray` 环境中的间距对于传统的数学排版标准来说过宽。

与标准 LaTeX 类似，`amsmath` 显示环境中的行使用 `\\`（或环境结束）来标记。由于数学显示中的换行通常需要对公式结构有深入的理解，这在当今的软件能力范围之外，因而通常被认为超出当前软件的处理能力。

## 2.2. 单行单个方程

单个方程可以使用 `equation` 环境生成。标签会自动生成并根据所使用的选项放置在最左或最右侧。`equation*` 环境会生成相同的方程，但不带标签。标准 LaTeX 也有 `equation`，但没有 `equation*`，后者相当于标准的显示数学环境。

一个值得注意的事实是，标签的存在并不会影响内容的定位。当行内没有足够空间放置标签时，标签会向上或向下移动：当标签在左侧时会移动到前一行；当标签在右侧时会移动到下一行。

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

![A single equiation on one line](/tex/images/java/tutorial/latex-ams-math-2-4.png)

## 2.3. 多行单个方程（无对齐）

`equation` 环境的变体是 `multline` 环境。它仅用于那些在单行中放不下的方程。必须使用 `\\` 来标记换行，因为不会自动检测。

`multline` 的第一行会在左边距缩进处对齐，最后一行则在右边距缩进处对齐。`\multlinegap` 长度决定了该缩进的大小。

除第一行和最后一行外的每一行都会在显示宽度内单独居中（除非使用 `fleqn` 选项）。然而，如果在某行中加入 `\shoveleft` 或 `\shoveright` 命令，该行会被强制向左或向右对齐。

`multline` 环境只有一个标签，因为它逻辑上只对应一个方程。因此，不能通过 `\tag` 或 `\notag` 来改变单独的行标签。若使用 `reqno`/`leqno` 选项，标签会分别在最后一行右对齐或第一行左对齐。

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

![一个等式跨越多行](/tex/images/java/tutorial/latex-ams-math-2-5.png)

下面的示例展示了 `\multlinegap` 对结果的影响。在第一种情况下，`*dy*` 对齐，看起来像是第一行缺少标签。当 `\multlinegap` 设置为 `0` 时，第二行左侧的空间不受标签影响，而第一行则被推到左边距，从而明确显示这是一条单一方程。

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

![The \multlinegap effect](/tex/images/java/tutorial/latex-ams-math-2-6.png)

## 2.4. 多行单个方程（带对齐）

当需要对单个多行方程进行对齐时，可使用 `split` 环境。只需在每行使用单个 `&` 来标记对齐点。

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

![一个具有简单对齐方式的单一方程](/tex/images/java/tutorial/latex-ams-math-2-7.png)

`split` 本身不会创建方程标签（因此不需要星号变体），因为它始终作为单个方程的内容使用。为此，你可以将其放入外层环境。

默认情况下，标签（以及 `split` 之外的任何方程部分）在 `split` 环境整体高度的垂直方向上居中。这对应于 `centertags` 选项。当指定 `tbtags` 选项时，标签会在 `split` 的最后一行（若标签在右侧）或第一行（若标签在左侧）出现。

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

![A single equiation with simple alignment and the tag on the last line](/tex/images/java/tutorial/latex-ams-math-2-8.png)

## 2.5. 无对齐的方程组

当需要在同一显示区域中放置两个或更多方程，而这些方程之间不需要对齐时，可使用 `gather` 环境。它会分别将每个方程在显示宽度内居中，并在需要时为每个方程配备单独的标签。`gather` 的每一行在逻辑上都是一个单独的方程。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
(a + b)^2 = a^2 + 2ab + b^2 \\
(a + b) \cdot (a - b) = a^2 - b^2
\end{gather}
```

![未对齐的方程组](/tex/images/java/tutorial/latex-ams-math-2-9.png)

如果需要在某行抑制方程编号，可在逻辑行中使用 `\notag` 命令。`gather` 环境本身默认不为方程编号。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
D(a,r) \equiv \{ z \in \mathbf{C} \colon |z - a| < r \} \notag \\
\operatorname{seg} (a, r) \equiv \{ z \in \mathbf{C} \colon \Im z < \Im a, \ |z - a| < r \} \\
C (E, \theta, r) \equiv \bigcup_{e \in E} c (e, \theta, r)
\end{gather}
```

![省略标签的方程组](/tex/images/java/tutorial/latex-ams-math-2-10.png)

## 2.6. 带简单对齐的方程组

当需要在同一显示区域中排版多个方程并使它们在垂直方向上对齐时，可使用 `align` 环境。最简单的情况是，在每行使用单个 `&` 来标记对齐点。

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

![Equation groups with simple alignment](/tex/images/java/tutorial/latex-ams-math-2-11.png)

## 2.7. 多重对齐

`align` 环境可以定义多个对齐点。布局会根据需要创建足够数量的列对，类似于前置 `{rlrl...}` 的 `array`。假设有 *n* 对 `rl` 列，则每行需要的 `&` 数为 *2n − 1*：每对列内部一个 `&`（共 *n* 个），以及用于分隔列对的 *n − 1* 个 `&`。

`align` 环境会在显示宽度内均匀分布素材。如果有额外空间，空间会等分到相邻的列对以及两侧的显示边距。

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

![多序列比对](/tex/images/java/tutorial/latex-ams-math-2-12.png)

`flalign` 的布局类似，但在边距处没有额外空间。下例中可以看到，由于这一特性，方程 (3) 能够在单行内完成（而方程 (2) 仍需换行）。

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

在两种情况下，列对之间的最小间距可以通过修改 `\minalignsep` 来设置。默认值为 `10pt`，可以使用 `\renewcommand` 进行更改，因为它是一个宏命令而非长度参数。下面的示例演示了改变 `\minalignsep` 的效果。

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

![\minalignsep effect](/tex/images/java/tutorial/latex-ams-math-2-14.png)

下面的示例展示了 `align` 的一种非常常见的用法。注意使用 `\text` 在数学素材中插入普通文本。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align}
     x &= y        &&   \text{by hypothesis} \\
    x' &= y'       &&   \text{by definition} \\
x + x' &= y + y'   &&   \text{by Axiom 1}
\end{align}
```

![The use of \text](/tex/images/java/tutorial/latex-ams-math-2-15.png)

## 2.8. 打断显示：`\intertext`

有时需要在对齐显示的行之间插入一小段文字。这可以通过 `\intertext` 命令实现。关键是确保所有对齐属性在插入文字后仍保持不变，而文字本身会以普通段落的形式排版到显示宽度内。如果仅在显示结束后再开始新显示，文本将无法保持对齐。此命令必须紧随 `\\` 或 `\\*` 命令之后。

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

![The \intertext command](/tex/images/java/tutorial/latex-ams-math-2-16.png)

> “and finally” 这几个词位于左边距之外，但所有三个方程仍然保持对齐。

## 2.9. 方程编号与标签

在 LaTeX 中，方程的标签通常会自动生成，它们本质上是 LaTeX 计数器 `equation` 的打印表示。生成过程分三步：设置 `equation` 计数器的值、格式化标签、以及在正确位置打印。

前两步紧密相连，因为只有在相应标签自动打印时，`equation` 计数器的值才会递增。下面展示了一个同时拥有星号和非星号形式的显示环境。只有非星号形式会改变 `equation` 计数器的值，因为它会自动为每个逻辑方程添加标签，而星号形式则不会。

当需要在非星号形式的某个逻辑方程上抑制标签时，应在 `\\` **之前** 放置 `\notag`（或 `\nonumber`）。你也可以在 `\\` **之前** 使用 `\tag` 将默认标签替换为自定义的文本（括号内的内容即为该方程的标签）。

需要注意的是，使用 `\tag` 时计数器的递增也会被抑制。这意味着默认标签的设置在视觉上等同于 `\tag{\theequation}`，但二者并不等价。星号形式的 `\tag*` 会在不加括号（也不加其他可能由文档类添加的内容）的情况下排版其参数文本。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align}
x^2+y^2 &= z^2 \label{eq:A} \\
x^3+y^3 &= z^3 \notag \\
x^4+y^4 &= r^4 \tag{$*$} \\
x^5+y^5 &= r^5 \tag*{$*$} \\
x^6+y^6 &= r^6 \tag{\ref{eq:A}$} \\
A_1 &= N_0 (\lambda ; \Omega') - \phi ( \lambda ; \Omega') \\
A_2 &= \phi (\lambda ; \Omega') \, \phi (\lambda ; \Omega) \tag*{ALSO (\theequation)} \\
A_3 &= \mathcal{N} (\lambda ; \omega)
\end{align}
```

![\tag, \tag*, \notag, \label and \ref](/tex/images/java/tutorial/latex-ams-math-2-17.png)

> 注意 `\label` 与 `\ref` 命令用于为方程提供某种“相对编号”。

## 2.10. 从属编号序列

*amsmath* 包还支持所谓的 “方程子编号”。`subequations` 环境会产生形如 (2a)、(2b)、(2c) … 的标签。该编号方案基于两个普通的 LaTeX 计数器：`parentequation` 和 `equation`。在 `subequations` 环境内的所有已标记方程均使用此方案。

下面的示例展示了标签在一定程度上的重新定义，但请注意，` \theequation` 的重新定义必须放在 `subequations` 环境内部。

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

![Subordinate numbering sequences](/tex/images/java/tutorial/latex-ams-math-2-18.png)

> `subequations` 环境必须位于它所影响的显示之外——也就是说，它 **不** 应该嵌套在自身内部。主计数器会在每次使用此环境时递增。位于 `subequations` 环境内部但不在任何单独（逻辑）方程内的 `\label` 命令，会产生指向父编号的 `\ref`（例如指向 2 而不是 2i）。

## 2.11. 重置方程计数器

常见的做法是让方程在章节或章内编号，形式为 (1.1)、(1.2)、…、(2.1)、(2.2) …。`amsmath` 包提供了使用 `\numberwithin` 声明来实现此功能的简便方式。

例如，要让方程标签包含章节编号，并在每个章节开始时自动重置方程计数器，可在前言中加入如下声明：`\numberwithin{equation}{section}`。

## 附录 A. 使用 Aspose.TeX API 渲染 LaTeX 方程

接下来我们将了解 Aspose.TeX API 如何将 LaTeX 方程生成为单独的图形。

假设你需要将方程以光栅图像的形式获取，以便在非 TeX 的出版物（例如网页）中使用。使用 Aspose.TeX API，可按以下方式实现：

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

如你所见，API 同样能够将 LaTeX 方程转换为 SVG 文件。以上示例展示了在 .NET 环境中使用 Aspose.TeX 的方式。下面是等效的 Java 代码。

将 `outputFile` 设置为现有文件夹中的 `java.nio.file.Path`，例如 `Paths.get(outputDirectory, "equations.png")`。导入所用的 `com.aspose.tex` 类以及 `java.awt.Color`、`java.io.ByteArrayOutputStream`、`java.io.OutputStream`、`java.nio.file.Files` 和 `java.nio.file.Paths`，并处理或声明异常。示例以 150 DPI 在白色背景上渲染两个公式，保留第一个公式的编号。三个参数的 `render()` 方法返回 `Size2D`。日志保存在内存中，两个流在渲染后关闭。

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderEquationsToPNG.java" >}}

你可以在 [Aspose.TeX for .NET](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/) 或 [Aspose.TeX for Java](/tex/{{lang.url-fragment}}java/latex-math-formula-rendering/) 的文章中找到有关渲染选项的详细信息。但这里我们关注的是其中的一个重要选项：使用该选项可以指定 LaTeX 文档前言，以获得所需的渲染结果。（此后，我们仅展示 C# 版本的源码。）

```csharp
// The preamble for the very first example on this page
options.Preamble = @"\usepackage[leqno]{amsmath}";
```

当你需要将方程排版在比 LaTeX 默认 `\textwidth` 更窄的区域时，也可以使用此选项。实现方式有两种：

```csharp
// The preamble for the 2.7 examples
options.Preamble = @"\usepackage[textwidth=232pt]{geometry}
\usepackage{amsmath}";
// or
options.Preamble = @"\usepackage{amsmath}
\setlength{\textwidth}{232pt}";
```

在 Aspose.TeX API 中，默认使用以下前言；除非你需要向 `amsmath` 包传递选项或更改默认的 `\textwidth` 等，否则无需在渲染器选项中显式指定前言：

```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

## 附录 B. 使用 Aspose LaTeX Equation 网页应用渲染 LaTeX 方程

还有一个 [LaTeX Equation Editor 网页应用](https://products.aspose.app/tex/equation-editor) 可以编辑并查看 LaTeX 方程。你可以在文本框中输入方程，然后点击 *View* 按钮查看结果。或者，使用字段上方的控制面板，通过选择子表达式类别、子表达式，再编辑参数（如果有），来构建方程。你可以在 *Formula* 字段下方找到前言及其他选项。
