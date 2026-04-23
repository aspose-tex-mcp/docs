---
translation: true
template: /templates/_template-net.md
title: LaTeX 图形 | \includegraphics 命令
linktitle: Includegraphics LaTeX
weight: 18	
url: /net/latex-graphics/
description: 在 TeX 中插入图形是值得一提的事情。谈到它时，首先想到的是 `\includegraphics` 命令。
lastmod: "2026-04-22"
---

{{<section overview>}}

实际上，LaTeX 图形有两个值得一提的方面：

* 通过 LaTeX/TeX 命令直接描述的矢量图形，以及
* 通过外部格式（如 EPS、PDF 或光栅 PNG 和 PDF）描述的外部图形的嵌入。

前者在原始 LaTeX 及其宏包中支持有限。它通过 TeX 的垂直和水平规则实现。原因是原始 LaTeX 基于原始 TeX 引擎，该引擎的主要输出为 *DVI* 格式，这不适合描述直线、曲线或二进制光栅图像数据。但能够输出为支持图形的格式（如 pdfTeX 输出为 PDF）的引擎也可以使用与格式相关的宏包或宏包功能来处理图形。后者的图形由于相同原因在基本 LaTeX 中不受支持。我们将在下文讨论图形嵌入功能。

## LaTeX `graphics` 宏包和 `\includegraphics` 命令

谈到 LaTeX 图形的嵌入时，首先想到的是 `\includegraphics` 命令。它在 `graphics` 宏包中定义，你应在导言区提及该宏包以启用其功能。

```tex
\usepackage{graphics}
```

如果你的排版系统默认未配置使用例如 pdfTeX，你应指定相应的选项，以强制宏包使用所需的 `driver` 文件：

```tex
\usepackage[pdftex]{graphics}
```

`driver` 文件是宏包的一部分，用于实现宏包命令与特定格式低层 TeX 扩展原语之间的接口。Aspose.TeX 的 LaTeX 图形支持已配置为使用其自带的 driver，因此无需指定 driver 选项。

现在，包含 PNG 图像的最简单方式是输入：

```tex
\includegraphics{sample-image.png}
```

其中 `sample-image.png` 是你想要包含的文件名。你甚至可以省略扩展名。`graphics` 宏包包含支持格式的定义列表。搜索文件时，它会遍历该列表并包含找到的第一个匹配文件。

你也可以使用绝对或相对路径指定完整文件名：

```tex
\includegraphics{d:/sample-image.png} % absolute path
\includegraphics{./sample-image.png} % relative to the current directory
\includegraphics{../img/sample-image.png} % relative to the directory containing the current one
```

另一种指定图形文件位置的方法是在调用 `\includegraphics` 之前使用 `\graphicspath` 命令定义一系列备选路径：

```tex
\graphicspath{{d:/img}{c:/img}{d:/work/img}}
```

### 缩放图形

LaTeX `graphics` 宏包提供了用于操作内容的命令。因此，你可以按如下方式缩放包含的图形（实际上，任何由 TeX/LaTeX 代码描述的内容）：

```tex
\scalebox{.5}{\includegraphics{sample-image.png}} % scales both width and height by 0.5
\scalebox{.5}[1.5]{\includegraphics{sample-image.png}} % scales the width and height by 0.5 and 1.5 respectively
```

### 调整图形大小

这与缩放类似，但你需要指定所需的尺寸而不是缩放因子：

```tex
\resizebox{10mm}{!}{\includegraphics{sample-image.png}} % changes the width to 10mm preserving the proprtions
\resizebox{20mm}{10mm}{\includegraphics{sample-image.png}} % changes both width and height independently
```

### 旋转图形

```tex
\rotatebox{25}{\includegraphics{sample-image.png}} % rotates the image by 25 degrees counterclockwise
```

## LaTeX `graphicx` 宏包

LaTeX `graphicx` 宏包提供了 `key=value` 接口用于内容变换。要启用其功能，你应在导言区提及它：

```tex
\usepackage{graphicx}
\usepackage[pdftex]{graphicx} % with the driver option
```

你可以组合以下任何选项，但请注意顺序很重要。

### Graphics viewport
```tex
\includegraphics[viewport=10 10 280 220]{sample-image.png} % sets the viewport with the lower left corner
                                                           % at the point (10, 10) (coinsides with (0, 0)
                                                           % of the box) and dimensions 280x220pt
\includegraphics[viewport=10 10 250 220,clip]{sample-image.png} % the same, but the image is clipped by the viewport
```

### 缩放图形

```tex
\includegraphics[scale=.5]{sample-image.png} % scales both width and height by 0.5
```

### 调整图形大小

```tex
\includegraphics[width=15mm]{sample-image.png} % changes the width to 15mm preserving the proprtions
\includegraphics[height=15mm,width=25mm]{sample-image.png} % changes both width and height independently
```

### 旋转图形

```tex
\includegraphics[angle=10]{sample-image.png} % rotates the image by 10 degrees counterclockwise
```

要了解更多关于 `graphics` 宏包捆绑功能的信息，请参阅文档[此处](https://ctan.org/pkg/graphics)和[此处](http://mirrors.ctan.org/macros/latex/required/graphics/graphics.pdf)。

**你还可以查看基于 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 构建的免费转换[Web 应用](https://products.aspose.app/tex/conversion/latex/)。**
