---
translation: true
template: /templates/_template-java.md
linktitle: 包括图
title: 乳胶包括图
weight: 10
url: /java/latex-includegraphics/
keywords: 包括图乳胶，乳胶，包括图形，插入图像乳胶，乳胶graphicx，乳胶插入图像，包括图形乳胶软件包，绘制io乳胶，乳胶包括图形宽度，包括图形宽度，图表乳胶
description: 了解乳胶包括图形宏，以及图像转换，视口，剪辑以及图形和Graphicx软件包之间的差异。
lastmod: "2025-06-10"
---

{{<section overview>}}

## 介绍

在研究您的学术和科学文档(例如研究论文，会议记录和学术演讲)时，您可能有时希望包括图形数字。

一方面，这些可以是图纸，图，直方图或通常称为矢量图形的其他内容。现代乳胶系统(例如“ PDFTEX”)为在文档中创建此类图形提供了大量工具。例如，`pict2e`，`pgf(tikz)`和`pgfplots`软件包。在大多数情况下，数字本身是由Tex引擎生成的，并将其包含在输出文件中，作为适合特定输出格式的向量图形指令的序列。

另一方面，您可能还具有也希望在出版物中包含的栅格图像。乳胶系统目前也能够执行此操作，但是您需要在乳胶文件中指定图像文件的路径作为某些乳胶宏的参数。

本文使用`Graphics`(以及随附的`GraphICX`)软件包中包含乳胶文件中的栅格图像。

## 选择哪个软件包，`graphics'或`graphicx`？

两个软件包`Graphics`和`graphicx`都非常相似。主要区别在于语法。尽管“ Graphics”软件包使用一组单独的宏来将转换应用于图像，但`graphicx`软件包使用`key = value`符号对`\includegraphics`宏的参数''表示这些转换。我们将一次为两个软件包提供每个用例的示例，以使差异更加清晰。

## 包括选定的包裹

这是用“ \usepackage”命令与任何其他乳胶软件包相同的方法来完成的：


```tex
\usepackage{graphics} % to use the graphics package
\usepackage{graphicx} % to use the graphicx package
```

### 指定驱动程序

如果您的排版系统未配置为默认情况下使用“ pdftex”，则应指定适当的选项，该选项将迫使软件包使用所需的“驱动程序”：


```tex
\usepackage[pdftex]{graphics} % graphics
\usepackage[pdftex]{graphicx} % graphicx
```

“驱动程序”是软件包的一部分，该软件包的一部分在软件包命令和格式依赖性的低级Tex扩展原始图之间实现了接口。 **Aspose.TeX**的乳胶图形支持配置为使用自己的驱动程序，因此您无需指定驱动程序选项。

## 乳胶`\includegraphics`宏

现在让我们以最简单的示例继续进行。当然，这是一个根本没有任何转换的图像的情况。预计，使用两个软件包的乳胶代码相同：


```tex
\includegraphics{sample-image.png}
```

此示例假设您的映像文件与乳胶文件位于同一目录中。但是有几种指定不同位置的方法。两个软件包的乳胶代码将再次相同：


```tex
\includegraphics{d:/sample-image.png} % absolute path
\includegraphics{./sample-image.png} % relative to the current directory
\includegraphics{../img/sample-image.png} % relative to the directory containing the current one
```

指定图形文件位置的另一种方法是在调用`


```tex
\graphicspath{{d:/img}{c:/img}{d:/work/img}}
```

## 乳胶图形转换

乳胶`Graphics`和`graphICX“软件包都提供了多种操纵内容的方法。

### 比例图乳胶

因此，您可以缩放随附的图形(实际上是Tex/latex代码所描述的任何内容)如下：


```tex
% 图形示例
\scalebox{.5}{\includegraphics{sample-image.png}} % 将宽度和高度分别缩放 0.5
\scalebox{.5}[1.5]{\includegraphics{sample-image.png}} % 将宽度和高度分别缩放 0.5 和 1.5

% graphicx 示例
\includegraphics[scale=.5]{sample-image.png} % 将宽度和高度分别缩放 0.5
% graphicx 包中没有类似函数可以独立缩放两个维度
```

### 调整大小的乳胶

它类似于缩放，但是您指定所需的大小，而不是缩放系数：


```tex
% 图形示例
\resizebox{10mm}{!}{\includegraphics{sample-image.png}} % 将宽度更改为 10mm，同时保持比例
\resizebox{20mm}{10mm}{\includegraphics{sample-image.png}} % 分别更改宽度和高度

% graphicx 示例
\includegraphics[width=15mm]{sample-image.png} % 将宽度更改为 15mm，同时保持比例
\includegraphics[height=15mm,width=25mm]{sample-image.png} % 分别更改宽度和高度
```

### 旋转图乳胶

```tex
% 图形示例
\rotatebox{25}{\includegraphics{sample-image.png}} % 将图像逆时针旋转 25 度

% graphicx 示例
\includegraphics[angle=-10]{sample-image.png} % 将图像顺时针旋转 10 度
```

### 设置视口和剪辑

```tex
% This time there's no analogue for the graphics package

% graphicx example
\includegraphics[viewport=10 10 280 220]{sample-image.png} % sets the viewport with the lower left corner
                                                           % at the point (10, 10) (coinsides with (0, 0)
                                                           % of the box) and dimensions 280x220pt
\includegraphics[viewport=10 10 250 220,clip]{sample-image.png} % the same, but the image is clipped by the viewport
```

至于“ GraphICX”软件包，可以将转换组合在一起，但顺序很重要。
要了解有关“ Graphics”软件包捆绑功能的更多信息，请参阅[CTAN](https://ctan.org/pkg/graphics)上的软件包页面
[软件包文档](http://mirrors.ctan.org/macros/latex/required/graphics/graphics.pdf)。

### 乳胶包括图形免费网络应用

如果您不想以编程方式使用Include Graphics乳胶软件包，则还可以查看基于[Aspose.TeX for .NET api]构建的免费[latex include graphics](https://products.aspose.app/tex/includegraphics/)Web应用程序(4)。 

该应用程序允许您选择多个图像并为其视觉调整转换。它还使用“ GraphICX”软件包生成乳胶源代码，并在页面上显示结果。

### Aspose.TeX库中的乳胶图渲染功能

**Aspose.TeX**库提供了一种创建光栅和SVG数字的方法，您可以在Tex/latex上下文之外的出版物中使用这些图表。例如，在网页上。这称为**乳胶图渲染**。简而言之，API的这一部分允许您呈现乳胶源代码的片段，而不论页面布局如何。有关更多详细信息，请参阅此[文章](/tex/{{lang.url-fragment}}java/latex-figure-rendering/)。

关于[包括外部乳胶软件包](/tex/{{lang.url-fragment}}java/external-latex-packages/)的文章也可以为您提供有关如何从乳胶图中创建数字的线索。