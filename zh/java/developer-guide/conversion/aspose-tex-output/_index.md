---
translation: true
template: /templates/_template-java.md
title: 的输出接口|爪哇 | Java的Aspose.TeX
linktitle: 的输出接口
weight: 16
url: /java/aspose-tex-output/
description: Aspose.TeX api解决方案的转换功能与TEX一起使用，作为输出格式，请参见代码示例。
lastmod: "2025-06-10"
---

{{<section overview>}}

请参阅java **Aspose.TeX** [API参考](https://reference.aspose.com/tex/java/com.aspose.tex/package-frame)有关I/O实现的正式定义。

## 输出目录的概念

由于tex语言的I/O元素只能处理文件名，因此aspose.tex将目录定义为名称和大部分数据之间的映射。大部分数据应该是文件，流，数组或其他任何数据。API允许我们分别指定输入和输出工作目录。它为输出提供了常规[iOutputworkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputWorkingDirectory)接口，用户可以为其自己的目的实现。它还提供了自己的实现，将在下面讨论。该接口扩展了[iinputworkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory)，因为引擎可以首先创建和编写文件，然后将其读回。接口自己的方法[getOuputfile()](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputWorkingDirectory#getOutputFile-java.lang.String-java.lang.String:A-)返回流的流，而不是[getfile()](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-)返回的流。

### 将文件输出输出到磁盘文件系统

正如我们提到的[上图](/tex/{{lang.url-fragment}}/java/conversion/)，[outputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--)的最常见值可能是[outputsFilesystemdirectory](https://reference.aspose.com/tex/java/com.aspose.tex/OutputFileSystemDirectory)类的一个实例。

这是我们将其设置的方式：

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-OutputFileSystemDirectory.java" >}}

此用例非常简单，因此我们很长一段时间都不会呆在上面。

### 将文件输出写入邮政编码

我们还可以创建一个文件(或流)，并让Tex引擎将其用作ZIP存档来存储输出文件。这里是：

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-OutputZipDirectory.java" >}}

首先，我们为zip文件创建一个输出流。然后，在创建转换选项之后，我们将[outputworkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--)选项设置为[outputzipdirectory](https://reference.aspose.com/tex/java/com.aspose.tex/OutputZipDirectory)类的实例。

## 输出终端的概念

输出中还有另一个重要部分 - 终端输出。至于这个，java的**Aspose.TeX**将常规[iOutputterminal](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputTerminal)接口定义为具有两种方法。其中一个返回[BufferedWriter](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedWriter.html)实例。另一个将[outputStream](https://docs.oracle.com/javase/6/docs/api/java/io/OutputStream.html)实例作为基础流返回。提供的接口的实现将在下面讨论。

### 将终端输出写入控制台

为此，我们需要将[终端图](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getTerminalOut--)选项设置为[outputConsoleterminal](https://reference.aspose.com/tex/java/com.aspose.tex/OutputConsoleTerminal)类的实例。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-OutputConsoleTerminal.java" >}}

同样，这是该选项的默认值，因此无需指定它。因此，本节仅提供演示目的。

### 将终端输出写入文件

与输入终端不同，**aspose.tex的Java**提供了[iOutputterminal](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputTerminal)的实现，这使我们能够将终端输出写入某些输出目录中的文件。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-OutputFileTerminal.java" >}} 

在这里，我们要求TEX引擎将终端输出写入文件，并使用名称[<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).TRM将其存储在我们为其余输出指定的同一输出目录中存储。但这不是必需的。我们不妨将[IOutputterminal](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputTerminal)实现的任何其他实例传递给构造函数。