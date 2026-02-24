---
translation: true
template: /templates/_template-java.md
linktitle: 分隔符
title: 7. 分隔符 | LaTeX 手册
weight: 70
url: /java/latex-math-delimiters/
keywords: LaTeX、LaTeX 数学公式、LaTeX 数学、LaTeX 数学分隔符、LaTeX 数学花括号、LaTeX 数学圆括号
description: 本文讨论如何使用不同类型的分隔符将公式逻辑地划分为子公式。
lastmod: "2026-02-24"
---

{{<section overview>}}

无论数学公式多么庞大，TeX 都知道如何将某些符号放大到合适的外观。例如，输入以下内容的结果是

```tex
$\sqrt{1+\sqrt{1+\sqrt{1+
            \sqrt{1+\sqrt{1+\sqrt{1+\sqrt{1+x}}}}}}}$
```

展示了各种可用的根号（或平方根）符号：

![不同大小的根号](/tex/images/java/tutorial/latex-math-7-1.png)

这里的三个最大符号是相同的，只是垂直段会根据需要重复以达到所需的大小。同时，较小的符号是取自 TeX 数学字体的不同字符。

类似的情况也会出现在括号等所谓的“分隔符”符号上。这类符号在数学中很重要，因为它们为复杂表达式的底层结构提供了可视化的提示。换句话说，它们限定了各个子公式的边界。下面是 LaTeX 提供的 22 种基本分隔符列表：

![LaTeX 中定义的 22 种基本分隔符](/tex/images/java/tutorial/latex-math-7-2.png)

若要让这些符号略微放大，只需分别输入 `\bigl` 或 `\bigr` 来表示左/右分隔符。这使得嵌套分隔符的公式更易阅读：

![使用 \big 分隔符的示例](/tex/images/java/tutorial/latex-math-7-3.png)

`\big` 分隔符比普通分隔符大一点，足以让差别可见，却又足够小，可用于段落文本中：

![\big 分隔符与普通分隔符的比较](/tex/images/java/tutorial/latex-math-7-4.png)

如果输入 `\Bigl` 和 `\Bigr` 而非 `\bigl`、`\bigr`，则可以得到更大一档、适合显示的符号：

![\Big 分隔符](/tex/images/java/tutorial/latex-math-7-5.png)

它们比上一步的版本高出 50%。在展示公式时常会使用更高的分隔符（相当于 `\big` 的两倍）。可以通过输入 `\biggl` 和 `\biggr` 来实现：

![\bigg 分隔符](/tex/images/java/tutorial/latex-math-7-6.png)

最后，你可以输入 `\Biggl` 和 `\Biggr`，其高度约为 `\bigl`、`\bigr` 的 2.5 倍：

![\Bigg 分隔符](/tex/images/java/tutorial/latex-math-7-7.png)

LaTeX 还提供 `\bigm`、`\Bigm`、`\biggm` 和 `\Biggm` 命令，用于生成可在公式中部使用的分隔符。此类分隔符表现为关系符号，TeX 会在其两侧留出一点空白：

![公式中部的分隔符](/tex/images/java/tutorial/latex-math-7-8.png)

也可以仅使用 `\big`、`\Big`、`\bigg` 或 `\Bigg` 来生成表现得像普通变量的分隔符。这些命令主要用于斜线和反斜线：

![普通的大号符号](/tex/images/java/tutorial/latex-math-7-9.png)

TeX 实现了一种算法，用于计算配对分隔符需要多高才能包围给定的子公式。你可以使用它，而不必自行决定使用 `\big`、`\bigg` 或其他。只需写

```tex
\left<delim1><subformula>\right<delim2>
```

TeX 将排版子公式，并在左侧和右侧放置指定的分隔符。分隔符的大小恰好足够覆盖子公式：

![由 \left 和 \right 命令设置的分隔符](/tex/images/java/tutorial/latex-math-7-10.png)

当使用 `\left` 和 `\right` 时，它们必须成对出现，就像大括号成组一样。不能在一个子公式中使用 `\left`，在另一个子公式中使用 `\right`。此外，也不能输入类似 `\left(...{...\right...}` 或 `\left(...\begingroup...\right)...\endgroup` 的内容。这是因为 TeX 必须先排版介于 `\left` 与 `\right` 之间的子公式，才能决定分隔符的大小。当不使用 `\left` 和 `\right` 时，括号和方括号不需要匹配。因此可以输入类似 `$[0,1)$` 的内容。

但是，当 TeX 能够自动计算 `\left` 和 `\right` 的大小时，为什么还要学习 `\bigl`、`\bigr` 等？事实上，有至少三种情况需要自行决定合适的分隔符大小：

(1) 只需比较下面的两个公式：

![使用竖线的 \left 和 \right 与 \bigl 和 \bigr 的比较](/tex/images/java/tutorial/latex-math-7-11.png)

事实上，使用 `\left` 和 `\right` 并不是明智的选择，因为它们无法算出最适合阅读的分隔符大小。

(2) 另一方面，有时 `\left` 和 `\right` 会选取比你需要的更大的分隔符。这通常发生在它们在展示模式下包围大型运算符时：

![使用求和符号的 \left 和 \right 与 \bigl 和 \bigr 的比较](/tex/images/java/tutorial/latex-math-7-12.png)

TeX 的算法会让 `\left` 和 `\right` 把 `\sum` 及其上下标一起包围，但在此类特殊情况下，让上下标稍微突出会更好。因此这里使用 `\bigg` 分隔符更合适。

(3) 当需要排版一个巨大的展示公式时，必须将其拆分为两行或多行，并且希望左右分隔符大小一致；但不能在第一行使用 `\left`、在最后一行使用 `\right`，因为 `\left` 和 `\right` 必须成对出现。唯一的解决办法是，例如在第一行使用 `\Biggl`，在最后一行使用 `\Biggr`。

> 虽然 `\left` 和 `\right` 通常可以生成任意大的分隔符，但斜线和尖括号有最大尺寸限制。如果请求非常大的这些符号，只会得到可用的最大尺寸。

你也可以使用一种技巧来生成所谓的空（空白）分隔符。当你需要排版的公式在视觉上只有一个大分隔符时，就需要这种分隔符。例如，

![案例中的空分隔符](/tex/images/java/tutorial/latex-math-7-13.png)

has '{' but no '}'. It can be produced by a construction of the form

```tex
$|x|=\left\{ ... \right.$ 
```

其中 `\right.` 生成右侧的空分隔符。

LaTeX 还提供了一些额外的分隔符，它们未列入 22 种基本集合，因为它们有些特殊。命令 `\arrowvert`、`\Arrowvert` 和 `\bracevert` 分别由垂直箭头、双垂直箭头和大大括号的可重复部分构成，不含箭头头部或大括号的弯曲部分。它们的效果类似于 `\vert` 和 `\Vert`，但间距更大且粗细不同。还有 `\lgroup` 与 `\rgroup`，由去除中间部分的大括号构成；以及 `\lmoustache` 与 `\rmoustache`，产生大括号的上半部和下半部。下面展示了使用 `\Big` 和 `\bigg` 版本的 `\vert`、`\Vert` 以及这七种特殊分隔符的效果：

![LaTeX 提供的额外分隔符](/tex/images/java/tutorial/latex-math-7-14.png)

可以看到，`\lgroup` 与 `\rgroup` 有点像加粗的圆括号，角部更为尖锐；这使得它们在某些大型展示中颇具吸引力。请注意，它们只能用于 `\Big` 及更大的尺寸，不能像普通括号那样随意使用。
