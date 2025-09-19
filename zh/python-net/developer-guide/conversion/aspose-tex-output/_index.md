---
translation: true
template: /templates/_template-python-net.md
title: Aspose.TeX的输出接口| 通过 .NET 为 Python 提供 Aspose.TeX
linktitle: Aspose.TeX的输出接口
weight: 16
url: /python-net/aspose-tex-output/
description: 这是对python的Aspose.TeX API解决方案的转换功能的说明，并用Tex作为输出格式，并带有代码示例。
lastmod: "2025-06-10"
---

{{<section overview>}}


> 有关 I/O 实现的正式定义，请参考 **Aspose.TeX for Python** 的 [API 参考](https://reference.aspose.com/tex/python-net/aspose.tex.io/)。

## 输出目录背后的想法

aspose.tex将目录定义为名称和大部分数据之间的映射，其中大部分数据可以是文件，流，数组或其他类型的数据。 API允许规范单独的输入和输出工作目录。对于输出，API提供了常规[iOutputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/ioutputworkingdirectory/)接口，该接口可以由用户为其特定需求而实现。此外，API提供了现成的实现，将在下面讨论。 *iOutputworkingDirectory*接口扩展了[iinputworkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/)，因为引擎可能首先创建和编写文件，然后将其读回。该接口包括[get_output_file()](https://reference.aspose.com/tex/python-net/aspose.tex.io/ioutputworkingdirectory/get_output_file/#str)方法，该方法返回流写为写入的流，与[get_file()](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/get_file/#str-bool)方法相比，该方法返回流以从中读取的流。

### 将输出作为文件保存在磁盘文件系统中

如[上面](/tex/{{lang.url-fragment}}net/latex-to-image/)所述，[output_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/output_working_directory/)通常被设置为[outputfilesystemdirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputfilesystemdirectory/)类的实例。

这是我们将其设置的方式：

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-OutputFileSystemDirectory.py" >}}

这种特殊的用例很简单，因此无需进一步深入研究。

### 将输出作为邮政编码文件保存。

另一个选项是创建文件或流，并将其用作zip存档来存储输出文件。这是一个示例：

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-OutputZipDirectory.py" >}}

首先，我们为zip文件创建一个输出流。然后，在创建转换选项后，我们将 *output_working_directory*选项设置为[outputzipdirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputzipdirectory/)类的实例。

## 输出终端背后的想法

终端输出是输出的另一个重要方面。为此，**aspose.tex for Python**定义了常规[iOutputterminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/ioutputterminal/)接口，该接口具有单个属性，该属性返回[终端作者](https://reference.aspose.com/tex/python-net/aspose.tex.io/terminalwriter/)实现的实例。可用的实现将在下面讨论。

### 将终端输出写入控制台

为此，我们需要将[terminal_out](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/terminal_out/)选项设置为[outputConsoleterminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputconsoleterminal/)类的实例。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-OutputConsoleTerminal.py" >}}

再次，这是该选项的默认值，因此无需指定它。因此，本节仅用于演示目的。

### 将终端输出写入文件

与输入终端相反，**aspose.tex的python**包括*iOutputterm*接口的实现，使我们能够将终端输出写入指定的输出目录中的文件。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-OutputFileTerminal.py" >}} 

在这种情况下，我们指示TEX引擎将终端输出写入名为[<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).TRM的文件，该文件将位于与其余输出的同一输出目录中。但是，这不是强制性的。我们还可以向构造函数提供 *iOutputtermal*实现的任何其他实例。