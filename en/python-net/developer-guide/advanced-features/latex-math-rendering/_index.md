---
translation: true
template: /templates/_template-python-net.md
title: LaTeX math formulas rendering | Python via .NET
linktitle: LaTeX math formulas rendering
weight: 10
url: /python-net/latex-math-formula-rendering/
description: The article provides an overview of the Aspose.TeX API solution for Python and its functionality for rendering LaTeX math formulas. Learn the code examples
lastmod: "2024-09-20"
---

{{<section overview>}}

## Rendering a LaTeX math formula to PNG

If needed, take a look at the [API reference section for this topic](https://reference.aspose.com/tex/python-net/aspose.tex.features/). In fact, the best way to demonstrate the **LaTeX math formula** rendering feature is to start with an example. Here it is:

Set `ASPOSE_TEX_OUTPUT_DIR` to your output directory, or use the default `output` folder. All LaTeX input is included in the examples; no external input files are needed. Apply a license first as described in [Licensing](/tex/{{lang.url-fragment}}python-net/licensing/).

{{< gist "aspose-com-gists" "cbf380b84d7f2067481756d42da32b08" "Aspose.TeX.Examples-Features-PngLaTeXMathRendering.py" >}}

Let's get to the details. Firstly, we initiate a [rendering options](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrendereroptions/) object, similar to the TeX/LaTeX typesetting, which includes the specification for the desired output image resolution.

Next, we specify the preamble. The default preamble is:


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

which offers enhanced support for mathematical formulas compared to standard LaTeX. For instance, you can include the `color` package to customize the highlighting in the formula, as demonstrated in the provided code example.

Then we set `scale = 3000` for 300% scaling and `margin = 5` to leave space around the rendered fragment. The PNG example uses `resolution = 150` DPI.

The next two options determine the foreground and background colors. Any parts of the formula that are not affected by the custom highlighting will be displayed in the `text_color` color.

The example assigns a binary file stream to `log_stream`, saving the rendering log as `math-formula.png.log` beside `math-formula.png`. Both streams are closed automatically by the `with` statement.

The `show_terminal` option controls terminal output in the console. These examples set it to `False`; the log is still written to the file.

The actual rendering process is carried out by the [MathRenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrenderer/render/) method, which returns the size of the formula in points.

The second argument is the binary output stream opened for the image. The third argument supplies the rendering options.

And finally, the `MathRenderer.render()` method is invoked, with the options being passed as the third argument. The LaTeX code of the formula is provided as the first argument.

The final lines print the rendering error report, or `No rendering errors.` when it is empty, followed by the width and height in points.

Here is the result of the rendering.

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.png">![LaTeX Math Formula rendering to PNG](/tex/images/python-net/math-formula.png)</a>

This represents the most common and broad application of the **LaTeX math formula rendering** functionality.

**You can also explore the free [web app](https://products.aspose.app/tex/equation-editor/png), which utilizes the implemented feature of the [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**

## Rendering a LaTeX math formula to SVG

Similarly, we can convert a LaTeX math formula into SVG format using the same approach.

{{< gist "aspose-com-gists" "cbf380b84d7f2067481756d42da32b08" "Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.py" >}}

This example creates `math-formula.svg` and its rendering log, `math-formula.svg.log`, in the same output directory.

The differences are:

* Instead of using the [PngMathRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrendereroptions/) class, we utilize the [SvgMathRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrendereroptions/) class.
* We don't specify resolution.
* Instead of using the [PngMathRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrenderer/) class, we use the [SvgMathRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrenderer/) class.
 
Here is the result:

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.svg">![LaTeX Math Formula rendering to SVG](/tex/images/python-net/math-formula.svg)</a>

**You can also explore the free [web app](https://products.aspose.app/tex/equation-editor/svg), which utilizes the implemented feature of the [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**