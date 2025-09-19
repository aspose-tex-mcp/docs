---
translation: true
template: /templates/_template-java.md
linktitle: 简单公式
title: 1. 简单公式|乳胶手册
weight: 10
url: /java/latex-math-simple-formulas/
keywords: 乳胶，乳胶数学公式，乳胶数学，乳胶数学字母，乳胶希腊字母，乳胶编号
description: 本文讨论了如何与Tex和latex创建简单的原子数学表达式。
lastmod: "2025-06-10"
---

{{<section overview>}}

最简单的公式是单个字母“*x*”或单个数字“4”。要在 LaTeX 文本中插入此类公式，请分别输入“$x$”或“$4$”。所有数学公式都括在特殊的数学括号（“$”）。

当您输入 `$x$` 时，'*x*' 会以斜体显示，但 `$2$` 则会以罗马字体显示为 '2'。通常，根据数学打印的常规惯例，键盘上的所有字符在数学公式中都有特殊的解释。字母表示斜体字母，而数字和标点符号表示罗马数字和标点符号。连字符 (-) 表示减号。左侧 `$` 会将 TeX 置于“数学模式”，而右侧 `$` 会将其关闭。因此，如果您忘记了一个 `$` 或多输入了一个 `$`，您可能会收到一条错误消息，因为 TeX 会感到困惑。

TeX 在数学公式中自行处理大部分空格。同时，它会忽略 `$` 之间的任何空格。您可以输入 `$(x + y)/(x - y)$` 或 `$(x+y) / (x-y)$`，但这两种方式都会生成一个公式 ![单字符下标和上标](/tex/images/java/tutorial/latex-math-1-1.png)，其中 '+' 和 '-' 符号周围有一些额外的空格，但 '/' 符号周围没有空格。因此，您不必记住复杂的数学空格规则，可以随意使用空格。当需要标记控制序列（命令）的结尾时，空格仍按正常方式使用。在大多数情况下，TeX 的空格可以满足数学家的期望；但是如果您想覆盖 TeX 的间距规则，您可以使用控制序列来实现，我们稍后会讨论。

数学公式中常见的一种用法是使用希腊字母。在 LaTeX 中，您可以输入 `$\alpha, \beta, \gamma, \delta$` 来获取前四个希腊字母。例如，`$\Gamma$` 会生成大写的 gamma 字母。不要将希腊字母 `\kappa` 和 `\nu` 与斜体字母 *v* 和 *x* 混淆；希腊字母 `\phi` 与斜线零 `\emptyset` 不同。小写字母 `\epsilon` 与表示集合成员的符号不同。一些小写希腊字母在 LaTeX 斜体字体中有不同的形式：`$\phi, \theta, \epsilon, \rho$` 产生 ![单字符下标和上标](/tex/images/java/tutorial/latex-math-1-2.png)，而`$\varphi, \vartheta, \varepsilon, \varrho$` 产生 ![单字符下标和上标](/tex/images/java/tutorial/latex-math-1-3.png)

除了希腊字母外，还有很多数学符号，例如“近似等于”（“$\approx$”）和“映射到”（“$\mapsto$”）。您可以在[此处](/tex/{{lang.url-fragment}}java/latex-math-symbols-commands/)找到这些控制序列及其对应符号的完整列表。