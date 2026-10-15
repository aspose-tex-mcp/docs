---
translation: true
template: /templates/_template-java.md
title: 其他管理Tex选项| Java的Aspose.TeX
linktitle: 其他选项
weight: 17
url: /java/other-options/
description: Java的Aspose.TeX API解决方案的转换功能，让我们设置发动机启动的初始相互作用模式。这是一些代码示例。
lastmod: "2025-06-10"
---

{{<section overview>}}


每个示例创建 LaTeX 的 `TeXOptions` 并配置一个选项。将这些选项传递给 `TeXJob`，提供适当的 LaTeX 输入，并在运行作业前设置输出工作目录。导入 `com.aspose.tex.TeXOptions`、`TeXConfig` 和所选示例使用的类：`Interaction`、`com.aspose.tex.rendering.XpsSaveOptions` 或 `PdfSaveOptions`，以及日期示例使用的 `java.util.Calendar`/`GregorianCalendar`。在调用方法中处理或声明异常。光栅化和字体子集示例使用 `PdfSaveOptions`；请使用兼容的 `PdfDevice` 渲染。按照[许可指南](/tex/{{lang.url-fragment}}java/licensing/)应用许可证。

## 如何设置交互模式

正如我们提到的[此处](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes)，**aspose.tex的Java**允许我们设置发动机启动的初始交互模式。这是我们的工作方式：

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-InteractionMode.java" >}}

## 如何设置工作名称

当我们将主要输入文件作为文件名传递时，我们将获得具有相同名称的输出文件，尽管其他扩展名。 Tex引擎将输入文件的名称称为 *作业名称*，并将其用于输出文件，除非在编写具有明确指定其他名称的辅助文件的情况下。当我们以[流](/tex/{{lang.url-fragment}}java/other-ways-of-main-input/#providing-the-main-input-file-to-the-tex-engine-as-a-stream)为单位的主要输入文件时，Tex引擎使用默认的作业名称，即 *texput*。
在这两种情况下，我们都可以通过分配适当的转换选项来覆盖作业名称。

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-JobName.java" >}}

## 如何“停止时间”

乳胶具有从序言中的某些定义中自动生成标题的功能。此标题通常包含当前日期。我们可能希望以一些理想的价值冻结日期。这是可以做到的：

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-DateTime.java" >}}

## 如何忽略丢失的软件包

LaTeX 文件可能引用 Aspose.TeX for Java 库中不可用的软件包。引擎通常会在尝试加载此类软件包时因错误而停止。使用 `ignoreMissingPackages(true)` 可以跳过不可用的软件包。这不会提供这些软件包定义的命令；输入不得依赖这些命令。

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-IgnoreMissingPackages.java" >}}

## 如何避免建立连接

通常，如果字体提供所需的数据，则TEX引擎为某些字符的连接构建。我们可以指示发动机使用以下代码跳过结扎建筑：

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-NoLigatures.java" >}}

## 如何重复工作

正如我们已经提到的[上文](/tex/{{lang.url-fragment}}net/latex-io/#latex-input)有关标签和参考文献的情况，在某些情况下，我们可能希望两次运行同一工作。这是可以做到的：

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-Repeat.java" >}}

## 如何将数学公式转换为栅格图像

有时，我们可能需要将数学公式作为栅格图像，而不是在字体中键入。以下选项可以用于此目的：

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RasterizeFormulas.java" >}}

## 如何将图形转换为栅格图像

Objecttex引擎允许我们以栅格格式(PNG和JPG)以及PS(EPS)和XPS(OXPS)格式包括图形文件。最后两种格式通常包含向量元素和文本。要使它们栅格化并将其包含在固体图像中，我们可以使用以下选项：

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RasterizeIncludedGraphics.java" >}}

## 如何子集字体

字体子集将嵌入字体限定为文档中使用的字形。对输出大小的影响取决于字体以及输出设备嵌入字体的方式。如下所示，在启用 `subsetFonts(true)` 之前先指定保存选项：

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-SubsetFonts.java" >}}