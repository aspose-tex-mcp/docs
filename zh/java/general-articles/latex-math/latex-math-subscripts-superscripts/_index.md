---
translation: true
template: /templates/_template-java.md
linktitle: 下标和上标
title: 2. LaTeX 中的下标和上标
weight: 20
url: /java/latex-math-subscripts-superscripts/
keywords: latex、latex 数学公式、latex 数学、latex 数学下标、latex 数学上标、latex 撇号
description: 本文讨论如何使用 TeX 和 LaTeX 构建包含下标和上标的数学公式。
lastmod: "2026-02-24"
---

{{<section overview>}}

## 引言：LaTeX 中的上标和下标

**上标** 是一个小字符或符号，位于文本基线之上。例如，在表达式 `x²` 中，`2` 是上标。

**下标** 是一个小字符或符号，位于文本基线之下。例如，在水的化学式 `H₂O` 中，`2` 是下标。

## 如何在 LaTeX 中编写下标/上标

现在让我们尝试从简单的公式构建更复杂的公式。首先，你可以使用 `^` 和 `_` 来得到上标和下标，如下例所示：

![单字符下标和上标](/tex/images/java/tutorial/latex-math-2-1.png)

请注意，`^` 和 `_` 只作用于下一个字符。如果你想要更复杂的下标或上标，只需将其放在大括号中：

![多字符下标和上标](/tex/images/java/tutorial/latex-math-2-2.png)

这些示例中的大括号指定了“子公式”——更大公式的较小部分。TeX 为每个子公式创建一个盒子，并把该盒子视为单个符号。大括号同样用于常规的分组。

在 LaTeX 中，`^` 和 `_` 只能作用于后面的单个字符。如果你想要更复杂的下标或上标，需要把它们放在大括号中。例如，`$x^y^z$` 或 `$x_y_z$` 是非法的，因为 TeX 会报 “双下标” 或 “双上标” 的错误。你应该使用 `$x^{y^z}`、`$x^{yz}`、`$x_{y_z}` 或 `$x_{yz}` 来明确表达意图。

单个字符后面的上标或下标仅作用于该字符；但如果它们跟在一个子公式后面，则会作用于整个子公式，并相应地提升或降低位置。

![单个符号和子公式上的下标与上标](/tex/images/java/tutorial/latex-math-2-3.png)

## 在空的子公式上写下标或上标

有时你可能需要在空的子公式上添加下标或上标，以产生一些罕见的记号，例如 *<sub>2</sub>F<sub>3</sub>*。最好的做法是输入 `${}_2F_3`。

或者 `${_2}F_3`，再或者 `${_2F_3}`。

您也可以使用空的子公式来实现更复杂的排版需求。

## 同时出现的上下标

你还可以同时使用上下标，并且可以任意顺序指定它们：

![同时出现的上下标](/tex/images/java/tutorial/latex-math-2-4.png)

这些同时出现的“上下标”会相互叠加。不过，对于某些字母，下标会向左移动，并且这种移动在某些字母上会非常明显。比较下面的两个公式：

![同时出现的上下标对齐](/tex/images/java/tutorial/latex-math-2-5.png)

因此，如果你希望下标和上标对齐，可以使用第二个示例中展示的技巧。它同样利用了空的子公式。

## 在 LaTeX 中写 prime（撇号）

在数学公式中经常出现的符号是 prime。LaTeX 提供 `\prime` 命令，它会产生与普通字母大小相同的撇号。因此，你通常只会在上标或下标中使用它。但你也可以直接输入 `'` 来代替 `^\prime`，`''` 代替 `^\prime\prime`，依此类推。

![撇号（Prime）](/tex/images/java/tutorial/latex-math-2-6.png)

## 双上标 LaTeX

在 LaTeX 中，你可以通过把整个上标表达式放在大括号 `{}` 中来写双上标。例如：`x^{a^b}`

## 双下标 LaTeX

在 LaTeX 中，你可以通过把整个下标表达式放在大括号 `{}` 中来写双下标。例如：`X_{i_{j}}`
