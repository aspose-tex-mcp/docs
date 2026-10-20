---
translation: true
template: /templates/_template-java.md
title: LaTeX转XPS | Java
linktitle: LaTeX转XPS
weight: 12
url: /java/latex-to-xps/
description: Java的Aspose.TeX API解决方案的转换功能使您可以将LaTeX文件转换为XPS格式。学习代码示例。
lastmod: "2026-04-21"
---

{{<section overview>}}


另一种目标格式是[**xps**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification)。一个**XPS**文件实际上是一个ZIP软件包，其中包含文档的分页内容，以及特定查看者(例如Windows XPS Viewer)和打印所需的元数据。包装中的所有数据均在目录中作为文件组织。其中一些包含图像，字体和ICC配置文件等资源。其他是各种特定模式中的XML文件。后者包括包含文档数据本身的文件。文档数据是一组文件 - 每个文件包含文档单个页面的数据。此类文件由单个页面元素和子元素树组成 -  *canvas*， *path* 和 *glyphs*。 *canvas*是一个分组元素，可以包含其他*帆布*，*路径*和*glyphs*。它的目的是控制所有儿童元素作为一个小组的外观。 *路径*元素用于定义向量图形路径。和 *字形*元素用于定义文本内容。这三个元素均具有定义外观各个方面的属性。

有[**aspose.page**](https://products.aspose.com/page/)库，该库提供了用于操纵XPS文档的API，并将其转换为PDF和栅格图像格式。

## 如何将LaTeX转换为XPS

转换为XPS与[转换为栅格图像格式](/tex/{{lang.url-fragment}}java/latex-to-image/)一样简单，除了[SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getSaveOptions--)之外，我们必须使用[XPSDEVICE](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/xpsdevice/) 类的实例。

将 `inputFile` 设置为 LaTeX 文件（例如 `hello-world.ltx`）的完整路径，将 `outputDirectory` 设置为现有输出文件夹。导入代码片段中使用的 `com.aspose.tex` 和 `com.aspose.tex.rendering` 类。调用方法必须处理或声明异常。请按照[许可指南](/tex/{{lang.url-fragment}}java/licensing/)应用许可证，以避免评估版限制。此示例采用非交互式处理，并关闭输出资源。 对于无需外部文件的输入文件 `hello-world.ltx`，默认输出文件为 `hello-world.xps`。

{{< gist "aspose-com-gists" "a30f406f6b8ace1b7d15c68a1df75c6d" "Example-ConvertLaTeXToXPS-Simplest.java" >}}

### 编写主输出XPS文件的另一种方法

[XPSDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/xpsdevice/#XpsDevice-java.io.OutputStream-)类的另一个构造函数使我们能够以替代方式获取生成的XPS文件。

使用与上文相同的 `inputFile` 和 `outputDirectory` 值。将 `xpsFile` 设置为 `java.nio.file.Path`，例如 `Paths.get(outputDirectory, "any-name.xps")`。除 Aspose.TeX 类外，还需导入 `java.io.OutputStream`、`java.nio.file.Files`、`java.nio.file.Path` 和 `java.nio.file.Paths`。 流决定 XPS 文件的输出位置；辅助文件仍写入 `outputDirectory`。

{{< gist "aspose-com-gists" "a30f406f6b8ace1b7d15c68a1df75c6d" "Example-ConvertLaTeXToXPS-Alternative.java" >}}

效果与我们得到[这里](/tex/{{lang.url-fragment}}java/latex-to-pdf/#编写主输出pdf文件的另一种方法)相同。

**您还可以查看基于 [Aspose.TeX for .NET](https://products.aspose.com/tex/net/) API 构建的免费 LaTeX 到 XPS 转换 [网页应用](https://products.aspose.app/tex/conversion/latex-to-xps)。[此处](https://products.aspose.com/tex/java/) 是 Java 版本页面。**