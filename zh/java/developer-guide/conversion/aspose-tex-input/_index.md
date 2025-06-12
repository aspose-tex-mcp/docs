---
translation: true
template: /templates/_template-java.md
title: Aspose.TeX的输入接口|爪哇
linktitle: Aspose.TeX的输入接口
weight: 15
url: /java/aspose-tex-input/
description: Aspose.TeX api解决方案的转换功能与TEX一起使用，作为输入格式，请参见代码示例。
lastmod: "2025-06-10"
---

{{<section overview>}}

请参阅java **Aspose.TeX** [API参考](https://reference.aspose.com/tex/java/com.aspose.tex/package-frame)有关I/O实现的正式定义。

## 输入目录的概念

由于tex语言的I/O个性只能处理文件名，因此**用于 Java 的 Aspose.TeX**将目录定义为名称和大部分数据之间的映射。大部分数据应该是文件，流，数组或其他任何数据。API允许我们分别指定输入和输出工作目录。它提供了常规[iInputworkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory)接口，用户可以为其自己的目的实现。它还提供了自己的实现，将在下面讨论。该接口定义了[getfile()](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-)方法，该方法返回数据流并确定文件的全名，同时以假设为不同的名称为第一个参数，实际上是映射密钥。

### 从磁盘文件系统获取文件输入

这就是我们的方式：

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-InputFileSystemDirectory.java" >}}

此用例非常简单，因此我们很长一段时间都不会呆在上面。

### 从zip档案中获取文件输入

我们还可以将输入文件放入zip存档中，并将其视为输入目录。在这种情况下，我们应该按以下方式进行：

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-InputZipDirectory.java" >}}

首先，我们创建包含zip文件的流。然后，在创建转换选项后，我们将[InputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getInputWorkingDirectory--)选项设置为[InputzipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/InputZipDirectory)类的实例。构造函数的第二个论点是存档内部的基本路径。如果我们希望整个存档成为输入目录，则应传递空字符串。 

## 输入终端的概念

现在，让我们记住，还有终端输入。至于这个，java的**Aspose.TeX**将常规[iinputterminal](https://reference.aspose.com/tex/java/com.aspose.tex/IInputTerminal)接口定义为具有两种方法。其中一个返回[BufferedReader](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedReader.html)实例。另一种方法将[InputStream](https://docs.oracle.com/javase/6/docs/api/java/io/InputStream.html)作为基础流返回。提供的接口的实现将在下面讨论。

### 从控制台获取终端输入

为此，我们需要将[终端素](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getTerminalIn--)选项设置为[InputConsoleterminal](https://reference.aspose.com/tex/java/com.aspose.tex/InputConsoleTerminal)类的实例。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-InputConsoleTerminal.java" >}}

但是，告诉您真相，这是该选项的默认值，因此没有真正的指定。由于这一事实，只要没有其他实施，本节就只有演示目的。

从理论上讲，如果我们具有具有可预测行为的交互式TEX文件(或脚本)，我们可能希望实现输入终端的版本，该版本包含一个互补的脚本以响应Tex Engine的请求。有时间尝试您的手！