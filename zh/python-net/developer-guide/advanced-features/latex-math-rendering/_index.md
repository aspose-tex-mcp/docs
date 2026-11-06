---
translation: true
template: /templates/_template-python-net.md
title: LaTeX 数学公式渲染 | Python via .NET
linktitle: LaTeX 数学公式渲染
weight: 10
url: /python-net/latex-math-formula-rendering/
description: 本文概述了 Aspose.TeX API 在 Python 中的解决方案及其渲染 LaTeX 数学公式的功能。了解代码示例
lastmod: "2026-04-03"
---

{{<section overview>}}

## 将 LaTeX 数学公式渲染为 PNG

如果需要，请查看本主题的 [API 参考章节](https://reference.aspose.com/tex/python-net/aspose.tex.features/)。事实上，演示 **LaTeX 数学公式** 渲染功能的最佳方式是从一个示例开始。下面是示例：

将 `ASPOSE_TEX_OUTPUT_DIR` 设置为输出目录，或使用默认的 `output` 文件夹。示例包含全部 LaTeX 代码，无需外部输入文件。请先应用许可证。 [许可证](/tex/zh/python-net/licensing/).

{{< gist "aspose-com-gists" "cbf380b84d7f2067481756d42da32b08" "Aspose.TeX.Examples-Features-PngLaTeXMathRendering.py" >}}

让我们进入细节。首先，我们实例化一个 [rendering options](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrendereroptions/) 对象，这类似于 TeX/LaTeX 排版，并包含所需输出图像分辨率的规格。

接下来，我们指定前导内容。默认的前导内容是：

```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

与标准 LaTeX 相比，这提供了对数学公式的增强支持。例如，您可以包含 `color` 包来自定义公式中的高亮显示，如提供的代码示例所示。

设置 `scale = 3000` 将比例设为 300%，并通过 `margin = 5` 在片段周围留出空白。PNG 示例使用 `resolution = 150` DPI。

接下来的两个选项决定前景色和背景色。公式中未受到自定义高亮影响的任何部分将以 `text_color` 颜色显示。

示例将二进制文件流赋给 `log_stream`，在 `math-formula.png` 旁保存日志 `math-formula.png.log`。`with` 语句会自动关闭这两个流。

`show_terminal` 控制是否在控制台显示终端输出。示例将其设为 `False`，但仍将日志写入文件。

实际的渲染过程由 [MathRenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrenderer/render/) 方法执行，该方法返回公式的点数大小。

第二个参数是为图像打开的二进制输出流，第三个参数提供渲染选项。

最后，调用 `MathRenderer.render()` 方法，第三个参数传入选项。公式的 LaTeX 代码作为第一个参数提供。

最后几行输出错误报告；如果报告为空，则输出 `No rendering errors.`，然后显示以点为单位的宽度和高度。

下面是渲染结果。

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.png">![LaTeX Math Formula rendering to PNG](/tex/images/python-net/math-formula.png)</a>

这代表了 **LaTeX 数学公式渲染** 功能最常见且最广泛的应用。

**您还可以探索免费的 [web app](https://products.aspose.app/tex/equation-editor/png)，它利用了 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 实现的功能。**

## 将 LaTeX 数学公式渲染为 SVG

同样，我们可以使用相同的方法将 LaTeX 数学公式转换为 SVG 格式。

{{< gist "aspose-com-gists" "cbf380b84d7f2067481756d42da32b08" "Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.py" >}}

此示例在同一输出目录中创建 `math-formula.svg` 和日志 `math-formula.svg.log`。

区别如下：

* 与使用 [PngMathRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrendereroptions/) 类不同，我们使用 [SvgMathRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrendereroptions/) 类。
* 我们不指定分辨率。
* 与使用 [PngMathRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrenderer/) 类不同，我们使用 [SvgMathRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrenderer/) 类。

下面是结果：

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.svg">![LaTeX Math Formula rendering to SVG](/tex/images/python-net/math-formula.svg)</a>

**您还可以探索免费的 [web app](https://products.aspose.app/tex/equation-editor/svg)，它利用了 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 实现的功能。**
