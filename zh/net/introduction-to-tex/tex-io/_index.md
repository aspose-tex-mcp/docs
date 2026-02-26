---
translation: true
template: /templates/_template-net.md
title: TeX 输入/输出
linktitle: TeX I/O
weight: 12
url: /net/tex-io/
description: 在 Aspose.TeX API 中使用 TeX 作为输出或输入格式的基础知识。TeX 作业在一个明确指定的文件上运行。 
lastmod: "2026-02-26"
---

{{<section overview>}}

## TeX 文件

从技术上讲，任何文件都可以是 TeX 文件。它甚至不需要 *.tex* 扩展名。TeX 引擎逐字节读取输入，尝试识别它已知的命令（即其内部状态中的命令）。它只会在遇到未识别的命令时报告错误和/或在终端请求更正（如果它在[交互模式](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes)下运行）。但如果你期望看到类似精美排版的文档，输入应遵循 TeX 语法，并且最好仅包含引擎已知的命令。

## TeX 输入

TeX 作业在一个明确指定的 TeX 文件上运行。因此，我们将此文件包含在某个 TeX 作业的输入中。此外，TeX 有四个与辅助输入相关的原语：

* `\input<file name>` 需要文件名，并在包含该命令的文件处理到 `\input` 命令时立即开始处理该文件。auxiliary 文件结束后，处理返回到包含 `\input` 命令的文件。
* `\openin<4-bit-number>=<file name>` 也需要文件名，但它仅打开文件并将其映射到 0 到 15 之间的一个编号。
* `\read<number> to <control sequence>` 需要文件映射的编号，并一次读取一行，使得 `<control sequence>` 对应读取的记号列表。
* `\closein<4-bit-number>` 关闭映射到该编号的文件。

传递给 `\input` 和 `\openin` 命令的文件名同样会被计入 TeX 输入，我们将它们称为 *辅助输入* 文件或 *依赖项*，而为作业指定的文件我们称为 *主输入* 文件。

这四个命令可以出现在主输入文件或辅助输入文件中。但请注意循环依赖。

当在[交互模式](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes)下运行时，若出现任何错误，TeX 引擎会在终端请求更正。此时，你可能想将错误的命令替换为新的命令。这将是另一种也是最后一种向 TeX 提供输入的方式，我们称之为 *终端输入*。

## TeX 输出

正如我们在[上文](/tex/{{lang.url-fragment}}net/tex-io/#tex-input)中提到的，TeX 作业在一个明确指定的文件上运行。该文件可能不包含任何可排版的数据。它可能只有不会产生字符的控制序列。但通常它会包含此类数据，以便我们得到一个目标格式的文件，该文件应包含我们的排版文本（或引擎和格式允许的其他内容，如果它们已扩展以适应某些目标格式的额外特性）。该文件的名称与输入文件的名称相同。我们将此文件称为 *主输出* 文件。正如我们在[上文](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)提到的，对于原始 TeX，这将是一个 DVI 格式的文件。我们将输入和输出文件去除扩展名后的名称称为 *作业名称*。

此外，TeX 有三个与辅助输出相关的原语：

* `\openout<4-bit-number>=<file name>` 需要文件名，打开文件并将其映射到 0 到 15 之间的一个编号。
* `\write<number>{token list}` 需要文件映射的编号，并将 `token list` 写入该文件。
* `\closeout<4-bit-number>` 关闭映射到该编号的文件。

传递给 `\openout` 命令的文件名同样会被计入 TeX 输出，我们将它们称为 *辅助输出* 文件。

当 TeX 引擎遍历输入时，可能会向 *日志* 或 *转录* 文件输出一些调试信息。我们会将此文件计入 TeX 输出。

在写入日志文件的同时，TeX 引擎可能会向终端输出较少的详细信息。这是 TeX 引擎写入输出的最后一种方式，我们称之为 *终端输出*。

## TeX 交互模式

TeX 作业在任何给定时刻都可能处于四种交互模式中的一种。这些模式通过以下 TeX 原语切换：

* `\batchmode`。引擎省略所有停顿并省略终端输出，因此既不需要输入也不需要输出终端。
* `\nonstopmode`。引擎省略所有停顿，仅需要终端进行输出。
* `\scrollmode`。引擎省略错误停顿，并且需要终端进行输入和输出。
* `\errorstopmode`。引擎在每个机会都会停下来进行交互。

Aspose.TeX 允许我们在创建对象时将交互模式指定为 TeX 作业选项。此模式将在加载 TeX 格式后（如果需要加载任何格式）立即设置到引擎的内部状态中，并在引擎遇到上述四个命令之一时切换到另一个模式。此选项的默认值将保留由 TeX 格式定义的交互模式。如果未加载任何格式，交互模式将与 `\errorstopmode` 命令设置的相同。
