---
translation: true
template: /templates/_template-java.md
linktitle: S简单公式
title: 1. 简单公式
weight: 10
url: /java/latex-math-simple-formulas/
keywords: latex、latex 数学公式、latex 数学、latex 数学字母、latex 希腊字母、latex 数字
description: 本文讨论如何使用 TeX 和 LaTeX 创建用于更复杂公式的简单原子数学表达式。
lastmod: "2026-02-24"
---

{{<section overview>}}

最简单的公式是单个字母 `*x*` 或单个数字 `4`。要在 LaTeX 文本中插入这样的公式，只需输入 `$x$` 或 `$4$`。

所有数学公式都被包裹在特殊的数学括号（`$...$`）中。

当你输入 `$x$` 时，*x* 会以斜体显示，而 `$2$` 则会以罗马体（正常字体）显示数字 2。

通常情况下，键盘上的所有字符在数学公式中都有特殊的解释，遵循数学排版的常规约定。字母会以斜体显示，数字和标点符号则以罗马体显示。连字符（-）表示减号。左侧的 `$` 将 TeX 切换到“数学模式”，右侧的 `$` 将其切出。因此，如果忘记了其中一个 `$`，TeX 很可能会报错，因为会产生混乱。

或者输入额外的 `\$` 来输出文字形式的美元符号。

TeX 会自行处理大多数数学公式中的间距。同时，它会忽略你在公式内部放置的空格。你可以写 `$(x + y)/(x - y)`，或者写成 `$(x+y) / (x-y)`。

这两种写法都会生成一个公式 ![Single-character subscripts and superscripts](/tex/images/java/tutorial/latex-math-1-1.png)，在 `+` 和 `-` 符号两侧会有一些额外的空白，而 `/` 符号两侧则没有。因此，你不必记住复杂的数学间距规则，完全可以随意使用空格。当需要标记控制序列（命令）的结束时，空格仍然按照常规使用。在大多数情况下，TeX 的间距符合数学家的期望；但如果你想覆盖 TeX 的间距规则，可通过控制序列来实现，稍后我们会讨论。

在数学公式中常见的一件事是使用希腊字母。在 LaTeX 中，你可以输入 `$\alpha, \beta, \gamma, \delta` 来得到前四个希腊字母。`\Gamma` 会产生大写的伽马字母。

不要把希腊字母 `\kappa`、`\nu` 与斜体字母 *v*、*x* 混淆；希腊字母 `\phi` 与斜杠零 `\emptyset` 是不同的。小写的 `\epsilon` 与表示集合成员关系的符号不同。某些小写希腊字母在 LaTeX 斜体字体中有变体形式：`$\phi, \theta, \epsilon, \rho` 会显示如下：

![]( /tex/images/java/tutorial/latex-math-1-2.png)

而 `$\varphi, \vartheta, \varepsilon, \varrho` 会显示如下：

![]( /tex/images/java/tutorial/latex-math-1-3.png)

除了希腊字母之外，还有许多数学符号，例如“约等于”（`$\approx`）和“映射到”（`$\mapsto`）。

你可以在[这里](/tex/{{lang.url-fragment}}java/latex-math-symbols-commands/)找到这些控制序列及其对应符号的完整列表。
