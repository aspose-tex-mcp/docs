---
translation: true
template: /templates/_template-conversion-child.md
title: Convert SVG to PDF - C# code and Online Converter
description: Convert SVG to PDF in C#. Save SVG as PDF file using C# code. Try online SVG to PDF Converter for free!
url: /net/conversion/svg-to-pdf/
family: html
platformtag: net
feature: conversion
informat: SVG
outformat: PDF
otherformats: XPS GIF JPEG PNG TIFF BMP
---

{{<section banner>}}
---
h1: Convert SVG to PDF online or via C#
h2: High-fidelity SVG to PDF conversion using server-side .NET APIs. Instantly convert SVG to PDF format with our free online converter!
---

{{<section overview>}}
---
h2: Convert SVG to PDF Using C#
---

SVG is an XML language for creating two-dimensional vector and mixed vector/raster graphics. In order to convert SVG to PDF, we will use [Aspose.HTML for .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) API which is a feature-rich, powerful and easy to use document manipulation and conversion API for the C# platform. SVG conversion is often required to take advantage of other formats. Using our document processing library, you can programmatically convert SVG to PDF with full control over various conversion options with just a few lines of code.

{{<section demos>}}
---
h2: Free Online SVG Converter
---

Test the quality of SVG to PDF conversion right in your browser! The following C# example demonstrates how to convert an SVG document. We describe the source code for reading SVG from a file and then converting SVG to PDF with default saving options. Please load SVG from the local file system, select the output format and run the example. You will immediately get the result as a separate file. So, quickly convert SVG to PDF format online!

{{<section "app-pluging" i18n-exclude>}}

{{<app/converter SVG PDF  XPS TIFF PNG BMP "JPG|JPEG" GIF>}}
using Aspose.Html;
using Aspose.Html.Dom.Svg;
using Aspose.Html.Converters;
using Aspose.Html.Saving;

    using var document = new SVGDocument("image.svg");
{{#if_output 'PDF'}}
    var options = new PdfSaveOptions();
{{/if_output}}
{{#if_output 'XPS'}}
    var options = new XpsSaveOptions();
{{/if_output}}
{{#if_output 'BMP' 'JPG' 'GIF' 'PNG' 'TIFF'}}
    var options = new ImageSaveOptions(ImageFormat.{{output param2 camel}});
{{/if_output}}
    Converter.ConvertSVG(document, options, "output.{{output lower}}");   
{{</app/converter>}}


{{<section steps>}}
---
h2: Steps to Convert SVG to PDF in C#
---

1.  Load an SVG file using one of the SVGDocument() constructors of the [SVGDocument](https://reference.aspose.com/html/net/aspose.html.dom.svg/svgdocument/) class.
1.  Create a new [PdfSaveOptions](https://reference.aspose.com/html/net/aspose.html.saving/pdfsaveoptions/) object.
1.  Use the [ConvertSVG()](https://reference.aspose.com/html/net/aspose.html.converters/converter/convertsvg/#convertsvg_3) method to save SVG as a PDF file. You need to pass the SVGDocument, PdfSaveOptions, and output file path to the ConvertSVG() method.


{{<section documentation>}}
---
h2: SVG to PDF Conversion in Documentation
---

SVG to PDF conversion is often required to establish limited access to document editing or copying, to produce official documentation or send some information, for example, by email. Please visit the documentation article [Convert SVG to PDF](https://docs.aspose.com/html/net/converting-between-formats/svg-to-pdf/) to learn more about Aspose.HTML for .NET API conversion features and to consider C# examples for the most common SVG to PDF conversion scenarios. In the article, you will find information on how to convert SVG to PDF using ConvertSVG() methods and how to apply PdfSaveOptions.

  - <a href="https://docs.aspose.com/html/net/converting-between-formats/svg-to-pdf/#svg-to-pdf-by-a-single-line-of-code" target="_blank">SVG to PDF by a single line of code</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/svg-to-pdf/#convert-svg-to-pdf-using-pdfsaveoptions" target="_blank">Convert SVG to PDF using PdfSaveOptions</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/svg-to-pdf/#output-stream-providers" target="_blank">Convert SVG to PDF using MemoryStreamProvider</a>

{{<section online-converters>}}
---
h2: Free Online Converters
---

{{<section get-started>}}
---
h2: How to Install Aspose.HTML for .NET library
---

{{<section other-conversions>}}
---
title: Other Supported SVG Conversions
subTitle: "You can also convert SVG to many other file formats:"
---