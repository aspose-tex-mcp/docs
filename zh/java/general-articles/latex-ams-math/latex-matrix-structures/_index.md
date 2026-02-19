---
translation: true
template: /templates/_template-java.md
linktitle: 矩阵及类似环境
title: 3. 矩阵及类似环境
weight: 30
url: /java/latex-ams-matrix/
keywords: ams-latex, amsmath, amscd, latex matrix, latex cases, latex delarray, latex commutative diagrams
description: 本文简要介绍使用 AMS‑LATEX 包排版 LaTeX 矩阵类结构的方法。
lastmod: "2026-02-19"
---

{{<section overview>}}

`amsmath` 包中定义了若干用于排版矩阵类结构的环境。它们在语法和布局上都类似于标准 LaTeX 的 `array` 环境。一般来说，各种二维数学结构和表格布局都可以用数组来描述。

三种环境 — `cases`、`matrix` 和 `pmatrix` — 替代了标准 LaTeX 的相应命令。标准命令使用不同的记法，因而不能与这里介绍的环境形式混用。若使用旧的命令，`amsmath` 包会产生错误信息。相反，如果在未加载该包的情况下尝试使用 `amsmath` 环境形式，最常见的错误信息是：`"Misplaced alignment tab character &"`。

## 3.1. `cases` 环境

`cases` 环境用于处理单个方程有多个变体的情形，这类构造在数学中非常常见。它生成一个两列的数组，且两列左对齐。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
P_{r - j} = \begin{cases}
                     0 & \text{if $r - j$ is odd,} \\
r! \, (-1)^{(r - j)/2} & \text{if $r - j$ is even.}
\end{cases}
\end{equation}
```

![Cases environment](/tex/images/java/tutorial/latex-ams-math-3-1.png)

请注意 `\text` 命令的使用以及文字串中的“嵌入数学模式”。

## 3.2. 矩阵环境

矩阵环境与 LaTeX 的 `array` 不同，它们不接受指定列格式的参数，而是提供默认格式：最多 10 列居中对齐。其间距也略有不同于 `array` 的默认设置。下面的示例演示了 `matrix`、`pmatrix`、`bmatrix`、`Bmatrix`、`vmatrix` 和 `Vmatrix` 环境。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather*}
\begin{matrix} 0 & 1 \\ 1 & 0 \end{matrix} \quad \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix} \\
\begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix} \quad \begin{Bmatrix} 1 & 0 \\ 0 & -1 \end{Bmatrix} \\
\begin{vmatrix} a & b \\ c & d \end{vmatrix} \quad \begin{Vmatrix} i & 0 \\ 0 & -i \end{Vmatrix}
\end{gather*}
```

![Matrix environments](/tex/images/java/tutorial/latex-ams-math-3-2.png)

`MaxMatrixCols` 计数器决定矩阵环境中列的最大数量。可以使用 LaTeX 的标准计数器命令进行修改。`\arraycolsep` 长度参数的值决定列之间的间距。和普通数组一样，数组两侧不会额外添加间距。更多列会增加 LaTeX 的工作负担并占用更多资源。不过，将 `MaxMatrixCols` 设置为 20 或更高是可行的，且对现代 TeX 实现来说几乎没有性能影响。

```tex
\usepackage{amsmath}
\setcounter{MaxMatrixCols}{20}
% -------------------------------------------------------------------------------
\[
\begin{Vmatrix}
\,a&b&c&d&e&f&g&h&i&j &\cdots\,{} \\
&a&b&c&d&e&f&g&h&i &\cdots\,{} \\
& &a&b&c&d&e&f&g&h &\cdots\,{} \\
& & &a&b&c&d&e&f&g &\cdots\,{} \\
& & & &\ddots&\ddots&\hdotsfor[2]{5}\,{}
\end{Vmatrix} \]
```

![More columns in matrix environments](/tex/images/java/tutorial/latex-ams-math-3-3.png)

在本例中使用 `\hdotsfor` 命令生成跨越若干列的点阵行。可选参数（此处为 2）用于指定默认间距（3 个数学单位）之间的倍数。行末的细间距 `\,{}` 与大括号组仅用于美化布局；它们一起产生约 6mu（或 1/3 em）的细间距。

若要在文本中使用小型行内矩阵，可使用 `smallmatrix` 环境。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
To show the effect of the matrix on surrounding lines inside a paragraph, we put it here:
$ \left( \begin{smallmatrix}
1 & 0 \\ 0 & -1
\end{smallmatrix} \right) $
and follow it with enough text to ensure that there is at least one full line below the matrix.
```

![The smallmatrix environment](/tex/images/java/tutorial/latex-ams-math-3-4.png)

请注意，尽管小矩阵所在行前的文字包含下沉字符，文本行仍保持原样，没有被拉开。

## 3.3. 在下标和上标中堆叠

有时需要在下标或上标中排版多行。可以使用带有 `\\` 换行的 `\substack` 命令。

`subarray` 环境稍微更通用，允许将行左对齐或右对齐，而不是居中。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
\sum_{\substack{0 \le i \le m \\ 0 < j < n}} P(i, j) \\
\sum_{\begin{subarray}{l}
i \in \Lambda \\
0 \le i \le m \\
0 < j < n
\end{subarray}} P(i, j)
\end{gather}
```

![Stacking in sub- and superscripts](/tex/images/java/tutorial/latex-ams-math-3-5.png)

> 注意：这两个环境在作为下标或上标出现时必须用大括号包裹。

## 3.4. 交换图（Commutative diagrams）

`amscd` 包提供了一些用于基于数组生成简易交换图的命令。它提供了若干简写形式来指定装饰箭头及其他连线。但该包有局限性——例如，只能绘制水平或垂直的连线。

在 `CD` 环境中，记号 `@>>>`、`@<<<`、`@VVV`、`@AAA` 分别生成向右、向左、向下和向上的箭头。下面的示例还演示了 `\DeclareMathOperator` 命令的使用。

```tex
\usepackage{amsmath,amscd}
\DeclareMathOperator\add{add}
\DeclareMathOperator\cf {cf}
\DeclareMathOperator\cov{cov}
\DeclareMathOperator\non{non}
% -------------------------------------------------------------------------------
\[ \begin{CD}
\cov (L) @>>> \non (K) @>>> \cf (K) \\
@VVV @AAA @AAA \\
\add (L) @>>> \add (K) @>>> \cov (K) \\
\end{CD} \]
```

![Simple commutative diagram](/tex/images/java/tutorial/latex-ams-math-3-6.png)

下面说明如何指定装饰。对于水平箭头，第一次和第二次 `>`（或 `<`）之间的内容会被排成上标，第二次和第三次之间的内容会被排成下标。类似地，垂直箭头中第一次和第二次、第二次和第三次 `A`（或 `V`）之间的内容会被排成左/右侧标（side‑script）。下例将展示这种格式的实际使用。

记号 `@=` 与 `@|` 分别产生水平和垂直的双线。

如果不想显示实际的箭头，可以使用 “空箭头” `@.` 来填充需要的数组位置。

```tex
\usepackage{amsmath, amscd}
\DeclareMathOperator{\End}{End}
% -------------------------------------------------------------------------------
\[ \begin{CD}
S^{W_\Lambda}\otimes T @>j>> T \\
@VVV @VV{\End P}V \\
(S \otimes T)/I @= (Z\otimes T)/J
\end{CD} \]

```

![Commutative diagram with scripts](/tex/images/java/tutorial/latex-ams-math-3-7.png)

相同的布局也可以用标准 LaTeX 实现，但效果不佳。

```tex
\[\begin{array}{ccc}
S^{\mathcal{W}_\Lambda}\otimes T & \stackrel{j}{\longrightarrow} & T \\
\Big\downarrow & & \Big\downarrow\vcenter{\rlap{$\scriptstyle{\mathrm{End}}\,P$}} \\
(S\otimes T)/I & = & (Z\otimes T)/J
\end{array}\]
```

![Commutative diagram in standard LaTeX](/tex/images/java/tutorial/latex-ams-math-3-8.png)

本例清楚地说明了 `amscd` 包能够产生更好结果的原因：语法更简洁，水平箭头更长，元素间距也有显著提升。更专业的宏包还能帮助你实现更精美的排版。

## 3.5. 用 `delarray` 包为数组加定界符

本节介绍 `array` 包的一个实用扩展——`delarray`。使用该扩展，用户可以为数学 `array` 环境指定可伸缩的左、右定界符。下面给出一个示例：

```tex
\usepackage{delarray}
% -------------------------------------------------------------------------------
\[ \mathcal{Q} =
\begin{array}[t] ( {cc} ) X & Y \end{array}
\begin{array}[t] [ {cc} ] A & B \\ C & D \end{array}
\begin{array}[b] \lgroup{cc}\rgroup L \\ M \end{array}
\]
```

![The use of the delarray package](/tex/images/java/tutorial/latex-ams-math-3-9.png)

> 注意：`delarray` 包独立于 `amsmath`，但若有需要会自动加载 `array` 包。

定界符位于 `{cc}` 两侧。

该示例还展示了 `delarray` 包最有用的功能之一：`[t]` 与 `[b]` 可选参数，这在 `amsmath` 的矩阵环境中是不被允许的。这表明 `delarray` 的语法并不等同于在 `array` 环境外使用 `\left` 与 `\right`，因为定界符会随数组本身一起提升。
