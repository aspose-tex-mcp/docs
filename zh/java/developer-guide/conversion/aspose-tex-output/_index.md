---
translation: true
template: /templates/_template-java.md
title: Aspose.TeX 的输出接口 | Aspose.TeX for Java 开发指南
linktitle: Aspose.TeX 的输出接口
weight: 16
url: /java/aspose-tex-output/
description: Aspose.TeX api解决方案的转换功能与TEX一起使用，作为输出格式，请参见代码示例。
lastmod: "2026-04-21"
---

{{<section overview>}}

请参阅java **Aspose.TeX** [API参考](https://reference.aspose.com/tex/java/com.aspose.tex/)有关I/O实现的正式定义。

文件系统、ZIP 和终端示例将 `hello-world.tex` 排版为 XPS。将 `inputDirectory` 设置为包含 TeX 文件的文件夹，将 `outputDirectory` 设置为现有的输出文件夹。对于 ZIP 输出，将 `outputZip` 设置为现有文件夹中的 `java.nio.file.Path`。 导入所选示例使用的 Aspose.TeX 类、`com.aspose.tex.rendering.XpsDevice` 以及所需的 `java.io` 和 `java.nio.file` 类。调用方法必须处理或声明异常。按照[许可指南](/tex/{{lang.url-fragment}}java/licensing/)应用许可证，以避免评估版限制。

## 输出目录的概念

由于tex语言的I/O元素只能处理文件名，因此aspose.tex将目录定义为名称和大部分数据之间的映射。大部分数据应该是文件，流，数组或其他任何数据。API允许我们分别指定输入和输出工作目录。它为输出提供了常规[iOutputworkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/)接口，用户可以为其自己的目的实现。它还提供了自己的实现，将在下面讨论。该接口扩展了[iinputworkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/)，因为引擎可以首先创建和编写文件，然后将其读回。接口自己的方法[getOuputfile()](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/#getOutputFile-java.lang.String-java.lang.String:A-)返回流的流，而不是[getfile()](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-)返回的流。

### 将文件输出输出到磁盘文件系统

正如我们提到的[上图](/tex/{{lang.url-fragment}}/java/conversion/)，[outputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--)的最常见值可能是[outputsFilesystemdirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputfilesystemdirectory/)类的一个实例。

这是我们将其设置的方式：

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputFileSystemDirectory.java" >}}

此用例非常简单，因此我们很长一段时间都不会呆在上面。

### 将文件输出写入邮政编码

我们还可以创建一个文件(或流)，并让Tex引擎将其用作ZIP存档来存储输出文件。这里是：

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputZipDirectory.java" >}}

首先，我们为zip文件创建一个输出流。然后，在创建转换选项之后，我们将[outputworkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--)选项设置为[outputzipdirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputzipdirectory/)类的实例。 此示例将 `hello-world.xps` 和 `hello-world.log` 保存到归档中。作业结束后，在关闭底层流之前调用输出目录的 `finish()`。示例在作业结束前保持流和工作目录打开，随后关闭它们。

## 输出终端的概念

输出中还有另一个重要部分 - 终端输出。至于这个，java的**Aspose.TeX**将常规[iOutputterminal](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputterminal/)接口定义为具有两种方法。其中一个返回[BufferedWriter](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedWriter.html)实例。另一个将[outputStream](https://docs.oracle.com/javase/6/docs/api/java/io/OutputStream.html)实例作为基础流返回。提供的接口的实现将在下面讨论。

### 将终端输出写入控制台

为此，我们需要将[终端图](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getTerminalOut--)选项设置为[outputConsoleterminal](https://reference.aspose.com/tex/java/com.aspose.tex/outputconsoleterminal/)类的实例。

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputConsoleTerminal.java" >}}

`OutputConsoleTerminal` 是此选项的默认值。此示例显式选择它，并在转换期间将终端输出写入控制台。四个示例均以非交互方式运行；文件系统和 ZIP 示例将终端输出保存在内存中。

### 将终端输出写入文件

与输入终端不同，**aspose.tex的Java**提供了[iOutputterminal](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputterminal/)的实现，这使我们能够将终端输出写入某些输出目录中的文件。

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputFileTerminal.java" >}}

创建 `OutputFileTerminal` 之前先设置输出工作目录。它将终端输出写入该目录中的 [<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trm，在此示例中为 `hello-world.trm`。此终端文件与 TeX 日志 `hello-world.log` 分开。要将终端输出写入其他位置，请向构造函数传入其他 [IOutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/) 实现。