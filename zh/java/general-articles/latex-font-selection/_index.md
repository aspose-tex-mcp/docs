---
translation: true
template: /templates/_template-java.md
linktitle: 字体选择方案
title: LaTeX 字体选择方案
weight: 60
url: /java/latex-font-selection/
keywords: latex、latex 字体、latex 字体选择、nfss
description: 本文简要描述了在处理文档时使用 LaTeX 字体的方式，并提及了 TeX 字体度量和字符形状。
lastmod: "2026-02-28"
---

{{<section overview>}}


在处理源文档时，LaTeX 排版系统对所使用的字体了解不多。它仅计算字符的位置，而无需了解形状。它所需的最关键信息是字符的 *黑盒*，即由宽度、高度和深度定义。这些尺寸存储在每种字体对应的名为 TeX 字体度量 (`.tfm`) 文件的独立外部文件中。

字符形状随后发挥作用。如果 LaTeX 系统生成 `.dvi` 文件，*驱动程序* 会将 `.dvi` 文件中的字符定位数据与 `.pk` 文件中的字符形状信息或轮廓描述（例如 PostScript）相结合，以在输出介质上生成字符图像。然而，其他 LaTeX 系统如 **PDF TeX** 或 **VTEX** 会跳过 `.dvi` 文件的生成，而是直接生成 **PDF** 或 **PostScript** 输出。在这种情况下，字符形状会在相应的格式化程序生成最终输出时嵌入。
