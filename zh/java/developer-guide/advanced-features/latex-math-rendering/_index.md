---
translation: true
template: /templates/_template-java.md
title: LaTeX数学公式渲染 | Aspose.TeX for Java
linktitle: LaTeX数学公式渲染
weight: 10
url: /java/latex-math-formula-rendering/
description: 本文介绍了在 Aspose.TeX Java API 中渲染 LaTeX 数学公式的方式。了解如何使用功能的代码示例。
lastmod: "2026-02-27"
---

{{<section overview>}}

## 如何将 LaTeX 数学公式渲染为 PNG

事实上，演示 **LaTeX数学公式** 渲染功能的最简单方法是从示例开始。如下所示：

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-PngLaTeXMathRendering.java" >}}

让我们进入细节。首先，我们创建一个[渲染选项](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRendererOptions)实例，类似于 TeX/LaTeX 排版。我们在此同时指定输出图像的分辨率。

接下来，指定前导宏。默认前导宏为：

```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

它提供比基础 LaTeX 稍微高级一点的数学公式支持。例如，您可以添加 `color` 包，以便在公式中使用自定义高亮，正如代码示例中所示。

然后我们指示渲染器将输出放大 300%。

接下来两个选项定义前景色和背景色。公式中未被自定义高亮覆盖（“着色”）的部分将使用 `TextColor` 颜色显示。

示例中的下一行并没有太大意义。它仅演示您可以将日志输出定向到某个流。

最后一个选项 `ShowTerminal` 允许您切换是否将终端输出写入控制台。

实际执行渲染的方法是[MathRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/mathrenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.MathRendererOptions-)。它返回公式的点数大小。

图像写入的流作为第二个参数传递给该方法。我们随后创建该流。

最后，我们调用 `MathRenderer.render()` 方法本身，将选项作为第三个参数传入。公式的 LaTeX 代码作为第一个参数传入。

示例的最后几行打印了两个渲染产物——公式的大小以及简要的错误报告（如果有错误的话）。

以下是渲染结果。

<a href="/tex/images/java/math-formula.png">![LaTeX Figure rendering to PNG](/tex/images/java/math-formula.png)</a>

这是 **LaTeX数学公式** 渲染的最通用使用场景。

**您也可以查看基于 [Aspose.TeX for .NET](https://products.aspose.com/tex/net/) API 实现的免费[Web 应用](https://products.aspose.app/tex/equation-editor/png)。[这里](https://products.aspose.com/tex/java/) 是 Java 版本页面。**

## 如何将 LaTeX 数学公式渲染为 SVG

以相同的方式，我们可以将 LaTeX 数学公式渲染为 SVG 格式。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.java" >}}

区别如下：

* 我们使用 [SvgMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/SvgMathRendererOptions) 类，而不是 [PngMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRendererOptions)。
* 我们不指定分辨率。
* 我们使用 [SvgMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/SvgMathRenderer) 类，而不是 [PngMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRenderer)。

以下是结果：

<a href="/tex/images/java/math-formula.svg">![LaTeX Math Formula rendering to SVG](/tex/images/java/math-formula.svg)</a>

**您也可以查看基于 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 实现的免费[Web 应用](https://products.aspose.app/tex/equation-editor/svg)。**
