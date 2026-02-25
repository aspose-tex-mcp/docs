---
translation: true
template: /templates/_template-net.md
title: Aspose.TeX的输入接口 | .NET
linktitle: Aspose.TeX的输入接口
weight: 15
url: /net/aspose-tex-input/
description: 这里解释了 Aspose.TeX API 解决方案在 .NET 中将 TeX 作为输入格式进行转换的功能，并附有代码示例。
keywords: aspose.tex 输入、.net tex、输入目录、输入压缩包、输入控制台、tex 选项、输入工作目录、输入压缩目录、输入终端、tex 转换
lastmod: "2026-02-25"
aliases: 
- /cpp/typesetting-tex-input/
- /cpp/creating-custom-tex-format/
---

{{<section overview>}}

请参阅 **Aspose.TeX for .NET** 的 [API 参考文档](https://reference.aspose.com/tex/net/aspose.tex.io/) 以获取 I/O 实现的正式定义。

## 输入目录的概念

由于 TeX 语言的 I/O 原语只能处理文件名，**Aspose.TeX for .NET** 将目录定义为名称与数据块之间的映射。数据块可以是文件、流、数组或其他任何东西。API 允许我们分别指定输入和输出工作目录。它提供了通用的 [IInputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/) 接口，用户可以自行实现。它还提供了自己的实现，稍后将讨论。该接口定义了 [GetFile()](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/getfile/) 方法，该方法返回数据流并确定文件的完整名称，同时将某个假设的不同名称作为第一个参数，该参数实际上是映射键。

### 从磁盘文件系统获取文件输入

下面是实现方式：

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-InputFileSystemDirectory.cs" >}}

此用例相当简单，无需再作进一步说明。

### 从 ZIP 存档获取文件输入

我们也可以将输入文件放入 ZIP 存档，并将其视为输入目录。在这种情况下，应按以下步骤进行：

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-InputZipDirectory.cs" >}}

首先，创建包含 ZIP 文件的流。随后，在创建转换选项后，我们将 [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/inputworkingdirectory/) 选项设置为 [InputZipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/) 类的实例。构造函数的第二个参数是存档内部的基路径。如果希望整个存档成为输入目录，则应传入空字符串。

## 输入终端的概念

现在需要提醒的是还有终端输入。针对该输入，**Aspose.TeX for .NET** 定义了通用的 [IInputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/iinputterminal/) 接口，该接口仅包含一个返回 [TextReader](https://docs.microsoft.com/en-us/dotnet/api/system.io.textreader) 实例的属性。下面将讨论提供的实现。

### 从控制台获取终端输入

为此，需要将 [TerminalIn](https://reference.aspose.com/tex/net/aspose.tex/texoptions/terminalin/) 选项设置为 [InputConsoleTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/inputconsoleterminal/) 类的实例。

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-InputConsoleTerminal.cs" >}}

但说实话，这正是该选项的默认值，因此实际上无需显式指定。鉴于此，并且目前没有其他实现，此章节仅用于演示目的。

理论上，如果我们拥有具有可预测行为的交互式 TeX 文件（或脚本），可以实现一个输入终端的版本，用于响应 TeX 引擎请求的补充脚本。有时间可以尝试一下！
