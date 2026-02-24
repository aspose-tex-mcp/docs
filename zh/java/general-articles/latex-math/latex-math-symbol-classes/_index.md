---
translation: true
template: /templates/_template-java.md
linktitle: 数学公式中的不同字符
title: 4. 数学公式中不同字符的含义
weight: 40
url: /java/latex-math-symbol-classes/
keywords: latex、latex 数学公式、latex 数学、latex 数学符号、latex 数学变量、latex 数学二元运算、latex 数学关系、latex 数学重音符号
description: 本文讨论了 TeX 数学符号的分类以及这些类别在数学中的含义。
lastmod: "2026-02-24"
---

{{<section overview>}}

52 个字母（`A` 到 `Z` 与 `a` 到 `z`）表示斜体符号，数学家会称之为“变量”。TeX 将它们称为“普通符号”，因为它们构成了数学公式的主体。LaTeX 还把下面这 18 个字符

``0 1 2 3 4 5 6 7 8 9 ! ? . | ` @ "``

视为普通符号，这意味着当这些符号相邻出现或与字母相邻时，TeX 不会插入额外的空格。与字母不同，这 18 个字符在公式中保持罗马体。

三个字符 `+`、`-` 和 `*` 被称为“二元运算”，因为它们作用于公式的两个部分。星号 (*) 很少使用，但它也表现为二元运算。以下是二元运算在普通符号旁出现时的排版示例：

![Binary operations](/tex/images/java/tutorial/latex-math-4-1.png)

TeX 不会将 `/` 视为二元运算，因为在类似 `$1/2` 的公式中这会导致间距错误。因此，TeX 将 `/` 视为普通符号。

以下是一些更复杂的二元运算示例：

![More complex binary operations](/tex/images/java/tutorial/latex-math-4-2.png)

顺便说明，如果二元运算未出现在两个可操作的量之间，它们会被当作普通符号处理。因此，在如下情况中，`+`、`-`、`*` 前后不会插入额外的空格：

![Binary operation as ordinary symbols](/tex/images/java/tutorial/latex-math-4-3.png)

下面的示例显示二元运算可以在上标和下标中作为普通符号使用：

![Binary operation as ordinary symbols in superscripts and subscripts](/tex/images/java/tutorial/latex-math-4-4.png)

LaTeX 将四个字符 `=`, `<`, `>`, 和 `:` 视为“关系符”，因为它们表示两个量之间的关系。这类关系与二元运算的意义相差较大，符号的排版方式也略有不同：

![Relations](/tex/images/java/tutorial/latex-math-4-5.png)

字符 ','（逗号）和 ';'（分号）在公式中被视为标点符号，这意味着 TeX 在它们后面会插入一点额外的空格，而前面不加空格。

![Punctuation marks](/tex/images/java/tutorial/latex-math-4-6.png)

在公式中，通常不会在 '.'（句点）后面添加额外的空格，所以 TeX 将句点视为普通符号。如果希望 ':' 被当作标点而非关系符，只需使用 `\colon`。如果想让逗号被当作普通符号，只需把它放在大括号中。TeX 会把大括号中的任何内容视为普通符号。

![Colon as punctuation and comma as ordinary symbol](/tex/images/java/tutorial/latex-math-4-7.png)

字符 `(` 和 `[` 被称为“左括号”，而 `)` 和 `]` 被称为“右括号”。它们的行为类似普通符号，但能够帮助 TeX 判断何时二元运算并非真正以二元方式使用。

最后，LaTeX 保留了另外 10 个字符：

``\ $ % # & ~ { } _ ^``

这些字符不能在数学模式中使用。虽然 `{` 和 `}` 用于分组，但可以使用命令 `\{` 和 `\}` 来分别得到左大括号和右大括号。

特殊字符 `^` 和 `_` 除了在公式中使用外不应出现。相反，诸如 `\alpha`、`\approx` 等数学符号名，以及诸如 `\overline` 的数学操作命令，不能出现在普通文本中。另外，空行或 `\par` 在数学模式中也是不允许的。

数学家也喜欢在字母上使用重音符号，以有效表示数学对象之间的关系。这大大扩展了可用符号的数量，而无需增加字体。数学重音符号与普通文本中的重音符号略有不同。间距也不同；TeX 在公式中遵循特殊的重音规则，以防两种重音被混淆。LaTeX 提供了以下数学重音符号：

![Accents](/tex/images/java/tutorial/latex-math-4-8.png)

其中前九个分别在文本中对应 `\^`, `\v`, `\~`, `\'`, ``\` ``, `\.`, `\"`, `\u`, `\=`；`\vec` 只在公式中出现。如果在公式中使用 `\^`、`\v` 等，或在普通文本中使用 `\hat`、`\check` 等，TeX 将报错。

在 LaTeX 文件的开头添加符号可以节省大量击键次数，并使文件更易于阅读。

```tex
\def\Ahat{{\hat A}}
\def\chat{{\hat c}}
\def\scheck{{\check s}}
```

在 LaTeX 文件的开头添加符号可以节省大量击键次数，并使文件更易于阅读。

当字母 *i* 和 *j* 在数学公式中带重音时，应使用无点的基符号，分别为 `\imath` 和 `\jmath`。因此，使用带帽子 i 和 j 的论文可以在开头加入如下定义：

```tex
\def\ihat{{\hat\imath}}
\def\jhat{{\hat\jmath}}
```

可以在任何子公式上添加数学重音。但通常这样做意义不大，因为 TeX 只会把重音居中到整个子公式上。特别是，`\bar` 重音始终保持相同大小；它不像会随公式长度扩展的 `\overline`。有些人即使只对单个字母使用，也更喜欢 `\overline` 的较长横线。然而，LaTeX 提供了两个会随长度扩展的重音，分别是 `\widehat` 和 `\widetilde`。下面我们来看前面段落中讨论的案例示例。

![Wide accents](/tex/images/java/tutorial/latex-math-4-9.png)

最后一个示例展示了可用的最大尺寸。
