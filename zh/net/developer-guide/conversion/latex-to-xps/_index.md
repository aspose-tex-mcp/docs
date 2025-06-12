---
translation: true
template: /templates/_template-net.md
title: 乳胶到XPS | Aspose.TeX for .NET
linktitle: 乳胶到XPS
weight: 12
url: /net/latex-to-xps/
description: .NET的Aspose.Tex API解决方案的转换功能使LATEX文件转换为XPS格式。这是一些代码示例。
lastmod: "2025-06-10"
---

{{<section overview>}}


另一种目标格式是[**xps**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification)。一个**xps**文件实际上是一个ZIP软件包，其中包含文档的分页内容，以及特定查看者(例如Windows XPS查看器)和打印所需的元数据。软件包中的所有数据均由文件表示。其中一些是二进制的，并且包含图像，字体和ICC配置文件等资源。其他是各种特定模式中的XML文件。后者包括包含文档数据本身的文件。文档数据由一组文件组成 - 每个文件都包含文档单个页面的数据。此类文件由单个页面元素和子元素树组成 -  *canvas*， *path* 和 *glyphs*。 *canvas*是一个分组元素，可以包含其他*帆布*，*路径*和*glyphs*。它可以控制所有子元素作为一个小组的外观。 *路径*元素用于定义向量图形路径。 *字形 *元素用于定义文本内容。这三个元素均具有定义外观各个方面的属性。

有[**aspose.page**](https://products.aspose.com/page/)库，该库提供了用于操纵XPS文档的API，并将其转换为PDF和栅格图像格式。

## 如何将乳胶转换为XPS

乳胶到XPS转换与[转换为栅格图像格式](/tex/{{lang.url-fragment}}net/latex-to-image/)一样简单，只是必须将[saveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/)设置为[XPSSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpssaveoptions/)类实例(默认情况下或明确)，并且必须将设备更改为[XPSDEVICE](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)class的实例。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToXps-Simplest.cs" >}}

### 编写主输出XPS文件的另一种方法

[XPSDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/xpsdevice/)类的另一个构造函数使我们可以以替代方式获取所得的XPS文件。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToXps-Alternative.cs" >}}

效果与我们得到[这里](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file)相同。

**您还可以根据[Aspose.TeX for .NET api](https://products.aspose.com/tex/net/)构建的免费乳胶转换[Web App](https://products.aspose.app/tex/conversion/latex-to-xps)。**