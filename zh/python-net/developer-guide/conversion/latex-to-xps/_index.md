---
translation: true
template: /templates/_template-python-net.md
title: 乳胶到XPS | 通过 .NET 为 Python 提供 Aspose.TeX
linktitle: 乳胶到XPS
weight: 12
url: /python-net/latex-to-xps/
description: Python的Aspose.TeX API解决方案提供了转换功能，可以将乳胶文件转换为XPS格式。这是一些代码示例。
lastmod: "2025-06-10"
---

{{<section overview>}}

另一种目标格式是[**xps**](https://docs.aspose.com/page/net/what-is-xps-file/)。 [**xps**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification)文件本质上是一个zip软件包，其中包含文档的分页内容，以及必要的元数据，以通过特定的观看者(例如Windows XPS Viewer)和打印。该软件包由各种文件组成，其中一些是二进制文件，并包含图像，字体和ICC配置文件等资源。其他是特定模式中的XML文件，包括包含文档数据本身的文件。文档数据分为多个文件，每个文件代表文档的单个页面。这些文件由单个页面元素和一个子元素树组成，包括 *canvas*， *path*和 *glyphs*。 *canvas*元素是一个分组元素，可以包含其他 *帆布 *， *路径 *和 *glyphs*，并且它控制着所有子元素作为一个组的外观。 *路径*元素用于定义向量图形路径，而*glyphs*元素用于定义文本内容。这三个元素均具有定义外观各个方面的属性。

存在[**aspose.page**](https://products.aspose.com/page/)库，该库提供了用于操纵XPS文档的API，还可以将这些文档转换为PDF和栅格图像格式。

## 将乳胶转换为XPS

将乳胶转换为XPS的过程同样简单，类似于[转换为栅格图像格式](/tex/{{lang.url-fragment}}python-net/latex-to-image/)。但是，它需要将[save_options](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/save_options/)设置为[xpsSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.xps/xpssaveoptions/)类的实例(默认情况下或显式)，然后将设备更改为[xpsdevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.xps/xpsdevice/)类的实例。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToXps-Simplest.py" >}}

### 编写主输出XPS文件的另一种方法

*XpsDevice*类有一个替代构造函数，它允许以不同的方式获得所得的XPS文件。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToXps-Alternative.py" >}}

效果与我们得到[这里](/tex/{{lang.url-fragment}}python-net/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file)相同。

**您还可以探索免费的[用于 LaTeX 到 XPS 转换的 Web 应用程序](https://products.aspose.app/tex/conversion/latex-to-xps)，它是使用 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 开发的。**