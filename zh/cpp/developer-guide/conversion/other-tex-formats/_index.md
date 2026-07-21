---
translation: true
template: /templates/_template-cpp.md
title: 其他TEX转换输出格式| C++的Aspose.TeX
linktitle: 其他Tex格式
weight: 18
url: /cpp/other-tex-formats/
description: C ++的Aspose.TeX API解决方案的转换功能允许转换乳胶文件和您自己的自定义TEX文件。这是一些代码示例。
lastmod: "2025-06-10"
---

{{<section overview>}}

您目前不太可能要转换以除乳胶以外的任何其他格式编写的TEX文件。但是，如果您出于某种原因正在学习Tex语言和/或内部语言，这是可能的。无论如何，**aspose.tex for c ++**允许您转换以普通Tex格式编写的文件。它还使您可以创建以这些格式设计的自定义格式和排版文档。

我们将从创建自定义格式开始。

## 创建自定义格式

让我们记住，格式文件是Tex发动机内部状态的二进制文件。

```C++
// Create typesetting options for no format on ObjectTeX engine extension.
System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::get_ObjectIniTeX());
// Specify a file system working directory for input.
options->set_InputWorkingDirectory(System::MakeObject<InputFileSystemDirectory>(RunExamples::InputDirectory));
// Specify a file system working directory for output.
options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
    
// Run format creation.
Aspose::TeX::TeXJob::CreateFormat(u"customtex", options);
    
// For further output to look write.
options->get_TerminalOut()->get_Writer()->WriteLine();
```
如您所见，该代码类似于用于转换Tex文件的代码。但是有一些差异。

首先，在这里我们使用[TexConfig.ObigntInitex](https://reference.aspose.com/tex/cpp/aspose.tex/texconfig/#aefa7bbdf2ed28d6499f2dc5d5ad2ca3e)作业配置。这是一种特殊的配置，它使引擎的状态“处女”，即内部参数具有其默认值，并且控制序列的集合与原始序列相吻合。在我们的示例中，从提到的意义上提到的[此处](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)的含义扩展了一组原语。

接下来，我们照常设置输入和输出工作目录。输入工作目录需要包含主要格式源文件及其所有依赖项。

第二个关键区别是我们运行工作的方式。这次，我们使用静态[createformat()](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/)方法，该方法与选项一起使用主源文件的名称，该名称必须与格式名称相同。

## 以您的自定义格式排版TEX文件

现在，我们已经拥有自己的TEX格式，我们想在以这种格式写下Tex文件。这是代码：

```C++
// Create typesetting options for a custom format on ObjectTeX engine extension.
System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::ObjectTeX(formatProvider));
options->set_JobName(u"typeset-with-custom-format");
// Specify the input working directory.
options->set_InputWorkingDirectory(wd);
// Specify a file system working directory for output.
options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
            
// Run typesetting.
System::MakeObject<Aspose::TeX::TeXJob>(System::MakeObject<System::IO::MemoryStream>(System::Text::Encoding::get_ASCII()->GetBytes(u"Congratulations! You have successfully typeset this text with your own TeX format!\\end")), System::MakeObject<XpsDevice>(), options)->Run();
            
// For further output to look write.
options->get_TerminalOut()->get_Writer()->WriteLine();
```

显然，我们必须以某种方式指定格式。首先，我们需要创建一个[formatprovider](https://reference.aspose.com/tex/cpp/aspose.tex.resourceproviders/formatprovider/)类的实例。然后，在选项构造函数中，我们使用[TexConfig.Objecttex()](https://reference.aspose.com/tex/cpp/aspose.tex/texconfig/#aefa7bbdf2ed28d6499f2dc5d5ad2ca3e)配置，该配置将我们的格式提供程序作为参数，并将格式加载到引擎的“处女”状态之上。

代码的其余部分应该熟悉。它使用此[指南](/tex/{{lang.url-fragment}}cpp/conversion/)前面讨论的功能。

## 以普通Tex格式排版Tex文件

如果我们从刚刚演示的代码中丢弃格式提供商，则引擎将加载默认格式，即[Object Tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/)在其第四种意义上。因此，如果您有一个以普通Tex格式编写的TEX文件，则可以将其转换为任何受支持的目标格式。