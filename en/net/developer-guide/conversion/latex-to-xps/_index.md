---
translation: true
template: /templates/_template-net.md
title: LaTeX to XPS | .NET
linktitle: LaTeX to XPS
weight: 12
url: /net/latex-to-xps/
aliases: /net/other-target-formats/
description: Conversion functionality of Aspose.TeX API solution for .NET lets convert LaTeX files to XPS format. Here are some code examples.
keywords: latex to xps, aspose tex, .net conversion, xps format, tex to xps, document conversion, aspose page, xpsdevice, xpssaveoptions, c# example
lastmod: "2026-11-02"
---

{{<section overview>}}


Another target format is [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). An **XPS** file is physically a ZIP package that contains paginated content of a document, along with the metadata required for proper display by specific viewers (such as Windows XPS Viewer) and printing. All data in a package is represented by files. Some of them are binary and contain resources such as images, fonts, and ICC profiles. Others are XML files in various specific schemas. The latter include files that contain the document data itself. Document data consists of a set of files - each file contains data for an individual page of the document. Such files consist of a single page element and a tree of child elements - *Canvas*, *Path* and *Glyphs*. *Canvas* is a grouping element that can contain other *Canvases*, *Paths* and *Glyphs*. It serves to control the appearance of all child elements as a group. *Path* elements are used to define vector graphics paths. And *Glyphs* elements are used to define textual content. All three elements have properties to define various aspects of appearance.

There is the [**Aspose.Page**](https://products.aspose.com/page/) library that provides an API for manipulating XPS documents, as well as converting them to PDF and raster image formats.

## How to convert LaTeX to XPS

The LaTeX to XPS conversion is just as simple as the [conversion to raster image formats](/tex/{{lang.url-fragment}}net/latex-to-image/), except that the [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) MUST be set to an [XpsSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpssaveoptions/) class instance (by default or explicitly), and the device MUST be changed to an instance of the [XpsDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/) class.

**Simplest conversion example**

The example below shows how to convert a LaTeX file to XPS in a few steps:

1. Create `TeXOptions` for the ObjectLaTeX format with `TeXOptions.ConsoleAppOptions(TeXConfig.ObjectLaTeX)`.
2. Specify the output working directory, for example, an `OutputFileSystemDirectory`.
3. Set `SaveOptions` to an `XpsSaveOptions` instance.
4. Run a `TeXJob` for the source `.tex` file with an `XpsDevice`. The XPS file is written to the output working directory.

This code demonstrates the most direct way to produce an XPS file from LaTeX.

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToXPS-Simplest.cs" >}}

### An alternative way to write the main output XPS file

There's another constructor of the [XpsDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/xpsdevice/) class, which lets us get the resulting XPS file in an alternative way.

**Alternative conversion example**

This snippet demonstrates using the `XpsDevice` constructor that accepts a `Stream`. The steps are:

1. Open the stream to write the XPS document to (here, a file stream; a `MemoryStream` works the same way).
2. Create `TeXOptions`, specify the output working directory and set `SaveOptions` to an `XpsSaveOptions` instance, as in the previous example.
3. Run a `TeXJob` with an `XpsDevice` created with the stream. The XPS document is written to the stream; other output files, such as the transcript, still go to the output working directory.

This approach is useful when you need to write the XPS document to a stream of your choice, for example, to keep it in memory or send it over a network.

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToXPS-Alternative.cs" >}}

The effect is the same as we get [here](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-the-main-output-pdf-file).

**You may also check out the free LaTeX-to-XPS conversion [web app](https://products.aspose.app/tex/conversion/latex-to-xps) built based on [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**