---
translation: true
template: /templates/_template-conversion-child.md
title: Convert SVG to BMP - Online Converter and C# code
description: Convert SVG to BMP in C#. Save SVG as BMP image using C# code. Try online SVG to BMP Converter for free!
url: /net/conversion/svg-to-bmp/
family: html
platformtag: net
feature: conversion
informat: SVG
outformat: BMP
otherformats: PDF XPS GIF JPEG PNG TIFF 
---

{{<section banner>}}
---
h1: Convert SVG to BMP online or via C#
h2: High-fidelity SVG to BMP conversion using server-side .NET APIs. Instantly convert SVG to BMP format with our free online converter!
---

{{<section overview>}}
---
h2: Convert SVG to BMP Using C#
---

SVG is an XML language for creating two-dimensional vector and mixed vector/raster graphics. In order to convert SVG to BMP, we will use [Aspose.HTML for .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) API which is a feature-rich, powerful and easy to use document manipulation and conversion API for the C# platform. SVG conversion is often required to take advantage of other formats. Using our document processing library, you can programmatically convert SVG to BMP image with full control over various conversion options with just a few lines of code.

{{<section demos>}}
---
h2: Free Online SVG Converter
---

Test the quality of SVG to BMP conversion right in your browser! The following C# example demonstrates how to convert an SVG document. We describe the source code for reading SVG from a file and then converting SVG to BMP with default saving options. Please load SVG from the local file system, select the output format and run the example. You will immediately get the result as a separate file. So, quickly convert SVG to BMP format online!

{{<section "app-pluging" i18n-exclude>}}

{{<app/converter SVG BMP XPS TIFF PNG PDF "JPG|JPEG" GIF>}}
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
h2: Steps to Convert SVG to BMP in C#
---

1.  Load an SVG file using one of the SVGDocument() constructors of the [SVGDocument](https://reference.aspose.com/html/net/aspose.html.dom.svg/svgdocument/) class.
1.  Create a new [ImageSaveOptions](https://reference.aspose.com/html/net/aspose.html.saving/imagesaveoptions/) object with BMP ImageFormat. By default, the Format property is [PNG.](https://reference.aspose.com/html/net/aspose.html.rendering.image/imageformat/)
1.  Use the [ConvertSVG()](https://reference.aspose.com/html/net/aspose.html.converters/converter/convertsvg/#convertsvg_3) method to save SVG as a BMP image. You need to pass the SVGDocument, ImageSaveOptions, and output file path to the ConvertSVG() method.

{{<section documentation>}}
---
h2: SVG to BMP Conversion in Documentation
---

BMP files are bitmap image files that are used to store high quality raster digital images and sometimes it may be necessary to convert SVG to BMP. Please visit the documentation article [Convert SVG to BMP](https://docs.aspose.com/html/net/converting-between-formats/svg-to-bmp/) to learn more about Aspose.HTML for .NET API conversion features and to consider C# examples for the most common SVG to BMP conversion scenarios. In the article, you will find information on how to convert SVG to BMP using ConvertSVG() methods and how to apply ImageSaveOptions.

  - <a href="https://docs.aspose.com/html/net/converting-between-formats/svg-to-bmp/#convert-svg-to-bmp" target="_blank">Convert SVG to BMP</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/svg-to-bmp/#convert-svg-to-bmp-using-imagesaveoptions" target="_blank">Convert SVG to BMP using ImageSaveOptions</a> 

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