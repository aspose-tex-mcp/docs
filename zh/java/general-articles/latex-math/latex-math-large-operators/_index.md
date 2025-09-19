---
translation: true
template: /templates/_template-java.md
linktitle: 大型运营商
title: 6. 大型操作员|乳胶手册
weight: 60
url: /java/latex-math-large-operators/
keywords: 乳胶，乳胶数学公式，乳胶数学，乳胶数学大型运营商，乳胶总和，乳胶积分
description: 本文讨论了如何构建包含大型运营商的数学公式，例如与Tex和Latex集成。
lastmod: "2025-06-10"
---

{{<section overview>}}

在数学中，有一些符号表示，例如“求和”或“集成”操作。它们被称为“大型操作员”，就像键入普通符号和字母一样。不同之处在于，Tex将以显示样式的显示样式为大型操作员选择一个更大的符号。

![无超级/下标的求和和集成](/tex/images/java/tutorial/latex-math-6-1.png)

显示的 `\sum` 通常与“极限”一起出现，即与出现在其上方和下方的子公式一起出现。极限应像下标和上标一样输入；`$$\sum_{n=1}^m$$` 或 `$$\sum^m_{n=1}$$` 都产生

![限制的总和](/tex/images/java/tutorial/latex-math-6-2.png)

数学排版的正常惯例假定应将上述公式更改为

![求和无限](/tex/images/java/tutorial/latex-math-6-3.png)

(即，无限制)，如果它发生在文本而不是在显示中。 Tex遵循这些惯例。

即使在显示样式中，集成符号上的上标和下标也不被设置为限制：

![在文本和显示中集成](/tex/images/java/tutorial/latex-math-6-4.png)

如果子公式比较复杂，将下标和上标设置为极限值可以提高美观度，但会占用更多页面空间。您可以强制 TeX 以这种方式处理公式，方法是在 `\int`、`\sum` 或其他运算符后立即键入 `\limits`，无论子公式中将使用哪种样式。另一方面，有时不希望显示求和符号的限制。您可以通过在大运算符后立即键入 `\nolimits` 来更改 TeX 的惯例。

![强制限制，没有限制来求和和集成](/tex/images/java/tutorial/latex-math-6-5.png)

如果您指定 `\nolimits\limits`（例如，某些宏，如 `\int`，指定 `\nolimits`），则最后一个命令优先。`\displaylimits` 命令可用于切换到 TeX 的常规约定；即，限制将仅以样式 *D* 和 *D'* 显示。

如果您需要在大型操作员下方放置多个限制，则可以使用“ \ atop”这样做。键入以下公式的正确方法是 

```tex
$$\sum_{\scriptstyle0\le i\le m\atop\scriptstyle0<j<n}P(i,j)$$.
```

![总结标志下的多排限制](/tex/images/java/tutorial/latex-math-6-6.png)

这里有必要“ \ scriptStyle”命令，否则限制的两个行都在脚本标题中，太小了。这是另一种难得的情况，需要覆盖Tex的风格规则。