---
translation: true
template: /templates/_template-java.md
title: LaTeX to XPS | Java
linktitle: LaTeX to XPS
weight: 12
url: /java/latex-to-xps/
aliases: /java/other-target-formats/
description: Conversion functionality of Aspose.TeX API solution for Java lets you convert LaTeX files to the XPS format. Learn the code examples.
lastmod: "2024-09-20"
---

{{<section overview>}}


Another target format is [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). An **XPS** file is physically a ZIP package that contains paginated content of a document, as well as the metadata required for proper display by specific viewers (such as Windows XPS Viewer) and printing. All data in a package is organized as files in directories. Some of them contain resources such as images, fonts, and ICC profiles. Others are XML files in various specific schemas. The latter include files that contain the document data itself. Document data is a set of files - each file contains data for an individual page of the document. Such files consist of a single page element and a tree of child elements - *Canvas*, *Path* and *Glyphs*. *Canvas* is a grouping element that can contain other *Canvases*, *Paths* and *Glyphs*. Its purpose is control over the appearance of all child elements as a group. *Path* elements are used to define vector graphics paths. And *Glyphs* elements are used to define text content. All three elements have properties to define various aspects of appearence.

There is the [**Aspose.Page**](https://products.aspose.com/page/) library that provides an API for manipulating XPS documents, as well as converting them to PDF and raster image formats.

## How to convert LaTeX to XPS
The conversion to XPS is just as simple as the [conversion to raster image formats](/tex/{{lang.url-fragment}}java/latex-to-image/), except that in addition to the [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getSaveOptions--), we have to use an instance of the [XpsDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/xpsdevice/) class.

Set `inputFile` to the full path of a self-contained LaTeX file, such as `hello-world.ltx`, and `outputDirectory` to an existing output folder. The default output is `hello-world.xps` for this input. Import the classes from `com.aspose.tex` and `com.aspose.tex.rendering` used in the snippet. The calling method must handle or declare exceptions. Apply a license as described in the [licensing guide](/tex/{{lang.url-fragment}}java/licensing/) to avoid evaluation restrictions. The example selects noninteractive processing and closes its output resources.

{{< gist "aspose-com-gists" "a30f406f6b8ace1b7d15c68a1df75c6d" "Example-ConvertLaTeXToXPS-Simplest.java" >}}

### An alternative way to write the main output XPS file

There's another constructor of the [XpsDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/xpsdevice/#XpsDevice-java.io.OutputStream-) class, which allows us to get the resulting XPS file in an alternative way.

Use the same `inputFile` and `outputDirectory` values as above. Set `xpsFile` to a `java.nio.file.Path`, for example `Paths.get(outputDirectory, "any-name.xps")`. In addition to the Aspose.TeX classes, import `java.io.OutputStream`, `java.nio.file.Files`, `java.nio.file.Path`, and `java.nio.file.Paths`. The stream controls the XPS destination; auxiliary files still go to `outputDirectory`.

{{< gist "aspose-com-gists" "a30f406f6b8ace1b7d15c68a1df75c6d" "Example-ConvertLaTeXToXPS-Alternative.java" >}}

The effect is the same as we get [here](/tex/{{lang.url-fragment}}java/latex-to-pdf/#an-alternative-way-to-write-the-main-output-pdf-file).

**You may also check out the free LaTeX-to-XPS conversion [web app](https://products.aspose.app/tex/conversion/latex-to-xps) built based on [Aspose.TeX for .NET](https://products.aspose.com/tex/net/) API. [Here](https://products.aspose.com/tex/java/) is the Java version page.**