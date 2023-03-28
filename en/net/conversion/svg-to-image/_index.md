---
translation: true
template: /templates/_template-conversion-child.md
title: Convert SVG to Image - C# code and Online Converter
description: Convert SVG to Image in C#. Save SVG as a raster image using C# code. Try online SVG to Image Converter for free!
url: /net/conversion/svg-to-image/
family: html
platformtag: net
feature: conversion
informat: SVG
outformat: Image
otherformats: GIF JPEG PNG TIFF BMP PDF XPS
---

{{<section banner>}}
---
h1: Convert SVG to Image online or via C#
h2: High-fidelity SVG to Image conversion using server-side .NET APIs. Instantly convert SVG to raster image formats with our free online converter!
---

{{<section overview>}}
---
h2: Convert SVG to Image Using C#
---

SVG is an XML language for creating two-dimensional vector and mixed vector/raster graphics. In order to convert SVG to Image, we will use [Aspose.HTML for .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) API which is a feature-rich, powerful and easy to use document manipulation and conversion API for the C# platform. SVG conversion is often required to take advantage of other formats. Using our document processing library, you can programmatically convert SVG to Image image with full control over various conversion options with just a few lines of code.

{{<section demos>}}
---
h2: Free Online SVG Converter
---

Test the quality of SVG to Image conversion right in your browser! The following C# example demonstrates how to convert an SVG document. We describe the source code for reading SVG from a file and then converting SVG to Image with default saving options. Please load SVG from the local file system, select the output format and run the example. You will immediately get the result as a separate file. So, quickly convert SVG to Image formats online!

{{<section "app-pluging" i18n-exclude>}}

{{<app/converter SVG PNG BMP  TIFF "JPG|JPEG" GIF XPS PDF>}}
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
h2: Steps to Convert SVG to Image in C#
---

1.  Load an SVG file using one of the SVGDocument() constructors of the [SVGDocument](https://reference.aspose.com/html/net/aspose.html.dom.svg/svgdocument/) class.
1.  Create a new [ImageSaveOptions](https://reference.aspose.com/html/net/aspose.html.saving/imagesaveoptions/) object and specify ImageFormat. By default, the Format property is [PNG.](https://reference.aspose.com/html/net/aspose.html.rendering.image/imageformat/)
1.  Use the [ConvertSVG()](https://reference.aspose.com/html/net/aspose.html.converters/converter/convertsvg/#convertsvg_3) method to save SVG as a BMP image. You need to pass the SVGDocument, ImageSaveOptions, and output file path to the ConvertSVG() method.

{{<section documentation>}}
---
h2: SVG to Image Conversion in Documentation
---

SVG is one of the most used formats for website building and print graphics to achieve scalability. But sometimes you need to convert SVG and save it in a common raster image format. Please visit the documentation chapter [Converting Between Formats](https://docs.aspose.com/html/net/converting-between-formats/) to learn more about Aspose.HTML for .NET API conversion features and to consider C# examples for the most common SVG to Image conversion scenarios. In the articles, you find information on how to convert HTML to Image using ConvertSVG() methods, and how to apply ImageSaveOptions.

  - <a href="https://docs.aspose.com/html/net/converting-between-formats/svg-to-jpg/#svg-to-jpg-by-a-single-line-of-code" target="_blank">SVG to JPG by a single line of code</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/svg-to-jpg/#convert-svg-to-jpg-using-imagesaveoptions" target="_blank">Convert SVG to JPG using ImageSaveOptions</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/svg-to-jpg/#output-stream-providers" target="_blank">Convert SVG to JPG using MemoryStreamProvider</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/svg-to-png/" target="_blank">Convert SVG to PNG</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/svg-to-bmp/" target="_blank">Convert SVG to BMP</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/svg-to-tiff/" target="_blank">Convert SVG to TIFF</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/svg-to-gif/" target="_blank">Convert SVG to GIF</a> 

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