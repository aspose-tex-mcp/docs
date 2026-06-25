---
translation: true
template: /templates/_template-net.md
title: LaTeX 转 PDF | .NET
linktitle: LaTeX 转 PDF
weight: 11
url: /net/latex-to-pdf/
keywords: latex 转 pdf, latex pdf, 将 latex 转换为 pdf
description: 了解如何使用 Aspose.TeX API 在 .NET 平台上将 TeX 转换为 PDF 的方法，请阅读本文，其中描述了操作步骤并提供了代码示例。
lastmod: "2026-04-22"
---

{{<section overview>}}


## 如何将 LaTeX 转换为 PDF

让我们详细了解 C# 代码，它提供了将 LaTeX 转换为 PDF 格式的最简方法。

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToPDF-Simplest.cs" >}}

因此，我们需要做的第一件事（有时不是最先的那件事）是创建一个 [TeXOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) 类的实例。唯一能够完成此操作的静态方法是 [ConsoleAppOptions()](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions/)，因此不要被它的名字所困惑。该方法接受一个 [TeXConfig](https://reference.aspose.com/tex/net/aspose.tex/texconfig/) 类的 **实例**，这正好适用于转换 [LaTeX 文件](/tex/{{lang.url-fragment}}net/latex-io/#latex-file)。此配置告诉 Object TeX 引擎加载 Object LaTeX 格式并准备接受 LaTeX 文件。Object LaTeX 格式实际上就是 [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/) 格式，只是它使用了特定于 [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) 的原语来设置页面度量。

首个必需的选项是 [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/)，它定义了 TeX 输出将被写入的空间或区域。[这里](/tex/{{lang.url-fragment}}net/aspose-tex-output/) 有关于 **Aspose.TeX for .NET** 中输出目录概念的详细说明。在本例中，我们使用 [OutputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) 类，它允许我们将输出写入指定的目录或文件夹。

第二个选项是 [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation/saveoptions/) 类的实例，它将控制将 [对象模型](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) 转换为目标格式的方式。由于我们要将 LaTeX 转换为 PDF，使用的就是 [PdfSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/) 类的实例。

接下来需要创建一个 [TeXJob](https://reference.aspose.com/tex/net/aspose.tex/texjob/) 类的实例。若要转换存储在文件系统中的 LaTeX 文件，我们使用该构造函数的 [此](https://reference.aspose.com/tex/net/aspose.tex/texjob/texjob/) 版本。必须指定文件的完整路径。否则，引擎会在当前目录（即 [CurrentDirectory](https://docs.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory)）中查找，通常找不到。即使文件没有 *.tex* 扩展名，也可以省略，引擎会自动追加。构造函数的第二个参数是一个 [Device](https://reference.aspose.com/tex/net/aspose.tex.presentation/device/) 类的实例。因为我们要将 LaTeX 转换为 PDF，所以这里使用的是 [PdfDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/) 类的实例。最后一个参数则是我们刚才准备好的转换选项。

剩下的唯一工作就是调用 [run](https://reference.aspose.com/tex/net/aspose.tex/texjob/run/) 方法启动任务。

无论任务是否成功，首先会在终端看到输出。成功时，它类似如下：

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

我们可以在指定的输出目录中找到引擎工作的“成果”。其中包括转录文件以及 **就在这里！** 的主输出 PDF 文件。

## 以另一种方式写入主输出 PDF 文件

[PdfDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/pdfdevice/) 类还有另一个构造函数，允许我们以另一种方式获取生成的 PDF 文件。

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToPDF-Alternative.cs" >}}

指定目录中的 *any-name.pdf* 文件即为我们的主输出 PDF 文件。与此同时，与 [图像输出](/tex/{{lang.url-fragment}}net/latex-to-image/) 不同，我们在由转换选项定义的输出目录中不会找到任何 PDF 文件。例外情况是，*any-name.pdf*（通过其路径）位于与 [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) 选项相同的文件系统目录中，该目录是使用 [OutputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) 指定的。

## 关于输入选项

如果我们的主输入文件需要依赖项（例如未包含在基本 LaTeX 系统和支持的宏包中的宏包），我们必须像设置 [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) 那样设置 [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) 选项，并将依赖项放入该目录。依赖项可以任意组织在子目录中。若我们有自己的文件需要在排版过程中一起包含（例如外部图形文件），还必须使用指向这些文件所在位置的路径来设置 [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/inputworkingdirectory/)。我们也可以将主输入文件放在输入目录的某个子目录下，并在 `run()` 方法中指定相对路径（如果主输入文件位于根目录，则可以不指定路径）。[这里](/tex/{{lang.url-fragment}}net/aspose-tex-input/) 有关于 **Aspose.TeX for .NET** 中输入目录概念的详细说明以及提供的实现。

其他 TeX 作业选项请参阅 [此处](/tex/{{lang.url-fragment}}net/other-options/)。

**您还可以查看基于 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 构建的免费 LaTeX 转 PDF 转换 [Web 应用](https://products.aspose.app/tex/conversion/latex-to-pdf)。**
