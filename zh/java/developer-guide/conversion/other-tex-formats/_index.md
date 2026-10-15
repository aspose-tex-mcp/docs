---
translation: true
template: /templates/_template-java.md
title: 其他TeX转换输出格式 | Java
linktitle: 其他TeX格式
weight: 18
url: /java/other-tex-formats/
description: Java的Aspose.TeX API解决方案的转换功能允许转换LaTeX文件和您自己的自定义TEX文件。这是一些代码示例。
lastmod: "2026-04-21"
---

{{<section overview>}}

您目前不太可能要转换以除LaTeX以外的任何其他格式编写的TEX文件。但是，如果您出于某种原因正在学习Tex语言和/或内部语言，这是可能的。无论如何，**用于 Java 的 Aspose.TeX**允许您转换以简单的Tex格式编写的文件。它还使您可以创建以这些格式设计的自定义格式和排版文档。

我们将从创建自定义格式开始。

## 创建自定义格式

让我们记住，格式文件是Tex发动机内部状态的二进制文件。

将 `inputDirectory` 设置为包含 `customtex.tex` 及其依赖文件的文件夹，将 `outputDirectory` 设置为现有的输出文件夹。格式源文件必须以 `\dump` 结束；此示例在输出文件夹中创建 `customtex.fmt`。导入示例中使用的 Aspose.TeX 类，以及排版所需的 `com.aspose.tex.rendering.XpsDevice`、`java.io.ByteArrayInputStream` 和 `java.nio.charset.StandardCharsets`。调用方法必须处理或声明异常。按照[许可指南](/tex/{{lang.url-fragment}}java/licensing/)应用许可证，以避免评估版限制。

{{< gist "aspose-com-gists" "d21a098d3848236e0c258661f5bbc0ae" "Example-CreateCustomTeXFormat.java" >}}

如您所见，该代码类似于用于转换Tex文件的代码。但是有一些差异。

首先，在这里，我们使用[TexConfig.ObigntInitex()](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/#objectIniTeX--) 作业配置。这是一种特殊的配置，它使引擎的状态“处女”，即内部参数具有其默认值，并且控制序列的集合与原始序列相吻合。在我们的示例中，从提到的意义上提到的[此处](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)的含义扩展了一组原语。

接下来，我们照常设置输入和输出工作目录。输入工作目录需要包含主要格式源文件及其所有依赖项。

第二个关键区别是我们运行工作的方式。这次，我们使用静态[createformat()](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#createFormat-java.lang.String-com.aspose.tex.TeXOptions-) 方法，该方法与选项一起使用主源文件的名称，该名称必须与格式名称相同。

## 以您的自定义格式排版TEX文件

现在，我们已经拥有自己的TEX格式，我们想在以这种格式写下Tex文件。这是代码：

将 `formatDirectory` 设置为包含已创建的 `customtex.fmt` 的文件夹，将 `outputDirectory` 设置为现有的输出文件夹。此示例将独立的文本流排版为 `typeset-with-custom-format.xps`，因此无需输入工作目录。如果主输入有图像等依赖文件，请设置输入工作目录。

{{< gist "aspose-com-gists" "d21a098d3848236e0c258661f5bbc0ae" "Example-TypesetWithCustomTeXFormat.java" >}}

显然，我们必须以某种方式指定格式。首先，我们需要创建一个[formatprovider](https://reference.aspose.com/tex/java/com.aspose.tex/formatprovider/) 类的实例。然后，在选项构造函数中，我们使用[TeXConfig.objectTeX(FormatProvider)](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/#objectTeX-com.aspose.tex.FormatProvider-)配置，该配置将我们的格式提供程序作为参数，并将格式加载到引擎的“处女”状态之上。

两个示例均以非交互方式运行，并将终端输出保存在内存中。排版示例在作业完成后关闭输入流，释放 XPS 设备，并关闭工作目录和格式提供程序。这些功能已在此[指南](/tex/{{lang.url-fragment}}java/conversion/)中介绍。

## 以普通Tex格式排版Tex文件

如果我们使用不带格式提供程序的 `TeXConfig.objectTeX()`，则引擎将加载默认格式，即[Object Tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/)在其第四种意义上。因此，如果您有一个以普通Tex格式编写的TEX文件，则可以将其转换为任何受支持的目标格式。