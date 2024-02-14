---
title: LaTeX Figure rendering | Aspose.TeX for Python
linktitle: LaTeX include figure
type: docs
weight: 20
url: /python-net/latex-figure-rendering/
description: This article provides an overview of Aspose.TeX API solution for Python and its functionality for rendering LaTeX fragments (figures). It also includes code examples to demonstrate how to use this feature.
keywords: latex figure, figure size latex, latex picture, latex image, latex include figure, latex pic, latex figure options
lastmod: "2023-02-28"
sitemap:
    changefreq: "weekly"
    priority: 0.8
submenu: menu-tex-for-python-net
---

In certain situations, you may need to extract specific content from a LaTeX file as a standalone rendered piece, commonly referred to as a *figure*, without any connection to the page layout. This could be useful, for example, when creating illustrations for an online publication. Our API allows you to accomplish this. The target formats for rendering figures are PNG and SVG, just like with the LaTeX math formula rendering feature. It is worth noting that **LaTeX figure rendering** is a more general feature compared to [LaTeX math formula rendering](/tex/python-net/latex-math-formula-rendering).

## Rendering a LaTeX figure to PNG

If needed, first take a look at the [API reference section for this topic](https://reference.aspose.com/tex/python-net/aspose.tex.features/). Similar to formula rendering, we will begin with an example. Here it is:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.py" >}}

To begin, we create an instance of the [LaTeX figure renderer options](https://reference.aspose.com/tex/python-net/aspose.tex.features/figurerendereroptions/) class, where we simultaneously specify the output image resolution.

Next, we need to specify the preamble. Unlike LaTeX math formula rendering, there is no default preamble for LaTeX figure rendering. Therefore, if you are planning to render graphics created using the `pict2e` LaTeX package, for example, you will need to specify it in the preamble:

```tex
\usepackage{pict2e}
```

Then we instruct the renderer to scale the output by 300%.

The next option determines the background color. Unlike with math formula rendering, we do not need to specify a foreground color, as we assume that the colors are entirely controlled by the LaTeX code. Similarly, the background color is also controlled by the LaTeX code, so this option is simply provided for convenience.

The following line in the example may not be particularly meaningful. It is simply intended to demonstrate that you have the option to direct the log output to a specific stream.

The final option, `ShowTerminal`, enables you to control whether the terminal output should be displayed in the console.

The method responsible for rendering the figure is [FigureRenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/figurerenderer/render/#str-io.RawIOBase-aspose.tex.features.FigureRendererOptions). It returns the size of the figure in points.

The method accepts a stream as the second argument, which is the stream where the image will be written. We create the stream in the next line.

Finally, we invoke the `FigureRenderer.render()` method itself, passing the options as the third argument. The LaTeX code of the figure is provided as the first argument.

The last few lines of the example display two pieces of information related to figure rendering - the size of the figure and a brief error report (if there are any errors).

Here is the result of rendering.

<a href="/tex/python-net/latex-figure-rendering/text-and-formula.png">![LaTeX Figure rendering to PNG](/tex/python-net/latex-figure-rendering/text-and-formula.png)</a>

This represents the most general use case for the **LaTeX figure rendering** feature.

## Rendering a LaTeX figure to SVG

Similarly, we can also render a LaTeX figure in SVG format.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.py" >}}

The differences are:
 * Instead of using the [PngFigureRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerendereroptions/) class, we utilize the [SvgFigureRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerendereroptions/) class.
 * We do not need to specify the resolution.
 * Instead of using the [PngFigureRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerenderer/) class, we utilize the [SvgFigureRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerenderer/) class.
 
Here is the result:

<a href="/tex/python-net/latex-figure-rendering/text-and-formula.svg">![LaTeX Figure rendering to SVG](/tex/python-net/latex-figure-rendering/text-and-formula.svg)</a>