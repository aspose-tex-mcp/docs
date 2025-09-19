---
translation: true
template: /templates/_template-java.md
linktitle: 字体选择方案
title: 乳胶字体选择方案
weight: 60
url: /java/latex-font-selection/
keywords: 乳胶，乳胶字体，乳胶字体选择，NFSS
description: 本文简要介绍了乳胶字体在处理文档中的使用。它还提到了Tex字体指标和性格形状。
lastmod: "2025-06-10"
---

{{<section overview>}}


在处理源文档时，LaTeX 排版系统对其使用的字体了解不多。它只计算字符的位置，无需了解其形状。它所需的最关键信息是字符的*黑框*，这些黑框由字符的宽度、高度和深度定义。这些尺寸存储在每个字体的单独外部文件中，称为 TeX 字体度量（`.tfm`）。

字符大小稍后才会发挥作用。如果 LaTeX 系统生成`.dvi`文件，则*驱动程序*会将`.dvi`文件中的字符位置数据与`.pk`文件或轮廓描述（例如 PostScript）中的字符形状信息相结合，以在输出介质上生成字符图像。然而，其他 LaTeX 系统（例如 **PDF TeX** 或 **VTEX**）会绕过`.dvi`文件的生成，而是直接生成**PDF**或**PostScript**输出。在这种情况下，当相应的格式化程序生成最终输出时，字符形状就会被嵌入。