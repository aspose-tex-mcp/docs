---
translation: true
template: /templates/_template-net.md
title: 其他管理Tex选项| .NET
linktitle: 其他选项
weight: 17
url: /net/other-options/
description: Aspose.TeX API解决方案的转换功能。这是一些代码示例。
lastmod: "2025-06-10"
---

{{<section overview>}}

## 如何设置交互模式

正如我们提到的[此处](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes)，**Aspose.TeX for .NET**让我们设置引擎启动的初始交互模式。这是我们的工作方式：

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-InteractionMode.cs" >}}

## 如何设置工作名称

当我们将主要输入文件作为文件名传递时，我们将获得具有相同名称的输出文件，尽管其他扩展名。 Tex引擎将输入文件的名称称为 *作业名称*，并将其用于输出文件，除非在编写具有明确指定其他名称的辅助文件的情况下。当我们以[流](/tex/{{lang.url-fragment}}net/other-ways-of-main-input/#providing-the-main-input-file-as-a-stream)为单位的主要输入文件时，Tex引擎使用默认的作业名称，即 *texput*。
在这两种情况下，我们都可以通过分配适当的转换选项来覆盖作业名称。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-JobName.cs" >}}


## 如何“停止时间”

乳胶具有从序言中的某些定义中自动生成标题的功能。此标题通常包含当前日期。我们可能希望以一些理想的价值冻结日期。这是可以做到的：

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-DateTime.cs" >}}

## 如何忽略丢失的软件包

我们可能需要转换一个乳胶文件，该文件引用了.net库Aspose.TeX不支持的某些软件包。在这种情况下，Tex发动机在尝试加载这样的软件包时会出现错误。为了避免这种情况，我们可以使用以下选项：

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-DateTime.cs" >}}

## 如何避免建立连接

通常，如果字体提供所需的数据，则TEX引擎为某些字符的连接构建。我们可以指示发动机使用以下代码跳过结扎建筑：

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-NoLigatures.cs" >}}

## 如何重复工作

正如我们已经提到的[上文](/tex/{{lang.url-fragment}}net/latex-io/#latex-input)有关标签和参考文献的情况，在某些情况下，我们想两次运行相同的工作。这是可以做到的：

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-Repeat.cs" >}}

## 如何将数学公式转换为栅格图像

有时，我们可能需要将数学公式作为栅格图像，而不是在字体中键入。以下选项可以用于此目的：

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-RasterizeFormulas.cs" >}}

## 如何将图形转换为栅格图像

Objecttex引擎允许我们以栅格格式(PNG和JPG)以及PS(EPS)和XPS(OXPS)格式包括图形文件。最后两种格式通常包含向量元素和文本。要使它们栅格化并将其包含在固体图像中，我们可以使用以下选项：

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-RasterizeIncludedGraphics.cs" >}}

## 如何子集字体

如果我们想减少输出文件的大小，我们可以求助于字体子集，这意味着输出文档中的字体只会包含有关文档中使用的字形的数据。这是我们可以解决这个问题的方法：

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-SubsetFonts.cs" >}}