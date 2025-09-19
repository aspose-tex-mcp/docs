---
translation: true
template: /templates/_template-conversion-cpp.md
title: 乳胶到PDF| C++的Aspose.TeX
linktitle: 乳胶到PDF
weight: 11
url: /cpp/latex-to-pdf/
keywords: 乳胶到PDF，乳胶PDF，将乳胶转换为PDF
description: 要使用Aspose.TeX API解决方案C ++将TEX转换为PDF。
lastmod: "2025-06-10"
---

{{<section overview>}}

## 如何将乳胶转换为PDF

让我们详细了解C ++的代码，提供将乳胶转换为PDF格式的最简单方法。

{{<app/converter
  input="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-pdf.input">}}"  
  formats="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-pdf.output">}}"
  title="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-pdf.title">}}"
>}}
{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-pdf">}}
{{</app/converter>}}

因此，我们需要做的第一件事(有时不是第一件)是创建[Texoptions](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/)类的实例。这样做的唯一静态方法是[consoleappoptions()](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/consoleappoptions)，因此不要被其名称的含义所困扰。该方法采用[TexConfig](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_config/)类的[实例](https://reference.aspose.com/tex/cpp/aspose.tex/texconfig/get_objectlatex/)，该类完全适合转换[latex文件](/tex/{{lang.url-fragment}}net/latex-io/#latex-file)。该配置告诉对象Tex引擎加载对象乳胶格式并准备好接受乳胶文件。对象乳胶格式实际上只是[乳胶](/tex/{{lang.url-fragment}}net/what-is-latex/)格式，只是它使用[Object tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)特定的原始图来设置页面指标。

所需的第一个选项是[outputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory/)，该选项定义了将编写Tex输出的空间或区域。 [此处](/tex/{{lang.url-fragment}}cpp/aspose-tex-output/)是有关C ++ **Aspose.TeX**中输出目录概念的详细信息。在此示例中，我们使用[outputeFilesystemDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputfilesystemdirectory/)类，该类使我们能够将输出写入指定的目录或文件夹。

第二个选项是[SaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation/saveoptions/)类实例，它将控制[对象模型](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object)对目标格式的转换。由于我们将乳胶转换为PDF，因此是[PDFSaveoptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/)类实例。

然后，我们需要创建一个[Texjob](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/)类的实例。要转换存储在文件系统中的乳胶文件，我们使用[this](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/texjob/#texjobtexjobsystemstring-systemsharedptrpresentationdevice-systemsharedptrtexoptions-constructor)版本的构造函数。我们必须指定文件的完整路径。否则，发动机将在当前目录(即[CurrentDirectory](https://docs.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory))中寻找它，并且很可能找不到它。但是，如果我们的文件具有 *.tex*一个，我们可能会省略扩展名。引擎将自动添加它。构造函数的第二个参数是[设备](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.device)类实例。由于我们将乳胶转换为PDF，因此是[PDFDEVICE](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/)类实例。作为最后一个论点，我们通过了最近准备的转换选项。

现在剩下要做的就是[运行](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_job#a0bc7f8b329ea1f19cbba84bf2060f6fb)工作。

无论运行是否成功，我们都会看到的第一个结果将是终端输出。在成功的情况下，看起来像这样：

```text
This is ObjectTeX, Version 3.1415926-1.0 (Aspose.TeX 21.8)
entering extended mode

(<input_directory>\hello-world.ltx
LaTeX2e <2011/06/27>
(article.cls
Document Class: article 2007/10/19 v1.4h Standard LaTeX document class
(size10.clo))
No file hello-world.aux.
[1]
(<output_directory>\hello-world.aux) )
Output written on hello-world.pdf (1 page).
Transcript written on hello-world.log.
```

我们将在我们指定为输出目录的文件夹中找到引擎劳动力的其他“水果”。这些将是成绩单文件，**在这里是！**，主要输出PDF文件。

## 编写主输出PDF文件的另一种方法

[PDFDEVICE](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/pdfdevice/)类的另一个构造函数使我们可以以另一种方式获取所得的PDF文件。

```C++
    // Create the stream to write the XPS file to.
    {
        System::SharedPtr<System::IO::Stream> pdfStream = System::IO::File::Open(System::IO::Path::Combine(RunExamples::OutputDirectory, u"any-name.pdf"), System::IO::FileMode::Create);
        // Clearing resources under 'using' statement
        System::Details::DisposeGuard<1> __dispose_guard_0({ pdfsStream});
        // ------------------------------------------
        
        try
        {
            // Create conversion options for Object LaTeX format on Object TeX engine extension.
            System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::get_ObjectLaTeX());
            // Specify the file system working directory for the output.
            options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
            // Initialize the options for saving in PDF format.
            options->set_SaveOptions(System::MakeObject<PdfSaveOptions>());
            // Default value.
            // Run LaTeX to XPS conversion.
            System::MakeObject<TeXJob>(System::IO::Path::Combine(RunExamples::InputDirectory, u"hello-world.ltx"), System::MakeObject<PdfDevice>(pdfStream), options)->Run();
        }
        catch(...)
        {
            __dispose_guard_0.SetCurrentException(std::current_exception());
        }
    }
```

指定目录中的 *any-name.pdf*文件将是我们的主要输出PDF文件。同时，与[图像输出](/tex/{{lang.url-fragment}}cpp/latex-to-png/#an-alternative-way-to-write-main-output-png-files)不同，我们在转换选项定义的输出目录中找不到任何PDF文件。异常： *any-name.pdf*位于同一文件系统目录中(通过其路径)，使用[outputfilesystemdirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputfilesystemdirectory/)分配给[outputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory/)选项。

## 关于输入选项
如果我们的主要输入文件需要依赖项，例如，这些依赖项不包含在基本乳胶系统和受支持的软件包中，则我们必须设置[requientInputDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_requiredinputdirectory)选项选项的类似方式，我们设置了[outputworkworkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory/)选项并将依赖项放入该目录中。依赖项可以在子目录中任意组织。如果我们有自己的文件要在排版过程中包括，例如外部图形文件，我们还必须使用通往收集这些文件的位置的路径来设置[InputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_inputworkingdirectory)。我们还可以将主输入文件放置在输入目录中的某个位置，并在`run()`方法中指定相对路径(或者如果主输入文件位于根中，则根本没有指定路径)。 [此处](/tex/{{lang.url-fragment}}cpp/aspose-tex-input/)是有关C ++ 的aspose.tex中输入目录概念的详细信息，并提供了实现。

讨论了其他TEX的工作选择[此处](/tex/{{lang.url-fragment}}cpp/other-options/)。

**您还可以根据[Aspose.TeX for c ++ api](https://products.aspose.com/tex/cpp/)构建的免费乳胶转换[Web App](https://products.aspose.app/tex/conversion/latex-to-pdf)。**