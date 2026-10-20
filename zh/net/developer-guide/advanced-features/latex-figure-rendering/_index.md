---
translation: true
template: /templates/_template-net.md
title: LaTeX 图形渲染 | Aspose.TeX for .NET
linktitle: LaTeX 包含图形
weight: 20
url: /net/latex-figure-rendering/
description: Aspose.TeX API 为 .NET 提供的 LaTeX 片段（图形）渲染解决方案在本文中进行说明。了解如何使用该功能的代码示例。
keywords: LaTeX 图形、LaTeX 图形大小、LaTeX 图片、LaTeX 图像、LaTeX 包含图形、LaTeX 图片、LaTeX 图形选项
lastmod: "2026-06-12"
---

{{<section overview>}}

有时您可能希望从 LaTeX 文件中提取部分内容作为单独渲染的片段，或者称作 *“图形”*，而不与页面布局关联。例如，这可以作为您在互联网上发布的插图。您可以使用我们的 API 实现此功能。目标格式有两种选择——PNG 和 SVG。与 LaTeX 数学公式渲染功能相同。值得注意的是，**LaTeX 图形渲染**是对[LaTeX 数学公式渲染](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/)的概括。

## 如何将 LaTeX 图形渲染为 PNG

与本主题相关的 API 参考部分位于[此处](https://reference.aspose.com/tex/net/aspose.tex.features/)。与公式渲染一样，我们将从示例开始。代码如下：

{{< gist "aspose-com-gists" "cd0acc55d1634f17dcf42e02075ca005" "Example-RenderFigureToPNG.cs" >}}

首先，我们创建一个[LaTeX figure options](https://reference.aspose.com/tex/net/aspose.tex.features/figurerendereroptions/)实例，并在此同时指定输出图像的分辨率。

接下来，指定前导代码（preamble）。LaTeX 图形渲染没有默认的前导代码，因此如果您要渲染使用 `pict2e` LaTeX 包绘制的图形，需要在前导代码中声明：

```tex
\usepackage{pict2e}
```

然后，我们指示渲染器将输出按 300% 缩放。

下一个选项定义背景颜色。与数学公式渲染不同，我们不指定前景颜色，因为我们假设颜色完全由 LaTeX 代码控制。事实上，背景颜色也是如此，这只是一个便利选项。

示例中的下一行代码意义不大，仅演示了如何将日志输出定向到某个流。

最后一个选项 `ShowTerminal` 允许您切换是否将终端输出写入控制台。

实际执行渲染的方式是调用[FigureRenderer.Render()](https://reference.aspose.com/tex/net/aspose.tex.features/figurerenderer/render/)。它返回图形的尺寸（以点为单位）。

渲染方法的第二个参数是用于写入图像的流。我们随后创建该流。

最后，我们调用 `FigureRenderer.Render()` 方法本身，将选项作为第三个参数传入。图形的 LaTeX 代码作为第一个参数传入。

示例的最后几行会输出两个渲染产出——图形的尺寸以及简要的错误报告（如果有错误）。

以下是渲染结果。

<a href="/tex/net/latex-figure-rendering/text-and-formula.png">![LaTeX 图形渲染为 PNG](/tex/images/net/text-and-formula.png)</a>

这是 **LaTeX 图形渲染** 功能最常见的使用场景。

## 如何将 LaTeX 图形渲染为 SVG

以类似的方式，我们可以将 LaTeX 图形渲染为 SVG 格式。

{{< gist "aspose-com-gists" "cd0acc55d1634f17dcf42e02075ca005" "Example-RenderFigureToSVG.cs" >}}

区别如下：

* 我们使用[SvgFigureRendererOptions](https://reference.aspose.com/tex/net/aspose.tex.features/svgfigurerendereroptions/)类，而不是[PngFigureRendererOptions](https://reference.aspose.com/tex/net/aspose.tex.features/pngfigurerendereroptions/)。
* 不再指定分辨率。
* 使用[SvgFigureRenderer](https://reference.aspose.com/tex/net/aspose.tex.features/svgfigurerenderer/)类，而不是[PngFigureRenderer](https://reference.aspose.com/tex/net/aspose.tex.features/pngfigurerenderer/)。

以下是渲染结果：

<a href="/tex/net/latex-figure-rendering/text-and-formula.svg">![LaTeX 图形渲染为 SVG](/tex/images/net/text-and-formula.svg)</a>


## 构建 LaTeX 图形渲染 AI 代理

如果您想使用 Aspose.TeX API 创建自己的 LaTeX 图形渲染 AI 代理，以下是一个可能的代理工作流程示例：

![LaTeX 图形渲染 AI 工作流程框图](/tex/images/net/tutorial/blockscheme-ai-for-graphic-rendering.png)

1. 导入层（LLM 核心）

将非结构化或混乱的自然语言提示解析为干净、独立的 LaTeX 数学图元和图形环境（`\begin{picture}`、`\includegraphics`）。

2. 虚拟文件系统（IO 层）

将外部图形依赖项（`.png`、`.jpg`）安全地暂存到内存或沙盒化的 `InputFileSystemDirectory` 目录中，以便编译器可以立即解析布局引用。

3. 配置

分析结构代码标记，并自动添加驱动程序、依赖项（例如 `graphicx` 或 `pict2e`）、缩放因子和背景透明度状态。

4. 统一执行节点（Aspose.TeX 引擎）

编译统一文件，并将其直接传递给专用的 `FigureRenderer`，以计算精确的矢量边界框边距，并输出响应式可视化画布片段（SVG 或高分辨率 PNG）。