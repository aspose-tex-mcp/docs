---
translation: true
template: /templates/_template-java.md
linktitle: 可扩展和可调整符号
title: 5. 可扩展和可调整符号
weight: 50
url: /java/latex-math-extensible-symbols/
keywords: ams-latex、amsmath、amsxtra、LaTeX 数学运算符、LaTeX 数学分隔符、LaTeX 数学括号、LaTeX 数学花括号、LaTeX 数学重音符号
description: 本文讨论了与使用可扩展和可调整数学符号相关的 LaTeX 特性。
lastmod: "2026-02-19"
---

{{<section overview>}}

在 LaTeX 中，有一些特性可以生成能够任意伸展到所需大小的结构。数学排版急需这种可变性。我们将在本文中讨论其中的一些方面。本节中涉及的所有命令（除非另有说明）均由标准 LaTeX 提供。

## 5.1. Ellipsis...

`amsmath` 宏包几乎在所有情况下都用单一的 `\dots` 命令替代标准 LaTeX 中的 `\ldots`、`cdots` 等。省略号的垂直位置以及其周围的间距会根据 `\dots` 后面的符号类型自动选择。如果下一个符号是加号，点会居中；如果是逗号，点会落在基线。它始终是三个点，但间距是可变的。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
A series $H_1, H_2, \dots, H_n$, a sum
$H_1 + H_2 + \dots, H_n$, an orthogonal product
$H_1 \times H_2 \times \dots \times H_n$.
```

![自动确定间距的省略号](/tex/images/java/tutorial/latex-ams-math-5-1.png)

然而，当省略号出现在公式末尾时，后面的对象可能是 `\end`、`\)` 或 `\]`，此时 LaTeX 无法判断点的定位。在这种情况下，需要使用 `\dotsc`（后接逗号的省略号）、`\dotsb`（后接二元运算符或关系符的省略号）、`\dotsm`（后接乘法点的省略号）、`\dotsi`（后接积分号的省略号）或在其他情况下使用 `\dotso` 来手动指定。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
A series $H_1, H_2, \dotsc\,$, a sum
$H_1 + H_2 + \dotsb\,$, an orthogonal product
$H_1 \times H_2 \times \dotsm\,$, and an infinite
integral: \[ \int_{H_1} \int_{H_2} \dotsi \;
{-\Gamma}\, d\Theta \]
```

![公式末尾的省略号](/tex/images/java/tutorial/latex-ams-math-5-2.png)

## 5.2. Symbols that are horizontally extensible

水平可伸展的符号

基本上，LaTeX 允许为任何数学重音命令设置多个宽度的字形，只要可用字体提供这些宽度。然而，在标准 LaTeX 中，仅有两个此类命令：`\widehat` 和 `\widetilde`。

在下例中，我们演示了几个生成类似上述可伸展重音的构造的命令。它们都产生数学类 *Ordinary* 的复合符号。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align*}
\widehat {\psi_\delta(t) E_t h}
&= \widetilde {\psi_\delta(t) E_t h} \\
\overline {\psi_\delta(t) E_t h}
&= \underline {\psi_\delta(t) E_t h} \\
\overbrace {\psi_\delta(t) E_t h}
&= \underbrace {\psi_\delta(t) E_t h}
& & \text{Do not change style} \\
\overrightarrow {\psi_\delta(t) E_t h} 
&= \overleftarrow {\psi_\delta(t) E_t h}
& & \text{Do not change style} \\[-3pt]
& & & \text{without \textsf{amsmath}} \\
\underrightarrow {\psi_\delta(t) E_t h}
&= \underleftarrow {\psi_\delta(t) E_t h}
& & \text{Do need \textsf{amsmath}} \\
\overleftrightarrow {\psi_\delta(t) E_t h}
&=\underleftrightarrow{\psi_\delta(t) E_t h}
& & \text{Do need \textsf{amsmath}}
\end{align*}
```

![可伸展的重音](/tex/images/java/tutorial/latex-ams-math-5-3.png)

这里的“change style”（改变样式）指的是符号会受到所使用的数学样式的影响，从而在分式或上下标等情况下呈现正确的外观。那些不改变样式的符号只能在显示公式的最高层级中正确显示。

## 5.3. Symbols that are vertically extensible

垂直可伸展的符号

垂直可伸展性要广得多。下表列出了所有可垂直伸展的符号。

*Vertically extensible symbols*

|||||||
|:---:|---|:---:|---|:---:|---|
| !["Parentheses"](/tex/images/java/tutorial/latex-ams-math-delim-5-1.png) | `(` `)` | !["Curly Braces Open"](/tex/images/java/tutorial/latex-ams-math-delim-5-11.png) | `\{` `\}` | !["Double Vertical Bars"](/tex/images/java/tutorial/latex-ams-math-delim-5-18.png) | *`\lVert` `\rVert`* |
| !["Angle Brackets"](/tex/images/java/tutorial/latex-ams-math-delim-5-2.png) | `\langle` `\rangle` | !["Curly Braces Close"](/tex/images/java/tutorial/latex-ams-math-delim-5-11.png) | `\lbrace` `\rbrace` | !["Single Vertical Bars"](/tex/images/java/tutorial/latex-ams-math-delim-5-19.png) | *`\lvert` `\rvert`* |
| !["Lgroup and Rgroup"](/tex/images/java/tutorial/latex-ams-math-delim-5-3.png) | `\lgroup` `\rgroup` | !["Square Brackets Open"](/tex/images/java/tutorial/latex-ams-math-delim-5-12.png) | `[` `]` | !["Vertical Bar"](/tex/images/java/tutorial/latex-ams-math-delim-5-20.png) | `|` |
| !["Moustaches"](/tex/images/java/tutorial/latex-ams-math-delim-5-4.png) | `\lmoustache` `\rmoustache` | !["Square Brackets Close"](/tex/images/java/tutorial/latex-ams-math-delim-5-12.png) | `\lbrack` `\rbrack` | !["Vertical Bar"](/tex/images/java/tutorial/latex-ams-math-delim-5-20.png) | `\vert` |
| !["Down Arrow"](/tex/images/java/tutorial/latex-ams-math-delim-5-5.png) | `\Downarrow` | !["Ceiling Brackets Open"](/tex/images/java/tutorial/latex-ams-math-delim-5-13.png) | `\lceil` `\rceil` | !["Arrow Vertical Bar"](/tex/images/java/tutorial/latex-ams-math-delim-5-20.png) | `\arrowvert` |
| !["Up Arrow"](/tex/images/java/tutorial/latex-ams-math-delim-5-6.png) | `\Uparrow` | !["Floor Brackets Close"](/tex/images/java/tutorial/latex-ams-math-delim-5-14.png) | `\lfloor` `\rfloor` | !["Brace Vertical Bar"](/tex/images/java/tutorial/latex-ams-math-delim-5-21.png) | `\bracevert` |
| !["Up Down Arrow"](/tex/images/java/tutorial/latex-ams-math-delim-5-7.png) | `\Updownarrow` | !["Double Brackets Open"](/tex/images/java/tutorial/latex-ams-math-delim-5-15.png) | ***`\llbracket` `\rrbracket`*** | !["Double Arrow Vertical Bar"](/tex/images/java/tutorial/latex-ams-math-delim-5-22.png) | `\Arrowvert` |
| !["Single Down Arrow"](/tex/images/java/tutorial/latex-ams-math-delim-5-8.png) | `\downarrow` | !["Slash"](/tex/images/java/tutorial/latex-ams-math-delim-5-16.png) | `/` | !["Double Vertical Line"](/tex/images/java/tutorial/latex-ams-math-delim-5-22.png) | `\|` |
| !["Single Up Arrow"](/tex/images/java/tutorial/latex-ams-math-delim-5-9.png) | `\uparrow` | !["Back Slash"](/tex/images/java/tutorial/latex-ams-math-delim-5-17.png) | `\backslash` | !["Double Vertical Line"](/tex/images/java/tutorial/latex-ams-math-delim-5-22.png) | `\Vert` |
| !["Single Up Down Arrow"](/tex/images/java/tutorial/latex-ams-math-delim-5-10.png) | `\updownarrow` | | `.` | !["Square Root Sign"](/tex/images/java/tutorial/latex-ams-math-delim-5-23.png) | `\sqrtsign` |

> *斜体中的符号需要 `amsmath` 宏包，若再加粗则需要 `stmaryrd` 宏包。句点 (.) 本身不是可伸展符号，但可用于生成“不可见”的定界符。`\sqrtsign` 符号不能与 `\left`、`\right` 或 `\middle` 一起使用。*

> *同义词：[ - `\lbrack`, `[`;	] - `\rbrack`, `]`;	{ - `\lbrace`, `\{`;	} - `\rbrace`, `\}`; | - `\vert`, `|`;	|| - `\Vert`, `\|`。*

这些符号仅在特定使用方式下才会伸展。它们必须基于以下构造：

```tex
\left <ext-Open> <sub-formula> \right <ext-Close>
```

> 如果 LaTeX 使用 eTeX 引擎，那么也可以在这些可伸展符号上使用 `\middle`。

这里的 `<ext-Open>` 和 `<ext-Close>` 可以是上表中列出的任意符号（`\sqrtsign` 除外）。它们必须是如 [fntguide](https://www.latex-project.org/help/documentation/fntguide.pdf) 中所述可伸展的符号。因此，需要有一个代表不存在实际字形的符号可供使用。这个符号，也被称为 *null delimiter*（空定界符），就是句点 (.)。用于排版可伸展符号的实际字形大小会根据其之间子公式的高度和深度进行选择。

根号符号 `\sqrtsign` 会在垂直和水平上都进行伸展，以适应其参数的大小。在 LaTeX 中，通常使用 `\sqrt` 命令来得到这个符号。

```tex
\[
  \sqrtsign{1 + \sqrtsign{1 + \sqrtsign{1 +
    \sqrtsign{1 + \sqrtsign{1 + \sqrtsign{1 + x}}}}}}
\]
```

![伸展的根号](/tex/images/java/tutorial/latex-ams-math-5-24.png)
