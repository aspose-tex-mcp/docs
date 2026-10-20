---
translation: true
template: /templates/_template-net.md
title: LaTeX Figure rendering | Aspose.TeX for .NET
linktitle: LaTeX include figure
weight: 20
url: /net/latex-figure-rendering/
description: Aspose.TeX API solution for .NET LaTeX fragment (figure) rendering is described in this article. Learn the code examples on how to use the functionality.
keywords: latex figure, figure size latex, latex picture, latex image, latex include figure, latex pic, latex figure options
lastmod: "2026-06-12"
---

{{<section overview>}}


Sometimes you may want to extract some content from a LaTeX file as a separately rendered piece, or a *"figure"*, without any connection to the page layout. It can be an illustration for your publication on the Internet, for example. You can do it with our API. As for the target formats, there are two options - PNG and SVG. As is in the case with the LaTeX math formula rendering feature. It's also worth noting that **LaTeX figure rendering** is a generalization of [LaTeX math formula rendering](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/).

## How to render a LaTeX figure to PNG

The API reference section related to this topic is [here](https://reference.aspose.com/tex/net/aspose.tex.features/). And as with formula rendering, we will start with an example. Here it is:

{{< gist "aspose-com-gists" "cd0acc55d1634f17dcf42e02075ca005" "Example-RenderFigureToPNG.cs" >}}

First of all, we create a [LaTeX figure options](https://reference.aspose.com/tex/net/aspose.tex.features/figurerendereroptions/) instance. We do it here simultaneously specifying the output image resolution.

Next, we specify the preamble. There's no default preamble for LaTeX figure rendering, so if you are, for instance, going to render some graphics plotted using the `pict2e` LaTeX package, you need to specify it in the preamble:


```tex
\usepackage{pict2e}
```

Then we instruct the renderer to scale the output by 300%.

The next option defines the background color. Unlike with math formula rendering, we don't specify a foreground color since we assume that the colors are entirely under the control of the LaTeX code. In fact, so is the background color, so this is just a convenience option.

The next line of the example doesn't make much sense. It just demonstrates that you can direct the log output to some stream.

And the last option `ShowTerminal` allows you to toggle writing the terminal output to the console.

The method that actually performs the rendering is [FigureRenderer.Render()](https://reference.aspose.com/tex/net/aspose.tex.features/figurerenderer/render/). It returns the size of the figure in points.

The stream where the image is to be written is accepted by the method as the second argument. We create the stream next.

And finally, we call the `FigureRenderer.Render()` method itself, passing options as the third argument. The LaTeX code of the figure is passed as the first argument.

The last lines of the example print two artifacts of figure rendering - the size of the figure and the brief error report (in case there are errors).

Here is the result of rendering.

<a href="/tex/net/latex-figure-rendering/text-and-formula.png">![LaTeX Figure rendering to PNG](/tex/images/net/text-and-formula.png)</a>

This is the most general use case for the **LaTeX figure rendering** feature.

## How to render a LaTeX figure to SVG

In much the same way, we can render a LaTeX figure in SVG format.

{{< gist "aspose-com-gists" "cd0acc55d1634f17dcf42e02075ca005" "Example-RenderFigureToSVG.cs" >}}

The differences are:

* We use [SvgFigureRendererOptions](https://reference.aspose.com/tex/net/aspose.tex.features/svgfigurerendereroptions/) class instead of [PngFigureRendererOptions](https://reference.aspose.com/tex/net/aspose.tex.features/pngfigurerendereroptions/).
* We don't specify the resolution.
* We use [SvgFigureRenderer](https://reference.aspose.com/tex/net/aspose.tex.features/svgfigurerenderer/) class instead of [PngFigureRenderer](https://reference.aspose.com/tex/net/aspose.tex.features/pngfigurerenderer/).
 
Here is the result:

<a href="/tex/net/latex-figure-rendering/text-and-formula.svg">![LaTeX Figure rendering to SVG](/tex/images/net/text-and-formula.svg)</a>


## Building a LaTeX Figure rendering AI Agent

If you want to create your own AI Agent for figure rendering within LaTeX using Aspose.TeX API, here is a suggestion for a possible workflow of such an agent:

![Blockscheme for AI LaTeX figure rendering workflow](/tex/images/net/tutorial/blockscheme-ai-for-graphic-rendering.png) 

1. The ingestion layer (LLM core)
Parses unstructured or messy natural language prompts into clean, isolated LaTeX math primitives and figure environments (`\begin{picture}`, `\includegraphics`).

2. The virtual file system (IO layer)
Safely stages external graphic dependencies (`.png`, `.jpg`) into an in-memory or sandboxed `InputFileSystemDirectory` directory so the compiler can resolve layout references instantly.

3. The configuration
Analyzes structural code markers and automatically adds drivers, dependencies (like `graphicx` or `pict2e`), scale factors, and background transparency states.

4. The unified execution node (Aspose.TeX engine)
Compiles the unified file and passes it directly to the specialized `FigureRenderer` to compute precise vector bounding box margins and output responsive visual canvas fragments (SVG or high-DPI PNG).
