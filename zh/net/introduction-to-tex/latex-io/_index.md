---
translation: true
template: /templates/_template-net.md
title: LaTeX 输入/输出  
linktitle: LaTeX I/O
weight: 17
url: /net/latex-io/
description: 此页面简要描述了使用 LaTeX 作为输出或输入格式的特殊之处，以及 *.aux* 文件作为 LaTeX 的强制性部分。
keywords: latex io, latex i, latex o, latex 输入文件, latex 输入
lastmod: "2026-02-26"
---

{{<section overview>}}

## LaTeX 文件

如果我们有一个 [TeX file](/tex/{{lang.url-fragment}}net/tex-io/#tex-file) 并且它具有以下结构，那么我们将此文件称为 *LaTeX 文件*：


```tex
\documentclass{<a document class>}
% Preamble
...
\begin{document}
% Document body
...
\end{document}
```

其中 `<a document class>` 是一个 [document class](https://en.wikibooks.org/wiki/LaTeX/Document_Structure#Document_classes) 的名称，它是一个输入 TeX 文件，用来定义输出文档页面的外观以及最适合特定文档类型的宏。

说实话，你可以在 `\documentclass{}` 之前插入原始控制序列，例如 `\nonstopmode` 等。但每个 LaTeX 宏都会检查它是否位于文件的恰当位置。

关于在处理 LaTeX 文件时 TeX 的 [input](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) 和 [output](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) 有几件值得注意的事情。

## LaTeX 输出文件

典型的 LaTeX 作业会创建一个辅助输出文件，文件名为 [job name](/tex/{{lang.url-fragment}}net/tex-io/#tex-output)，扩展名为 *.aux*。如果你为数学公式（方程）设置了标签并在正文中引用，它通常会包含引擎在作业运行过程中收集的引用数据。若你没有使用此类功能，该文件仅包含 `\relax` 控制序列（TeX 原始指令之一），所以不要感到惊讶。

虽然 `\openout`、`\write` 和 `\closeout` 原始指令并未被禁止，但包是使用它们的最合适场所。因此，如果你在开发自定义包，最好在自己的包中使用这些指令。

输出的其他部分是任意的，也遵循通用的 [TeX output](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) 概念，取决于你的 TeX 文件（程序）具体要做什么、使用了哪些包（见下文）等。

## LaTeX 输入文件

前面提到的 *.aux* 文件在 LaTeX 中同时是输入的强制性部分。算法上，LaTeX 无法在一次运行中完成引用相关的任务，因此同一个作业需要运行两次——第一次收集数据，第二次使用这些数据。许多基于 LaTeX 的软件系统会自动运行两次 LaTeX 作业。提示：Aspose.TeX API 中有一个 [option](/tex/{{lang.url-fragment}}net/other-options/#how-to-repeat-the-job) 可以让我们控制这种行为。

另一个强制性部分是 [document class](/tex/{{lang.url-fragment}}net/latex-io/#latex-file)。文档类文件本身可能隐式依赖其他文件，这些文件同样会被包含在 LaTeX 输入中。

如果你想使用超出基本 LaTeX 及其文档类范围，但由特定 TeX 引擎实现支持的功能，通常需要使用宏包，并在导言区通知引擎。*LaTeX 包* 是一个文件或一组文件，以同一名称组合，提供此类功能。要通知引擎，需要使用 `\usepackage` 命令并提供包名和可省略的选项（如果该包定义了选项的话）。

例如，


```tex
\usepackage[a6paper,landscape]{geometry}
```

虽然 `\input`、`\openin`、`\read` 和 `\closein` 原始指令并未被禁止，但包是使用它们的最合适场所。因此，如果你在开发自定义包，最好在自己的包中使用这些指令。

输入的其他部分是任意的，也遵循通用的 [TeX input](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) 概念，取决于你的 TeX 文件（程序）具体要做什么、使用了哪些包等。
