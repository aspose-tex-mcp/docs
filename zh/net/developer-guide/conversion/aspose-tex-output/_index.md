---
translation: true
template: /templates/_template-net.md
title: Aspose.TeX 的输出接口 | Aspose.TeX for .NET 开发指南
linktitle: Aspose.TeX 的输出接口
weight: 16
url: /net/aspose-tex-output/
description: 本文通过代码示例，讲解了 Aspose.TeX API 解决方案在 .NET 环境下将 TeX 文件转换为输出格式的功能。
keywords: aspose tex output, .net tex, output directory, output zip, output console, output terminal, tex options, outputfiledirectory, outputzipdirectory, tex conversion
lastmod: "2026-04-22"
---

{{<section overview>}}

请参阅 **Aspose.TeX for .NET** 的 [API 参考文档](https://reference.aspose.com/tex/net/aspose.tex.io/)，了解 I/O 实现的正式定义。

## 输出目录的概念

由于 TeX 语言的 I/O 原语只能处理文件名，Aspose.TeX 将目录定义为名称与数据块之间的映射。数据块可以是文件、流、数组或其他任何形式。API 允许我们分别指定输入和输出工作目录。它为输出提供了通用的 [IOutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputworkingdirectory/) 接口，用户可以根据自己的需求实现该接口。它还提供了自己的实现，下面将进行讨论。该接口继承自 [IInputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/)，因为引擎可能先创建并写入文件，然后再读取。接口的 [GetOutputFile()](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputworkingdirectory/getoutputfile/) 方法返回用于写入的流，而不是由 [GetFile()](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/getfile/) 返回的读取流。

### 将文件输出写入磁盘文件系统

正如我们在[上文](/tex/{{lang.url-fragment}}net/latex-to-image/)提到的，最常用的 [OutputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) 值通常是 [OutputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) 类的实例。

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-OutputFileSystemDirectory.cs" >}}

此用例非常简单，因而无需再做详细说明。

### 将文件输出写入 ZIP 压缩包

我们也可以创建一个文件（或流），让 TeX 引擎将其用作 ZIP 压缩包来存储输出文件。示例如下：

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-OutputZipDirectory.cs" >}}

首先，为 ZIP 文件创建输出流。随后，在创建转换选项后，我们将 [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) 选项设置为 [OutputZipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/) 类的实例。

## 输出终端的概念

输出还有另一个重要部分——终端输出。针对该部分，**Aspose.TeX for .NET** 定义了通用的 [IOutputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/) 接口，该接口仅包含一个返回 [TextWriter](https://docs.microsoft.com/en-us/dotnet/api/system.io.textwriter) 实例的属性。下面将讨论提供的实现。

### 将终端输出写入控制台

为实现该功能，需要将 [TerminalOut](https://reference.aspose.com/tex/net/aspose.tex/texoptions/terminalout/) 选项设置为 [OutputConsoleTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/) 类的实例。

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-OutputConsoleTerminal.cs" >}}

同样，这也是该选项的默认值，实际上无需显式指定。因此本节仅作演示用途。

### 将终端输出写入文件

不同于输入终端，**Aspose.TeX for .NET** 提供了 [IOutputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/) 的实现，使我们能够将终端输出写入某个输出目录中的文件。

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-OutputFileTerminal.cs" >}} 

此处我们让 TeX 引擎将终端输出写入名为 [<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trm 的文件，该文件将存储在我们为其他输出指定的同一输出目录中。但这并非必须。我们同样可以向构造函数传入任何其他 [IOutputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/) 实现的实例。
