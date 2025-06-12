---
translation: true
template: /templates/_template-net.md
title: 乳胶图渲染| Aspose.TeX for .NET
linktitle: 乳胶包括图
weight: 20
url: /net/latex-figure-rendering/
description: ASPOSE.TEX API解决方案用于.NET乳胶片段(图)渲染。了解有关如何使用功能的代码示例。
keywords: 乳胶图，图形尺寸乳胶，乳胶图片，乳胶图像，乳胶包括图，乳胶图片，乳胶图选项
lastmod: "2025-06-10"
---

{{<section overview>}}


有时，您可能需要从乳胶文件中提取一些内容作为单独渲染的片段或 *“图”*，而无需与页面布局的任何连接。例如，它可以是您在互联网上出版的例证。您可以使用我们的API进行。至于目标格式，有两种选项-PNG和SVG。与乳胶数学公式渲染功能一样。还值得注意的是，**乳胶图渲染**是[乳胶数学公式渲染](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/)的概括。

## 如何将乳胶图形渲染到png

与此主题相关的API参考部分是[此处](https://reference.aspose.com/tex/net/aspose.tex.features/)。与公式渲染一样，我们将从一个示例开始。这里是：

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.cs" >}}

首先，我们创建[乳胶图选项](https://reference.aspose.com/tex/net/aspose.tex.features/figurerendereroptions/)实例。我们在这里同时指定输出图像分辨率。

接下来，我们指定前导码。LaTeX 图形渲染没有默认的前导码，因此，例如，如果您要渲染一些使用 `pict2e` LaTeX 包绘制的图形，则需要在前导码中指定它：


```tex
\usepackage{pict2e}
```

然后，我们指示渲染器将输出扩展300％。

下一个选项定义背景颜色。与数学公式渲染不同，我们没有指定前景颜色，因为我们假设颜色完全在乳胶代码的控制之下。实际上，背景颜色也是如此，因此这只是一个便利选择。

该示例的下一行没有太多意义。它只是证明您可以将日志输出引导到某些流。

最后一个选项`ShowTerminal`使您可以切换将终端输出写入控制台。

实际执行渲染的方法是[figurerenderer.render()](https://reference.aspose.com/tex/net/aspose.tex.features/figurerenderer/render/)。它返回点的大小。

该方法将要编写图像的流作为第二个参数接受。我们下一步创建流。

最后，我们将`FigureRenderer.render()`方法本身称为第三个参数。该图的乳胶代码作为第一个参数传递。

示例的最后一行打印了图形渲染的两个伪像 - 图的大小和简短的错误报告(如果有错误)。

这是渲染的结果。

<a href="/tex/net/latex-figure-rendering/text-and-formula.png">![乳胶图渲染到PNG](/tex/images/net/text-and-formula.png)</a>

这是**乳胶图渲染**功能最通用的用例。

## 如何将乳胶数字渲染到SVG

以几乎相同的方式，我们可以以SVG格式渲染乳胶图。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.cs" >}}

差异是：

* 我们使用[SVGFIGURERENDEREROPTIONS](https://reference.aspose.com/tex/net/aspose.tex.features/svgfigurerendereroptions/)类，而不是[PNGFIGURERENDEREROPTIONS](https://reference.aspose.com/tex/net/aspose.tex.features/pngfigurerendereroptions/)。
* 我们没有指定分辨率。
* 我们使用[svgfigurerenderer](https://reference.aspose.com/tex/net/aspose.tex.features/svgfigurerenderer/)类代替[pngfigurerenderer](https://reference.aspose.com/tex/net/aspose.tex.features/pngfigurerenderer/)。
 
这是结果：

<a href="/tex/net/latex-figure-rendering/text-and-formula.svg">![乳胶图渲染到SVG](/tex/images/net/text-and-formula.svg)</a>