---
translation: true
template: /templates/_template-java.md
title: 乳胶图渲染| Java的Aspose.TeX
linktitle: 乳胶图渲染
weight: 20
url: /java/latex-figure-rendering/
description: Aspose.TeX API解决方案用于Java乳胶片段(图)渲染。了解有关如何使用功能的代码示例。
lastmod: "2025-06-10"
---

{{<section overview>}}

可能会从乳胶文件中提取一些内容(图形，写作，绘图等)作为单独渲染的片段或 *figure*，而不管其在输出文档页面上，无论其位置如何。例如，您在互联网上出版的插图就是这种情况。我们的API可以帮助您完成任务。有两种可用的目标格式-PNG和SVG。就像乳胶数学公式渲染一样。我们还必须注意，**乳胶图渲染**是[乳胶数学公式渲染](/tex/{{lang.url-fragment}}java/latex-math-formula-rendering/)的概括。

## 如何将乳胶图形渲染到png

与公式渲染一样，我们将从一个示例开始。这里是：

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.java" >}}

首先，我们创建一个[渲染选项](https://reference.aspose.com/tex/java/com.aspose.tex/PngFigureRendererOptions)实例。我们在此处执行此操作，并指定输出图像分辨率。

接下来，我们指定前导码。LaTeX 图形渲染没有默认的前导码，因此，例如，如果你想渲染一些使用 `pict2e` LaTeX 包绘制的图形，则需要在前导码中指定它：

```tex
\usepackage{pict2e}
```

然后，我们指示渲染器将输出扩展300％。

下一个选项定义背景颜色。与数学公式渲染不同，我们没有指定前景颜色，因为我们假设颜色完全在乳胶代码的控制之下。实际上，背景颜色也是如此，因此这只是一个便利选择。

该示例的下一行没有太多意义。它只是证明您可以将日志输出引导到某些流。

最后一个选项`ShowTerminal`使您可以切换将终端输出写入控制台。

实际执行渲染的方法是[figurerenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/figurerenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.FigureRendererOptions-)。它返回点的大小。

该方法将要编写图像的流作为第二个参数接受。我们下一步创建流。

最后，我们将`FigureRenderer.render()`方法本身称为第三个参数。该图的乳胶代码作为第一个参数传递。

示例的最后一行打印了图形渲染的两个伪像 - 图的大小和简短的错误报告(如果有错误)。

这是渲染的结果。

![乳胶图渲染到PNG](/tex/images/java/text-and-formula.png)

这是**乳胶图渲染**功能最通用的用例。

## 如何将乳胶数字渲染到SVG

以几乎相同的方式，我们可以将乳胶数字呈现为SVG格式。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.java" >}}

差异是：

 * 我们使用[SVGFIGURERENDEREROPTIONS](https://reference.aspose.com/tex/java/com.aspose.tex/SvgFigureRendererOptions)类代替[Pngfigurerendereroptions](https://reference.aspose.com/tex/java/com.aspose.tex/PngFigureRendererOptions)。
 * 我们没有指定分辨率。
 * 我们使用[svgfigurerenderer](https://reference.aspose.com/tex/java/com.aspose.tex/SvgFigureRenderer)类代替[pngfigurerenderer](https://reference.aspose.com/tex/java/com.aspose.tex/PngFigureRenderer)。
 
这是结果：

<a href="/tex/images/java/text-and-formula.svg">![乳胶图渲染到SVG](/tex/images/java/text-and-formula.svg)</a>
