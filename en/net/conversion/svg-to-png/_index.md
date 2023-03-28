---
translation: true
template: /templates/_template-conversion-child.md
title: Convert SVG to PNG - Online Converter and C# code
description: Convert SVG to PNG in C#. Save SVG as PNG image using C# code. Try online SVG to PNG Converter for free!
url: /net/conversion/svg-to-png/
family: html
platformtag: net
feature: conversion
informat: SVG
outformat: PNG
otherformats: PDF XPS GIF JPEG BMP TIFF 
---

{{<section banner>}}
---
h1: Convert SVG to PNG online or via C#
h2: High-fidelity SVG to PNG conversion using server-side .NET APIs. Instantly convert SVG to PNG format with our free online converter!
---

{{<section overview>}}
---
h2: Convert SVG to PNG Using C#
---

SVG is an XML language for creating two-dimensional vector and mixed vector/raster graphics. In order to convert SVG to PNG, we will use [Aspose.HTML for .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) API which is a feature-rich, powerful and easy to use document manipulation and conversion API for the C# platform. SVG conversion is often required to take advantage of other formats. Using our document processing library, you can programmatically convert SVG to PNG image with full control over various conversion options with just a few lines of code.

{{<section demos>}}
---
h2: Free Online SVG Converter
---

Test the quality of SVG to PNG conversion right in your browser! The following C# example demonstrates how to convert an SVG document. We describe the source code for reading SVG from a file and then converting SVG to PNG with default saving options. Please load SVG from the local file system, select the output format and run the example. You will immediately get the result as a separate file. So, quickly convert SVG to PNG format online!

{{<section "app-pluging" i18n-exclude>}}

{{<app/converter SVG PNG PDF XPS TIFF BMP "JPG|JPEG" GIF>}}
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
h2: Steps to Convert SVG to PNG in C#
---

1.  Load an SVG file using one of the SVGDocument() constructors of the [SVGDocument](https://reference.aspose.com/html/net/aspose.html.dom.svg/svgdocument/) class.
1.  Create a new [ImageSaveOptions](https://reference.aspose.com/html/net/aspose.html.saving/imagesaveoptions/) object. By default, the Format property is [PNG.](https://reference.aspose.com/html/net/aspose.html.rendering.image/imageformat/)
1.  Use the [ConvertSVG()](https://reference.aspose.com/html/net/aspose.html.converters/converter/convertsvg/#convertsvg_3) method to save SVG as a PNG image. You need to pass the SVGDocument, ImageSaveOptions, and output file path to the ConvertSVG() method.


{{<section documentation>}}
---
h2: SVG to PNG Conversion in Documentation
---

PNG file format supports lossless image compression that makes it popular among its users. Please visit the documentation article [Convert SVG to PNG](https://docs.aspose.com/html/net/converting-between-formats/svg-to-png/) to learn more about Aspose.HTML for .NET API conversion features and to consider C# examples for the most common SVG to PNG conversion scenarios. In the article, you will find information on how to convert SVG to PNG using ConvertSVG() methods and how to apply ImageSaveOptions.

  - <a href="https://docs.aspose.com/html/net/converting-between-formats/svg-to-png/#svg-to-png-by-a-single-line-of-code" target="_blank">SVG to PNG by a single line of code</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/svg-to-png/#convert-svg-to-png-using-imagesaveoptions" target="_blank">Convert SVG to PNG using ImageSaveOptions</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/svg-to-png/#output-stream-providers" target="_blank">Convert SVG to PNG using MemoryStreamProvider</a> 

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