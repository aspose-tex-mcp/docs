---
translation: true
template: /templates/_template-python-net.md
title: 乳胶到PDF | 通过 .NET 为 Python 提供 Aspose.TeX
linktitle: 乳胶到PDF
weight: 11
url: /python-net/latex-to-pdf/
keywords: 乳胶到PDF，乳胶PDF，将乳胶转换为PDF
description: 在本文中，使用Aspose.TeX API解决方案来了解如何将TEX转换为PDF，该文章提供了详细的说明和代码示例。
lastmod: "2025-06-10"
---

{{<section overview>}}

## 将乳胶转换为PDF

现在，让我们研究Python代码，该代码提供了将乳胶转换为PDF格式的最直接方法。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToPdf-Simplest.py" >}}

首先，我们需要创建一个[Texoptions](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/)类的实例。 [console_app_options()](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/console_app_options/#aspose.tex.TeXConfig)方法是实现此目的的唯一静态方法，因此不必担心其名称。此方法采用[texconfig](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/)类的[Object_Latex](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_latex/)实例，该实例非常适合转换[latex文件](/tex/{{lang.url-fragment}}net/latex-io/#latex-file)。该配置指示对象Tex引擎加载对象乳胶格式，并准备好处理乳胶文件。对象乳胶格式与[latex](/tex/{{lang.url-fragment}}net/what-is-latex/)格式基本相同，但它利用[object tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)特定的原始图来定义页面指标。

第一个需要指定的选项是 [output_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/output_working_directory/)，它决定了 TeX 输出的保存位置。如有需要，您可以在 [Aspose.TeX](/tex/{{lang.url-fragment}}net/aspose-tex-output/) 中找到更多关于输出目录概念的信息。在本例中，我们使用 [OutputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputfilesystemdirectory/) 类，它使我们能够将输出写入指定的目录或文件夹。

第二个选项需要[SaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/saveoptions/)类的实例，该实例确定了[对象模型](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object)的方式如何转换为所需的格式。在我们的情况下，当我们将乳胶转换为PDF时，它是指[PDFSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfsaveoptions/)类的实例。

要转换存储在文件系统中的乳胶文件，我们需要使用[constructor](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#str-aspose.tex.presentation.Device-aspose.tex.TeXOptions)将文件的完整路径作为参数创建[texjob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/)类的实例。如果我们没有指定完整的路径，则引擎将在当前目录中查找文件(这是脚本的工作目录)，并且可能找不到它。但是，如果我们的文件具有“ .tex”扩展名，我们可以省略扩展名，因为引擎将自动将其附加。构造函数的第二个参数是[设备](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/device/)类的实例。在我们的情况下，由于我们将乳胶转换为pdf，因此是[pdfdevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfdevice/)类的一个实例。最后，我们将最近准备的转换选项作为最后一个参数。

现在，剩下的就是[运行](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/run/#)工作。

执行后，无论它是否成功，我们将看到的第一件事是终端输出。如果执行成功，输出将看起来与此相似：

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

在我们指定为输出目录的文件夹中，我们将找到成绩单文件，**它是！**，主要输出PDF文件以及引擎工作的其他结果。

## 编写主输出PDF文件的另一种方法

* pdfdevice *类有另一个[构造函数](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfdevice/__init__/#io.RawIOBase)，它允许我们以不同的方式获得所得的PDF文件。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToPdf-Alternative.py" >}}

主输出PDF文件将命名为`任何name.pdf`，并将位于指定目录中。但是，与[图像输出](/tex/{{lang.url-fragment}}python-net/latex-to-image/#an-alternative-way-to-write-the-main-output-png-files)不同，转换选项指定的输出目录中没有其他PDF文件。例外是使用 *outputfilesystemdirectory*分配给 *output_working_directory *选项的同一文件系统目录

## 关于输入选项

如果我们的主要输入文件需要依赖项，例如未包含在基本乳胶系统和受支持的软件包中的软件包，则有必要以类似的方式设置[queld_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/)选项，因为我们设置 *output_working_directory*选项，并将依赖项放在该目录中。依赖项可以根据需要在子目录中组织。此外，如果我们有自己的文件要包含在排版过程中，例如外部图形文件，我们还必须使用通往存储这些文件的位置的路径来设置[input_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/input_working_directory/)。我们还可以将主输入文件放置在输入目录内，并在`run()`方法中指定相对路径，或者如果主输入文件在root中，则根本没有指定路径。有关python **的** aspose.tex中输入目录概念的更多详细信息以及提供的实现，请参阅[此处](/tex/{{lang.url-fragment}}python-net/aspose-tex-input/)。

也讨论了[其他TEX的工作选择](/tex/{{lang.url-fragment}}python-net/other-options/)。

**您还可以探索免费的[用于 LaTeX 到 PDF 转换的 Web 应用程序](https://products.aspose.app/tex/conversion/latex-to-pdf)，它是使用 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 开发的。**