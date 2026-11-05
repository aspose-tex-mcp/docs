---
translation: true
template: /templates/_template-java.md
linktitle: 包含图形
title: LaTeX 包含图形 | Aspose.TeX 教程
weight: 10
url: /java/latex-includegraphics/
keywords: LaTeX 包含图形、LaTeX 插入图像、LaTeX GraphicX、LaTeX 插入图像、LaTeX 包含图形宏包、LaTeX 绘制输入/输出、LaTeX 包含图形宽度、包含图形宽度、LaTeX 图形缩放
description: 了解 LaTeX 包含图形宏，以及图像变换、视口、裁剪和 graphics 和 graphicx 宏包之间的区别。
lastmod: "2026-02-20"
---

{{<section overview>}}

## 介绍

在撰写学术和科研文档时，例如研究论文、会议论文集和学术演示文稿，你可能偶尔需要插入图形图像。

一方面，这些图形可以是绘图、曲线图、直方图或其他通常称为矢量图形的内容。现代 LaTeX 系统（如 `pdfTeX`）提供了许多用于在文档中创建此类图形的工具。例如 `pict2e`、`PGF(TikZ)` 和 `PGFplots` 包。在大多数情况下，图形本身是由 TeX 引擎生成的，并作为适用于特定输出格式的矢量图形指令序列包含在输出文件中。

另一方面，你可能还有想要在出版物中插入的光栅图像。LaTeX 系统目前也能够完成这项工作，只是需要在 LaTeX 文件中将图像文件的路径作为某个宏的参数进行指定。

本文介绍如何使用 `graphics`（以及随附的 `graphicx`）包中的 `\includegraphics` 宏在 LaTeX 文件中插入光栅图像。

## 应该选择哪个包，`graphics` 还是 `graphicx`？

两个包 `graphics` 和 `graphicx` 非常相似，主要区别在于语法。`graphics` 包使用一组独立的宏来对图像进行变换，而 `graphicx` 包使用 `key=value` 记法来为 `\includegraphics` 宏的参数指定这些变换。我们会同时给出两种包的示例，以便更清晰地展示区别。

## 引入所选包

这与引入其他 LaTeX 包的方式相同，使用 `\usepackage` 命令：

```tex
\usepackage{graphics} % 使用 graphics 包
\usepackage{graphicx} % 使用 graphicx 包
```

### 指定驱动程序

如果你的排版系统默认未使用例如 `pdfTeX`，则应指定相应的选项以强制包使用所需的 `driver`：

```tex
\usepackage[pdftex]{graphics} % graphics
\usepackage[pdftex]{graphicx} % graphicx
```

`driver` 是包的一部分，用于实现包命令与特定格式的底层 TeX 扩展原语之间的接口。**Aspose.TeX** 的 LaTeX 图形支持已配置为使用其自有驱动程序，因此不需要显式指定 driver 选项。

## LaTeX `\includegraphics` 宏

现在让我们从最简单的示例开始。这当然是一个不进行任何变换的图像插入案例。显然，使用两个包的 LaTeX 代码是相同的：

```tex
\includegraphics{sample-image.png}
```

该示例假设你的图像文件与 LaTeX 文件位于同一目录。但还有多种方式可以指定不同的位置。两种包的 LaTeX 代码同样：

```tex
\includegraphics{d:/sample-image.png} % 绝对路径
\includegraphics{./sample-image.png} % 相对于当前目录
\includegraphics{../img/sample-image.png} % 相对于包含当前文件的目录
```

另一种指定图形文件位置的方法是，在调用 `\includegraphics` 之前使用 `\graphicspath` 命令定义一组备用路径：

```tex
\graphicspath{{d:/img}{c:/img}{d:/work/img}}
```

## LaTeX 图形变换

LaTeX `graphics` 与 `graphicx` 包提供了多种操作内容的方式。

### 缩放图形

因此，你可以如下方式缩放包含的图形（实际上是任何由 TeX/LaTeX 代码描述的东西）：

```tex
% graphics 示例
\scalebox{.5}{\includegraphics{sample-image.png}} % 将宽度和高度均缩放至 0.5 倍
\scalebox{.5}[1.5]{\includegraphics{sample-image.png}} % 将宽度缩放至 0.5 倍，高度缩放至 1.5 倍

% graphicx 示例
\includegraphics[scale=.5]{sample-image.png} % 将宽度和高度均缩放至 0.5 倍
% 对于 graphicx 包，没有对应的同时独立缩放两个维度的写法
```

### 调整图形尺寸

这与缩放相似，只是你指定所需的尺寸而不是缩放因子：

```tex
% graphics 示例
\resizebox{10mm}{!}{\includegraphics{sample-image.png}} % 将宽度改为 10mm，保持比例
\resizebox{20mm}{10mm}{\includegraphics{sample-image.png}} % 同时独立修改宽度和高度

% graphicx 示例
\includegraphics[width=15mm]{sample-image.png} % 将宽度改为 15mm，保持比例
\includegraphics[height=15mm,width=25mm]{sample-image.png} % 同时独立修改宽度和高度
```

### 旋转图形

```tex
% graphics 示例
\rotatebox{25}{\includegraphics{sample-image.png}} % 将图像逆时针旋转 25 度

% graphicx 示例
\includegraphics[angle=-10]{sample-image.png} % 将图像顺时针旋转 10 度
```

### 设置视口和裁剪

```tex
% 对于 graphics 包没有对应的写法

% graphicx 示例
\includegraphics[viewport=10 10 280 220]{sample-image.png} % 设置视口左下角坐标为 (10, 10)（对应框的原点 (0, 0)），尺寸为 280×220pt
\includegraphics[viewport=10 10 250 220,clip]{sample-image.png} % 同上，但图像会被视口裁剪
```

对于 `graphicx` 包，变换可以组合使用，但顺序很重要。

若欲了解 `graphics` 包的完整功能，请参阅 [CTAN 上的包页面](https://ctan.org/pkg/graphics) 和 [包文档](http://mirrors.ctan.org/macros/latex/required/graphics/graphics.pdf)。

### LaTeX Include Graphics 免费网页应用

如果你不想以编程方式使用 includegraphics LaTeX 包，也可以试用基于 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 构建的免费 [LaTeX Include Graphics](https://products.aspose.app/tex/includegraphics/) 网页应用。

该应用允许你选择多张图像并直观地调整其变换，同时生成使用 `graphicx` 包的 LaTeX 源代码并在页面上呈现渲染结果。

### Aspose.TeX 库中的 LaTeX Figure Rendering 功能

**Aspose.TeX** 库提供了一种在 TeX/LaTeX 环境之外（例如网页）创建光栅和 SVG 图形的方法。这称为 **LaTeX Figure Rendering**。简而言之，该 API 的此部分可以在不考虑页面布局的情况下渲染 LaTeX 源代码片段。更多细节，请参阅此 [文章](/tex/{{lang.url-fragment}}java/latex-figure-rendering/)。

关于 [在 LaTeX 中引用外部包](/tex/{{lang.url-fragment}}java/external-latex-packages/) 的文章也可以帮助你了解如何从 LaTeX 绘图中创建图形。
