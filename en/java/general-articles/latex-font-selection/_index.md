---
title: LaTeX font selection scheme
type: docs
weight: 60
url: /java/latex-font-selection/
keywords: latex, latex fonts, latex font selection, nfss
description: This article briefly describes the use of LaTeX fonts in processing documents. It also mentions TeX font metrics and character shapes.
lastmod: "2024-04-19"
sitemap:
    changefreq: "weekly"
    priority: 0.8
submenu: menu-tex-for-java
---

While processing the source document, the LaTeX typesetting system doesn't have much knowledge about the font it is using. It just calculates the positions of the characters, without needing to know shapes. The most crucial information it requires are the characters' *black boxes*, which are defined by their widths, heights, and depths. These dimensions are stored in a separate external file known as a TeX font metric (`.tfm`) file for each font.

The character chapes come into play later. If a LaTeX system produces a `.dvi` file, a *driver* program combines character placement data from the `.dvi` file with information about character shapes from the `.pk` file or from outline descriptions (such as PostScript) to produce the character image on the output medium. However, other LaTeX systems like **PDF TeX** or **VTEX** bypass the production of a `.dvi` file and instead directly generate **PDF** or **PostScript** output. In that case, the character shapes are embedded when the corresponding formatter produces the final output.
