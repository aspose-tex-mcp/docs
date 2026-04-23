---
translation: true
template: /templates/_template-net.md
title: LaTeX 转 XPS | .NET
linktitle: LaTeX 转 XPS
weight: 12
url: /net/latex-to-xps/
aliases: /net/other-target-formats/
description: Aspose.TeX API 解决方案的 .NET 转换功能可以将 LaTeX 文件转换为 XPS 格式。以下是一些代码示例。
keywords: latex 转 xps, aspose tex, .net 转换, xps 格式, tex 转 xps, 文档转换, aspose page, xpsdevice, xpssaveoptions, c# 示例
lastmod: "2026-04-22"
---

{{<section overview>}}


另一个目标格式是[**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification)。**XPS** 文件实际上是一个 ZIP 包，包含文档的分页内容以及特定查看器（例如 Windows XPS Viewer）正确显示和打印所需的元数据。包中的所有数据都以文件形式表示。其中一些是二进制文件，包含图像、字体和 ICC 配置文件等资源。其他则是采用各种特定模式的 XML 文件。后者包括包含文档数据本身的文件。文档数据由一组文件组成——每个文件包含文档中单独页面的数据。此类文件由单个页面元素和子元素树组成——*Canvas*、*Path* 和 *Glyphs*。*Canvas* 是一种分组元素，能够容纳其他 *Canvas*、*Path* 和 *Glyphs*，用于统一控制所有子元素的外观。*Path* 元素用于定义矢量图形路径。*Glyphs* 元素用于定义文本内容。这三种元素都有属性，用于定义外观的各种方面。

有[**Aspose.Page**](https://products.aspose.com/page/) 库提供了操作 XPS 文档的 API，并且可以将它们转换为 PDF 和光栅图像格式。

## 如何将 LaTeX 转换为 XPS

LaTeX 到 XPS 的转换和[转换为光栅图像格式](/tex/{{lang.url-fragment}}net/latex-to-image/)一样简单，只是必须将 [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) 设置为 [XpsSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpssaveoptions/) 类实例（默认或显式），并且必须将设备更改为 [XpsDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/) 类的实例。

**最简转换示例**

下面的示例演示了如何在几步操作中将 LaTeX 文件转换为 XPS：

1. 创建 `TexDocument` 实例。  
2. 使用 `TexDocument.Load` 加载源 `.tex` 文件。  
3. （可选）配置 `XpsSaveOptions`，例如压缩设置。  
4. 通过调用 `document.Save` 并传入 `XpsDevice` 将文档保存为 XPS。

此代码展示了从 LaTeX 生成 XPS 文件的最直接方式。

{{< gist "aspose-com-gists" "1d10927e18d23e49096c91ce726e9d6f" "Example-ConvertLaTeXToXPS-Simplest.cs" >}}

### 以另一种方式写入主输出 XPS 文件

还有一种 [XpsDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/xpsdevice/) 类的构造函数，可让我们以另一种方式获取生成的 XPS 文件。

**备用转换示例**

此代码片段演示了使用接受 `Stream` 的 `XpsDevice` 构造函数。步骤如下：

1. 创建 `TexDocument` 并加载 LaTeX 源。  
2. 创建 `MemoryStream` 用于保存 XPS 输出。  
3. 使用该流实例化 `XpsDevice`。  
4. 将文档保存到设备，然后可以使用该流（例如，发送到网络或存储到数据库）。

当需要将 XPS 数据保存在内存中而非磁盘文件时，这种方式非常有用。

{{< gist "aspose-com-gists" "1d10927e18d23e49096c91ce726e9d6f" "Example-ConvertLaTeXToXPS-Alternative.cs" >}}

效果与我们在[此处](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file)得到的相同。

**您也可以尝试基于 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 构建的免费 LaTeX 转 XPS 转换[网页应用](https://products.aspose.app/tex/conversion/latex-to-xps)。**
