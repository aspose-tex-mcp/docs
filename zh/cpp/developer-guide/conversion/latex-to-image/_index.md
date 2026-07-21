---
translation: true
template: /templates/_template-conversion-cpp.md
title: 乳胶到图像| C++的Aspose.TeX
linktitle: 乳胶到图像
weight: 10
url: /cpp/latex-to-image/
keywords: 乳胶到PNG，乳胶PNG，乳胶到图像，乳胶图像，乳胶到JPG，乳胶JPG，乳胶，乳胶至JPEG，jpeg，latex jpeg，latex jpeg，latex to tiff，tiff，latex tiff，latex to bmp to bmp，latex bmp
description: 要使用 Aspose.TeX API 解决方案将 TEX 转换为图像格式，请了解本文，它描述了如何执行此操作以及代码示例。
lastmod: "2026-04-20"
---

{{<section overview>}}

**Aspose.TeX for C++**还允许我们将乳胶文件转换为其他许多栅格图像格式。

## 如何将乳胶转换为png

让我们详细了解C ++的代码，提供将乳胶转换为PNG格式的最简单方法。

{{<app/converter 
  input="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images.input">}}"  
  formats="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images.output">}}"
  title="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images.title">}}"
>}}
{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images">}}
{{</app/converter>}}
        

因此，我们需要做的第一件事(有时不是第一件)是创建[Texoptions](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/)类的实例。这样做的唯一静态方法是[consoleappoptions()](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/consoleappoptions/)，因此不要被其名称的含义所困扰。该方法将[TexConfig](https://reference.aspose.com/tex/cpp/aspose.tex/texconfig/)类的[GET_OBJECTLATEX()实例](https://reference.aspose.com/tex/cpp/aspose.tex/texconfig/get_objectlatex/)进行，该类完全适合转换[latex file](/tex/{{lang.url-fragment}}net/latex-io/#latex-file)。该配置告诉对象Tex引擎加载对象乳胶格式并准备好接受乳胶文件。对象乳胶格式实际上只是[乳胶](/tex/{{lang.url-fragment}}net/what-is-latex/)格式，只是它使用[Object tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)特定的原始图来设置页面指标。

所需的第一个选项是[outputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory/)，该选项定义了将编写Tex输出的空间或区域。 [此处](/tex/{{lang.url-fragment}}cpp/aspose-tex-output/)是有关C ++ **Aspose.TeX**中输出目录概念的详细信息。在此示例中，我们使用[OutputFileSystemDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputfilesystemdirectory/)类，该类使我们能够将输出写入指定的目录或文件夹。

第二个选项是[SaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex.presentation/saveoptions/)类实例，它将控制[对象模型](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object)对目标格式的转换。由于我们将乳胶转换为png，因此是[pngsaveoptions](https://reference.aspose.com/tex/cpp/aspose.tex.presentation.image/pngsaveoptions/)类实例，它使我们可以指定输出图像的分辨率。

接下来，我们需要创建[Texjob](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/)类的实例。要转换存储在文件系统中的乳胶文件，我们使用[this](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/texjob/#texjobtexjobsystemstring-systemsharedptrpresentationdevice-systemsharedptrtexoptions-constructor)版本的构造函数。我们需要指定文件的完整路径。否则，发动机将在当前目录(即[CurrentDirectory](https://learn.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory?view=net-10.0))中寻找它，并且很可能找不到它。但是，如果我们的文件具有 *.tex*一个，我们可能会省略扩展名。引擎将自动添加它。构造函数的第二个参数是[设备](https://reference.aspose.com/tex/cpp/aspose.tex.presentation/device/)类实例。由于我们将乳胶转换为png，因此它是[Imagedevice](https://reference.aspose.com/tex/cpp/aspose.tex.presentation.image/imagedevice/)类(对于所有受支持的图像格式)实例。作为最后一个论点，我们通过了最近准备的转换选项。

现在剩下要做的就是[运行](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/#a0bc7f8b329ea1f19cbba84bf2060f6fb)工作。

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
Output written on hello-world.png (1 page).
Transcript written on hello-world.log.
```

我们将在我们指定为输出目录的文件夹中找到引擎劳动力的其他“水果”。这些将是成绩单文件，**在这里是！**，主要输出png映像文件。

## 编写主要输出PNG文件的另一种方法

还有另一种将图像数据作为字节数组数组的方法，第二维中的每个数组代表单独的页面的图像数据。

```C++
    // Create conversion options for Object LaTeX format on Object TeX engine extension.
    System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::get_ObjectLaTeX());
    // Specify the file system working directory for the output.
    options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
    // Initialize the options for saving in PNG format.
    options->set_SaveOptions(System::MakeObject<PngSaveOptions>());
    // Run LaTeX to PNG conversion.
    System::SharedPtr<ImageDevice> device = System::MakeObject<ImageDevice>();
    System::MakeObject<TeXJob>(System::IO::Path::Combine(RunExamples::InputDirectory, u"hello-world.ltx"), device, options)->Run();
    
    // Save pages file by file.
    for (int32_t i = 0; i < device->get_Result()->get_Length(); i++)
    {
        {
            System::SharedPtr<System::IO::Stream> fs = System::IO::File::Open(System::IO::Path::Combine(RunExamples::OutputDirectory, System::String(u"page-") + (i + 1) + u".png"), System::IO::FileMode::Create);
            // Clearing resources under 'using' statement
            System::Details::DisposeGuard<1> __dispose_guard_0({ fs});
            // ------------------------------------------
            
            try
            {
                fs->Write(device->get_Result()[i], 0, device->get_Result()[i]->get_Length());
            }
            catch(...)
            {
                __dispose_guard_0.SetCurrentException(std::current_exception());
            }
        }
    }
```
*“Page-n.png”*文件将写入我们指定的任何路径。与[PDF输出](/tex/{{lang.url-fragment}}cpp/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file)不同，他们将复制写入输出目录的输出PNG文件。
## 关于输入选项

如果我们的主要输入文件需要依赖项，例如未包含在基本 LaTeX 系统和支持的软件包中的内容，我们必须以类似设置 [OutputWorkingDirectory] 的方式设置 [RequiredInputDirectory] 选项，并将依赖项放入该目录中。依赖项可以任意组织在子目录中。如果我们有自己的文件需要在排版过程中包含，例如外部图形文件，还必须使用指向这些文件所在位置的路径来设置 [InputWorkingDirectory]。我们也可以将主输入文件放置在输入目录中的某个位置，并在 `run()` 方法中指定相对路径（如果主输入文件位于根目录，则可以省略路径）。[此处](/tex/{{lang.url-fragment}}cpp/aspose-tex-input/)提供了关于 C++ Aspose.TeX 输入目录概念的详细信息及实现。

讨论了其他TEX的工作选择[此处](/tex/{{lang.url-fragment}}cpp/other-options/)。

**您还可以根据[Aspose.TeX for .NET](https://products.aspose.com/tex/net/) API 构建的免费乳胶转换 [Web App](https://products.aspose.app/tex/conversion/latex-to-png)。 [这里](https://products.aspose.com/tex/cpp/) 是 C++ 版本页。**

下面，我们讨论乳胶转换为其他受支持的光栅图像格式。我们不会仅仅因为实际上没有任何细节而详细介绍。唯一的区别是转换选项中[SaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_saveoptions/)属性的类型。

## 如何将乳胶转换为jpeg

```C++
...
// Initialize the options for saving in JPEG format.
options->set_SaveOptions(System::MakeObject<JpegSaveOptions>());
```

**您也可以检查基于[Aspose.TeX for .NET](https://products.aspose.com/tex/net/)API构建的免费乳胶转换[Web App](https://products.aspose.app/tex/conversion/latex-to-jpg)。 [此处](https://products.aspose.com/tex/cpp/)是C ++版本页。**

## 如何将乳胶转换为tiff

```C++
...
// Initialize the options for saving in TIFF format.
options->set_SaveOptions(System::MakeObject<TiffSaveOptions>());
```

**您还可以根据[Aspose.TeX for .NET](https://products.aspose.com/tex/net/) API 构建的免费乳胶转换 [Web App](https://products.aspose.app/tex/conversion/latex-to-tiff)。 [这里](https://products.aspose.com/tex/cpp/) 是 C++ 版本页。**

## 如何将乳胶转换为BMP

```C++
...
// Initialize the options for saving in BMP format.
options->set_SaveOptions(System::MakeObject<BmpSaveOptions>());
```

**您还可以根据[Aspose.TeX for .NET](https://products.aspose.com/tex/net/)API构建的免费乳胶到BMP转换[Web App](https://products.aspose.app/tex/conversion/latex-to-bmp)。 [这里](https://products.aspose.com/tex/cpp/)是C ++版本页。**