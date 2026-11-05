---
translation: true
template: /templates/_template-java.md
title: Aspose.TeX 的输入接口 | Aspose.TeX for Java 开发指南
linktitle: Aspose.TeX 的输入接口
weight: 15
url: /java/aspose-tex-input/
description: Aspose.TeX api解决方案的转换功能与TEX一起使用，作为输入格式，请参见代码示例。
lastmod: "2026-04-21"
---

{{<section overview>}}

请参阅java **Aspose.TeX** [API参考](https://reference.aspose.com/tex/java/com.aspose.tex/)有关I/O实现的正式定义。

文件系统和 ZIP 示例将 `hello-world.tex` 排版为 `hello-world.xps`。将 `inputDirectory` 设置为包含 TeX 文件的文件夹，将 `outputDirectory` 设置为现有的输出文件夹。对于 ZIP 输入，将 `inputZip` 设置为指向包含 `in/hello-world.tex` 的归档文件的 `java.nio.file.Path`。 导入所选示例使用的 Aspose.TeX 类、`com.aspose.tex.rendering.XpsDevice` 以及所需的 `java.io` 和 `java.nio.file` 类。调用方法必须处理或声明异常。按照[许可指南](/tex/{{lang.url-fragment}}java/licensing/)应用许可证，以避免评估版限制。

## 输入目录的概念

由于tex语言的I/O个性只能处理文件名，因此**用于 Java 的 Aspose.TeX**将目录定义为名称和大部分数据之间的映射。大部分数据应该是文件，流，数组或其他任何数据。API允许我们分别指定输入和输出工作目录。它提供了常规[iInputworkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/)接口，用户可以为其自己的目的实现。它还提供了自己的实现，将在下面讨论。该接口定义了[getfile()](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-)方法，该方法返回数据流并确定文件的全名，同时以假设为不同的名称为第一个参数，实际上是映射密钥。

### 从磁盘文件系统获取文件输入

这就是我们的方式：

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-InputFileSystemDirectory.java" >}}

此用例非常简单，因此我们很长一段时间都不会呆在上面。

### 从zip档案中获取文件输入

我们还可以将输入文件放入zip存档中，并将其视为输入目录。在这种情况下，我们应该按以下方式进行：

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-InputZipDirectory.java" >}}

首先，我们创建包含zip文件的流。然后，在创建转换选项后，我们将[InputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getInputWorkingDirectory--)选项设置为[InputzipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputzipdirectory/)类的实例。构造函数的第二个论点是存档内部的基本路径。如果我们希望整个存档成为输入目录，则应传递空字符串。 此示例在 TeX 作业结束前保持 ZIP 流和输入目录打开，随后关闭它们。示例以非交互方式运行，并将终端输出保存在内存中。

## 输入终端的概念

现在，让我们记住，还有终端输入。至于这个，java的**Aspose.TeX**将常规[iinputterminal](https://reference.aspose.com/tex/java/com.aspose.tex/iinputterminal/)接口定义为具有两种方法。其中一个返回[BufferedReader](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedReader.html)实例。另一种方法将[InputStream](https://docs.oracle.com/javase/6/docs/api/java/io/InputStream.html)作为基础流返回。提供的接口的实现将在下面讨论。

### 从控制台获取终端输入

为此，我们需要将[终端素](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getTerminalIn--)选项设置为[InputConsoleterminal](https://reference.aspose.com/tex/java/com.aspose.tex/inputconsoleterminal/)类的实例。

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-InputConsoleTerminal.java" >}}

`InputConsoleTerminal` 是此选项的默认值。此示例仅演示终端配置，不运行作业。请求终端输入的作业需要用户输入或自定义终端实现。上面的文件系统和 ZIP 示例使用完整的输入文件以非交互方式运行。

从理论上讲，如果我们具有具有可预测行为的交互式TEX文件(或脚本)，我们可能希望实现输入终端的版本，该版本包含一个互补的脚本以响应Tex Engine的请求。有时间尝试您的手！