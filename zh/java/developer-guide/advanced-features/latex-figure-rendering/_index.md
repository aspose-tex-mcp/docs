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

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.java" >}}

首先，我们创建一个 [渲染选项](https://reference.aspose.com/tex/java/com.aspose.tex/PngFigureRendererOptions) 实例。在这里同时指定输出图像的分辨率。

接下来，我们指定前导代码（preamble）。LaTeX figure rendering 没有默认的前导代码，因此如果您想渲染使用 `pict2e` LaTeX 包绘制的图形，需要在前导代码中声明它：

```tex
\usepackage{pict2e}
```

然后，我们指示渲染器将输出按 300% 缩放。

下一个选项定义背景颜色。与数学公式渲染不同，我们不指定前景色，因为我们假设颜色完全由 LaTeX 代码控制。事实上，背景色也是如此，这只是一个便利选项。

示例中的下一行并没有太大意义。它仅演示您可以将日志输出定向到某个流。

最后一个选项 `ShowTerminal` 允许您切换是否将终端输出写入控制台。

实际执行渲染的方法是 [FigureRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/figurerenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.FigureRendererOptions-)。它返回图形的点数大小。

方法的第二个参数接受用于写入图像的流。我们随后创建该流。

最后，我们调用 `FigureRenderer.render()` 方法本身，将选项作为第三个参数传入。图形的 LaTeX 代码作为第一个参数传入。

示例的最后几行打印了图形渲染的两个结果——图形大小以及简要的错误报告（如果有错误）。

以下是渲染结果。

![LaTeX 图形渲染为 PNG](/tex/images/java/text-and-formula.png)

这是 **LaTeX figure rendering** 功能的最通用用例。

## 如何将 LaTeX figure 渲染为 SVG

以类似的方式，我们可以将 LaTeX figure 渲染为 SVG 格式。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.java" >}}

区别如下：

* 我们使用 [SvgFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/SvgFigureRendererOptions) 类，而不是 [PngFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/PngFigureRendererOptions)。
* 我们不指定分辨率。
* 我们使用 [SvgFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/SvgFigureRenderer) 类，而不是 [PngFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/PngFigureRenderer)。

以下是结果：

<a href="/tex/images/java/text-and-formula.svg">![LaTeX 图形渲染为 SVG](/tex/images/java/text-and-formula.svg)</a>
