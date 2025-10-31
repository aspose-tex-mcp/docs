---
translation: true
template: /templates/_template-net.md
title: Aspose.TeX的输入接口| .NET的Aspose.TeX
linktitle: Aspose.TeX的输入接口
weight: 15
url: /net/aspose-tex-input/
description: Aspose.TeX api解决方案的转换功能。
keywords: aspose.tex 输入、.net tex、输入目录、输入 zip、输入控制台、tex 选项、iinputworkingdirectory、inputzipdirectory、inputterminal、tex 转换
lastmod: "2025-06-10"
---

{{<section overview>}}

请参阅**Aspose.TeX for .NET** [API参考](https://reference.aspose.com/tex/net/aspose.tex.io/)有关I/O实施的正式定义。

## 输入目录的概念

由于tex语言的I/O元素只能处理文件名，因此**Aspose.TeX for .NET**将目录定义为名称和大部分数据之间的映射。大部分数据应该是文件，流，数组或其他任何数据。API允许我们分别指定输入和输出工作目录。它提供了常规[iInputworkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/)接口，用户可以为其自己的目的实现。它还提供了自己的实现，将在下面讨论。该接口定义了[getfile()](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/getfile/)方法，该方法返回数据流并确定文件的全名，同时以假设为不同的名称为第一个参数，实际上是映射密钥。

### 从磁盘文件系统获取文件输入

这就是我们的方式：

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-InputFileSystemDirectory.cs" >}}

此用例非常简单，因此无需重点关注它。

### 从zip档案中获取文件输入

我们还可以将输入文件放入zip存档中，并将其视为输入目录。在这种情况下，我们应该按以下方式进行：

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-InputZipDirectory.cs" >}}

首先，我们创建包含zip文件的流。然后，在创建转换选项后，我们将[InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/inputworkingdirectory/)选项设置为[InputzipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/)类的实例。构造函数的第二个论点是存档内部的基本路径。如果我们希望整个存档成为输入目录，则应传递空字符串。 

## 输入终端的概念

现在是时候记住还有终端输入了。至于这一点，**Aspose.TeX for .NET**定义了一般[iinputterminal](https://reference.aspose.com/tex/net/aspose.tex.io/iinputterminal/)接口，只有一个属性返回[TexTreader](https://docs.microsoft.com/en-us/dotnet/api/system.io.textreader)实现实例。提供的实现将在下面讨论。

### 从控制台获取终端输入

为此，我们需要将[终端素](https://reference.aspose.com/tex/net/aspose.tex/texoptions/terminalin/)选项设置为[InputConsoleterminal](https://reference.aspose.com/tex/net/aspose.tex.io/inputconsoleterminal/)类的实例。

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-InputConsoleTerminal.cs" >}}

但是，告诉您真相，这是该选项的默认值，因此没有真正的指定。由于这一事实，只要没有其他实施，本节就只有演示目的。

从理论上讲，如果我们具有具有可预测行为的交互式TEX文件(或脚本)，我们可能希望实现输入终端的版本，该版本包含一个互补的脚本以响应Tex Engine的请求。有时间尝试您的手！
