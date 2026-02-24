---
translation: true
template: /templates/_template-java.md
linktitle: LaTeX 命令
title: 3. LaTeX 命令 | LaTeX 手册
weight: 30
url: /java/latex-math-commands/
keywords: latex, latex 数学公式, latex 数学, latex 数学命令, latex 开方, latex 数学下划线, latex 数学上划线
description: 本文讨论了另一种使用 LaTeX 提供的宏命令来编写数学公式的方法。
lastmod: "2026-02-24"
---

{{<section overview>}}

另一种从简单公式构建复杂公式的方法是使用命令 `\sqrt`、`\underline` 或 `\overline`。它们同样作用于其后面的字符或子公式：

![LaTeX 命令的最简单应用](/tex/images/java/tutorial/latex-math-3-1.png)

你也可以得到立方根及类似的东西：

![任意次数的根号](/tex/images/java/tutorial/latex-math-3-2.png)

这三个命令会在任意大小和形状的子公式上方或下方加线；这些线的长度和位置会随子公式的大小而变化，使其足够长以覆盖子公式，并且高低适当，不会与子公式重叠。特别是，根号符号会根据被 `\sqrt` 的内容的高度和深度出现不同的位置：

![任意次数的根号](/tex/images/java/tutorial/latex-math-3-3.png)

在这种情况下，你可能希望所有的根号看起来一致，例如：

![任意次数的根号](/tex/images/java/tutorial/latex-math-3-4.png)

实现这一点的简便方法是使用 `\mathstrut` 命令：

```tex
$\sqrt{\mathstrut a} + \sqrt{\mathstrut d} + \sqrt{\mathstrut y}$.
```

`\mathstrut` 是一个不可见的零宽盒子。它的高度和深度与左括号 '(' 的高度和深度相同。因此，包含 `\mathstrut` 的子公式始终具有相同的高度和深度，除非它们还涉及更复杂的构造，如下标和上标。
