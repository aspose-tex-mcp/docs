---
title: LaTeX math formulas rendering | Python
linktitle: LaTeX math formulas rendering
type: docs
weight: 10
url: /python-net/latex-math-formula-rendering/
description: The article provides an overview of the Aspose.TeX API solution for Python and its functionality for rendering LaTeX math formulas. Learn the code examples
lastmod: "2021-10-14"
sitemap:
    changefreq: "weekly"
    priority: 0.8
submenu: menu-tex-for-python-net
---

## Rendering a LaTeX math formula to PNG

If needed, take a look at the [API reference section for this topic](https://reference.aspose.com/tex/python-net/aspose.tex.features/). In fact, the best way to demonstrate the **LaTeX math formula** rendering feature is to start with an example. Here it is:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Features-PngLaTeXMathRendering.py" >}}

Let's get to the details. Firstly, we initiate a [rendering options](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrendereroptions/) object, similar to the TeX/LaTeX typesetting, which includes the specification for the desired output image resolution.

Next, we specify the preamble. The default preamble is:
```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```
which offers enhanced support for mathematical formulas compared to standard LaTeX. For instance, you can include the `color` package to customize the highlighting in the formula, as demonstrated in the provided code example.

Then we instruct the renderer to scale the output by 300%.

The next two options determine the foreground and background colors. Any parts of the formula that are not affected by the custom highlighting will be displayed in the `TextColor` color.

The following line in the example serves as an illustration that you have the option to redirect the log output to a specific stream.

And finally, the `ShowTerminal` option enables you to control whether the terminal output should be displayed in the console.

The actual rendering process is carried out by the [MathRenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrenderer/render/) method, which returns the size of the formula in points.

The method accepts the stream where the image will be written as its second argument. Subsequently, we proceed to create the stream.

And finally, the `MathRenderer.render()` method is invoked, with the options being passed as the third argument. The LaTeX code of the formula is provided as the first argument.

The final lines of the example display two outputs of the math formula rendering process - the size of the formula and a concise error report, if any errors occur.

Here is the result of the rendering.

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.png">![LaTeX Math Formula rendering to PNG](/tex/python-net/latex-math-formula-rendering/math-formula.png)</a>

This represents the most common and broad application of the **LaTeX math formula rendering** functionality.

**You can also explore the free [web app](https://products.aspose.app/tex/equation-editor/png), which utilizes the implemented feature of the [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**

## Rendering a LaTeX math formula to SVG

Similarly, we can convert a LaTeX math formula into SVG format using the same approach.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.py" >}}

The differences are:
 * Instead of using the [PngMathRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrendereroptions/) class, we utilize the [SvgMathRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrendereroptions/) class.
 * We don't specify resolution.
 * Instead of using the [PngMathRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrenderer/) class, we use the [SvgMathRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrenderer/) class.
 
Here is the result:

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.svg">![LaTeX Math Formula rendering to SVG](/tex/python-net/latex-math-formula-rendering/math-formula.svg)</a>

**You can also explore the free [web app](https://products.aspose.app/tex/equation-editor/svg), which utilizes the implemented feature of the [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**