---
translation: true
template: /templates/_template-conversion-child.md
title: Convert EPUB to XPS in C# - Online EPUB to XPS Converter
description: Sample code for EPUB to XPS C# conversion. Easily use C# API within any .NET application. Try online EPUB to XPS Converter for free!
url: /net/conversion/epub-to-xps/
family: html
platformtag: net
feature: conversion
informat: EPUB
outformat: XPS
otherformats: DOCX PDF XPS GIF JPEG PNG TIFF BMP
---

{{<section banner>}}
---
h1: Convert EPUB to XPS online or with C#
h2: Generate XPS from EPUB source file using .NET API. Instantly convert EPUB to XPS format with our free online converter!
---

{{<section overview>}}
---
h2: Convert EPUB to XPS Using C#
---

In order to convert EPUB to XPS, we’ll use [Aspose.HTML for .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) API which is a feature-rich, powerful and easy to use document manipulation and conversion API for the C# platform. EPUB is an open XML-based format for digital books and publications that can be viewed and read on a variety of devices. EPUB to XPS conversion is often required to take advantage of XPS format. .NET developers can easily load & convert EPUB to XPS in just a few lines of code. Powerful C# API allows you to convert EPUB to popular formats quickly and in high quality!

{{<section demos>}}
---
h2: Online EPUB Converter
---

Test the quality of EPUB to XPS conversion right in your browser! It's fast, easy, secure and completely free! The following C# example demonstrates how to convert an EPUB document. We describe the source code for reading EPUB from a file and then converting EPUB to XPS with default saving options. Please load EPUB from the local file system, select the output format and run the example. You will immediately get the result as a separate file.

{{<section "app-pluging" i18n-exclude>}}

{{<app/converter EPUB  XPS PDF DOCX "JPG|JPEG" PNG GIF TIFF BMP >}}
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
h2: Steps to Convert EPUB to XPS in C#
---

If you would like to consider conversion functionality in your product or you want to convert EPUB to XPS programmatically, please see the C# code example above or learn the Documentation chapter. API, you can transform EPUB to XPS with full control over a wide range of conversion parameters. It can be different scenarios, but any EPUB conversion can be made with a few required steps:

1.  Open an existing EPUB file.
1.  Create a new [XpsSaveOptions](https://reference.aspose.com/html/net/aspose.html.saving/xpssaveoptions/) object.
1.  Use the [ConvertEPUB()](https://reference.aspose.com/html/net/aspose.html.converters/converter/convertepub/#convertepub_27) method of the Converter class to save EPUB as an XPS file. You need to pass the EPUB file stream, PdfSaveOptions, and output file path to the ConvertEPUB() method for EPUB to XPS conversion.
1.  The XPS file will be saved to the specified path.

{{<section documentation>}}
---
h2: EPUB to XPS Conversion in Documentation
---

The EPUB format has gained popularity as an XML-based e-book format and is designed to adapt the content’s presentation to the reader device. An XPS file represents page layout files that are based on XML Paper Specifications, created by Microsoft. Sometimes you need to get XPS documents instead of EPUB, such as making them print-optimized, safe and secure, etc. Please visit the documentation article [Convert EPUB to XPS](https://docs.aspose.com/html/net/converting-between-formats/epub-to-xps/) to learn more about Aspose.HTML for .NET API conversion features and to consider C# examples for the most common EPUB to XPS conversion scenarios. In the article, you find information on how to convert EPUB to XPS using ConvertEPUB() methods, and how to apply XpsSaveOptions and ICreateStreamProvider parameters.

  - <a href="https://docs.aspose.com/html/net/converting-between-formats/epub-to-xps/#epub-to-xps-by-two-lines-of-code" target="_blank">EPUB to XPS by two lines of code</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/epub-to-xps/#convert-epub-to-xps-using-xpssaveoptions" target="_blank">Convert EPUB to XPS using XpsSaveOptions</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/epub-to-xps/#output-stream-providers" target="_blank">Convert EPUB to XPS using MemoryStreamProvider</a>

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