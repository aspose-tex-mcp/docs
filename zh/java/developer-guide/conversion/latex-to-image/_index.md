---
translation: true
template: /templates/_template-java.md
title: LaTeX转图像 | Java
linktitle: LaTeX转图像
weight: 10
url: /java/latex-to-image/
keywords: LaTeX转PNG，LaTeX PNG，LaTeX转图像，LaTeX图像，LaTeX转JPG，LaTeX JPG，LaTeX转JPEG，LaTeX JPEG，LaTeX转TIFF，LaTeX TIFF，LaTeX转BMP，LaTeX BMP
description: 要使用Aspose.TeX API解决方案将TEX转换为图像格式，用于Java的TEX API解决方案，以了解如何执行此操作和代码示例。
lastmod: "2026-04-21"
---

{{<section overview>}}
**Aspose.TeX for Java** provides features for converting LaTeX files to a number of raster image formats.

## 如何将LaTeX转换为PNG

让我们仔细研究Java代码，提供将LaTeX转换为PNG格式的最简单方法。

将 `inputFile` 设置为 LaTeX 文件（例如 `hello-world.ltx`）的完整路径，将 `outputDirectory` 设置为现有输出文件夹。导入代码片段中使用的 `com.aspose.tex` 和 `com.aspose.tex.rendering` 类。调用方法必须处理或声明异常。请按照[许可指南](/tex/{{lang.url-fragment}}java/licensing/)应用许可证，以避免评估版限制。此示例采用非交互式处理，并关闭输出资源。 PNG 示例将分辨率设置为 300 DPI。对于单页输入文件 `hello-world.ltx`，自动输出文件根据所选格式命名为 `hello-world.png`、`hello-world.jpg`、`hello-world.tif`、`hello-world.bmp` 或 `hello-world.svg`。

{{< gist "aspose-com-gists" "a30f406f6b8ace1b7d15c68a1df75c6d" "Example-ConvertLaTeXToPNG-Simplest.java" >}}

因此，我们需要做的第一件事(有时不是第一件事，正如我们稍后会发现的那样)是创建[Texoptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/)类的实例。这样做的唯一静态方法是[consoleappoptions()](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#consoleAppOptions-com.aspose.tex.TeXConfig-)，因此，我们不要理会其名称的含义。该方法将[TexConfig](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/)类的[Objectlatex()实例](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/#objectLaTeX--)进行，该类完全适合转换[latex file](/tex/{{lang.url-fragment}}net/latex-io/#latex-file)。此配置指示对象TeX引擎加载对象LaTeX格式并准备好接受LaTeX文件。对象LaTeX格式实际上只是[LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/)格式，只是它使用[Object tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)特定的原始图来设置页面指标。

所需的第一个选项是[outputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--)，该选项定义了将编写Tex输出的空间或区域。 [这里](/tex/{{lang.url-fragment}}java/aspose-tex-output/)是有关Java **Aspose.TeX**中输出目录概念的详细信息。在此示例中，我们使用[outputsystemdirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputfilesystemdirectory/)类，该类使我们能够将输出写入指定的目录或文件夹。

第二个选项是[SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/SaveOptions)类实例，它将控制[对象模型](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object)对目标格式的转换。由于我们将LaTeX转换为PNG，因此是[pngsaveoptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/pngsaveoptions/)类实例，它允许我们指定输出图像的分辨率。

接下来，我们需要创建[Texjob](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/)类的实例。要转换存储在文件系统中的LaTeX文件，我们使用[this](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#TeXJob-java.lang.String-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-)版本的构造函数。我们应该指定文件的完整路径。否则，发动机将在当前目录中寻找它(在[此处](https://docs.oracle.com/javase/7/docs/api/java/io/File.html))中寻找它，并且很可能找不到它。但是，如果我们的文件具有 *.tex*一个，我们可能会省略扩展名。引擎将自动添加它。构造函数的第二个参数是[设备](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/device/)类实例。由于我们将LaTeX转换为PNG，因此它是[Imagedevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/imagedevice/)类(对于所有受支持的图像格式)实例。作为最后一个论点，我们通过了最近准备的转换选项。

我们现在要做的就是[运行](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#run--)工作。

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

我们将在我们指定为输出目录的文件夹中找到引擎运行的其他产品。这些将是成绩单(.log)文件，**voila！**，主输出PNG图像文件(S)。

## 编写主要输出PNG文件的另一种方法

还有另一种将图像数据作为字节数组数组的方法，第二维中的每个数组代表单独的页面的图像数据。

{{< gist "aspose-com-gists" "a30f406f6b8ace1b7d15c68a1df75c6d" "Example-ConvertLaTeXToPNG-Alternative.java" >}}

手动保存示例还需要 `java.nio.file.Files` 和 `java.nio.file.Paths`。它将 `ImageDevice.getResult()` 返回的页面数据保存为 `page-1.png`、`page-2.png` 等。由于设置了 `deviceWritesImages(false)`，自动 PNG 输出被禁用，手动保存的页面不会在输出目录中重复生成。这与[通过流输出 PDF](/tex/{{lang.url-fragment}}java/latex-to-pdf/#编写主输出pdf文件的另一种方法)不同，后者由流指定单个 PDF 文档的输出位置。

## 关于输入选项

如果我们的主要输入文件需要依赖项，例如，这些依赖项不包含在基本LaTeX系统和支持的软件包中，我们必须设置[requientInputInputDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getRequiredInputDirectory--)选项选项的类似方式，我们设置了[outputworkworkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--)选项并将依赖项放入该目录中。依赖项可以在子目录中任意组织。如果我们有自己的文件要在排版过程中包括，例如外部图形文件，我们还必须使用通往收集这些文件的位置的路径来设置[InputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getInputWorkingDirectory--)。我们还可以将主输入文件放置在输入目录中的某个位置，并将相对路径传递给 `TeXJob` 构造函数(或者如果主输入文件位于根中，则根本没有指定路径)。 [此处](/tex/{{lang.url-fragment}}java/aspose-tex-input/)是有关Java ** aspose.tex中输入目录概念的详细信息，并提供了实现。

讨论了其他TEX的工作选择[此处](/tex/{{lang.url-fragment}}java/other-options/)。

**您还可以查看基于 [Aspose.TeX for .NET](https://products.aspose.com/tex/net/) API 构建的免费LaTeX到PNG转换 [网页应用](https://products.aspose.app/tex/conversion/latex-to-png)。[此处](https://products.aspose.com/tex/java/) 是 Java 版本页面。**

下面，我们讨论LaTeX转换为其他受支持的光栅图像格式。我们不会仅仅因为实际上没有任何细节而详细介绍。唯一的区别是转换选项中[SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getSaveOptions--)属性的类型。

## 如何将LaTeX转换为JPG

{{< gist "aspose-com-gists" "a30f406f6b8ace1b7d15c68a1df75c6d" "Example-ConvertLaTeXToJPEG.java" >}}

**您也可以查看基于[Aspose.TeX for .NET](https://products.aspose.com/tex/net/)API构建的免费LaTeX转换[Web App](https://products.aspose.app/tex/conversion/latex-to-jpg)。 [这里](https://products.aspose.com/tex/java/)是Java版本页。**

## 如何将LaTeX转换为TIFF

{{< gist "aspose-com-gists" "a30f406f6b8ace1b7d15c68a1df75c6d" "Example-ConvertLaTeXToTIFF.java" >}}


**您还可以根据[Aspose.TeX for .NET](https://products.aspose.com/tex/net/)API构建的免费LaTeX转换[Web App](https://products.aspose.app/tex/conversion/latex-to-tiff)。 [这里](https://products.aspose.com/tex/java/)是Java版本页。**

## 如何将LaTeX转换为BMP

{{< gist "aspose-com-gists" "a30f406f6b8ace1b7d15c68a1df75c6d" "Example-ConvertLaTeXToBMP.java" >}}

**您还可以根据[Aspose.TeX for .NET](https://products.aspose.com/tex/net/)API构建的免费LaTeX到BMP转换[Web App](https://products.aspose.app/tex/conversion/latex-to-bmp)。 [这里](https://products.aspose.com/tex/java/)是Java版本页。**


## 如何将LaTeX转换为SVG

另一种支持的目标格式是[**svg**](https://en.wikipedia.org/wiki/SVG)。 **可扩展的向量图形(SVG)**是一种基于XML的矢量图像格式，用于定义二维图形，支持交互性和动画。

**SVG**图像以矢量图形格式定义，并存储在XML文本文件中。这意味着**svg**图像可以按大小缩放而不会丢失质量，并且**svg**可以搜索，索引，脚本编写和压缩。可以使用文本编辑器或矢量图形编辑器创建和编辑XML文本文件。 Thay由最常用的Web浏览器渲染。

另外，还有[**Aspose.SVG**](https://products.aspose.com/svg/)库，该库具有基于**svg**格式的各种功能。这些包括创建，加载，编辑和转换**SVG**文档。

向SVG的转换与[转换为栅格图像格式](/tex/{{lang.url-fragment}}java/latex-to-image/)一样简单，除了[SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getSaveOptions--)之外，我们还必须将设备更改为[SVGDEVICE](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/SvgDevice)类的实例。

{{< gist "aspose-com-gists" "a30f406f6b8ace1b7d15c68a1df75c6d" "Example-ConvertLaTeXToSVG-Simplest.java" >}}

**您也可以检查基于[Aspose.TeX for .NET](https://products.aspose.com/tex/net/)构建的免费LaTeX转换[Web App](https://products.aspose.app/tex/conversion/latex-to-svg)。 [这里](https://products.aspose.com/tex/java/)是Java版本页。**