---
translation: true
template: /templates/_template-net.md
title: LaTeX 转图像 | .NET
linktitle: LaTeX 转图像
weight: 10
url: /net/latex-to-image/
aliases: 
- /net/latex-to-png/
- /net/latex-to-svg/
keywords: latex to png, latex png, latex to image, latex image, latex to jpg, latex jpg, latex to jpeg, latex jpeg, latex to tiff, latex tiff, latex to bmp, latex bmp
description: 通过 Aspose.TeX API 将 TeX 转换为图像格式（适用于 .NET）的解决方案，请阅读本文了解如何操作以及代码示例。
lastmod: "2026-04-22"
---

{{<section overview>}}

**Aspose.TeX for .NET** 允许我们将 LaTeX 文件转换为多种光栅图像格式。

## 如何将 LaTeX 转换为 PNG

让我们详细查看 C# 代码，了解将 LaTeX 转换为 PNG 格式的最简方法。

{{< gist "aspose-com-gists" "58d1c43acd187f1cde7917fa9a430281" "Example-ConvertLaTeXToPNG-Simplest.cs" >}}

因此，我们需要做的第一件事（有时不是第一件事）是创建一个 [TeXOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) 类的实例。唯一的静态方法是 [ConsoleAppOptions()](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions/)，所以不要被其名称困惑。该方法接受 [ObjectLaTeX 实例](https://reference.aspose.com/tex/net/aspose.tex/texconfig/objectlatex/)（属于 [TeXConfig](https://reference.aspose.com/tex/net/aspose.tex/texconfig/) 类），该实例正好适用于转换 [LaTeX 文件](/tex/{{lang.url-fragment}}net/latex-io/#latex-file)。此配置告诉 Object TeX 引擎加载 Object LaTeX 格式，并准备接受 LaTeX 文件。Object LaTeX 格式实际上就是 [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/) 格式，只是使用了 [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) 特定的原语来设置页面度量。

第一个必需的选项是 [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/)，它定义了 TeX 输出将被写入的空间或区域。[这里](/tex/{{lang.url-fragment}}net/aspose-tex-output/) 有关于 **Aspose.TeX for .NET** 中输出目录概念的详细信息。在本例中，我们使用 [OutputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) 类，它允许我们将输出写入指定的目录或文件夹。

第二个选项是一个 [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation/saveoptions/) 类实例，用于控制将 [对象模型](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) 转换为目标格式的方式。因为我们要将 LaTeX 转换为 PNG，所以使用的是 [PngSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.image/pngsaveoptions/) 类实例，它允许我们指定输出图像的分辨率。

接下来我们需要创建一个 [TeXJob](https://reference.aspose.com/tex/net/aspose.tex/texjob/) 类的实例。想要转换存储在文件系统中的 LaTeX 文件时，我们使用 [此](https://reference.aspose.com/tex/net/aspose.tex/texjob/texjob/) 构造函数版本。我们需要指定文件的完整路径。否则，引擎会在当前目录（即 [CurrentDirectory](https://learn.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory?view=net-10.0)）中查找，且很可能找不到。即使省略 *.tex* 扩展名，也会自动追加。构造函数的第二个参数是一个 [Device](https://reference.aspose.com/tex/net/aspose.tex.presentation/device/) 类实例。因为我们将 LaTeX 转换为 PNG，所以使用的是 [ImageDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.image/imagedevice/) 类实例，这对所有受支持的图像格式都是通用的。最后一个参数传入我们刚刚准备好的转换选项。

现在唯一剩下的事情就是 [run](https://reference.aspose.com/tex/net/aspose.tex/texjob/run/) 该作业。

无论运行是否成功，首先会看到终端输出。如果运行成功，输出大致如下：

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

我们将在指定的输出目录中找到引擎工作产生的其他“成果”。其中包括记录文件以及 **看这里！** 主输出的 PNG 图像文件。

## 以另一种方式写入主输出 PNG 文件

还有另一种方式可以将图像数据作为字节数组数组获取，第二维的每个数组代表单独页面的图像数据。

**替代转换示例**  

下面的 C# 代码片段演示了另一种通过写入内存流而不是直接写入文件系统来获取 PNG 输出的方法。此方法在需要将生成的 PNG 字节保存在内存中以便进一步处理（例如通过网络发送、存入数据库或在保存前进行其他转换）时非常有用。

{{< gist "aspose-com-gists" "58d1c43acd187f1cde7917fa9a430281" "Example-ConvertLaTeXToPNG-Alternative.cs" >}}

*"page-n.png"* 文件将写入我们指定的任何路径。与 [PDF 输出](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file) 不同，它们会复制写入输出目录的 PNG 文件。

## 关于输入选项

如果我们的主输入文件需要依赖项（例如未包含在基本 LaTeX 系统和支持的宏包中的宏包），我们必须以类似设置 [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) 的方式设置 [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) 选项，并将依赖项放入该目录。依赖项可以任意组织在子目录中。如果我们有自己的文件需要在排版过程中包含，例如外部图形文件，还必须使用指向这些文件所在位置的路径设置 [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/inputworkingdirectory/) 选项。我们也可以将主输入文件放在输入目录的某个子路径下，并在 `run()` 方法中指定相对路径（如果主输入文件位于根目录，则可以不指定路径）。[这里](/tex/{{lang.url-fragment}}net/aspose-tex-input/) 有关于 **Aspose.TeX for .NET** 中输入目录概念的详细信息以及相应实现。

其他 TeX 作业选项请参见[此处](/tex/{{lang.url-fragment}}net/other-options/)。

**您还可以查看基于 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 构建的免费 LaTeX 转 PNG 转换 [网络应用](https://products.aspose.app/tex/conversion/latex-to-png)。**

下面，我们将讨论将 LaTeX 转换为其他受支持的光栅图像格式，而不深入细节，因为实际上没有太多细节。唯一的区别在于转换选项中 [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) 属性的类型。

## 如何将 LaTeX 转换为 JPG

{{< gist "aspose-com-gists" "58d1c43acd187f1cde7917fa9a430281" "Example-ConvertLaTeXToJPEG.cs" >}}

**您还可以查看基于 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 构建的免费 LaTeX 转 JPG 转换 [网络应用](https://products.aspose.app/tex/conversion/latex-to-jpg)。**

## 如何将 LaTeX 转换为 TIFF

{{< gist "aspose-com-gists" "58d1c43acd187f1cde7917fa9a430281" "Example-ConvertLaTeXToTIFF.cs" >}}

**您还可以查看基于 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 构建的免费 LaTeX 转 TIFF 转换 [网络应用](https://products.aspose.app/tex/conversion/latex-to-tiff)。**

## 如何将 LaTeX 转换为 BMP

{{< gist "aspose-com-gists" "58d1c43acd187f1cde7917fa9a430281" "Example-ConvertLaTeXToBMP.cs" >}}

**您还可以查看基于 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 构建的免费 LaTeX 转 BMP 转换 [网络应用](https://products.aspose.app/tex/conversion/latex-to-bmp)。**

## 如何将 LaTeX 转换为 SVG

还有一种受支持的目标格式是 [**SVG**](https://en.wikipedia.org/wiki/SVG)。**可伸缩矢量图形 (SVG)** 是一种基于 XML 的矢量图像格式，用于定义二维图形，支持交互和动画。

**SVG** 图像以矢量图形格式定义，并存储在 XML 文本文件中。因此，**SVG** 图像可以在不损失质量的情况下缩放大小，且 **SVG** 文件可以被搜索、索引、脚本化和压缩。XML 文本文件可以使用文本编辑器或矢量图形编辑器创建和编辑，并由主流网页浏览器渲染。

有一个 [**Aspose.SVG**](https://products.aspose.com/svg/) 库提供了与 **SVG** 相关的各种功能，包括创建、加载、编辑和转换 **SVG** 文档。

LaTeX 转 SVG 的转换同样像[转换为光栅图像格式](/tex/{{lang.url-fragment}}net/latex-to-image/) 那样简单，只是需要将 [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) 设置为 [SvgSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.svg/svgsaveoptions/) 类实例，并且必须把设备更改为 [SvgDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.svg/svgdevice/) 类的实例。

{{< gist "aspose-com-gists" "58d1c43acd187f1cde7917fa9a430281" "Example-ConvertLaTeXToSVG-Simplest.cs" >}}

**您还可以查看基于 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 构建的免费 LaTeX 转 SVG 转换 [网络应用](https://products.aspose.app/tex/conversion/latex-to-svg)。**
