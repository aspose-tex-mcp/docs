---
translation: true
template: /templates/_template-net.md
title: 其他TeX转换输出格式| .NET的Aspose.TeX
linktitle: 其他TeX格式
weight: 18
url: /net/other-tex-formats/
description: .NET的Aspose.TeX API解决方案的转换功能允许转换LaTeX文件和您自己的自定义TeX文件。这是一些代码示例。
lastmod: "2026-04-22"
---

{{<section overview>}}

您目前不太可能要转换以除LaTeX以外的任何其他格式编写的TeX文件。但是，如果您出于某种原因正在学习TeX语言和/或内部语言，这是可能的。无论如何，**Aspose.TeX for .NET**允许您转换以普通TeX格式编写的文件。它还使您可以创建以这些格式设计的自定义格式和排版文档。

我们将从创建自定义格式开始。

## 创建自定义格式

让我们记住，格式文件是TeX发动机内部状态的二进制文件。

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-CreateCustomFormat.cs" >}}

如您所见，该代码类似于用于转换TeX文件的代码。但是有一些差异。

首先，在这里我们使用[TeXConfig.ObjectIniTeX](https://reference.aspose.com/tex/net/aspose.tex/texconfig/objectinitex/)作业配置。这是一种特殊的配置，它使引擎的状态“处女”，即内部参数具有其默认值，并且控制序列的集合与原始序列相吻合。在我们的示例中，从提到的意义上提到的[此处](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)的含义扩展了一组原语。

接下来，我们照常设置输入和输出工作目录。输入工作目录需要包含主要格式源文件及其所有依赖项。

第二个关键区别是我们运行工作的方式。这次，我们使用静态[CreateFormat()](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/)方法，该方法与选项一起使用主源文件的名称，该名称必须与格式名称相同。

## 以您的自定义格式排版TeX文件

现在，我们已经拥有自己的TeX格式，我们想在以这种格式写下TeX文件。这是代码：

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-TypesetWithCustomFormat.cs" >}}

显然，我们必须以某种方式指定格式。首先，我们需要创建一个[FormatProvider](https://reference.aspose.com/tex/net/aspose.tex.resourceproviders/formatprovider/)类的实例。然后，在选项构造函数中，我们使用 [TeXConfig.ObjectTeX()](https://reference.aspose.com/tex/net/aspose.tex/texconfig/objecttex/) 配置，该配置将我们的格式提供程序作为参数，并将格式加载到引擎的“处女”状态之上。

代码的其余部分应该熟悉。它使用此[指南](/tex/{{lang.url-fragment}}net/conversion/)前面讨论的功能。

## 以普通TeX格式排版TeX文件

如果我们从刚刚演示的代码中丢弃格式提供商，则引擎将加载默认格式，即[Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/)在其第四种意义上。因此，如果您有一个以普通TeX格式编写的TeX文件，则可以将其转换为任何受支持的目标格式。
