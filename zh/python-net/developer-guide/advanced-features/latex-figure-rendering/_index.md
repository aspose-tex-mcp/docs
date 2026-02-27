---
translation: true
template: /templates/_template-python-net.md
title: LaTeX 图形渲染 | Python via .NET
linktitle: LaTeX 包含图形
weight: 20
url: /python-net/latex-figure-rendering/
description: 本文概述了 Aspose.TeX API 在 Python 中的解决方案及其用于渲染 LaTeX 片段（图形）的功能。了解代码示例。
keywords: latex figure, figure size latex, latex picture, latex image, latex include figure, latex pic, latex figure options
lastmod: "2026-02-27"
---

{{<section overview>}}

在某些情况下，您可能需要将 LaTeX 文件中的特定内容提取为一个独立渲染的部分，通常称为 *图形*，且不与页面布局关联。例如，这在为在线出版物创建插图时可能会很有用。我们的 API 允许您实现此功能。用于渲染图形的目标格式为 PNG 和 SVG，正如 LaTeX 数学公式渲染功能一样。值得注意的是，**LaTeX 图形渲染**是一个比 [LaTeX 数学公式渲染](/tex/{{lang.url-fragment}}python-net/latex-math-formula-rendering/) 更通用的功能。

## 将 LaTeX 图形渲染为 PNG

如有需要，首先查看此主题的 [API 参考章节](https://reference.aspose.com/tex/python-net/aspose.tex.features/)。与公式渲染类似，我们将从一个示例开始。示例代码如下：

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.py" >}}

首先，我们创建 [LaTeX 图形渲染器选项](https://reference.aspose.com/tex/python-net/aspose.tex.features/figurerendereroptions/) 类的实例，并同时指定输出图像的分辨率。

接下来，需要指定前导内容（preamble）。与 LaTeX 数学公式渲染不同，LaTeX 图形渲染没有默认的前导内容。因此，如果您计划渲染使用 `pict2e` LaTeX 包创建的图形，例如，需要在前导内容中指定该包：

```tex
\usepackage{pict2e}
```

然后我们指示渲染器将输出放大 300%。

下一个选项决定背景颜色。与公式渲染不同，我们不需要指定前景颜色，因为我们假设颜色完全由 LaTeX 代码控制。同样，背景颜色也由 LaTeX 代码控制，此选项仅为方便而提供。

示例中的下一行可能没有太大意义，它仅用于演示您可以将日志输出定向到特定流。

最后一个选项 `ShowTerminal` 允许您控制是否在控制台显示终端输出。

负责渲染图形的方法是 [FigureRenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/figurerenderer/render/#str-io.RawIOBase-aspose.tex.features.FigureRendererOptions)。该方法返回图形的点数大小。

该方法接受第二个参数作为流，即图像将被写入的流。我们在下一行创建该流。

最后，我们调用 `FigureRenderer.render()` 方法本身，将选项作为第三个参数传入。图形的 LaTeX 代码作为第一个参数提供。

示例的最后几行显示了与图形渲染相关的两条信息——图形的大小以及简要的错误报告（如果有错误）。

以下是渲染结果。

<a href="/tex/python-net/latex-figure-rendering/text-and-formula.png">![LaTeX 图形渲染为 PNG](/tex/images/python-net/text-and-formula.png)</a>

这代表了 **LaTeX 图形渲染** 功能的最通用使用场景。

## 将 LaTeX 图形渲染为 SVG

同样，我们也可以将 LaTeX 图形渲染为 SVG 格式。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.py" >}}

区别如下：

* 使用 [SvgFigureRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerendereroptions/) 类，而不是 [PngFigureRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerendereroptions/) 类。
* 不需要指定分辨率。
* 使用 [SvgFigureRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerenderer/) 类，而不是 [PngFigureRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerenderer/) 类。

以下是渲染结果：

<a href="/tex/python-net/latex-figure-rendering/text-and-formula.svg">![LaTeX 图形渲染为 SVG](/tex/images/python-net/text-and-formula.svg)</a>
