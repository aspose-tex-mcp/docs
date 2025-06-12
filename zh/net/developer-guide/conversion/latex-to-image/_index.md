---
translation: true
template: /templates/_template-net.md
title: 乳胶到图像| Aspose.TeX for .NET
linktitle: 乳胶到图像
weight: 10
url: /net/latex-to-image/
keywords: 乳胶到PNG，乳胶PNG，乳胶到图像，乳胶图像，乳胶到JPG，乳胶JPG，乳胶，乳胶至JPEG，jpeg，latex jpeg，latex jpeg，latex to tiff，tiff，latex tiff，latex to bmp to bmp，latex bmp
description: 要使用Aspose.TeX API解决方案。
lastmod: "2025-06-10"
---

{{<section overview>}}

**Aspose.TeX for .NET**允许我们将乳胶文件转换为许多栅格图像格式。

## 如何将乳胶转换为png

让我们详细了解C＃中的代码，提供最简单的方法将乳胶转换为PNG格式。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToPng-Simplest.cs" >}}

因此，我们需要做的第一件事(有时不是第一件)是创建[Texoptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/)类的实例。这样做的唯一静态方法是[consoleappoptions()](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions/)，因此不要被其名称的含义所困扰。该方法将[TexConfig](https://reference.aspose.com/tex/net/aspose.tex/texconfig/)类的[Objectlatex实例](https://reference.aspose.com/tex/net/aspose.tex/texconfig/objectlatex/)进行，该类完全适合转换[latex file](/tex/{{lang.url-fragment}}net/latex-io/#latex-file)。该配置告诉对象Tex引擎加载对象乳胶格式并准备好接受乳胶文件。对象乳胶格式实际上只是[乳胶](/tex/{{lang.url-fragment}}net/what-is-latex/)格式，只是它使用[Object tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)特定的原始图来设置页面指标。

所需的第一个选项是[outputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/)，该选项定义了将编写Tex输出的空间或区域。 [此处](/tex/{{lang.url-fragment}}net/aspose-tex-output/)是有关.net **的** aspose.tex中输出目录概念的详细信息。在此示例中，我们使用[outputeFilesystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)类，该类使我们能够将输出写入指定的目录或文件夹。

第二个选项是[SaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation/saveoptions/)类实例，它将控制[对象模型](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object)对目标格式的转换。由于我们将乳胶转换为png，因此是[pngsaveoptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.image/pngsaveoptions/)类实例，它使我们可以指定输出图像的分辨率。

然后，我们需要创建一个[Texjob](https://reference.aspose.com/tex/net/aspose.tex/texjob/)类的实例。要转换存储在文件系统中的乳胶文件，我们使用[this](https://reference.aspose.com/tex/net/aspose.tex/texjob/texjob/)版本的构造函数。我们需要指定文件的完整路径。否则，发动机将在当前目录(即[CurrentDirectory](https://docs.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory))中寻找它，并且很可能找不到它。然而， *.tex*扩展可能会省略。引擎将自动添加它。构造函数的第二个参数是[设备](https://reference.aspose.com/tex/net/aspose.tex.presentation/device/)类实例。由于我们将乳胶转换为png，因此这是一个[Imagedevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.image/imagedevice/)类实例，这对于所有受支持的图像格式都是常见的。作为最后一个论点，我们通过了最近准备的转换选项。

现在剩下要做的就是[运行](https://reference.aspose.com/tex/net/aspose.tex/texjob/run/)工作。

无论运行是否成功，我们都会看到的第一个结果将是终端输出。如果跑步成功，它将看起来像这样：


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

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToPng-Alternative.cs" >}}

*“ Page-n.png” *文件将写入我们指定的任何路径。与[PDF输出](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file)不同，他们将复制写入输出目录的输出PNG文件。

## 关于输入选项

如果我们的主要输入文件需要依赖项，例如，这些依赖项不包含在基本乳胶系统和支持的软件包中，我们必须设置[requientInputInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/)选项选项的类似方式，我们设置了[outputworkworkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/)选项并将依赖项放入该目录中。依赖项可以在子目录中任意组织。如果我们有自己的文件要在排版过程中包括，例如外部图形文件，我们还必须使用通往收集这些文件的位置的路径来设置[InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/inputworkingdirectory/)。我们还可以将主输入文件放置在输入目录中的某个位置，并在`run()`方法中指定相对路径(如果主输入文件在root中，则根本没有指定路径)。 [此处](/tex/{{lang.url-fragment}}net/aspose-tex-input/)是有关.net 的aspose.tex中输入目录概念的详细信息，并提供了实现。

讨论了其他TEX的工作选择[此处](/tex/{{lang.url-fragment}}net/other-options/)。

**您还可以查看基于 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 构建的免费 LaTeX 到 PNG 转换 [web 应用程序](https://products.aspose.app/tex/conversion/latex-to-png)。**

下面，我们讨论乳胶转换为其他受支持的光栅图像格式，而没有深入细节，因为实际上没有细节。唯一的区别是转换选项中[SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/)属性的类型。

## 如何将乳胶转换为JPG

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToJpeg.cs" >}}

**您还可以查看基于 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 构建的免费 LaTeX 到 JPG 转换 [web 应用程序](https://products.aspose.app/tex/conversion/latex-to-jpg)。**

## 如何将乳胶转换为tiff

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToTiff.cs" >}}

**您还可以查看基于 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 构建的免费 LaTeX 到 TIFF 转换 [网页应用](https://products.aspose.app/tex/conversion/latex-to-tiff)。**

## 如何将乳胶转换为BMP

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToBmp.cs" >}}

**您还可以查看基于 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 构建的免费 LaTeX 到 BMP 转换 [web 应用程序](https://products.aspose.app/tex/conversion/latex-to-bmp)。**

## 如何将乳胶转换为SVG

另一种支持的目标格式是[**svg**](https://en.wikipedia.org/wiki/SVG)。 **可扩展的向量图形(SVG)**是一种基于XML的矢量图像格式，用于定义二维图形，支持交互性和动画。

**SVG**图像以矢量图形格式定义，并存储在XML文本文件中。 **svg**可以将图像缩放而不会丢失质量，并且**svg**可以搜索，索引，脚本脚本和压缩。可以使用文本编辑器或矢量图形编辑器创建和编辑XML文本文件，并由最使用的Web浏览器渲染。

有[**Aspose.SVG**](https://products.aspose.com/svg/)库，它提供了与**svg**相关的各种功能。这些包括创建，加载，编辑和转换**SVG**文档。

乳胶到SVG转换也与[转换为栅格图像格式](/tex/{{lang.url-fragment}}net/latex-to-image/)一样简单，只是必须将[saveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/)设置为[svgsaveoptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.svg/svgsaveoptions/)类实例，并且必须将设备更改为[svgdevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.svg/svgdevice/)类的实例。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToSvg-Simplest.cs" >}}

**您还可以查看基于 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 构建的免费 LaTeX 到 SVG 转换 [web 应用程序](https://products.aspose.app/tex/conversion/latex-to-svg)。**