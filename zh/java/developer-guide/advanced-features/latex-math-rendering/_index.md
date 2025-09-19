---
translation: true
template: /templates/_template-java.md
title: 乳胶数学公式渲染| Java的Aspose.TeX
linktitle: 乳胶数学公式渲染
weight: 10
url: /java/latex-math-formula-rendering/
description: 本文介绍了Aspose.TeX API中的乳胶数学公式。了解如何使用功能的代码示例。
lastmod: "2025-06-10"
---

{{<section overview>}}

## 如何将乳胶数学公式渲染到PNG

实际上，演示**乳胶数学公式**渲染功能的最简单方法是从示例开始。这里是：

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-PngLaTeXMathRendering.java" >}}

让我们了解细节。首先，我们创建一个[渲染选项](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRendererOptions)实例，类似于Tex/latex排版。我们在这里同时指定输出图像分辨率。

接下来，我们指定序言。默认序言是：


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

与基本乳胶相比，它提供了更高级的数学公式支持。例如，如果您想在公式中使用自己的突出显示，则可以添加“颜色”软件包，如我们在代码示例中所示。

然后，我们指示渲染器将输出扩展300％。

接下来的两个选项定义了前景和背景颜色。自定义突出显示的未覆盖(“彩色”)的公式的那些部分将显示在`TextColor`颜色中。

该示例的下一行没有太多意义。它只是证明您可以将日志输出引导到某些流。

最后一个选项`ShowTerminal`使您可以切换将终端输出写入控制台。

实际执行渲染的方法是[Mathrenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/mathrenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.MathRendererOptions-)。它返回点数中的公式大小。

该方法将要编写图像的流作为第二个参数接受。我们下一步创建流。

最后，我们将`MathRenderer.render()`方法本身称为第三个参数。公式的乳胶代码作为第一个参数传递。

示例的最后一行打印了数学公式渲染的两个伪像 - 公式的大小和简短的错误报告(如果有错误)。

这是渲染的结果。

<a href="/tex/images/java/math-formula.png">![乳胶图渲染到PNG](/tex/images/java/math-formula.png)</a>

这是**乳胶数学公式**渲染最通用的用例。

**您还可以查看免费的 [网页应用](https://products.aspose.app/tex/equation-editor/png)，它基于 [Aspose.TeX for .NET](https://products.aspose.com/tex/net/) API 中实现的功能构建。[此处](https://products.aspose.com/tex/java/) 是 Java 版本页面。**

## 如何将乳胶数学公式渲染到SVG

以几乎相同的方式，我们可以将乳胶数学公式呈现为SVG格式。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.java" >}}

差异是：

* 我们使用[SVGMATHRENDEREROPTIONS](https://reference.aspose.com/tex/java/com.aspose.tex/SvgMathRendererOptions)类代替[PNGMATHRENDEREROPTIONS](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRendererOptions)。
* 我们没有指定分辨率。
* 我们使用[svgmathrenderer](https://reference.aspose.com/tex/java/com.aspose.tex/SvgMathRenderer)类，而不是[pngmathrenderer](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRenderer)。

这是结果：

<a href="/tex/images/java/math-formula.svg">![乳胶数学公式渲染到SVG](/tex/images/java/math-formula.svg)</a>

**您还可以查看基于 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 中实现的功能构建的免费 [web 应用程序](https://products.aspose.app/tex/equation-editor/svg)。**