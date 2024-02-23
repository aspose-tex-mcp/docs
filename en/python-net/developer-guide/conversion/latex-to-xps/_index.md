---
title: LaTeX to XPS | Aspose.TeX for Python
linktitle: LaTeX to XPS
type: docs
weight: 12
url: /python-net/latex-to-xps/
aliases: /python-net/other-target-formats/
description: The Aspose.TeX API solution for Python provides conversion functionality to convert LaTeX files to XPS format. Here are a few code examples.
lastmod: "2023-03-23"
sitemap:
    changefreq: "weekly"
    priority: 0.8
submenu: menu-tex-for-python-net
---

Another target format is [**XPS**](https://docs.aspose.com/page/net/what-is-xps-file/). An [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification) file is essentially a ZIP package that contains еру paginated content of a document, along with the necessary metadata for proper display by specific viewers (such as Windows XPS Viewer) and printing. The package consists of various files, some of which are binary and contain resources like images, fonts, and ICC profiles. Others are XML files in specific schemas, including files that contain the document data itself. The document data is divided into multiple files, with each file representing an individual page of the document. These files consist of a single page element and a tree of child elements, including *Canvas*, *Path*, and *Glyphs*. The *Canvas* element is a grouping element that can contain other *Canvases*, *Paths*, and *Glyphs*, and it controls the appearance of all child elements as a group. *Path* elements are used to define vector graphics paths, while *Glyphs* elements are used to define textual content. All three elements have properties that define various aspects of appearance.

There exists the [**Aspose.Page**](https://products.aspose.com/page/) library, which offers an API for manipulating XPS documents and also enables the conversion of these documents to PDF and raster image formats.

## Converting LaTeX to XPS

The process of converting LaTeX to XPS is equally straightforward, similar to the [conversion to raster image formats](/tex/python-net/latex-to-image/). However, it requires setting the [save_options](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/save_options/) to an instance of the [XpsSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.xps/xpssaveoptions/) class (either by default or explicitly), and changing the device to an instance of the [XpsDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.xps/xpsdevice/) class.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToXps-Simplest.py" >}}

### An alternative way to write the main output XPS file

There is an alternative constructor available for the *XpsDevice* class, which allows for obtaining the resulting XPS file in a different manner.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToXps-Alternative.py" >}}

The effect is the same as we get [here](/tex/python-net/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file).

**You can also explore the free [web app for LaTeX-to-XPS conversion](https://products.aspose.app/tex/conversion/latex-to-xps), which is developed using the [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**