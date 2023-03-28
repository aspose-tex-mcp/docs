---
translation: true
template: /templates/_template-conversion-child.md
title: Convert MHTML to PDF - Online Converter and C# code
description: Convert MHTML to PDF online or with C#. Use MHTML to PDF Converter to save MHTML as PDF file quickly, clearly and safely.
url: /net/conversion/mhtml-to-pdf/
family: html
platformtag: net
feature: conversion
informat: MHTML
outformat: PDF
otherformats: DOCX XPS GIF JPEG PNG TIFF BMP
---

{{<section banner>}}
---
h1: Convert MHTML to PDF online or via C#
h2: Use MHTML to PDF Converter to save MHTML as PDF file quickly, clearly and safely.
---

{{<section overview>}}
---
h2: Convert MHTML to PDF Using C#
---

To convert MHTML to PDF, we will use [Aspose.HTML for .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) API, which is a feature-rich, powerful and easy to use document manipulation and conversion API for the C# platform. MHTML conversions are often required to take advantage of other formats. Using our high-speed library, you can convert MHTML to PDF programmatically with full control over various conversion parameters. Powerful C# API allows you to convert MHTML to popular formats quickly and in high quality!

{{<section demos>}}
---
h2: Free Online MHTML Converter
---

Test the quality of MHTML to PDF conversion right in your browser! Please load an MHTML file from the local file system, select the required output format from the list and run the example. It's fast, easy, secure and completely free! The MHTML to PDF conversion will be done with the default save options. You will immediately get the result as a separate file. So, quickly convert any webpage or MHTML to PDF format online!

{{<section "app-pluging" i18n-exclude>}}

{{<app/converter MHTML PDF "JPG|JPEG" GIF DOCX BMP XPS TIFF PNG >}}
using Aspose.Html;
using Aspose.Html.Converters;
using Aspose.Html.Saving;

    using var stream = File.OpenRead("sample.mht");
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
    Converter.ConvertMHTML(stream, options, "output.{{output lower}}");   
{{</app/converter>}} 


{{<section steps>}}
---
h2: Steps to Convert MHTML to PDF in C#
---

If you want to programmatically convert MHTML to PDF,  please follow a few required steps:

1.  Open an existing MHTML file.
1.  Create an instance of the [PdfSaveOptions](https://reference.aspose.com/html/net/aspose.html.saving/pdfsaveoptions/) class.
1.  Use the [ConvertMHTML()](https://reference.aspose.com/html/net/aspose.html.converters/converter/convertmhtml/#convertmhtml_29) method of the [Converter](https://reference.aspose.com/html/net/aspose.html.converters/converter/) class to save MHTML as a PDF file. You need to pass the MHTML file stream, PdfSaveOptions, and output file path to the ConvertMHTML() method.
1.  The PDF file will be saved to the specified path.

{{<section documentation>}}
---
h2: MHTML to PDF Conversion in Documentation
---

MHTML to PDF conversion is often required to establish limited access to document editing or copying, to produce official documentation or send some information, for example, by email. Please visit the documentation article [Convert MHTML to PDF](https://docs.aspose.com/html/net/converting-between-formats/mhtml-to-pdf/) to learn more about Aspose.HTML for .NET API conversion features and to consider C# examples for the most common MHTML to PDF conversion scenarios. In the article, you will find information on how to convert MHTML to PDF using ConvertMHTML() methods and how to apply PdfSaveOptions or ICreateStreamProvider parameters.

  -  <a href="https://docs.aspose.com/html/net/converting-between-formats/mhtml-to-pdf/#mhtml-to-pdf-by-two-lines-of-code" target="_blank">MHTML to PDF by two lines of code</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/mhtml-to-pdf/#convert-mhtml-to-pdf-using-pdfsaveoptions" target="_blank">Convert MHTML to PDF using PdfSaveOptions</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/mhtml-to-pdf/#output-stream-providers" target="_blank">Convert MHTML to PDF using MemoryStreamProvider</a>

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
title: Other Supported MHTML Conversions
subTitle: "You can also convert MHTML to many other file formats:"
---