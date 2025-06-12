---
translation: true
template: /templates/_template-java.md
linktitle: 可扩展且可调的符号
title: 5. 可扩展且可调的符号|乳胶手册
weight: 50
url: /java/latex-math-extensible-symbols/
keywords: AMS-LATEX，AMSMATH，AMSXTRA，乳胶数学运营商，乳胶数学分配器，乳胶数学支架，乳胶数学括号，乳胶数学口音
description: 本文讨论了与使用可扩展且可调的数学符号有关的乳胶功能。
lastmod: "2025-06-10"
---

{{<section overview>}}

在乳胶中，有某些功能可以生产可以生长到任何必需尺寸的结构。数学排版迫切需要这种可变性。我们将在本文中讨论它的某些方面。本节中涵盖的所有命令(除非另有说明)由标准乳胶提供。


## 5.1. 省略...

`amsmath`软件包替换(几乎在所有情况下)所有这些`\ldots`，`cdots`等。从单个`\ dots`命令中从标准乳胶中替换。椭圆的垂直位置及其周围的空间都会根据` \dots`之后的符号类型自动选择。如果下一个符号是一个加号，则点将以焦点为中心；如果是逗号，他们将落在基线上。它总是三个点，但间距是可变的。


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
A series $H_1, H_2, \dots, H_n$, a sum
$H_1 + H_2 + \dots + H_n$, an orthogonal product
$H_1 \times H_2 \times \dots \times H_n$.
```

![具有自动确定间距的省略号](/tex/images/java/tutorial/latex-ams-math-5-1.png)

然而，当点恰好出现在公式末尾时，下一个对象会是类似 `\end` 或 `\)` 或 `$` 的东西，而 LaTeX 无法确定点的位置。在这种情况下，你必须使用 `\dotsc` 来表示点后跟逗号，`\dotsb` 表示点后跟*二元运算符*或*关系符号*，`\dotsm` 表示点后跟乘法点，`\dotsi` 表示点后跟积分，或者 `\dotso` 表示其他情况。

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

## 5.2. 水平扩展的符号

基本上，乳胶允许设置任何数学重音命令，每当可用字体提供时，都会从一系列宽度产生适当的字形。但是，在标准乳胶中只有两个这样的命令：`\ widehat`和`\ didetilde`。

在下一个示例中，我们演示了一些命令的使用，这些命令产生了类似于上述可扩展口音的构造。它们都产生数学类 *普通 *的复合符号。

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

![可扩展的口音](/tex/images/java/tutorial/latex-ams-math-5-3.png)

在这里，“更改样式”意味着所采用的符号受使用的数学样式的影响，因此在使用时(例如，在分数或下标/superscript中)时看起来正确。那些不更改样式的人只会在显示的公式的顶级出现。

## 5.3. 垂直扩展的符号

垂直可扩展性更宽。下表列出了所有垂直扩展的符号。

*垂直扩展的符号*

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


> *斜体符号需要 `amsmath` 包，或者如果以粗体显示，则需要 `stmaryrd` 包。句点 (.) 本身不是可扩展符号，但可以用来生成“不可见”的分隔符。`\sqrtsign` 符号不能与 `\left`、`\right` 或 `\middle` 一起使用。*

> *同义词：[ - `\lbrack`，`[`；] - `\rbrack`，`]`；{ - `\lbrace`，`\{`；} - `\rbrace`，`\}`；| - `\vert`，`|`；|| - `\Vert`，`\|`。*

这些符号仅在某些用法中才能扩展。它们必须基于以下结构：

```tex
\left <ext-Open> <sub-formula> \right <ext-Close>
```

> 如果 LaTeX 使用 eTeX 程序，那么您也可以通过 `\middle` 使用这些可扩展符号。

此处`<Ext-open>`和`<Ext-close>`可以是上表中列出的任何符号(除\ sqrtsign`除外)。它们必须是已设置为可扩展的符号，如[FNTGUIDE]中所述(33)。因此，必须可用代表不存在实际字形的符号。碰巧的是，这个符号，也称为 *null Delimiter *，是(。)。选择排列的实际字形的大小可与可扩展的符号选择以适合其位于它们之间的高高和深度。

激进符号`\sqrtsign`垂直和水平生长以适合其参数的大小。在乳胶中，您宁愿使用`\sqrt`命令来获取此符号。


```tex
\[
  \sqrtsign{1 + \sqrtsign{1 + \sqrtsign{1 +
    \sqrtsign{1 + \sqrtsign{1 + \sqrtsign{1 + x}}}}}}
\]
```

![扩展自由基](/tex/images/java/tutorial/latex-ams-math-5-24.png)