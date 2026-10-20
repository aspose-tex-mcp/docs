---
translation: true
template: /templates/_template-java.md
title: LaTeX Figure rendering | Aspose.TeX for Java
linktitle: LaTeX figure rendering
weight: 20
url: /java/latex-figure-rendering/
description: Aspose.TeX API solution for Java LaTeX fragment (figure) rendering is described in this article. Learn the code examples on how to use the functionality.
lastmod: "2024-09-20"
---

{{<section overview>}}

It may happen that you want to extract some content (a drawing, a writing, a plot, etc.) from a LaTeX file as a separately rendered piece, or a *"figure"*, regardless of its place on an output document page. An illustration for your publication on the Internet, for example, is the case. Our API can help you with the task. There are two available target formats - PNG and SVG. Just like in LaTeX math formula rendering. We must also note that **LaTeX figure rendering** is a generalization of [LaTeX math formula rendering](/tex/{{lang.url-fragment}}java/latex-math-formula-rendering/).

## How to render a LaTeX figure to PNG

And as with formula rendering, we will start with an example. Here it is:

Set `outputFile` to a `java.nio.file.Path` in an existing folder, for example `Paths.get(outputDirectory, "text-and-formula.png")` for PNG or `Paths.get(outputDirectory, "text-and-formula.svg")` for SVG. Import the Aspose.TeX renderer, options and `Size2D` classes used in the snippet, plus `java.awt.Color`, `java.io.ByteArrayOutputStream`, `java.io.OutputStream`, `java.nio.file.Files`, `java.nio.file.Path`, and `java.nio.file.Paths`. The calling method must handle or declare exceptions. Apply a license as described in the [licensing guide](/tex/{{lang.url-fragment}}java/licensing/) to avoid evaluation restrictions.

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderFigureToPNG.java" >}}

First of all, we create a [rendering options](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerendereroptions/) instance. We do it here along with specifying the output image resolution.

Next, we specify the preamble. There's no default preamble for LaTeX figure rendering, so if you want, for instance, to render some graphics plotted using the `pict2e` LaTeX package, you need to specify it in the preamble:

```tex
\usepackage{pict2e}
```

Then we instruct the renderer to scale the output by 300%. The examples also set a 5-point margin with `setMargin(5)` to leave space around the figure. The PNG example uses a resolution of 150 DPI.

The next option defines the background color. Unlike with math formula rendering, we don't specify a foreground color since we assume that the colors are entirely under the control of the LaTeX code. In fact, so is the background color, so this is just a convenience option.

The example directs rendering logs to a `ByteArrayOutputStream` using `setLogStream()`. The log and image output streams are closed automatically after rendering.

The `showTerminal()` option controls terminal output on the console. The examples set it to `false`; set it to `true` to display terminal output.

The method that actually performs the rendering is [FigureRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/figurerenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.FigureRendererOptions-), called on a `PngFigureRenderer` or `SvgFigureRenderer` instance. It returns a `Size2D` with the figure dimensions in points.

The method accepts the image output stream as its second argument. The example opens this stream in a try-with-resources block so it is closed after rendering.

Finally, we call `render()` on the renderer instance, passing the LaTeX figure as the first argument, the image output stream as the second, and the rendering options as the third.

The last lines of the example print two artifacts of figure rendering - the size of the figure and the brief error report (in case there are errors).

Here is the result of rendering.

![LaTeX Figure rendering to PNG](/tex/images/java/text-and-formula.png)

This is the most general use case for the **LaTeX figure rendering** feature.

## How to render a LaTeX figure to SVG

In much the same way, we can render a LaTeX figure to SVG format.

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderFigureToSVG.java" >}}

The differences are:

* We use [SvgFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/svgfigurerendereroptions/) class instead of [PngFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerendereroptions/).
* We don't specify the resolution.
* We use [SvgFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/svgfigurerenderer/) class instead of [PngFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerenderer/).
 
Here is the result:

<a href="/tex/images/java/text-and-formula.svg">![LaTeX Figure rendering to SVG](/tex/images/java/text-and-formula.svg)</a>
