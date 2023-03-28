---
translation: true
template: /templates/_template-conversion-child.md
title: Convert EPUB to Image - C# code and Online Converter
description: Sample C# code for EPUB to Image conversion. Easily use C# API within any .NET application. Try online EPUB to Image Converter for free!
url: /net/conversion/epub-to-image/
family: html
platformtag: net
feature: conversion
informat: EPUB
outformat: "Image"
otherformats: PDF DOCX XPS JPEG BMP GIF PNG TIFF
---

{{<section banner>}}
---
h1: Convert EPUB to Image online or with C#
h2: Generate Images from EPUB source file using .NET API. Instantly convert EPUB to Image format with our free online converter!
---

{{<section overview>}}
---
h2: Convert EPUB to Image Using C#
---

In order to convert EPUB to Image, we’ll use [Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) API which is a feature-rich, powerful and easy to use document manipulation and conversion API for the C# platform. EPUB is an open XML-based format for digital books and publications that can be viewed and read on a variety of devices. EPUB conversions are often required to take advantage of other formats. You can transform EPUB to Image formats programmatically with full control over a wide range of conversion parameters. Powerful C# API allows you to convert EPUB to Images quickly and in high quality!

{{<section demos>}}
---
h2: Online EPUB Converter
---

Test the quality of EPUB to Image conversion right in your browser! It's fast, easy, secure and completely free! The following C# example demonstrates how to convert an EPUB document. We describe the source code for reading EPUB from a file and then converting EPUB to raster image format with default saving options. Please load EPUB from the local file system, select the output format and run the example. You will immediately get the result as a separate file.

{{<section "app-pluging" i18n-exclude>}}

{{<app/converter EPUB "JPG|JPEG" GIF PDF DOCX PNG BMP TIFF XPS >}}
using Aspose.Html;
using Aspose.Html.Converters;
using Aspose.Html.Saving;

    using var stream = File.OpenRead(DataDir + "input.epub");
{{#if_output 'PDF'}}
    var options = new PdfSaveOptions();
{{/if_output}}
{{#if_output 'DOCX'}}
    var options = new DocSaveOptions();
{{/if_output}}
{{#if_output 'XPS'}}
    var options = new XpsSaveOptions();
{{/if_output}}
{{#if_output 'BMP' 'JPG' 'GIF' 'PNG' 'TIFF'}}
    var options = new ImageSaveOptions(ImageFormat.{{output param2 camel}});
{{/if_output}}
    Converter.ConvertEPUB(stream, options, "output.{{output lower}}");   
{{</app/converter>}}


{{<section steps>}}
---
h2: Steps to Convert EPUB to Image in C#
---

If you would like to consider conversion functionality in your product or you want to convert EPUB to Image programmatically, please see the C# code example above or learn the Documentation chapter. It can be different scenarios, but any EPUB conversion can be made with a few required steps:

1.  Open an existing EPUB file.
1.  Create a new [ImageSaveOptions](https://reference.aspose.com/html/net/aspose.html.saving/imagesaveoptions/) object and specify ImageFormat. By default, the Format property is [PNG.](https://reference.aspose.com/html/net/aspose.html.rendering.image/imageformat/)
1.  Use the [ConvertEPUB()](https://reference.aspose.com/html/net/aspose.html.converters/converter/convertepub/#convertepub_27) method of the Converter class to save EPUB as an Image. You need to pass the EPUB file stream, ImageSaveOptions, and output file path to the ConvertEPUB() method for EPUB to Image conversion.
1.  The Image file will be saved to the specified path.

{{<section documentation>}}
---
h2: EPUB to Image Conversion in Documentation
---

The EPUB format has gained popularity as an XML-based e-book format and is designed to adapt the content’s presentation to the reader device. Sometimes, it is required to get an image instead of EPUB documents, such as making them portable and easily shared on various devices, creating a picture gallery from eBooks, etc. Please visit the documentation chapter [Converting Between Formats](https://docs.aspose.com/html/net/converting-between-formats/) to learn more about Aspose.HTML for .NET API conversion features and to consider C# examples for the most common EPUB to Image conversion scenarios. In the articles, you find information on how to convert EPUB to Image using ConvertEPUB() methods, and how to apply ImageSaveOptions or [ICreateStreamProvider](https://reference.aspose.com/html/net/aspose.html.io/icreatestreamprovider/) parameters.

  - <a href="https://docs.aspose.com/html/net/converting-between-formats/epub-to-jpg/#epub-to-jpg-by-two-lines-of-code" target="_blank">EPUB to JPG by two lines of code</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/epub-to-jpg/#convert-epub-to-jpg-using-imagesaveoptions" target="_blank">Convert EPUB to JPG using ImageSaveOptions</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/epub-to-jpg/#output-stream-providers" target="_blank">Convert EPUB to JPG using MemoryStreamProvider</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/epub-to-png/" target="_blank">Convert EPUB to PNG</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/epub-to-bmp/" target="_blank">Convert EPUB to BMP</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/epub-to-tiff/" target="_blank">Convert EPUB to TIFF</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/epub-to-gif/" target="_blank">Convert EPUB to GIF</a>

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
title: Other Supported EPUB Conversions
subTitle: "You can also convert EPUB to many other file formats:"
---