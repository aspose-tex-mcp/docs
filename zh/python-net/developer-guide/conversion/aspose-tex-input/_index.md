---
translation: true
template: /templates/_template-python-net.md
title: Aspose.TeX的输入接口| 通过 .NET 为 Python 提供 Aspose.TeX
linktitle: Aspose.TeX的输入接口
weight: 15
url: /python-net/aspose-tex-input/
description: Aspose.TeX API解决方案的转换功能与Tex一起使用，作为输入格式，请参见代码示例。
lastmod: "2025-06-10"
---

{{<section overview>}}

> 有关 **Aspose.TeX for Python** 中 I/O 实现的正式定义，请查阅 [API 参考](https://reference.aspose.com/tex/python-net/aspose.tex.io/)。

## 输入目录背后的想法

鉴于Tex语言的I/O元素只能处理文件名，**aspose.tex for Python**将目录定义为名称和数据集合之间的映射。这些数据集可以是文件，流，数组或任何其他类型。 API允许单独规范输入和输出工作目录。它提供了常规[InputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputworkingdirectory/)类，用户可以为其特定需求实施。此外，API提供了内置的实现，将在后面讨论。该接口包括[get_file()](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/get_file/#str-bool)方法，该方法可检索数据流并根据给定名称确定完整的文件名，该名称用作映射密钥。

### 从磁盘文件系统检索文件输入

这是我们将采用的方法：

将 `ASPOSE_TEX_OUTPUT_DIR` 设置为输出目录（默认 `output`）。请先应用许可证。 [Licensing](/tex/zh/python-net/licensing/).

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputFileSystemDirectory.py" >}}

将 `ASPOSE_TEX_INPUT_DIR` 设置为包含 `hello-world.tex` 的文件夹（默认 `input`）。示例使用 `TeXConfig.object_tex()` 处理 plain TeX，生成 `hello-world.xps` 和 `hello-world.log`。输入文件：

```tex
Hello, World!
\end
```

### 从zip档案中检索文件输入

另一个选项是将输入文件存储在zip存档中，并将其视为输入目录。在这种情况下，应遵循以下步骤：

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputZipDirectory.py" >}}

`ASPOSE_TEX_INPUT_ZIP` 指定包含 `in/hello-world.tex` 的压缩包（默认 `zip-in.zip`）。以二进制模式 `rb` 打开，并在作业结束前保持流打开。

首先，我们创建包含zip文件的流。随后，在创建转换选项后，我们将[InputzipDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputzipdirectory/)类的实例分配给[Input_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/input_working_directory/)属性。构造函数的第二个参数表示存档中的基本路径。如果我们希望整个存档作为输入目录，则应提供一个空字符串作为参数。

## 输入终端背后的想法

现在，让我们考虑终端输入的概念。 **python的aspose.tex**定义了用于此目的的常规[iinputterminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputterminal/)接口，其中包括一个单个属性，该属性返回[终端Rreader](https://reference.aspose.com/tex/python-net/aspose.tex.io/terminalreader/)实现的实例。可用的实现将在稍后讨论。

### 从控制台获取终端输入

为了实现这一目标，我们需要将[InputConsoleterminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputconsoleterminal/)类的实例分配给[terminal_in](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/terminal_in/)选项。

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputConsoleTerminal.py" >}}

示例通过 `\read` 读取一行并写入 `texput.xps`。在终端输入例如 `Terminal input works!`，或通过标准输入提供该行。`SCROLL_MODE` 允许此输入请求。
