---
translation: true
template: /templates/_template-python-net.md
title: 乳胶到图像| Aspose.TeX for Python
linktitle: 乳胶到图像
weight: 10
url: /python-net/latex-to-image/
keywords: 乳胶到PNG，乳胶PNG，乳胶到图像，乳胶图像，乳胶到JPG，乳胶JPG，乳胶，乳胶至JPEG，jpeg，latex jpeg，latex jpeg，latex to tiff，tiff，latex tiff，latex to bmp to bmp，latex bmp
description: 要使用Aspose.TeX API解决方案将TEX转换为图像格式，以了解本文，以查看描述如何执行此操作和代码示例的文章。
lastmod: "2025-06-10"
---

{{<section overview>}}

**python的aspose.tex**为我们提供了将乳胶文件转换为各种光栅图像格式的功能。

## 将乳胶转换为PNG

现在，让我们研究Python代码，该代码提供了将乳胶转换为PNG格式的最直接方法。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToPng-Simplest.py" >}}

首先，我们需要使用[console_app_options()](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/console_app_options/#aspose.tex.TeXConfig)方法创建[Texoptions](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/)类的实例。不用担心名称，这只是创建实例的静态方法。此方法将[TexConfig](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/)类的[Object_Latex](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_latex/)实例，它非常适合转换[latex文件](/tex/{{lang.url-fragment}}net/latex-io/#latex-file)。此配置设置了对象Tex引擎以加载对象乳胶格式并准备好处理乳胶文件。对象乳胶格式基本与[乳胶格式](/tex/{{lang.url-fragment}}net/what-is-latex/)相同，但是它使用[Object tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)特定基本来定义页面指标。

第一个必需的选项是 [output_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/output_working_directory/)，它指定 TeX 输出的保存位置。如果您感兴趣，可以了解更多关于 [Aspose.TeX for Python](/tex/{{lang.url-fragment}}python-net/aspose-tex-output/) 中输出目录的概念。在本例中，我们利用 [OutputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputfilesystemdirectory/) 类将输出写入特定目录或文件夹。

第二个选项是[SaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/saveoptions/)类的实例，该实例负责管理[对象模型](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object)到所需格式的转换。在这种情况下，由于我们将乳胶转换为png，因此我们使用[pngsaveoptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.image/pngsaveoptions/)类实例，它允许我们指定输出图像的分辨率。

接下来，我们创建一个[Texjob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/)类的实例。在这种情况下，由于我们要转换存储在文件系统中的乳胶文件，因此我们使用[constructor的此版本](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#str-aspose.tex.presentation.Device-aspose.tex.TeXOptions)。我们需要为文件提供完整的路径，否则，引擎将在当前目录(即脚本的工作目录)中寻找它，并且可能找不到它。但是，可以省略“ .tex”扩展，因为发动机会自动将其附加。构造函数的第二个参数是[设备](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/device/)类的实例。由于我们将乳胶转换为png，因此这是一个[Imagedevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.image/imagedevice/)类实例，这对于所有受支持的图像格式都是常见的。最后，我们将准备好的转换选项作为最后一个参数。

现在，剩下的就是[运行](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/run/#)工作。

执行作业后，无论其成功或失败如何，我们将遇到的第一个输出是终端输出。在成功运行的情况下，输出将类似于以下内容：


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

引擎工作的结果可以在我们指定的输出目录中找到。这将包括成绩单文件，最重要的是，主输出PNG图像文件。

## 编写主要输出PNG文件的另一种方法

还有一种替代方法可以将图像数据作为字节数组的数组获取，其中第二维中的每个数组代表单独的页面的图像数据。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToPng-Alternative.py" >}}

“ Page-n.png”文件可以写入任何指定的路径。与[PDF输出](/tex/{{lang.url-fragment}}python-net/latex-to-pdf/#an-alternative-way-to-write-the-main-output-pdf-file)不同，这些PNG文件将复制写入输出目录的输出PNG文件。

## 关于输入选项

如果我们的主输入文件需要依赖项，例如基本 LaTeX 系统或受支持的软件包中未包含的软件包，我们需要设置 [required_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/) 选项，设置方式类似于设置 *output_working_directory* 选项，并将依赖项放置在该目录中。依赖项可以根据需要组织到子目录中。如果我们需要在排版过程中包含文件，例如外部图形文件，我们还需要将 [input_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/input_working_directory/) 设置为这些文件的存储位置。我们还可以将主输入文件放置在输入目录中，并在 `run()` 方法中指定相对路径；如果主输入文件位于根目录中，则无需指定任何路径。还有关于 **Aspose.TeX** 中的 [输入目录概念](/tex/{{lang.url-fragment}}python-net/aspose-tex-input/) 的更多详细信息以及所提供的实现描述。

还可以在这里学习[其他TEX职位选项](/tex/{{lang.url-fragment}}python-net/other-options/)。

**您还可以探索用于 LaTeX 到 PNG 转换的免费 [web 应用程序](https://products.aspose.app/tex/conversion/latex-to-png)，该应用程序是使用 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 开发的。**

下面，我们将简要说明乳胶转换为其他受支持的光栅图像格式，而不会介入太多细节，因为没有显着差异。唯一的变化在于转换选项中[save_options](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/save_options/)属性的类型。

## 将乳胶转换为JPG

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToJpeg.py" >}}

**您还可以探索免费的[用于 LaTeX 到 TIFF 转换的 Web 应用程序](https://products.aspose.app/tex/conversion/latex-to-tiff)，它是使用 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 开发的。**

## 将乳胶转换为tiff

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToTiff.py" >}}

**您还可以探索免费的[用于 LaTeX 到 TIFF 转换的 Web 应用程序](https://products.aspose.app/tex/conversion/latex-to-tiff)，它是使用 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 开发的。**

## 将乳胶转换为BMP

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToBmp.py" >}}

**您还可以探索免费的[用于 LaTeX 到 BMP 转换的 Web 应用程序](https://products.aspose.app/tex/conversion/latex-to-bmp)，它是使用 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 开发的。**


## 将乳胶转换为SVG

另一种支持的目标格式是[**SVG**](https://en.wikipedia.org/wiki/SVG)。 **可伸缩矢量图形(SVG)**是一种基于XML的矢量图像格式，用于定义二维图形。它支持互动性和动画。

**SVG**图像存储在XML文本文件中，并以矢量图形格式定义。这意味着**svg**的图像可以缩小大小而不会失去质量，并且**svg**文件本身可以被搜索，索引，脚本编写和压缩。 XML文本文件可以使用文本编辑器或矢量图形编辑器创建和编辑，并且可以由最常用的Web浏览器渲染。

[**Aspose.SVG**](https://products.aspose.com/svg/)API提供了一系列功能，用于使用**svg**，例如创建，加载，编辑和转换**svg**文档。

将乳胶转换为SVG与[转换为栅格图像格式](/tex/{{lang.url-fragment}}python-net/latex-to-image/)一样简单，唯一的区别是[save_options](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/save_options/)必须设置为[svgsaveoptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.svg/svgsaveoptions/)类的实例，并且必须将设备更改为[svgdevice](svgdevice](38))。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToSvg-Simplest.py" >}}

**您还可以探索免费的[用于 LaTeX 到 SVG 转换的 Web 应用程序](https://products.aspose.app/tex/conversion/latex-to-svg)，它是使用 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 开发的。**