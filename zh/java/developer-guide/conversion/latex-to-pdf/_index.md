---
translation: true
template: /templates/_template-java.md
title: 乳胶到PDF | Java的Aspose.TeX
linktitle: 乳胶到PDF
weight: 11
url: /java/latex-to-pdf/
keywords: 乳胶到PDF，乳胶PDF，将乳胶转换为PDF
description: 要使用Aspose.TeX API解决方案将TEX转换为PDF，用于Java学习本文，以查看描述如何执行此操作和代码示例的文章。
lastmod: "2025-06-10"
---

{{<section overview>}}


## 如何将乳胶转换为PDF

让我们仔细研究Java代码，提供将乳胶转换为PDF格式的最简单方法。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-LaTeXToPdf-Simplest.java" >}}

因此，我们需要做的第一件事(有时不是第一件事，正如我们稍后会发现的那样)是创建[Texoptions](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions)类的实例。这样做的唯一静态方法是[consoleappoptions()](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#consoleAppOptions-com.aspose.tex.TeXConfig-)，因此，我们不要理会其名称的含义。该方法采用[TexConfig](https://reference.aspose.com/tex/java/com.aspose.tex/TeXConfig)类的[实例](https://reference.aspose.com/tex/java/com.aspose.tex/TeXConfig#objectLaTeX--)，该类完全适合转换[latex文件](/tex/{{lang.url-fragment}}net/latex-io/#latex-file)。此配置指示对象Tex引擎加载对象乳胶格式并准备好接受乳胶文件。对象乳胶格式只是[latex](/tex/{{lang.url-fragment}}net/what-is-latex/)格式，只是它使用[Object tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)特定的原始图来设置页面指标。

所需的第一个选项是[outputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--)，该选项定义了将编写Tex输出的空间或区域。 [这里](/tex/{{lang.url-fragment}}java/aspose-tex-output/)是有关Java **Aspose.TeX**中输出目录概念的详细信息。在此示例中，我们使用[outputsystemdirectory](https://reference.aspose.com/tex/java/com.aspose.tex/OutputFileSystemDirectory)类，该类使我们能够将输出写入指定的目录或文件夹。

第二个选项是[SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/SaveOptions)类实例，它将控制[对象模型](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object)对目标格式的转换。由于我们将乳胶转换为PDF，因此是[PDFSaveoptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfSaveOptions)类实例。

然后，我们需要创建一个[Texjob](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob)类的实例。要转换存储在文件系统中的乳胶文件，我们使用[this](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob#TeXJob-java.lang.String-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-)版本的构造函数。我们应该指定文件的完整路径。否则，发动机将在当前目录中寻找它(在[此处](https://docs.oracle.com/javase/7/docs/api/java/io/File.html))中寻找它，并且很可能找不到它。但是，如果我们的文件具有 *.tex*一个，我们可能会省略扩展名。引擎将自动添加它。构造函数的第二个参数是[设备](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/Device)类实例。由于我们将乳胶转换为PDF，因此是[PDFDEVICE](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfDevice)类实例。作为最后一个论点，我们通过了最近准备的转换选项。

我们现在要做的就是[运行](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob#run--)工作。

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

我们将在我们指定为输出目录的文件夹中找到引擎运行的其他产品。这些将是成绩单(.log)文件，**voila！**，主要输出PDF文件。

## 编写主输出PDF文件的另一种方法

[PDFDEVICE](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfDevice#PdfDevice-java.io.OutputStream-)类的另一个构造函数使我们可以以另一种方式获取所得的PDF文件。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-LaTeXToPdf-Alternative.java" >}}

指定目录中的 *any-name.pdf*文件将是我们的主要输出PDF文件。同时，与[图像输出](/tex/{{lang.url-fragment}}java/latex-to-png/#an-alternative-way-to-write-main-output-png-files)不同，我们在转换选项定义的输出目录中找不到任何PDF文件。异常： *any-name.pdf*位于同一文件系统目录中(通过其路径)，使用[outputfilesystemdirectory](https://reference.aspose.com/tex/java/com.aspose.tex/OutputFileSystemDirectory)分配给[outputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--)选项。

## 关于输入选项

如果我们的主要输入文件需要依赖项，例如，这些依赖项不包含在基本乳胶系统和受支持的软件包中，则我们必须设置[requientInputDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getRequiredInputDirectory--)选项选项的类似方式，我们设置了[outputworkworkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--)选项并将依赖项放入该目录中。依赖项可以在子目录中任意组织。如果我们有自己的文件要在排版过程中包括，例如外部图形文件，我们还必须使用通往收集这些文件的位置的路径来设置[InputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getInputWorkingDirectory--)。我们还可以将主输入文件放置在输入目录中的某个位置，并在`run()`方法中指定相对路径(或者如果主输入文件位于根中，则根本没有指定路径)。 [此处](/tex/{{lang.url-fragment}}java/aspose-tex-input/)是有关Java ** aspose.tex中输入目录概念的详细信息，并提供了实现。

讨论了其他TEX的工作选择[此处](/tex/{{lang.url-fragment}}java/other-options/)。

**您还可以查看基于 [Aspose.TeX for .NET](https://products.aspose.com/tex/net/) API 构建的免费 LaTeX 转 PDF [网页应用](https://products.aspose.app/tex/conversion/latex-to-pdf)。[此处](https://products.aspose.com/tex/java/) 是 Java 版本页面。**