---
translation: true
template: /templates/_template-cpp.md
title: Aspose.TeX的输入接口| Aspose.TeX for C++ 开发指南
linktitle: Aspose.TeX的输入接口
weight: 15
url: /cpp/aspose-tex-input/
description: ASPOSE.TEX API解决方案的转换功能与TEX一起使用，作为输入格式，请参见代码示例。
lastmod: "2025-06-10"
---

{{<section overview>}}

有关 I/O 实现的正式定义，请参阅 **Aspose.TeX for C++** [API 参考](https://reference.aspose.com/tex/cpp/aspose.tex.io/)。

## 输入目录的概念

由于tex语言的I/O元素只能处理文件名，因此**aspose.tex for c ++**将目录定义为名称和大部分数据之间的映射。大部分数据应该是文件，流，数组或其他任何数据。API允许我们分别指定输入和输出工作目录。它提供了常规[iInputworkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputworkingdirectory/)接口，用户可以为其自己的目的实现。它还提供了自己的实现，将在下面讨论。该接口定义了[getfile()](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputworkingdirectory/getfile/)方法，该方法返回数据流并确定文件的全名，同时以假设为不同的名称为第一个参数，实际上是映射密钥。

### 从磁盘文件系统获取文件输入

这就是我们的方式：

```C++
// Create conversion options instance.
...
// Specify a file system working directory for input.
options->set_InputWorkingDirectory(System::MakeObject<InputFileSystemDirectory>(RunExamples::InputDirectory));

```

此用例非常简单，因此无需重点关注它。

### 从zip档案中获取文件输入

我们还可以将输入文件放入zip存档中，并将其视为输入目录。在这种情况下，我们应该按以下方式进行：

```C++
    // Open a stream on a ZIP archive that will serve as the input working directory.
    System::SharedPtr<System::IO::Stream> inZipStream = System::IO::File::Open(System::IO::Path::Combine(RunExamples::InputDirectory, u"zip-in.zip"), System::IO::FileMode::Open);

    // Create conversion options instance.
    ...
    // Specify a ZIP archive working directory for input.
    options->set_InputWorkingDirectory(System::MakeObject<InputZipDirectory>(inZipStream, u"in"));
```

首先，我们创建包含zip文件的流。然后，在创建转换选项后，我们将[InputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_inputworkingdirectory/)选项设置为[InputzipDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/inputzipdirectory/)类的实例。构造函数的第二个论点是存档内部的基本路径。如果我们希望整个存档成为输入目录，则应传递空字符串。 

## 输入终端的概念

现在是时候记住还有终端输入了。至于这个，**aspose.tex for c ++**定义了一般[iinputterminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputterminal/)接口，其接口只有一个属性返回[TexTreader](https://reference.aspose.com/tex/cpp/system.io/textreader/)实现实例。提供的实现将在下面讨论。

### 从控制台获取终端输入

为此，我们需要将[终端素](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_terminalin/)选项设置为[InputConsoleterminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/inputconsoleterminal/)类的实例。

```C++
// Create conversion options instance.
...
// Specify the console as the input terminal.
options->set_TerminalIn(System::MakeObject<InputConsoleTerminal>()); // Default. Not necessary to specify.

```

但是，告诉您真相，这是该选项的默认值，因此没有真正的指定。 :-)由于这个事实，只要没有其他实现，本节就只有演示目的。

从理论上讲，如果我们具有具有可预测行为的交互式TEX文件(或脚本)，我们可能希望实现输入终端的版本，该版本包含一个互补的脚本以响应Tex Engine的请求。有时间尝试您的手！