---
translation: true
template: /templates/_template-net.md
title: 乳胶I/O | Aspose.TeX for .NET
linktitle: 乳胶输入/输出
weight: 17
url: /net/latex-io/
description: 此页面简要地描述了与乳胶合作的特殊性作为输出或输入格式，而 * .aux *文件是乳胶的强制性部分。
keywords: 乳胶IO，乳胶i，乳胶o，乳胶输入文件，输入乳胶
lastmod: "2025-06-10"
---

{{<section overview>}}

## 乳胶文件

如果我们有一个具有以下结构的[TEX文件](/tex/{{lang.url-fragment}}net/tex-io/#tex-file)，则将此文件称为 *latex文件*：


```tex
\documentclass{<a document class>}
% Preamble
...
\begin{document}
% Document body
...
\end{document}
```

其中`<<a document>`是[文档类](https://en.wikibooks.org/wiki/LaTeX/Document_Structure#Document_classes)的名称，它是一个输入TEX文件，它定义了最适合某种类型的文档的输出文档页面和宏的显示。

老实说，您可以在`\documentclass{}`，如`\nonstopmode`等之前插入原始控制序列。但是每个乳胶宏都检查它是否位于文件的适当部分。

在使用乳胶文件的背景下，关于Tex [Input](/tex/{{lang.url-fragment}}net/tex-io/#tex-input)(3)和[输出](/tex/{{lang.url-fragment}}net/tex-io/#tex-output)有一些值得注意的事情。

## 乳胶输出文件

典型的乳胶作业创建了一个辅助输出文件，并以[作业名称](/tex/{{lang.url-fragment}}net/tex-io/#tex-output)为其名称和扩展名 *.aux*。该文件通常包含引擎在作业运行中收集的参考数据，如果您设置了数学公式(方程式)的标签，然后参考文本中的某个地方。如果您不使用任何此类文件，则此文件仅包含`\haliso`控制序列(这是Tex原始序列之一)。所以不要感到惊讶。

尽管`\openout`，“`\ write`和`\closeout'diminives`不禁止，但包装是最适合它们的地方。因此，如果您要开发它们，则最好在自己的自定义软件包中使用它们。

输出的其他部分是任意的，也遵循常规[TEX输出](/tex/{{lang.url-fragment}}net/tex-io/#tex-output)概念，取决于您的TEC文件(程序)应该执行的确切含义，您正在使用的包(请参见下文)等等。

## 乳胶输入文件

上述 *.aux*文件同时是乳胶输入的强制性部分。从算法上讲，乳胶无法在一次运行中完成与参考相关的任务，因此需要两次运行相同的作业 - 首次收集数据，第二次使用这些数据。许多基于乳胶的软件系统会自动两次运行乳胶作业。剧透：Aspose.TeX API中有一个[选项](/tex/{{lang.url-fragment}}net/other-options/#how-to-repeat-the-job)，可以控制这种行为。

另一个强制性部分是[文档类](/tex/{{lang.url-fragment}}net/latex-io/#latex-file)。依次，文档类文件可能会隐式取决于其他文件，因此，这些文件也包含在乳胶输入中。

如果您想使用基本乳胶及其文档类别范围之外的功能，但在某个TEX引擎实现的支持下，则通常使用一个软件包，该软件包必须在序言中通知引擎。一个 *乳胶软件包 *是一个文件，或以一个名称组装的一组文件，可提供此类功能。要通知引擎，您需要将`\usepackage`命令与软件包名称和可观的选项(如果包装定义)使用。

例如，


```tex
\usepackage[a6paper,landscape]{geometry}
```

尽管“ `\input`”，“ `\openin`”，`\read`和`\closein`原始词不禁止，但包装是最适合它们的地方。因此，如果您要开发它们，则最好在自己的自定义软件包中使用它们。

输入的其他部分是任意的，也遵循常规[TEX输入](/tex/{{lang.url-fragment}}net/tex-io/#tex-input)概念，并取决于您的TEX文件(程序)应该执行的操作，您正在使用的软件包等等。