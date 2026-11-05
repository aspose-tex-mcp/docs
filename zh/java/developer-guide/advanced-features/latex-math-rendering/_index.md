---
translation: true
template: /templates/_template-java.md
title: LaTeX数学公式渲染 | Aspose.TeX for Java 开发指南
linktitle: LaTeX数学公式渲染
weight: 10
url: /java/latex-math-formula-rendering/
description: 本文介绍了在 Aspose.TeX Java API 中渲染 LaTeX 数学公式的方式。了解如何使用功能的代码示例。
lastmod: "2026-02-27"
---

{{<section overview>}}

## 如何将 LaTeX 数学公式渲染为 PNG

事实上，演示 **LaTeX数学公式** 渲染功能的最简单方法是从示例开始。如下所示：

将 `outputFile` 设置为现有文件夹中的 `java.nio.file.Path`，例如 PNG 使用 `Paths.get(outputDirectory, "math-formula.png")`，SVG 使用 `Paths.get(outputDirectory, "math-formula.svg")`。导入使用的 Aspose.TeX 渲染器、选项和 `Size2D` 类，以及 `java.awt.Color`, `java.io.ByteArrayOutputStream`, `java.io.OutputStream`, `java.nio.file.Files`, `java.nio.file.Path`, `java.nio.file.Paths`。调用方法必须处理或声明异常。请按照[许可指南](/tex/{{lang.url-fragment}}java/licensing/)应用许可证，以避免评估版限制。

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderMathToPNG.java" >}}

让我们进入细节。首先，我们创建一个[渲染选项](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrendereroptions/)实例，类似于 TeX/LaTeX 排版。我们在此同时指定输出图像的分辨率。

接下来，指定前导宏。默认前导宏为：

```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

它提供比基础 LaTeX 稍微高级一点的数学公式支持。例如，您可以添加 `color` 包，以便在公式中使用自定义高亮，正如代码示例中所示。

然后我们指示渲染器将输出放大 300%。

两个选项设置前景色和背景色。未应用自定义高亮的公式部分使用 `setTextColor()` 设置的颜色。

示例通过 `setLogStream()` 将渲染日志写入 `ByteArrayOutputStream`。日志和图像输出流在渲染后自动关闭。

`showTerminal()` 控制是否将终端输出写入控制台。示例设置为 `false`；设置为 `true` 即可显示输出。

[MathRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/mathrenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.MathRendererOptions-) 在 `PngMathRenderer` 或 `SvgMathRenderer` 实例上调用，并以 `Size2D` 返回以点为单位的公式尺寸。

方法的第二个参数是图像输出流。示例在 try-with-resources 块中打开它，并在渲染后关闭。

最后在渲染器实例上调用 `render()`：第一个参数是 LaTeX 公式，第二个参数是图像输出流，第三个参数是渲染选项。

示例的最后几行打印了两个渲染产物——公式的大小以及简要的错误报告（如果有错误的话）。

以下是渲染结果。

<a href="/tex/images/java/math-formula.png">![LaTeX Figure rendering to PNG](/tex/images/java/math-formula.png)</a>

这是 **LaTeX数学公式** 渲染的最通用使用场景。

**您也可以查看基于 [Aspose.TeX for .NET](https://products.aspose.com/tex/net/) API 实现的免费[Web 应用](https://products.aspose.app/tex/equation-editor/png)。[这里](https://products.aspose.com/tex/java/) 是 Java 版本页面。**

## 如何将 LaTeX 数学公式渲染为 SVG

以相同的方式，我们可以将 LaTeX 数学公式渲染为 SVG 格式。

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderMathToSVG.java" >}}

区别如下：

* 我们使用 [SvgMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/svgmathrendereroptions/) 类，而不是 [PngMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrendereroptions/)。
* 我们不指定分辨率。
* 我们使用 [SvgMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/svgmathrenderer/) 类，而不是 [PngMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrenderer/)。

以下是结果：

<a href="/tex/images/java/math-formula.svg">![LaTeX Math Formula rendering to SVG](/tex/images/java/math-formula.svg)</a>

**您也可以查看基于 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 实现的免费[Web 应用](https://products.aspose.app/tex/equation-editor/svg)。**
