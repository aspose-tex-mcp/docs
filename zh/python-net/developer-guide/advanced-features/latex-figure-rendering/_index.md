---
translation: true
template: /templates/_template-python-net.md
title: 乳胶图渲染| 通过 .NET 为 Python 提供 Aspose.TeX
linktitle: 乳胶包括图
weight: 20
url: /python-net/latex-figure-rendering/
description: 本文概述了Aspose.TeX API解决方案及其用于渲染乳胶片段的功能(图)。学习代码示例。
keywords: 乳胶图，图形尺寸乳胶，乳胶图片，乳胶图像，乳胶包括图，乳胶图片，乳胶图选项
lastmod: "2025-06-10"
---

{{<section overview>}}

在某些情况下，您可能需要从 LaTeX 文件中提取特定内容作为独立的渲染片段，通常称为“图形”，而无需与页面布局建立任何关联。例如，在为在线出版物创建插图时，这可能很有用。我们的 API 允许您实现这一点。图形渲染的目标格式是 PNG 和 SVG，就像 LaTeX 数学公式渲染功能一样。值得注意的是，与 [LaTeX 数学公式渲染](/tex/{{lang.url-fragment}}python-net/latex-math-formula-rendering/) 相比，**LaTeX 图形渲染** 是一项更通用的功能。

## 将乳胶图形呈现到png

如果需要，请首先查看[此主题的API参考部分](https://reference.aspose.com/tex/python-net/aspose.tex.features/)。与公式渲染类似，我们将以一个示例开始。这里是：

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.py" >}}

首先，我们创建一个[乳胶图渲染器选项](https://reference.aspose.com/tex/python-net/aspose.tex.features/figurerendereroptions/)类的实例，我们同时指定输出图像分辨率。

接下来，我们需要指定序言。与乳胶数学公式渲染不同，乳胶图渲染没有默认的序言。因此，如果您打算使用“ Pict2e”乳胶软件包创建图形，则需要在序言中指定它：

```tex
\usepackage{pict2e}
```

然后，我们指示渲染器将输出扩展300％。

下一个选项确定背景颜色。与数学公式渲染不同，我们不需要指定前景颜色，因为我们假设颜色完全由乳胶代码控制。同样，背景颜色也由乳胶代码控制，因此为方便起见提供此选项。

示例中的以下行可能不是特别有意义。只是旨在证明您可以选择将日志输出引导到特定流。

最终选项“ Show -Terminal”使您可以控制终端输出是否应显示在控制台中。

负责渲染该图的方法是[figurerenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/figurerenderer/render/#str-io.RawIOBase-aspose.tex.features.FigureRendererOptions)。它返回点的大小。

该方法接受流作为第二个参数，这是图像写的流。我们在下一行中创建流。

最后，我们调用`figurerender.render()`方法本身，将选项作为第三个参数传递。该图的乳胶代码作为第一个参数提供。

该示例的最后几行显示了与图形渲染相关的两个信息 - 图的大小和简短的错误报告(如果有任何错误)。

这是渲染的结果。

<a href="/tex/python-net/latex-figure-rendering/text-and-formula.png">![乳胶图渲染到PNG](/tex/images/python-net/text-and-formula.png)</a>

这代表了**乳胶图渲染**功能最通用的用例。

## 将乳胶数字渲染为SVG

同样，我们也可以以SVG格式渲染乳胶图。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.py" >}}

差异是：

* 我们使用[svgfigurerendereroptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerendereroptions/)类，而不是使用[pngfigurerendereroptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerendereroptions/)类。
* 我们不需要指定分辨率。
* 我们使用[svgfigurererer](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerenderer/)类，而不是使用[pngfigurerenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerenderer/)类。
 
这是结果：

<a href="/tex/python-net/latex-figure-rendering/text-and-formula.svg">![乳胶图渲染到SVG](/tex/images/python-net/text-and-formula.svg)</a>