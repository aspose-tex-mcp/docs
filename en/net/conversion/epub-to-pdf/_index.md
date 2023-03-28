---
translation: true
template: /templates/_template-conversion-child.md
title: Convert EPUB to PDF - Online Converter and C# code
description: Sample code for EPUB to PDF C# conversion. Easily use C# API within any .NET application. Try online EPUB to PDF Converter for free!
url: /net/conversion/epub-to-pdf/
family: html
platformtag: net
feature: conversion
informat: EPUB
outformat: PDF
otherformats: DOCX XPS GIF JPEG PNG TIFF BMP
---

{{<section banner>}}
---
h1: Convert EPUB to PDF online or with C#
h2: Generate PDF from EPUB source file using .NET API. Instantly convert EPUB to PDF format with our free online converter!
---

{{<section overview>}}
---
h2: Convert EPUB to PDF Using C#
---

In order to convert EPUB to PDF, we’ll use [Aspose.HTML for .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) API which is a feature-rich, powerful and easy to use document manipulation and conversion API for the C# platform. EPUB is an open XML-based format for digital books and publications that can be viewed and read on a variety of devices. EPUB to PDF conversion is often required to take advantage of PDF format. .NET developers can easily load & convert EPUB to PDF in just a few lines of code. Powerful C# API allows you to convert EPUB to popular formats quickly and in high quality!

{{<section demos>}}
---
h2: Online EPUB Converter
---

Test the quality of EPUB to PDF conversion right in your browser! It's fast, easy, secure and completely free! The following C# example demonstrates how to convert an EPUB document. We describe the source code for reading EPUB from a file and then converting EPUB to PDF with default saving options. Please load EPUB from the local file system, select the output format and run the example. You will immediately get the result as a separate file.

{{<section "app-pluging" i18n-exclude>}}

{{<app/converter EPUB PDF DOCX "JPG|JPEG" PNG GIF TIFF XPS BMP >}}
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
h2: Steps to Convert EPUB to PDF in C#
---

If you would like to consider conversion functionality in your product or you want to convert EPUB to PDF programmatically, please see the C# code example above or learn the Documentation chapter. API, you can transform EPUB to PDF with full control over a wide range of conversion parameters. It can be different scenarios, but any EPUB conversion can be made with a few required steps:

1.  Open an existing EPUB file.
1.  Create a new [PdfSaveOptions](https://reference.aspose.com/html/net/aspose.html.saving/pdfsaveoptions/) object.
1.  Use the [ConvertEPUB()](https://reference.aspose.com/html/net/aspose.html.converters/converter/convertepub/#convertepub_27) method of the Converter class to save EPUB as a PDF file. You need to pass the EPUB file stream, PdfSaveOptions, and output file path to the ConvertEPUB() method for EPUB to PDF conversion.
1.  The PDF file will be saved to the specified path.

{{<section documentation>}}
---
h2: EPUB to PDF Conversion in Documentation
---

The EPUB format has gained popularity as an XML-based e-book format and is designed to adapt the content’s presentation to the reader device. Sometimes you need to get PDF documents instead of EPUB, such as making them print-optimized, safe and secure, making copies of EPUB documents, etc. Please visit the documentation article [Convert EPUB to PDF](https://docs.aspose.com/html/net/converting-between-formats/epub-to-pdf/) to learn more about Aspose.HTML for .NET API conversion features and to consider C# examples for the most common EPUB to PDF conversion scenarios. In the article, you find information on how to convert EPUB to PDF using ConvertEPUB() methods, and how to apply PdfSaveOptions and ICreateStreamProvider parameters.

  - <a href="https://docs.aspose.com/html/net/converting-between-formats/epub-to-pdf/#epub-to-pdf-by-two-lines-of-code" target="_blank">EPUB to PDF by two lines of code</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/epub-to-pdf/#convert-epub-to-pdf-using-pdfsaveoptions" target="_blank">Convert EPUB to PDF using PdfSaveOptions</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/epub-to-pdf/#output-stream-providers" target="_blank">Convert EPUB to PDF using MemoryStreamProvider</a>

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