---
translation: true
template: /templates/_template-net.md
title: Tex I/O | Aspose.TeX API解决方案.NET
linktitle: Tex I/O。
weight: 12
url: /net/tex-io/
description: 与Tex合作作为Aspose.TeX API中的输出或输入格式的基本原理。 Tex作业在明确指定的文件上运行。
lastmod: "2025-06-10"
---

{{<section overview>}}

## Tex文件

从技术上讲，任何文件都可以是TEX文件。它甚至不需要具有 *.tex*扩展名。 Tex引擎通过字节读取输入字节，以识别其已知的命令(即，在其内部状态的命令)。它只需报告有关终端上未认可的命令和/或请求更正的错误(如果它以[Interactive Mode](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes)运行)。但是，如果您期望看到类似排版的文档之类的内容，则输入应遵循Tex语法，理想情况下，仅包含引擎已知的命令。

## Tex输入

Tex作业在明确指定的TEX文件上运行。因此，我们将此文件包括在某个Tex作业的输入中。此外，Tex有四个与辅助输入相关的原语：

* `\input <文件名>`需要一个文件名，并在包含文件的处理后立即开始处理该文件。一旦达到辅助文件的末尾，处理将返回到包含`\input`命令的文件。
* `\openin <4-bit-number> = <文件名>`还需要一个文件名，但它只是打开文件并将其映射到0到15的数字。
* `\读取<数字> to <Control sequence>`需要文件映射到的数字，并一次从中读取一行，以便`<control sequence>`对应于令牌列表。
* `\closein <4-bit-number>`闭合映射到该号码的文件。

Tex输入中还包含其名称的文件传递给`\input`和`\openin`命令，我们将其称为 *辅助输入*文件或 *依赖项*，而为作业指定的文件，我们将称为 *main Input*文件。

这四个命令可以在主输入文件或辅助输入文件中发生。但是要当心循环依赖性。

在[交互式模式](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes)中运行时，如果有任何错误，则TEX引擎请求对终端进行更正。此时，您可能需要用新命令替换错误命令。这将是向TEX提供输入的另一种方法，我们将称为 *终端输入 *。

## Tex输出

正如我们提到的[上面](/tex/{{lang.url-fragment}}net/tex-io/#tex-input)，Tex作业在明确指定的文件上运行。该文件可能不包含任何数据以排版的数据。可能只有控制序列不会产生字符。但是通常它将包含此类数据，以便我们将以目标格式获得一个文件，该文件应包含我们的排字文本(或引擎和格式所允许的其他内容，如果它们扩展以适合某个目标格式的额外功能)。该文件将具有与指定为输入的文件相同的名称。我们将此文件称为 *MAIN OUTUPT*文件。正如我们提到的[上面](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)，对于原始TEX，这将是DVI格式的文件。我们将调用输入文件的名称和输出文件，而无需扩展 *作业名称*。

此外，Tex有三个与辅助输出相关的原始物：

* `\openout <4-bit-number> = <文件名>需要文件名`，打开文件并将其映射到0到15的数字。
* `\ write <数字> {token list}`需要文件映射到的数字，并将```token list)``列为文件。
* `\closeout <4-bit-number>`关闭映射到该号码的文件。
 
将其名称传递给`\openout`命令的文件都包含在Tex输出中，我们将其称为 *辅助输出*文件。

当TEX引擎通过输入运行时，它可能会将一些调试信息输出到 *log*或 *trascript*，文件。我们将在Tex输出中包括此文件。
同时，随着写入日志文件，Tex引擎可能会将较少详细信息输出到终端。这是Tex引擎写入我们称之为 *终端输出*的输出的最后方式。

## TEX交互模式

在任何给定时间，Tex作业可能以四种互动模式之一进行。这些模式通过以下Tex原始词进行切换：

* `\ batchmode`。发动机省略了所有停止，并省略了终端输出，因此不需要输入或输出的终端。
* `\ nonstopmode`。发动机省略了所有停止，因此仅需要端子才能输出。
* `\ scrollmode`。发动机省略了错误停止，并且需要输入和输出的终端。
* `\ errorStopmode`。发动机会停止每一次互动。

aspose.tex允许我们在创建对象时将交互模式指定为TEX作业选项。加载Tex格式后(如果应该完全加载任何格式)后，将立即在发动机的内部状态下设置此模式，并在引擎遇到四个命令之一的一个时，将立即切换到另一种模式。此选项的默认值将保留由Tex格式定义的交互模式。当没有加载格式时，交互模式与`\ errorsstopmode`命令设置的相同。