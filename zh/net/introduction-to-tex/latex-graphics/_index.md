---
translation: true
template: /templates/_template-java.md
title: 乳胶图形| \ include graphics命令
linktitle: 包括图乳胶
weight: 18
url: /net/latex-graphics/
description: 值得一提的是在TEX中包含图形。在谈论它时，想到的第一件事是“ \includegraphics”命令。
lastmod: "2025-06-10"
---

{{<section overview>}}

实际上，值得一提的乳胶图形有两个方面：

* 向量图形直接通过乳胶/tex命令描述，并且
* 包括外部格式描述的外部图形，例如EPS，PDF或栅格PNG和PDF。

前者对原始乳胶及其包装的支持有限。它是在Tex垂直和水平规则的帮助下实施的。这是因为原始乳胶基于原始TEX发动机，该发动机以 *DVI*格式产生主要输出，不适合描述线条和曲线或二进制栅格图像数据。但是，能够输出图形支持格式的引擎(例如PDFTEX到PDF)也可以使用依赖格式的软件包或软件包功能处理图形。由于相同的原因，基本乳胶不支持后一个图形。我们将在下面讨论图形包含功能。

## 乳胶`graphics'软件包和`\includegraphics`命令

在谈论乳胶图形包含时，想到的第一件事是`\includegraphics`命令。它是在“图形”软件包中定义的，您应该在序言中提到以启用其功能。

```tex
\usepackage{graphics}
```

如果您的排版系统未配置为默认情况下使用PDFTEX，则应指定适当的选项，该选项将迫使软件包使用所需的“驱动程序”文件：


```tex
\usepackage[pdftex]{graphics}
```

“驱动程序”文件是软件包的一部分，该软件包的一部分在软件包命令和格式依赖性的低级别Tex扩展程序之间实现了接口。 Aspose.TeX的乳胶图形支持配置为使用自己的驱动程序，因此您无需指定驱动程序选项。

现在，包括PNG图像的最简单方法是键入：


```tex
\includegraphics{sample-image.png}
```

其中`sample-image.png`是您要包含的文件的名称。您甚至可以使用扩展名。 “ Graphics”软件包包含支持格式的定义列表。查找文件时，它会遍历列表，并包含第一个匹配的文件。

您还可以使用绝对或相对路径指定完整的文件名：

```tex
\includegraphics{d:/sample-image.png} % absolute path
\includegraphics{./sample-image.png} % relative to the current directory
\includegraphics{../img/sample-image.png} % relative to the directory containing the current one
```

指定图形文件位置的另一种方法是在调用`

```tex
\graphicspath{{d:/img}{c:/img}{d:/work/img}}
```

### 缩放图形

乳胶“ Graphics”软件包提供了操纵内容的命令。因此，您可以缩放随附的图形(实际上是Tex/latex代码所描述的任何内容)如下：


```tex
\scalebox{.5}{\includegraphics{sample-image.png}} % scales both width and height by 0.5
\scalebox{.5}[1.5]{\includegraphics{sample-image.png}} % scales the width and height by 0.5 and 1.5 respectively
```

### 调整图形大小

它类似于缩放，但是您指定所需的大小，而不是缩放系数：


```tex
\resizebox{10mm}{!}{\includegraphics{sample-image.png}} % changes the width to 10mm preserving the proprtions
\resizebox{20mm}{10mm}{\includegraphics{sample-image.png}} % changes both width and height independently
```

### 旋转图形

```tex
\rotatebox{25}{\includegraphics{sample-image.png}} % rotates the image by 25 degrees counterclockwise
```

## 乳胶`graphicx`软件包

乳胶`graphicx`软件包提供了``键= value接口''的内容转换。要启用其功能，您应该在序言中提及它：


```tex
\usepackage{graphicx}
\usepackage[pdftex]{graphicx} % with the driver option
```

您可以结合以下任何选项，但请记住，该顺序很重要。

### 图形视口
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

要了解有关“ Graphics”软件包捆绑功能的更多信息，请参见文档[此处](https://ctan.org/pkg/graphics)和
[这里](http://mirrors.ctan.org/macros/latex/required/graphics/graphics.pdf)。

**您也可以查看基于[Aspose.TeX for .NET api](https://products.aspose.com/tex/net/)的免费转换[Web应用](https://products.aspose.app/tex/conversion/latex/)。**