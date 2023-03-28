---
translation: true
template: /templates/_template-conversion-child.md
title: Convert EPUB to PNG - Online Converter and C# code
description: Sample code for EPUB to PNG C# conversion. Easily use C# API within any .NET application. Try online EPUB to PNG Converter for free!
url: /net/conversion/epub-to-png/
family: html
platformtag: net
feature: conversion
informat: EPUB
outformat: PNG
otherformats: PDF DOCX XPS BMP JPEG GIF TIFF
---

{{<section banner>}}
---
h1: Convert EPUB to PNG online or with C#
h2: Generate PNG from EPUB source file using .NET API. Instantly convert EPUB to PNG format with our free online converter!
---

{{<section overview>}}
---
h2: Convert EPUB to PNG Using C#
---

In order to convert EPUB to PNG, we’ll use [Aspose.HTML for .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) API which is a feature-rich, powerful and easy to use document manipulation and conversion API for the C# platform. EPUB is an open XML-based format for digital books and publications that can be viewed and read on a variety of devices. EPUB conversions are often required to take advantage of other formats. You can transform EPUB to PNG programmatically with full control over a wide range of conversion parameters. Powerful C# API allows you to convert EPUB to popular formats quickly and in high quality!

{{<section demos>}}
---
h2: Online EPUB Converter
---

Test the quality of EPUB to PNG conversion right in your browser! It's fast, easy, secure and completely free! The following C# example demonstrates how to convert an EPUB document. We describe the source code for reading EPUB from a file and then converting EPUB to PNG with default saving options. Please load EPUB from the local file system, select the output format and run the example. You will immediately get the result as a separate file.

{{<section "app-pluging" i18n-exclude>}}

{{<app/converter EPUB PNG GIF PDF DOCX "JPG|JPEG" BMP TIFF XPS >}}
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
h2: Steps to Convert EPUB to PNG in C#
---

If you would like to consider conversion functionality in your product or you want to convert EPUB to PNG programmatically, please see the C# code example above or learn the Documentation chapter. It can be different scenarios, but any EPUB conversion can be made with a few required steps:

1.  Open an existing EPUB file.
1.  Create a new [ImageSaveOptions](https://reference.aspose.com/html/net/aspose.html.saving/imagesaveoptions/) object. By default, the Format property is [PNG.](https://reference.aspose.com/html/net/aspose.html.rendering.image/imageformat/)
1.  Use the [ConvertEPUB()](https://reference.aspose.com/html/net/aspose.html.converters/converter/convertepub/#convertepub_27) method of the Converter class to save EPUB as a PNG image. You need to pass the EPUB file stream, ImageSaveOptions, and output file path to the ConvertEPUB() method for EPUB to PNG conversion.
1.  The PNG file will be saved to the specified path.

{{<section documentation>}}
---
h2: EPUB to PNG Conversion in Documentation
---

The EPUB format has gained popularity as an XML-based e-book format and is designed to adapt the content’s presentation to the reader device. Sometimes, it is required to get an image instead of EPUB documents, such as making them portable and easily shared on various devices, creating a picture gallery from eBooks, etc. PNG file format supports lossless image compression that makes it popular among its users. Please visit the documentation article [Convert EPUB to PNG](https://docs.aspose.com/html/net/converting-between-formats/epub-to-png/) to learn more about Aspose.HTML for .NET API conversion features and to consider C# examples for the most common EPUB to PNG conversion scenarios. In the article, you find information on how to convert EPUB to PNG using ConvertEPUB() methods, and how to apply ImageSaveOptions and ICreateStreamProvider parameters.

  - <a href="https://docs.aspose.com/html/net/converting-between-formats/epub-to-png/#epub-to-png-by-a-single-line-of-code" target="_blank">EPUB to PNG by a single line of code</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/epub-to-png/#convert-epub-to-png-using-imagesaveoptions" target="_blank">Convert EPUB to PNG using ImageSaveOptions</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/epub-to-png/#output-stream-providers" target="_blank">Convert EPUB to PNG using MemoryStreamProvider</a>

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