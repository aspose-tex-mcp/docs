---
translation: true
template: /templates/_template-java.md
linktitle: 3. 乳胶命令
title: 乳胶命令|乳胶手册
weight: 30
url: /java/latex-math-commands/
keywords: 乳胶，乳胶数学公式，乳胶数学，乳胶数学命令，乳胶平方根，乳胶数学下划线，乳胶数学上线
description: 本文讨论了构成数学公式的另一种方法，该方法涉及乳胶提供的宏命令。
lastmod: "2025-06-10"
---

{{<section overview>}}

从简单的公式构建复杂公式的另一种方法是使用命令`\sqrt`，`\ usepline`或`\ overline`。它们还适用于跟随它们的角色或子形式：

![乳胶命令的最简单应用](/tex/images/java/tutorial/latex-math-3-1.png)

您还可以得到立方根和类似的东西：

![任意程度的根源](/tex/images/java/tutorial/latex-math-3-2.png)

这三个命令可以在任意大小和形状的子公式上方和下方放置线条；线条会改变其大小和位置，以便足够长以覆盖子公式，并且足够高或足够低以免与其重叠。具体来说，平方根符号会根据被 `\sqrt` 的高度和深度出现在各种位置：![任意程度的根源](/tex/images/java/tutorial/latex-math-3-3.png) 在这种情况下，您可能希望统一排版所有平方根，如下所示：![任意程度的根源](/tex/images/java/tutorial/latex-math-3-4.png) 最简单的方法是使用命令 `\mathstrut`：

```tex
$\sqrt{\mathstrut a} + \sqrt{\mathstrut d} + \sqrt{\mathstrut y}$.
```

`\mathstrut` 是一个不可见的零宽度框。它的高度和深度等于括号 '(' 的高度和深度。因此，包含 `\mathstrut` 的子公式始终具有相同的高度和深度，除非它们涉及更复杂的构造，例如上标和下标。