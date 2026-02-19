---
translation: true
template: /templates/_template-java.md
linktitle: 布局的预尺寸调整
title: 7. 布局的预尺寸调整
weight: 70
url: /java/latex-math-fine-tuning/
keywords: ams-latex、amsmath、latex 数学间距、latex 数学样式、latex 数学分隔符、latex 数学括号、latex 数学对齐
description: 本文讨论如何微调数学布局——自动调整大小和间距、使用大分隔符、精确对齐。
lastmod: "2026-02-19"
---

{{<section overview>}}

通常，LaTeX 能很好地排版数学公式。但有时需要对位置进行更细致的调整。本文讨论了一些微调布局的技巧，以使数学公式看起来更好一些。

## 7.1. 自动尺寸与间距

当数学符号和字母出现在分式、下标或上标中时，它们通常会变小（并且间距更紧）。数学公式可以使用八种 TeX 数学样式进行排版：

||||
|---|---|---|
| *D, D'* | `\displaystyle`| 单独一行显示 |
| *T, T'* | `\textstyle`| 嵌入正文 |
| *S, S'* | `\scriptstyle`| 在上标或下标中 |
| *SS, SS'* | `\scriptscriptstyle`| 在所有更高层级的上标或下标中 |

文本样式（*T*）用于在行文（`\( … \)` 或 `\(` 与 `\)` 之间）中的公式顶层，而显示样式用于显示公式的顶层（`$ … $` 或 `\[ … \]` 之间）。对于子公式，样式可以从下表确定：

||||||
|---|---|---|---|---|
| *D* | *S* | *S'* | *T* | *T'* |
| *D'* | *S'* | *S'* | *T'* | *T'* |
| *T* | *S* | *S'* | *S* | *S'* |
| *T'* | *S'* | *S'* | *S'* | *S'* |
| *S, SS* | *SS* | *SS'* | *SS* | *SS'* |
| *S', SS'* | *SS'* | *SS'* | *SS'* | *SS'* |

以下示例演示了各种样式：

```tex
\normalsize                 %% Style:
\[ b                        %% D
    ^0                      %% S
   +                        %% D
   \frac{(k + p)            %% T
          _{j'}             %% S'
         % \displaystyle
         \pm                %% T [D]
         \frac{(f + q)      %% S [T]
                ^{(pk)      %% SS [S]
                   ^y       %% SS
                   _{j'}}}  %% SS'
              {(h + y)}}    %% S' [T']
        {(l + q)            %% T'
          ^{(pk)}}          %% S'
\]
```

![Various math styles](/tex/images/java/tutorial/latex-ams-math-7-1.png)

您可以删除 `\displaystyle` 前的注释字符（`%`），观察括号中的样式如何改变：

![Explicitly changed math styles](/tex/images/java/tutorial/latex-ams-math-7-2.png)

它展示了如何显式指定每一部分使用的样式。

## 7.2. 子公式

在正文中，一对大括号表示一个组或作用域，其中的声明有效。在数学公式中，它们额外界定了一个子公式，子公式始终作为独立实体排版并加入外层公式。因此，子公式始终以自然宽度排版，TeX 在尝试将公式放入一行时不会在水平上拉伸或收缩它们。我们已经展示过，来自简单大括号组的子公式会被当作单个符号处理。这意味着空组会产生一个不可见的符号，从而改变间距。

下标/上标的内容以及许多（但不是全部）命令的参数，如 `\frac` 和 `\mathrel`，也是子公式。因此，它们会得到同样的特殊处理。例如，`\bm` 的参数并不一定作为子公式排版，这是一个重要的例外。在数学公式中，如果您只想限制声明的作用范围，请使用 `\begingroup` 和 `\endgroup` 定义一个组。请记住，专门的数学声明（如样式更改）会一直作用到当前子公式结束，无论是否还有其他组存在。

## 7.3. 大分隔符

LaTeX 定义了四个命令 — `\big`, `\Big`, `\bigg`, `\Bigg` — 用于直接控制可伸缩分隔符的大小。它们接受一个可伸缩分隔符作为唯一参数，并生成从 1.2 到 3 倍基准大小的更大版本。

每个命令还有三种变体，分别对应四种 *左符号*（`\bigl`, `\Bigl`, `\biggl`, `\Biggl`）、四种 *关系符号*（`\bigm`, `\Bigm`, `\biggm`, `\Biggm`）以及四种 *右符号*（`\bigr`, `\Bigr`, `\biggr`, `\Biggr`）。所有 16 种命令只能与能跟在 `\left`, `\right` 或（使用 eTeX 时）`\middle` 之后的符号一起使用（见此[table](/tex/{{lang.url-fragment}}java/latex-math-extensible-symbols#53-symbols-that-are-vertically-extensible)）。

在标准 LaTeX 中，这些分隔符的大小是固定的。然而，使用 `amsmath` 包时，大小会根据周围材料的字体大小和数学样式自动适应。下面的例子展示了这一点。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\[ \biggl( \mathbf{E}_{y} \int_0^{t_\varepsilon}
   L_{x, y^x(s)} \varphi(x)\, ds \biggr) \]
\Large
\[ \biggl( \mathbf{E}_{y} \int_0^{t_\varepsilon}
   L_{x, y^x(s)} \varphi(x)\, ds \biggr) \]
```

![Delimiters adapting to the current font size and math style](/tex/images/java/tutorial/latex-ams-math-7-3.png)

## 7.4. 调整根号指数的位置

在标准 LaTeX 中，根号符号上的指数位置并不总是很好。不过，您可以使用 `amsmath` 包中定义的 `\leftroot` 和 `\uproot` 命令来调整该指数的位置。正整数参数会分别将指数向左和向上移动，负数参数则向右和向下移动。这些参数的单位是数学单位（非常小），因此这些命令非常适合用于细微调节。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\[
  \sqrt[\beta]{k} \qquad
  \sqrt[\leftroot{2}\uproot{4} \beta]{k} \qquad
  \sqrt[\leftroot{1}\uproot{3} \beta]{k}
\]
```

![Adjusting the index of a radical sign](/tex/images/java/tutorial/latex-ams-math-7-4.png)

## 7.5. 使用 strut 和 phantom 进行微调

每当您想要“完美”地排版数学间距和对齐时，通常最好利用 TeX 原始的独特且高级的功能。这些功能通过一系列与 `\phantom` 和 `\smash` 相关的命令提供。它们既可以在数学公式中使用，也可以在正文中使用。

下面来看一个示例：

```tex
\usepackage{amsmath}
\newcommand\relphantom[1]{\mathrel{\phantom{#1}}}
\newcommand\ve{\varepsilon} \newcommand\tve{t_{\varepsilon}}
\newcommand\vf{\varphi} \newcommand\yvf{y_{\varphi}}
\newcommand\bfE{\mathbf{E}}
% -------------------------------------------------------------------------------
\begin{equation} \begin{split}
  f_{h, \ve}(x, y)
    &= \ve \bfE_{x, y} \int_0^{\tve} L_{x, \yvf(\ve u)} \vf(x) \,du  \\
    &= h \int L_{x, z} \vf(x) \rho_x(dz)                             \\
    &\relphantom{=} {} + h \biggl[
       \frac{1}{\tve}
       \biggl( \bfE_{y} \int_0^{\tve}  L_{x, y^x(s)} \vf(x) \,ds
               - \tve \int L_{x, z} \vf(x) \rho_x(dz)      \biggr) + \\
    &\relphantom{=} \phantom{{} + h \biggl[ }
       \frac{1}{\tve}
       \biggl( \bfE_{y} \int_0^{\tve}  L_{x, y^x(s)} \vf(x) \,ds
               - \bfE_{x, y} \int_0^{\tve} L_{x, \yvf(\ve s)}
                                            \vf(x) \,ds    \biggr) \biggr]
\end{split} \end{equation}
```

![The phantoms of the formula](/tex/images/java/tutorial/latex-ams-math-7-5.png)

这里，`\phantom` 命令用于调整水平定位。在导言区，它被用来定义一个宽度等于其参数（这里为 `=`）的不可见关系符号。在数学环境中，它用于通过在行首放置一个“幽灵”或不可见的子公式来对齐特定行。空的大括号 `{}` 等同于 `\mathord{}`，会生成一个不可见的零宽度符号，用于让 `+ h` 前的间距正确（如果没有 `{}`，加号会被解释为一元加号，前面的间距会不合适）。

与 `\phantom` 相对，`\smash` 命令会把内容（放在 LR‑box 中）排版，但随后忽略它们的高度和宽度，好像它们的高度和宽度都是零。`\hphantom` 是标准 LaTeX 中的一个组合命令，相当于 `\smash{\phantom{some phantom contents}}`，即生成一个高度为零、宽度为 phantom 内容宽度的不可见框。

`\vphantom` 类似，但它保持整体高度加深度不变，只把宽度设为零。`\mathstrut` 被定义为 `\vphantom(`，产生一个高度和深度与左括号相同、宽度为零的框。

使用 `amsmath` 包时，`\smash` 命令可以接受可选参数，使得 `\smash[t]{...}` 只忽略高度而保留深度，`\smash[b]{...}` 只忽略深度而保留高度。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
$\sqrt{x} + \sqrt{y} + \sqrt{z}$ \\
$\sqrt{x} + \sqrt{\mathstrut y} + \sqrt{z}$ \\
$\sqrt{x} + \sqrt{\smash{y}} + \sqrt{z}$ \\
$\sqrt{x} + \sqrt{\smash[b]{y}} + \sqrt{z}$
```

![Smashing the radical expression](/tex/images/java/tutorial/latex-ams-math-7-6.png)

看起来给 *y* 加一点额外的高度（使用 strut）会让根号看起来更相似。但实际上，它只会让它们看起来更不一致，整体更丑。事实证明，压扁 *y* 的底部是最好的办法。

下面的例子展示了一个非常常见的使用场景：`\smash` 命令被用来对周围分隔符的高度进行细致控制。它也说明了当真实行高必须已知时，`\smash` 可能会导致问题，这时可以使用 `\vphantom` 来修复。`\Hmjd` 是这样定义的复合符号：

```tex
\newcommand\Hmjd{\widetilde{\mathcal{H}^2}_{MJD}(\chi)}
```

为显示产生的垂直空间，我们添加了规则：

| *Appearance* | `Code` | *Comment* |
|:---:|:---:|---|
| !["Outer Brackets Too Large"](/tex/images/java/tutorial/latex-ams-math-smashing-7-1.png) | `\left( {\Hmjd } \right)` | *外部括号太大* |
| !["Outer Brackets Too Small and Rules Too Close"](/tex/images/java/tutorial/latex-ams-math-smashing-7-2.png) | `\left( \smash{\Hmjd } \right)` | *外部括号太小且规则太近* |
| !["Just Right"](/tex/images/java/tutorial/latex-ams-math-smashing-7-3.png) | `\left( \smash[t]{\Hmjd } \right) \vphantom{\Hmjd}` | *刚好合适！* |
| !["Both Vphantom and Partial Smash Needed"](/tex/images/java/tutorial/latex-ams-math-smashing-7-4.png) | `\left( \smash[t]{\Hmjd } \right)` | *需要同时使用 `\vphantom` 和部分压扁* |

> 在少数情况下，低层次的 TeX 处理可能会在细节排版上出现错误。尤其是在以下布局中会出现： (a) 子公式（分式的分子/分母或上下标）恰好是唯一的 LR‑box，或类似构造的数学盒子；以及 (b) 该盒子并未拥有其自然尺寸，例如更复杂的 `\makebox`、压扁和某些 phantom。

为了看到这一点，我们来看下面的例子：

```tex
\[
\sqrt{ \frac{a+b}{x_j} } \quad
\sqrt{ \frac{a+b}{\smash{x_j}} } \quad
\sqrt{ \frac{a+b}{{}\smash{x_j}} } \quad
\sqrt{ \frac{a+b}{\smash{x_j+b}} }
\]
```

![Problems caused by smashes](/tex/images/java/tutorial/latex-ams-math-7-7.png)

为了降低根号的深度，在第二个根号里加入了 `\smash`，但没有效果。第三个根号使用了空的大括号组后起效。但在第四个根号中根本不需要空的大括号组。总之，当 `\smash` 无效时，尝试在孤立的盒子前加一个空的数学子公式（`{}`），以促使正确处理。

## 7.6. 水平间距

更细致且更困难的调节需要使用下表所示的显式间距命令：

![Horizontal spacing commands](/tex/images/java/tutorial/latex-ams-math-7-8.png)

这些命令的全称和简写形式都很稳健，且可以在数学公式之外的普通文本中使用。它们与上世纪中叶用于排版数学的机器上可用的细、中、粗空间有关。

三个 TeX 参数 `\thinmuskip`、`\medmuskip` 和 `\thickmuskip` 的当前值决定了这些 `\..space` 命令所添加的空间量。它们在使用 `amsmath` 时的默认值列在表中。这些低层参数的取值必须使用数学单位（*mu*）给出，不能通过 `\setlength` 或类似方式设置。此外，通常不应修改它们的取值，因为 TeX 的数学排版内部会使用它们（见下表）。

![Spacing between symbols](/tex/images/java/tutorial/latex-ams-math-7-9.png)

> 表中，0 表示“无间距”，1 表示 `\thinmuspace`，2 表示 `\medmuskip`，3 表示 `\thickmuskip`，* 表示“不可实现”。加粗的条目表示对应的间距在数学脚本样式中不会被添加。

一个数学单位（`1mu`）等于当前数学字体尺寸的 1/18 个 *em*。因此，`mu` 的绝对值会随数学样式而变化，从而在不同样式下保持一致的间距。
