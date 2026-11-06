---
translation: true
template: /templates/_template-python-net.md
title: 其他管理Tex选项| 通过 .NET 为 Python 提供 Aspose.TeX
linktitle: 其他选项
weight: 17
url: /python-net/other-options/
description: python的Aspose.TeX API解决方案包含转换功能，使您可以设置发动机启动的初始交互模式。
lastmod: "2025-06-10"
---

{{<section overview>}}

以下示例生成 XPS 文件。请先应用[许可证](/tex/{{lang.url-fragment}}python-net/licensing/)，并将 `ASPOSE_TEX_OUTPUT_DIR` 设置为输出文件夹（默认为 `output`）。为每个示例使用单独的输出文件夹，以保留所有结果。

## 设置交互模式

如[在TEX交互中](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes)中提到的，**aspose.tex for Python**提供了设置发动机启动的初始交互模式的能力。这是如何完成的示例：

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-InteractionMode.py" >}}

## 设置作业名称

当将主要输入文件作为文件名提供时，结果输出文件将具有相同的名称，但具有不同的扩展名。 TEX引擎将输入文件的名称称为 *作业名称*，并将其用于输出文件。例外是具有明确指定文件名的辅助文件。但是，当主输入文件以[流](/tex/{{lang.url-fragment}}python-net/other-ways-of-main-input/#supplying-the-main-input-file-as-a-stream)为单位传递时，Tex引擎使用默认作业名称，即 *texput*。在这两种情况下，都可以通过分配适当的转换选项来覆盖作业名称。

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-JobName.py" >}}

## “停止时间”

要自动从序言中的某些定义中生成标题，乳胶提供了一个通常包括当前日期的功能。但是，在某些情况下，我们需要将日期修复到特定值。这是一种实现这一目标的方法：

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-DateTime.py" >}}

## 忽略丢失的软件包

如果我们有一个乳胶文件，其中包括对Python **库不支持的软件包的引用，则TEX引擎将遇到错误并在尝试加载这些软件包时停止。为了防止这种情况，我们可以利用以下选项：

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-IgnoreMissingPackages.py" >}}

## 如何避免建立连接

默认情况下，如果字体包含必要的数据，则TEX发动机为特定字符对构建了连接。但是，我们可以指示发动机使用以下代码绕过结扎的结构：

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-NoLigatures.py" >}}

## 重复工作

如[乳胶输入文件段落](/tex/{{lang.url-fragment}}net/latex-io/#latex-input-file)，标签和参考，在某些情况下，我们可能需要两次运行同一作业。这是一种实现这一目标的方法：

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-Repeat.py" >}}

## 将数学公式变成栅格图像

如果需要将数学公式转换为栅格图像而不是使用字体渲染，则可以将以下选项用于此目的：

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-RasterizeFormulas.py" >}}

## 将图形变成栅格图像

Objecttex引擎提供了以栅格格式(例如PNG和JPG)以及PS(EPS)和XPS(OXPS)格式包含图形文件的功能。后两种格式通常包含向量元素和文本。如果我们想将它们栅格化并将其包含在固体图像中，我们可以使用以下选项：

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-RasterizeIncludedGraphics.py" >}}

图形示例读取 `ASPOSE_TEX_INPUT_DIR`（默认为 `input`）下的 `Typesetting/triangle.eps`。准备资源时请保留此子目录结构。

## 子集字体
如果我们希望减少输出文件的大小，我们可以采用字体子集，而字体子集需要结果文档中的字体将不包括文档中不存在的字形的数据。这是实现这一目标的解决方案：

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-SubsetFonts.py" >}}