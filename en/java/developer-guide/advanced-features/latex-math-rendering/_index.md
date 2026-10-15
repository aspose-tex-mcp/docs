---
translation: true
template: /templates/_template-java.md
title: LaTeX math formulas rendering | Aspose.TeX for Java
linktitle: LaTeX math formulas rendering
weight: 10
url: /java/latex-math-formula-rendering/
description: LaTeX math formulas rendering within Aspose.TeX API for Java is described in this article. Learn the code examples of how to use the functionality.
lastmod: "2024-09-20"
---

{{<section overview>}}

## How to render a LaTeX math formula to PNG

In fact, the easiest way to demonstrate the **LaTeX math formula** rendering feature is to start with the example. Here it is:

Set `outputFile` to a `java.nio.file.Path` in an existing folder, for example `Paths.get(outputDirectory, "math-formula.png")` for PNG or `Paths.get(outputDirectory, "math-formula.svg")` for SVG. Import the Aspose.TeX renderer, options and `Size2D` classes used in the snippet, plus `java.awt.Color`, `java.io.ByteArrayOutputStream`, `java.io.OutputStream`, `java.nio.file.Files`, `java.nio.file.Path`, and `java.nio.file.Paths`. The calling method must handle or declare exceptions. Apply a license as described in the [licensing guide](/tex/{{lang.url-fragment}}java/licensing/) to avoid evaluation restrictions.

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderMathToPNG.java" >}}

Let's get to the details. First of all, we create a [rendering options](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrendereroptions/) instance, similar to the TeX/LaTeX typesetting. We do it here simultaneously specifying the output image resolution.

Next, we specify the preamble. The default preamble is:


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

which provides slightly more advanced math formula support than basic LaTeX. You can, for example, add the `color` package if you want to use your own highlighting in the formula, as we showed in the code example.

Then we instruct the renderer to scale the output by 300%.

Next two options define the foreground and background colors. Those parts of the formula that are not covered ("colored") by the custom highlighting will be displayed in the color set by `setTextColor()`.

The example directs rendering logs to a `ByteArrayOutputStream` using `setLogStream()`. The log and image output streams are closed automatically after rendering.

The `showTerminal()` option controls terminal output on the console. The examples set it to `false`; set it to `true` to display terminal output.

The method that actually performs the rendering is [MathRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/mathrenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.MathRendererOptions-), called on a `PngMathRenderer` or `SvgMathRenderer` instance. It returns a `Size2D` with the formula dimensions in points.

The method accepts the image output stream as its second argument. The example opens this stream in a try-with-resources block so it is closed after rendering.

Finally, we call `render()` on the renderer instance, passing the LaTeX formula as the first argument, the image output stream as the second, and the rendering options as the third.

The last lines of the example print two artifacts of math formula rendering - the size of the formula and the brief error report (in case there were errors).

Here is the result of rendering.

<a href="/tex/images/java/math-formula.png">![LaTeX Figure rendering to PNG](/tex/images/java/math-formula.png)</a>

This is the most general use case for **LaTeX math formula** rendering.

**You may also check out the free [web app](https://products.aspose.app/tex/equation-editor/png) built based on the feature implemented within [Aspose.TeX for .NET](https://products.aspose.com/tex/net/) API. [Here](https://products.aspose.com/tex/java/) is the Java version page.**

## How to render a LaTeX math formula to SVG

In much the same way, we can render a LaTeX math formula to SVG format.

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderMathToSVG.java" >}}

The differences are:

* We use [SvgMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/svgmathrendereroptions/) class instead of [PngMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrendereroptions/).
* We don't specify resolution.
* We use [SvgMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/svgmathrenderer/) class instead of [PngMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrenderer/).

Here is the result:

<a href="/tex/images/java/math-formula.svg">![LaTeX Math Formula rendering to SVG](/tex/images/java/math-formula.svg)</a>

**You may also check out the free [web app](https://products.aspose.app/tex/equation-editor/svg) built based on the feature implemented within [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**