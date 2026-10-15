---
translation: true
template: /templates/_template-java.md
title: LaTeX 图形渲染 | Aspose.TeX for Java
linktitle: LaTeX 图形渲染
weight: 20
url: /java/latex-figure-rendering/
description: 本文介绍了 Aspose.TeX API 在 Java 环境下渲染 LaTeX 片段（图形）的解决方案。通过代码示例，了解如何使用此功能。
lastmod: "2026-02-27"
---

{{<section overview>}}

有时您可能想要从 LaTeX 文件中提取某些内容（绘图、文字、图表等），作为单独渲染的片段，即*“figure”*，而不考虑它在输出文档页面上的位置。例如，为了在互联网上发布的插图。我们的 API 可以帮助您完成此任务。提供两种目标格式——PNG 和 SVG。就像 LaTeX 数学公式渲染一样。我们还需指出，**LaTeX figure rendering** 是 [LaTeX math formula rendering](/tex/{{lang.url-fragment}}java/latex-math-formula-rendering/) 的推广。

## 如何将 LaTeX figure 渲染为 PNG

正如公式渲染一样，我们将从一个示例开始。示例如下：

将 `outputFile` 设置为现有文件夹中的 `java.nio.file.Path`，例如 PNG 使用 `Paths.get(outputDirectory, "text-and-formula.png")`，SVG 使用 `Paths.get(outputDirectory, "text-and-formula.svg")`。导入使用的 Aspose.TeX 渲染器、选项和 `Size2D` 类，以及 `java.awt.Color`, `java.io.ByteArrayOutputStream`, `java.io.OutputStream`, `java.nio.file.Files`, `java.nio.file.Path`, `java.nio.file.Paths`。调用方法必须处理或声明异常。请按照[许可指南](/tex/{{lang.url-fragment}}java/licensing/)应用许可证，以避免评估版限制。

{{< gist "aspose-com-gists" "4598064edf58fab0b87d9543a4a88234" "Example-RenderFigureToPNG.java" >}}

首先，我们创建一个 [渲染选项](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerendereroptions/) 实例。在这里同时指定输出图像的分辨率。

接下来，我们指定前导代码（preamble）。LaTeX figure rendering 没有默认的前导代码，因此如果您想渲染使用 `pict2e` LaTeX 包绘制的图形，需要在前导代码中声明它：

```tex
\usepackage{pict2e}
```

然后，我们指示渲染器将输出按 300% 缩放。 示例还通过 `setMargin(5)` 在图形周围设置 5 点的边距。PNG 示例使用 150 DPI。

下一个选项定义背景颜色。与数学公式渲染不同，我们不指定前景色，因为我们假设颜色完全由 LaTeX 代码控制。事实上，背景色也是如此，这只是一个便利选项。

示例通过 `setLogStream()` 将渲染日志写入 `ByteArrayOutputStream`。日志和图像输出流在渲染后自动关闭。

`showTerminal()` 控制是否将终端输出写入控制台。示例设置为 `false`；设置为 `true` 即可显示输出。

[FigureRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/figurerenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.FigureRendererOptions-) 在 `PngFigureRenderer` 或 `SvgFigureRenderer` 实例上调用，并以 `Size2D` 返回以点为单位的图形尺寸。

方法的第二个参数是图像输出流。示例在 try-with-resources 块中打开它，并在渲染后关闭。

最后在渲染器实例上调用 `render()`：第一个参数是 LaTeX 图形，第二个参数是图像输出流，第三个参数是渲染选项。

示例的最后几行打印了图形渲染的两个结果——图形大小以及简要的错误报告（如果有错误）。

以下是渲染结果。

![LaTeX 图形渲染为 PNG](/tex/images/java/text-and-formula.png)

这是 **LaTeX figure rendering** 功能的最通用用例。

## 如何将 LaTeX figure 渲染为 SVG

以类似的方式，我们可以将 LaTeX figure 渲染为 SVG 格式。

{{< gist "aspose-com-gists" "4598064edf58fab0b87d9543a4a88234" "Example-RenderFigureToSVG.java" >}}

区别如下：

* 我们使用 [SvgFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/svgfigurerendereroptions/) 类，而不是 [PngFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerendereroptions/)。
* 我们不指定分辨率。
* 我们使用 [SvgFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/svgfigurerenderer/) 类，而不是 [PngFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerenderer/)。

以下是结果：

<a href="/tex/images/java/text-and-formula.svg">![LaTeX 图形渲染为 SVG](/tex/images/java/text-and-formula.svg)</a>
