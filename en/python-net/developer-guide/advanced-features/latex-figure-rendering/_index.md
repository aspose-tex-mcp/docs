---
translation: true
template: /templates/_template-python-net.md
title: LaTeX Figure rendering | Python via .NET
linktitle: LaTeX include figure
weight: 20
url: /python-net/latex-figure-rendering/
description: The article gives an overview of Aspose.TeX API solution for Python and its functionality for rendering LaTeX fragments (figures). Learn the code examples.
keywords: latex figure, figure size latex, latex picture, latex image, latex include figure, latex pic, latex figure options
lastmod: "2024-09-20"
---

{{<section overview>}}

In certain situations, you may need to extract specific content from a LaTeX file as a standalone rendered piece, commonly referred to as a *figure*, without any connection to the page layout. This could be useful, for example, when creating illustrations for an online publication. Our API allows you to accomplish this. The target formats for rendering figures are PNG and SVG, just like with the LaTeX math formula rendering feature. It is worth noting that **LaTeX figure rendering** is a more general feature compared to [LaTeX math formula rendering](/tex/{{lang.url-fragment}}python-net/latex-math-formula-rendering/).

## Rendering a LaTeX figure to PNG

If needed, first take a look at the [API reference section for this topic](https://reference.aspose.com/tex/python-net/aspose.tex.features/). Similar to formula rendering, we will begin with an example. Here it is:

Set `ASPOSE_TEX_OUTPUT_DIR` to your output directory, or use the default `output` folder. All LaTeX input is included in the examples; no external input files are needed. Apply a license first as described in [Licensing](/tex/{{lang.url-fragment}}python-net/licensing/).

{{< gist "aspose-com-gists" "cbf380b84d7f2067481756d42da32b08" "Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.py" >}}

To begin, we create an instance of the [LaTeX figure renderer options](https://reference.aspose.com/tex/python-net/aspose.tex.features/figurerendereroptions/) class, where we simultaneously specify the output image resolution.

Next, we need to specify the preamble. Unlike LaTeX math formula rendering, there is no default preamble for LaTeX figure rendering. Therefore, if you are planning to render graphics created using the `pict2e` LaTeX package, for example, you will need to specify it in the preamble:

```tex
\usepackage{pict2e}
```

Then we set `scale = 3000` for 300% scaling and `margin = 5` to leave space around the rendered fragment. The PNG example uses `resolution = 150` DPI.

The next option determines the background color. Unlike with math formula rendering, we do not need to specify a foreground color, as we assume that the colors are entirely controlled by the LaTeX code. Similarly, the background color is also controlled by the LaTeX code, so this option is simply provided for convenience.

The example assigns a binary file stream to `log_stream`, saving the rendering log as `text-and-formula.png.log` beside `text-and-formula.png`. Both streams are closed automatically by the `with` statement.

The `show_terminal` option controls terminal output in the console. These examples set it to `False`; the log is still written to the file.

The method responsible for rendering the figure is [FigureRenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/figurerenderer/render/#str-io.RawIOBase-aspose.tex.features.FigureRendererOptions) . It returns the size of the figure in points.

The second argument is the binary output stream opened for the image. The third argument supplies the rendering options.

Finally, we invoke the `FigureRenderer.render()` method itself, passing the options as the third argument. The LaTeX code of the figure is provided as the first argument.

The final lines print the rendering error report, or `No rendering errors.` when it is empty, followed by the width and height in points.

Here is the result of rendering.

<a href="/tex/python-net/latex-figure-rendering/text-and-formula.png">![LaTeX Figure rendering to PNG](/tex/images/python-net/text-and-formula.png)</a>

This represents the most general use case for the **LaTeX figure rendering** feature.

## Rendering a LaTeX figure to SVG

Similarly, we can also render a LaTeX figure in SVG format.

{{< gist "aspose-com-gists" "cbf380b84d7f2067481756d42da32b08" "Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.py" >}}

This example creates `text-and-formula.svg` and its rendering log, `text-and-formula.svg.log`, in the same output directory.

The differences are:

* Instead of using the [PngFigureRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerendereroptions/) class, we utilize the [SvgFigureRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerendereroptions/) class.
* We do not need to specify the resolution.
* Instead of using the [PngFigureRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerenderer/) class, we utilize the [SvgFigureRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerenderer/) class.
 
Here is the result:

<a href="/tex/python-net/latex-figure-rendering/text-and-formula.svg">![LaTeX Figure rendering to SVG](/tex/images/python-net/text-and-formula.svg)</a>