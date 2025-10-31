---
translation: true
template: /templates/_template-net.md
title: Aspose.TeX的输出接口| .NET的Aspose.TeX
linktitle: Aspose.TeX的输出接口
weight: 16
url: /net/aspose-tex-output/
description: Aspose.TeX API解决方案的转换功能，用于带有TEX的.NET作为输出格式，并在此处解释了代码示例。
keywords: aspose tex 输出、.net tex、输出目录、输出 zip、输出控制台、输出终端、tex 选项、outputfiledirectory、outputzipdirectory、tex 转换
lastmod: "2025-06-10"
---

{{<section overview>}}

请参阅**Aspose.TeX for .NET** [API参考](https://reference.aspose.com/tex/net/aspose.tex.io/)有关I/O实施的正式定义。

## 输出目录的概念

由于tex语言的I/O元素只能处理文件名，因此aspose.tex将目录定义为名称和大部分数据之间的映射。大部分数据应该是文件，流，数组或其他任何数据。API允许我们分别指定输入和输出工作目录。它为输出提供了常规[iOutputworkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputworkingdirectory/)接口，用户可以为其自己的目的实现。它还提供了自己的实现，将在下面讨论。该接口扩展了[iinputworkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/)，因为引擎可以首先创建和编写文件，然后将其读回。接口自己的方法[getOutputfile()](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputworkingdirectory/getoutputfile/)返回流的流，而不是[getfile()](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/getfile/)返回的流。

### 将文件输出输出到磁盘文件系统

正如我们提到的[上图](/tex/{{lang.url-fragment}}net/latex-to-image/)，[outputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/)的最常见值可能是[outpulefilesystemdirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)类的一个实例。

这是我们将其设置的方式：

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-OutputFileSystemDirectory.cs" >}}

此用例非常简单，因此无需重点关注它。

### 将文件输出写入邮政编码

我们还可以创建一个文件(或流)，并让Tex引擎将其用作ZIP存档来存储输出文件。这里是：

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-OutputZipDirectory.cs" >}}

首先，我们为zip文件创建一个输出流。然后，在创建转换选项之后，我们将[outputworkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/)选项设置为[outputzipdirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/)类的实例。

## 输出终端的概念

输出中还有另一个重要部分 - 终端输出。至于这个，**Aspose.TeX for .NET**定义了一般[iOutputterminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/)接口，其接口只有一个属性返回[TextWriter](https://docs.microsoft.com/en-us/dotnet/api/system.io.textwriter)实现实例。提供的实现将在下面讨论。

### 将终端输出写入控制台

为此，我们需要将[终端图](https://reference.aspose.com/tex/net/aspose.tex/texoptions/terminalout/)选项设置为[outputConsoleterminal](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)类的实例。

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-OutputConsoleTerminal.cs" >}}

同样，这是该选项的默认值，因此无需指定它。因此，本节仅提供演示目的。

### 将终端输出写入文件

与输入终端不同，**Aspose.TeX for .NET**提供了[iOutputterminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/)的实现，这使我们能够将终端输出写入某些输出目录中的文件。

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-OutputFileTerminal.cs" >}} 

在这里，我们要求Tex引擎将终端输出写入文件，并使用名称[<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).TRM将其存储在我们为其余输出指定的相同输出目录中存储。但这不是必需的。我们不妨将[IOutputterminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/)实现的任何其他实例传递给构造函数。
