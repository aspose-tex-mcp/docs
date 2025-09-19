---
translation: true
template: /templates/_template-java.md
linktitle: 乳胶文档课程
title: 乳胶文档课程
weight: 20
url: /java/latex-document-classes/
keywords: 乳胶文章类，乳胶文档类，乳胶文档模板，乳胶文章，乳胶书籍，乳胶幻灯片，乳胶报告，乳胶字母，乳胶中的文档类
description: 本文是乳胶文档类及其选项的简洁摘要。它还提供了一些示例。
lastmod: "2025-06-10"
---

{{<section overview>}}

## 乳胶中的文档类是什么？

LaTeX 定义了一些每个文档作者都必须遵循的规则。它还定义了源文件的结构，源文件本质上是一个排版程序。根据此结构，文档源代码必须包含一个负责文档内容本身的部分——*正文*，它包含在一对命令中：`\begin{document}`和`\end{document}`。LaTeX 会忽略正文末尾之后的任何内容。源代码中位于`\begin{document}`之前的部分称为“前言*”。

通常，序言中的第一个命令必须为`\ documentClass`，该命令采用单个必需的参数，该参数是**文档类**的名称。文档类本身是一组格式参数，布局指标，宏等，适用于开发某种类型的文档并以单个名称收集。在本文中，我们将讨论乳胶**预定义的**文档类，这些文档类别是内置的乳胶，并显示其用途，差异和相似之处。我们还将提及`\documentclass`命令可以采用的一些可选论点，并自定义文档的外观。

## 预定义的乳胶文档课程

标准乳胶包含以下文档类：

| <div style="text-align:center;">LaTeX<br>document<br>class</div> | <div style="text-align:center;">Usage</div> |
|---|---|
| **article** | LaTeX 文章类用于创建科学期刊、短篇报告、程序文档以及任何不需要复杂章节划分的短篇文档。|
| **report** | LaTeX 报告类用于包含多个章节的长篇文章（例如小册子和论文）。|
| **book** | 用于排版真实书籍。它包含适用于印刷书籍的各种排版标准：章节和部分、两种页面、前言、后记等。|
| **slides** | 它可以用于制作幻灯片，不过外部包 [beamer](https://ctan.org/pkg/beamer) 在这方面的功能更强大。|
| **letter** | 此文档类用于撰写信件。|

前两个文档类是基本的。因此，从**文章**开始时，只要您不确定所需的课程。

**报告**类非常相似。与**文章**的主要区别在于，您可以使用“ \ chancter”命令插入章节，而**文档**类别不能定义这样的分段单元。

## 乳胶**书**班

书籍标准的书籍具有前提和背面物质，这是书籍和报告或文章之间的主要区别。书的前提通常由半标题页，主标题页，版权页，前言或前言以及表内容组成。承认零件较少，奉献精神，数字列表，表格列表，同一系列中的其他书籍列表以及其他社论和促销内容。背面物质通常包括一个索引，并且可能包含后词，以及确认，参考书目，合成子等。

本书文档类为您提供了制作上述逻辑结构的命令，而其他文档类也无法为您提供此类工具。但是，不同的发布者通常有自己的包裹，并带有其他命令，以根据自己的风格铺设结构。

## 前物质，主要物质和背部命令

主要问题是包括书的正文，从第一章或部分开始，然后以附录结尾。正面，主和背面的问题分别从` \ frontMatter`，`\ mainmatter”和``\ Backmatter`命令开始。

> 在标准书籍类别中，前页使用罗马数字编号，而正文和后页使用阿拉伯数字编号。

> `\chapter` 命令不会在前页和后页中生成章节编号，但它会在目录中创建一个条目。这通常用于创建前言或致谢部分。在这些章节中，只能使用其他章节命令（例如 `\section*` 和 `\subsection`）的星号版本。

## 使用乳胶书课的一个例子

```tex
% Book document class
\documentclass{book}

\title{My first book}
\author{Me}
\date{\today}

\begin{document}

\maketitle

\frontmatter
\chapter{Dedication}
\chapter{Copyright}
\chapter{Acknowledgements}

\tableofcontents

\listoffigures
\listoftables

\mainmatter
\part{The first part}
\chapter{Chapter one}
\chapter{Chapter two}

\part{Last part}
\chapter{Chapter three}

\appendix
\chapter{First and only appendix}

\backmatter
\chapter{Bibliography}
\chapter{Other titles in this collection}

\end{document}
```

以下是该乳胶代码生成的文档结构：

<a href="/tex/java/latex-document-classes/latex-document-classes-1.png" style="display:inline-block;width:49%;">![示例输出](/tex/images/java/tutorial/latex-document-classes-1.png)</a>
<a href="/tex/java/latex-document-classes/latex-document-classes-2.png" style="display:inline-block;width:49%;">![示例输出](/tex/images/java/tutorial/latex-document-classes-2.png)</a>

这是目录的详细信息表：

<a href="/tex/java/latex-document-classes/latex-document-classes-3.png">![目录](/tex/images/java/tutorial/latex-document-classes-3.png)</a>

## **奇数**和**甚至**书中的页面

在书中，**奇数**和**甚至**页面看起来都不一样。利润率以及通常的标题和页脚不同，在绑定时会使书更可读。乳胶文档类处理此操作，您可能会发现：
- **左(偶数)**页面的左边边距更大，页码在页面的右上角，当前章节的标题在右侧；
- **右(奇数)**页面的右边距更大，并且页码在页面右上方的页码。

请注意，新章节始终从右页开始，页面头为空，仅留在脚中心的页码。

## **摘要**部分缺少

学术论文(例如文章或报告)通常包括一个称为**“摘要”**的介绍性部分。其目的是快速概述文档中涵盖的主题。您可能会发现它在标题之后和目录之前就打印出来，并以粗体设置为“抽象”。在乳胶中，这种结构被实现为“抽象”环境。

书籍文档类未提供**摘要**环境，这与文章和报告类别是另一个区别。

## 乳胶**字母**班

目前，字母文档类似乎有些古老(实际上，幻灯片文档类也是如此)。如果您需要制作传统信件，将它们放入信封中并通过邮件发送，则此文档类可能对您有用。尽管这是一种过时的沟通方式，但仍有一些情况下您可能需要准备像字母一样的文档。例如，推荐信或演讲信。

因此，这是班级的简要概述。

您可以生成具有单个输入文件的任何数量的字母。您的姓名和地址通常在所有字母中相同，通常在文档序言中指定。返回地址由`\address`命令声明，该命令接受`\\`(latex line break命令)分隔的多行作为参数。同样，`\signature`命令接受多行，包括您的姓名，标题等。但是，您可以在任何时候更改返回地址和签名。

每个字母都是由单独的“字母”环境生成的，该环境需要收件人的姓名和地址作为参数。这封信以`\open`命令开始，产生称呼，并以`\closing`命令结束，产生了闭合短语和签名。字母的主体是正常的乳胶输入。

所有这些命令都易于使用，并且非常强大，因为乳胶会自动照顾格式化字母。因此，不要让命令的数量吓到或困惑您。

下面的示例说明了这一切的工作原理。

```tex
% Example of a letter document class
\documentclass{letter}
 
\address{1234 Heart Avenue\\ Thoraxland, 12555}

\signature{Dr.~Lung\\ Head of Department}

\begin{document}

\begin{letter}
{Dr.~Gallbladder \\ University of Digestion\\ 66 Liver Street\\ Abdomenia, 45888}

\opening{Appreciated Anything,}

I write you a letter, and this is the body of the
letter.

\closing{I look forward to your reply,}

\end{letter}

\end{document}
```

<a href="/tex/java/latex-document-classes/latex-document-classes-4.png">![信函文件类示例](/tex/images/java/tutorial/latex-document-classes-4.png)</a>

请注意，当前日期也会自动产生。但是，您可以重新定义`\tovers`命令来更改信件中的日期。这是您的工作方式：

```tex
\renewcommand{\today}{01th of March of 2492}
```

如果您将此声明插入某个字母环境中，则将仅更改该信件的日期。否则，如果您将其插入序言中，将对输入文件生成的所有字母生效(除非将其插入某个字母环境中)。

## 乳胶文档类选项

现在，让我们看一下本文开头中提到的`\ documentClass`命令选项。

### 字体大小

字体大小由三个选项控制：10pt，11pt，12pt。默认情况下，10PT已生效。这些选项确定整个文档中使用的基本字体大小，除非在某个时候更改。它们还会影响某些格式化尺寸的比例因素。

```tex
\documentclass[12pt]{article}
```

> These options are not recognizable by the `slides` class.

### 纸张尺寸
这里的“纸张尺寸”是指您在上面打印文档的纸质表的大小。它不会影响排版系统输出(例如**pdf tex**)的页面表示的大小。它由6个选项控制：`lenterpaper`(8.5英寸x 11英寸)，`Legalperpaper`(8.5英寸x 14in)，`everivepaper`(7.25in x 10.5in)，`a4paper`(210mm x 297mm)，`a5 paperd.默认值为“信函纸”。

```tex
\documentclass[a4paper]{article}
```

### 页面方向

“景观”选项使所选纸张尺寸上的景观打印的输出格式化。有效地，它使乳胶互换在排版过程中使用的宽度和高度尺寸。 “肖像”选项没有这种效果，默认情况下使用。

```tex
\documentclass[landscape]{article} % landscape printing on the letterpaper
```

### 草稿模式

在段落构建过程中，如果 TeX 无法生成足够好的换行符（它有一个“良好度”评估算法），它就会生成一条超出文本区域右边界的行。它还会在文本记录文件（以及终端）中报告此类事件，并发出“overfull boxes”（溢出框）警告。`draft` 选项会使 LaTeX 在输出中用黑框标记此类行。`final` 选项不会生成黑框，并且是默认选项。

### 两面打印

`openany`选项允许章节从任意页面开始，而`openright`选项则允许所有章节从右侧页面开始。`report`类默认为“openany”，`book`类默认为`openright`。其他文档类无法识别这两个选项。

### 标题的页面

使用 `titlepage` 选项，LaTeX 会为 `\maketitle` 命令生成的标题创建一个单独的页面。它还会使 `abstract` 环境在新页面上开始摘要，并在其后设置分页符。除 `article` 类外，所有类的默认选项均为 `titlepage`，而 `article` 类的默认选项为 `notitlepage`。

> `letter` 类无法识别这些选项。

### 编号显示的公式

`leqno`选项使乳胶放置方程(显示的数学公式)数字或左侧的标签，而不是右侧，这是默认行为。

### 显示的公式对齐

`fleqn`选项对齐在左侧显示公式。否则，默认情况下它们为中心。
