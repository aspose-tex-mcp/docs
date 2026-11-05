---
translation: true
template: /templates/_template-java.md
linktitle: LaTeX 文档类
title: LaTeX 文档类 | Aspose.TeX 教程
weight: 20
url: /java/latex-document-classes/
keywords: LaTeX 文章类、LaTeX 文档类、LaTeX 文档模板、LaTeX 文章、LaTeX 书籍、LaTeX 幻灯片、LaTeX 报告、LaTeX 信函、LaTeX 中的文档类
description: 本文是对 LaTeX 文档类及其选项的简要概述，并提供了一些示例。
lastmod: "2026-02-20"
---

{{<section overview>}}

## 什么是 LaTeX 中的 documentclass？

LaTeX 定义了一些每个文档作者必须遵守的规则。它还定义了源文件的结构，本质上是一个排版程序。根据这种结构，文档源代码必须包含一部分负责文档内容本身——*正文*——该部分被一对命令包围：`\begin{document}` 与 `\end{document}`。LaTeX 会忽略正文结束后出现的任何内容。位于 `\begin{document}` 之前的源代码部分称为 *前导区*（preamble）。

通常，前导区中的第一条命令必须是 `\documentclass`，它接受一个必需参数，即 **文档类** 的名称。文档类本身是一组格式化参数、版面度量、宏等，适用于并有助于编写某种类型的文档，并以单一名称汇集。在本文中，我们将讨论 LaTeX **预定义** 的内置文档类，并展示它们的用法、区别和相似之处。我们还会提及 `\documentclass` 命令可以接受的一些可选参数，它们用于自定义文档的外观。

## 预定义的 LaTeX 文档类

标准 LaTeX 包含以下文档类：

| <div style="text-align:center;">LaTeX<br>document<br>class</div> | <div style="text-align:center;">Usage</div> |
|---|---|
| **article** | LaTeX article 类用于创建期刊文章、简短报告、程序文档，以及一般任何不需要复杂章节划分的短文档。 |
| **report** | LaTeX report 类用于包含多个章节的长篇文章（类似小型书籍和学位论文）。 |
| **book** | 用于排版正式的书籍。它包含所有适用于印刷书籍的排版标准：章节与部、两种页面风格、前言、后记等。|
| **slides** | 可用于制作幻灯片，尽管还有功能更强大的外部宏包 [beamer](https://ctan.org/pkg/beamer)。 |
| **letter** | 该文档类用于撰写信件。 |

前两个文档类是最基础的。因此，如果不确定需要哪种类，请先使用 **article**。

**report** 类与之非常相似。与 **article** 的主要区别在于，你可以使用 `\chapter` 命令插入章节，而 **article** 文档类并未定义这样的章节单元。

## LaTeX **book** 类

在排版标准中，书籍拥有前言（front matter）和后记（back matter），这正是书籍与报告或文章的主要区别。一本书的前言通常包括半标题页、正式标题页、版权页、前言或序言以及目录。非必需的内容还有致谢、献词、插图列表、表格列表、同系列其他书籍列表以及其他编辑和宣传内容。后记通常包括索引，可能还有后记、致谢、参考文献、版权页等。

book 文档类为你提供了生成上述逻辑结构的命令，而其他文档类则无法提供这些工具。不过，不同出版社通常会提供带有额外命令的宏包，以便根据其特定样式排版。

## 前言、主体和后记的命令

主体（main matter）指包含书本正文的部分，从第一章或第一部开始，到附录结束。前言、主体和后记分别通过 `\frontmatter`、`\mainmatter` 和 `\backmatter` 命令启动。

> 在标准 book 类中，前言页面使用罗马数字编号，而主体和后记页面使用阿拉伯数字编号。

> `\chapter` 命令在前言和后记中不会生成章节编号，但会在目录中创建条目。这通常用于创建前言或致谢章节。在此类章节中，其他分节命令（如 `\section*` 与 `\subsection`）只能使用带星号的形式。

## 使用 LaTeX book 类的示例

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

下面是该 LaTeX 代码生成的文档结构：

<a href="/tex/java/latex-document-classes/latex-document-classes-1.png" style="display:inline-block;width:49%;">![Example output](/tex/images/java/tutorial/latex-document-classes-1.png)</a>
<a href="/tex/java/latex-document-classes/latex-document-classes-2.png" style="display:inline-block;width:49%;">![Example output](/tex/images/java/tutorial/latex-document-classes-2.png)</a>

以下是详细的目录结构：

<a href="/tex/java/latex-document-classes/latex-document-classes-3.png">![Table of contents](/tex/images/java/tutorial/latex-document-classes-3.png)</a>

## 书籍中的 **奇数** 页和 **偶数** 页

在书籍中，**奇数** 页和 **偶数** 页的排版并不相同。页边距以及通常的页眉页脚会有所区别，以提高装订后阅读的舒适度。LaTeX 文档类会自动处理这些差异，表现为：

- **左侧（偶数）** 页面拥有较大的左边距，页码位于页面右上角，当前章节标题显示在右侧；
- **右侧（奇数）** 页面拥有较大的右边距，页码同样位于页面右上角。

请注意，新章节总是从右侧页面开始，此时页眉为空，页脚仅在页面中心显示页码。

## 缺少 **摘要**（Abstract）部分

学术论文（如文章或报告）通常在标题之后、目录之前包含一个名为 **“Abstract”** 的引言性章节，用于快速概述文档主题。在 LaTeX 中，这一结构通过 `abstract` 环境实现。

book 文档类并未提供 `abstract` 环境，这也是它与 article 和 report 类的另一区别。

## LaTeX **letter** 类

目前，letter 文档类显得有些老派（slide 文档类也是如此）。如果你需要撰写传统信件、装入信封并通过邮寄方式发送，这个文档类可能会对你有帮助。虽然这种通信方式已经相对过时，但在某些场景下仍然需要准备类似信件的文档，例如推荐信或自荐信。

下面简要介绍该类的用法。

你可以使用单一的输入文件生成任意数量的信件。姓名和地址（通常对所有信件相同）一般在前导区指定。回信地址通过 `\address` 命令声明，该命令接受多行文本，以 `\\`（LaTeX 换行命令）分隔。类似地，`\signature` 命令接受包括姓名、头衔等在内的多行文本。不过，你可以在任何时候更改回信地址和签名。

每封信由单独的 `letter` 环境生成，环境的参数是收信人的姓名和地址。信件以 `\opening` 命令开始，生成称呼；以 `\closing` 命令结束，生成结束语和签名。信件正文则是普通的 LaTeX 输入。

所有这些命令都易于使用，且功能强大，LaTeX 会自动处理信件的排版。因此不要因为命令数量而望而却步。

下面的示例展示了完整的工作流程。

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

<a href="/tex/java/latex-document-classes/latex-document-classes-4.png">![A letter document class example](/tex/images/java/tutorial/latex-document-classes-4.png)</a>

请注意，当前日期会自动生成。不过，你可以重新定义 `\today` 命令来修改信件中的日期，方法如下：

```tex
\renewcommand{\today}{01th of March of 2492}
```

如果将此声明放在特定的 `letter` 环境中，仅会影响该信件；若放在前导区，则对所有信件生效（除非在某个 `letter` 环境中再次声明）。

## LaTeX 文档类选项

下面我们来看看文章开头提到的 `\documentclass` 命令的各种选项。

### 字体大小

字体大小由三个选项控制：10pt、11pt、12pt。默认是 10pt。这些选项决定了整篇文档的基准字体大小，除非在某处另行修改。同时，它们也影响某些格式尺寸的比例因子。

```tex
\documentclass[12pt]{article}
```

> 这些选项在 `slides` 类中不可识别。

### 纸张尺寸

这里的 “纸张尺寸” 指的是你 **计划** 打印文档时所用的纸张规格。它不影响如 **PDF TeX** 等排版系统输出页面的实际尺寸。共有 6 种选项：`letterpaper`（8.5 × 11 英寸）、`legalpaper`（8.5 × 14 英寸）、`executivepaper`（7.25 × 10.5 英寸）、`a4paper`（210 mm × 297 mm）、`a5paper`（148 mm × 210 mm）以及 `b5paper`（176 mm × 250 mm）。默认值为 `letterpaper`。

```tex
\documentclass[a4paper]{article}
```

### 页面方向

`landscape` 选项使输出针对所选纸张尺寸的横向打印进行排版，实际上会在排版过程中交换宽度和高度的数值。`portrait` 选项则保持默认的纵向排版。

```tex
\documentclass[landscape]{article} % landscape printing on the letterpaper
```

### 草稿模式

当 TeX 在段落构建过程中无法找到足够好的换行点时，会产生超出正文右边界的行，并在日志文件（以及终端）中给出 “overfull box” 警告。`draft` 选项会在输出中用黑色方框标记这些行；`final` 选项则不产生黑框，默认即为 `final`。

### 双面打印

`openany` 选项允许章节在任意页面开始，而 `openright` 选项则强制所有章节在右手页（即奇数页）开始。`report` 类的默认值是 `openany`，`book` 类的默认值是 `openright`。其他文档类不识别这两个选项。

### 标题页

使用 `titlepage` 选项时，LaTeX 会为 `\maketitle` 命令生成的标题单独创建一页。该选项还会使 `abstract` 环境在新页开始并在摘要后强制分页。除 `article` 类外，所有类的默认值都是 `titlepage`；而 `article` 类的默认值是 `notitlepage`。

> 这些选项在 `letter` 类中不可识别。

### 编号显示公式

`leqno` 选项会让 LaTeX 将公式编号（标签）放在左侧，而不是默认的右侧。

### 显示公式对齐方式

`fleqn` 选项会将显示公式左对齐。若不使用该选项，公式默认居中排列。
