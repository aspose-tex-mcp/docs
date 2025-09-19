---
translation: true
template: /templates/_template-java.md
title: 乳胶到XPS | Java的Aspose.TeX
linktitle: 乳胶到XPS
weight: 12
url: /java/latex-to-xps/
description: Java的Aspose.TeX API解决方案的转换功能使您可以将乳胶文件转换为XPS格式。学习代码示例。
lastmod: "2025-06-10"
---

{{<section overview>}}


另一种目标格式是[**xps**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification)。一个**XPS**文件实际上是一个ZIP软件包，其中包含文档的分页内容，以及特定查看者(例如Windows XPS Viewer)和打印所需的元数据。包装中的所有数据均在目录中作为文件组织。其中一些包含图像，字体和ICC配置文件等资源。其他是各种特定模式中的XML文件。后者包括包含文档数据本身的文件。文档数据是一组文件 - 每个文件包含文档单个页面的数据。此类文件由单个页面元素和子元素树组成 -  *canvas*， *path* 和 *glyphs*。 *canvas*是一个分组元素，可以包含其他*帆布*，*路径*和*glyphs*。它的目的是控制所有儿童元素作为一个小组的外观。 *路径*元素用于定义向量图形路径。和 *字形*元素用于定义文本内容。这三个元素均具有定义外观各个方面的属性。

有[**aspose.page**](https://products.aspose.com/page/)库，该库提供了用于操纵XPS文档的API，并将其转换为PDF和栅格图像格式。

## 如何将乳胶转换为XPS

转换为XPS与[转换为栅格图像格式](/tex/{{lang.url-fragment}}java/latex-to-image/)一样简单，除了[SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getSaveOptions--)之外，我们必须使用[XPSDEVICE](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/XpsDevice)类的实例。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-LaTeXToXps-Simplest.java" >}}

### 编写主输出XPS文件的另一种方法

[XPSDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/XpsDevice#XpsDevice-java.io.OutputStream-)类的另一个构造函数使我们能够以替代方式获取生成的XPS文件。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-LaTeXToXps-Alternative.java" >}}

效果与我们得到[这里](/tex/{{lang.url-fragment}}java/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file)相同。

**您还可以查看基于 [Aspose.TeX for .NET](https://products.aspose.com/tex/net/) API 构建的免费 LaTeX 到 XPS 转换 [网页应用](https://products.aspose.app/tex/conversion/latex-to-xps)。[此处](https://products.aspose.com/tex/java/) 是 Java 版本页面。**