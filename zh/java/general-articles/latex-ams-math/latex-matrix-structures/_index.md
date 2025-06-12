---
translation: true
template: /templates/_template-java.md
linktitle: 矩阵和类似环境
title: 3. 矩阵和类似环境|乳胶手册
weight: 30
url: /java/latex-ams-matrix/
keywords: AMS-LATEX，AMSMATH，AMSCD，乳胶矩阵，乳胶案例，乳胶delarray，乳胶交换图
description: 本文简要介绍了使用AMS-LATEX软件包排版类似乳胶矩阵的结构。
lastmod: "2025-06-10"
---

{{<section overview>}}

`amsmath` 包中定义了许多用于排版矩阵结构的环境。它们在语法和布局上都与标准 LaTeX 的“array”环境类似。通常，各种二维数学结构和表格布局都可以用数组来描述。

三种环境——`cases`、`matrix`和`pmatrix`——取代了标准 LaTeX 的命令。标准命令使用不同的符号，因此它们不能与此处讨论的环境形式一起使用。如果使用旧命令之一，`amsmath`’ 包将生成错误消息。相反，如果您尝试在未加载包的情况下使用`amsmath` 环境形式，则很可能会收到以下错误消息：“对齐制表符 & 位置错误”。


## 3.1. 案例环境

`case`环境用于处理构造，其中单个方程式具有一些变体。这种结构在数学中非常普遍。它产生一个带有两个列的数组，均为左对齐。


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

![案例环境](/tex/images/java/tutorial/latex-ams-math-3-1.png)

请注意，文本字符串中的“ \ text”命令和“嵌入式数学模式”的使用。

## 3.2. 矩阵环境

与乳胶的“数组”不同，矩阵环境不接受指定列格式的参数。相反，它们提供默认格式：最多10个中心列。间距也与“数组”中的默认值略有不同。以下示例说明了“矩阵”，`pmatrix`，`bmatrix`，`bmatrix`，`vmatrix`和`vmatrix`环境。


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather*}
\begin{matrix} 0 & 1 \\ 1 & 0 \end{matrix} \quad \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix} \\
\begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix} \quad \begin{Bmatrix} 1 & 0 \\ 0 & -1 \end{Bmatrix} \\
\begin{vmatrix} a & b \\ c & d \end{vmatrix} \quad \begin{Vmatrix} i & 0 \\ 0 & -i \end{Vmatrix}
\end{gather*}
```

![矩阵环境](/tex/images/java/tutorial/latex-ams-math-3-2.png)

“ maxmatrixcols”计数器确定矩阵环境中的最大列数。您可以使用乳胶的标准计数器命令更改它。 `\ arraycolsep`长度参数的值确定列之间的空间量。就像在标准数组中一样，但数组的两侧都没有添加空间。更多的列将使乳胶更加努力，并需要更多的资源。但是，将“ maxmatrixcols”设置为20或更高的情况是可能的，没有明显的性能，因为当今典型的TEX实现，这种限制并不重要。


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

![矩阵环境中的更多列](/tex/images/java/tutorial/latex-ams-math-3-3.png)

在此示例中，`\ hdotsfor`命令用于在矩阵中产生一排点，跨越给定数量的列。可选参数(此处2)可用于指定点之间默认空间(3个数学单元)的乘数。薄的空间和支撑组`\，{}`在每一行的末端，只需使布局看起来更好；它们共同产生两个薄空间，约6mu或1/3em。

为了产生用于文本的小内联矩阵，您可以使用`smallmatrix“环境。


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
To show the effect of the matrix on surrounding lines inside a paragraph, we put it here:
$ \left( \begin{smallmatrix}
1 & 0 \\ 0 & -1
\end{smallmatrix} \right) $
and follow it with enough text to ensure that there is at least one full line below the matrix.
```

![小型木质环境](/tex/images/java/tutorial/latex-ams-math-3-4.png)

请注意，即使小矩阵之前的线包含带有后代的字母，文本行也不会分开。

## 3.3. 堆放下标和上标

有时您可能需要在下标或上标中排版多行。为此，您可以使用 `\substack` 命令，并用 `\\` 分隔行。

`subarray` 环境是一种更通用的结构，允许您将行左对齐或右对齐，而不是居中对齐。


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

![在子和上刻录中堆叠](/tex/images/java/tutorial/latex-ams-math-3-5.png)

> 请注意，当两个环境以下标或上标形式出现时，都需要用括号括起来。

## 3.4. 交换图
“ AMSCD”软件包定义了一些基于数组制作简单通勤图的命令。有一些有用的速记表格用于指定装饰的箭头和其他连接器。但是，它具有局限性 - 例如，这些连接器只能是水平或垂直的。

在 `CD` 环境中，符号 `@>>>`、`@<<<`、`@VVV` 和 `@AAA` 分别表示向右、向左、向下和向上的箭头。以下示例还展示了 `\DeclareMathOperator` 命令的用法。


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

![简单的交换图](/tex/images/java/tutorial/latex-ams-math-3-6.png)

让我们看看如何指定装饰。对于水平箭头，第一个和第二个 `>` 或 `<` 符号之间的内容将被排版为上标，而第二个和第三个之间的内容将被排版为下标。同样，垂直箭头的第一个和第二个，或第二个和第三个 `A` 或 `V` 之间的内容将被排版为左侧或右侧的“侧标”。我们将在下一个示例中看到这种格式的用法。

符号`@=`和`@|'给出水平和垂直双线。

您可以使用“ null Arrow”(`@。)而不是可见的箭头，在需要时填写数组。


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

![带有脚本的交换图](/tex/images/java/tutorial/latex-ams-math-3-7.png)

可以在标准乳胶中产生类似的布局。但这看起来不太好。


```tex
\[\begin{array}{ccc}
S^{\mathcal{W}_\Lambda}\otimes T & \stackrel{j}{\longrightarrow} & T \\
\Big\downarrow & & \Big\downarrow\vcenter{\rlap{$\scriptstyle{\mathrm{End}}\,P$}} \\
(S\otimes T)/I & = & (Z\otimes T)/J
\end{array}\]
```

![标准乳胶中的交换图](/tex/images/java/tutorial/latex-ams-math-3-8.png)

该示例很清楚地显示了“ AMSCD”软件包产生的结果多么好：符号更容易，水平箭头更长，元素之间的间距大大提高。更专业的软件包将帮助您取得更加美丽的效果。

## 3.5. 阵列周围的分隔器：“ Delarray”软件包

在本节中，我们将讨论“数组”软件包的有用的一般扩展。使用此扩展程序，用户可以指定开放和关闭可扩展的分界符，以包围数学“数组”环境。让我们看一下示例：


```tex
\usepackage{delarray}
% -------------------------------------------------------------------------------
\[ \mathcal{Q} =
\begin{array}[t] ( {cc} ) X & Y \end{array}
\begin{array}[t] [ {cc} ] A & B \\ C & D \end{array}
\begin{array}[b] \lgroup{cc}\rgroup L \\ M \end{array}
\]
```

![使用delarray软件包](/tex/images/java/tutorial/latex-ams-math-3-9.png)

> 请注意，`delarray` 包独立于 `amsmath`，但如果需要，它会自动加载 `array` 包。
将定界器放在{cc}`的两侧。

此示例还演示了 `delarray` 包最有用的特性：`[t]` 和 `[b]` 可选参数的使用，而 `amsmath` 的矩阵环境不允许使用这些参数。这表明，使用 `delarray` 语法并不等同于用 `\left` 和 `\right` 包围 `array` 环境，因为分隔符和数组本身都会被提升。