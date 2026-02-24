---
translation: true
template: /templates/_template-java.md
linktitle: 大型运算符
title: 6. LaTeX 大型运算符
weight: 60
url: /java/latex-math-large-operators/
keywords: latex、latex 数学公式、latex 数学、latex 数学大型运算符、latex 求和、latex 积分
description: 本文讨论如何使用 TeX 和 LaTeX 构建包含求和、积分等大型运算符的数学公式。
lastmod: "2026-02-24"
---

{{<section overview>}}

在数学中，有一些符号表示例如“求和”或“积分”运算。它们被称为“大算子”，你可以像输入普通符号和字母一样输入它们。不同之处在于，TeX 会在 **display**（显示）模式下为大算子选择更大的符号，而在 **text**（文本）模式下则使用较小的符号。

![Summation and integration without super/subscripts](/tex/images/java/tutorial/latex-math-6-1.png)

一个显示的 `\sum` 通常会带有“上下标”，即出现在它上方和下方的子公式。上下标应像下标和上标一样输入；
`$\sum_{n=1}^m$` 或 `$\sum^m_{n=1}$` 都会产生

![Summation with limits](/tex/images/java/tutorial/latex-math-6-2.png)

数学排版的常规约定认为，上述公式在 **text**（文本）中出现时应改为

![Summation without limits](/tex/images/java/tutorial/latex-math-6-3.png)

（即不带上下标），而 TeX 会遵循这些约定。

即使在 **display**（显示）模式下，积分符号的上标和下标也不会被设为上下限：

![Integration in text and in a display](/tex/images/java/tutorial/latex-math-6-4.png)

如果将上标和下标设为上下限，当子公式比较复杂时会有更好的外观，尽管会占用更多的版面空间。你可以在 `\int`、`\sum` 或其他算子后立即键入 `\limits` 来强制 TeX 以这种方式处理公式，而不管子公式将使用何种样式。另一方面，显示的求和符号有时并不需要上下限。你可以在大算子后键入 `\nolimits` 来改变 TeX 的默认约定。

![Forcing limits and no limits for summation and integration](/tex/images/java/tutorial/latex-math-6-5.png)

如果你写 `\nolimits\limits`（例如，某些宏如 `\int` 默认使用 `\nolimits`），则最后一个命令生效。`\displaylimits` 命令可用于恢复 TeX 的常规约定；即仅在 *D* 和 *D'* 样式下显示上下限。

如果需要在大算子下方放置多行上下限，可以使用 `\atop`。下面公式的正确写法是

```tex
$\sum_{\scriptstyle0\le i\le m\atop\scriptstyle0<j<n}P(i,j)$.
```

![Multi-row limits under the summation sign](/tex/images/java/tutorial/latex-math-6-6.png)

这里需要使用 `\scriptstyle` 命令，否则两行上下限都会被渲染为 `scriptscript` 大小，太小了。这是另一种需要覆盖 TeX 样式规则的少见情况。
