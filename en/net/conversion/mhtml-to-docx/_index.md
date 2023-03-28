---
translation: true
template: /templates/_template-conversion-child.md
title: Convert MHTML to DOCX - C# code and Online Converter
description: Convert MHTML to DOCX in C#. Save MHTML as DOCX file using C# code. Try online MHTML to DOCX Converter for free!
url: /net/conversion/mhtml-to-docx/
family: html
platformtag: net
feature: conversion
informat: MHTML
outformat: DOCX
otherformats: PDF XPS GIF JPEG PNG TIFF BMP
---

{{<section banner>}}
---
h1: Convert MHTML to DOCX online or via C#
h2: High-fidelity MHTML to DOCX conversion using .NET API. Instantly convert MHTML to DOCX format with our free online converter.
---

{{<section overview>}}
---
h2: Convert MHTML to DOCX Using C#
---

To convert MHTML to DOCX, we will use [Aspose.HTML for .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) API, which is a feature-rich, powerful and easy to use document manipulation and conversion API for the C# platform. MHTML conversions are often required to take advantage of other formats. Using our high-speed library, you can convert MHTML to DOCX programmatically with full control over various conversion parameters. Powerful C# API allows you to convert MHTML to popular formats quickly and in high quality!

{{<section demos>}}
---
h2: Free Online MHTML Converter
---

Test the quality of MHTML to DOCX conversion right in your browser! Please load an MHTML file from the local file system, select the required output format from the list and run the example. It's fast, easy, secure and completely free! The MHTML to DOCX conversion will be done with the default save options. You will immediately get the result as a separate file. So, quickly convert any webpage or MHTML to DOCX format online!

{{<section "app-pluging" i18n-exclude>}}

{{<app/converter MHTML DOCX PDF "JPG|JPEG" GIF BMP XPS TIFF PNG >}}
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
h2: Steps to Convert MHTML to DOCX in C#
---

If you want to programmatically convert MHTML to DOCX,  please follow a few required steps:

1.  Open an existing MHTML file.
1.  Create an instance of the [DocSaveOptions](https://reference.aspose.com/html/net/aspose.html.saving/docsaveoptions/) class.
1.  Use the [ConvertMHTML()](https://reference.aspose.com/html/net/aspose.html.converters/converter/convertmhtml/#convertmhtml_29) method of the Converter class to save MHTML as a DOCX file. You need to pass the MHTML file stream, DocSaveOptions, and output file path to the ConvertMHTML() method.
1.  The DOCX file will be saved to the specified path.

{{<section documentation>}}
---
h2: MHTML to DOCX Conversion in Documentation
---

MHTML to DOCX conversion is often required to take advantage of DOCX format for specific tasks. DOCX format is popular because it supports a wide range of formatting features and offers users a variety of options to write any type of document. Please visit the documentation article [Convert MHTML to DOCX](https://docs.aspose.com/html/net/converting-between-formats/mhtml-to-docx/) to learn more about Aspose.HTML for .NET API conversion features and to consider C# examples for the most common MHTML to DOCX conversion scenarios. In the article, you will find information on how to convert MHTML to DOCX using ConvertMHTML() methods and how to apply DocSaveOptions or ICreateStreamProvider parameters.

  -  <a href="https://docs.aspose.com/html/net/converting-between-formats/mhtml-to-docx/#mhtml-to-docx-by-two-lines-of-code" target="_blank">MHTML to DOCX by two lines of code</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/mhtml-to-docx/#convert-mhtml-to-docx-using-docsaveoptions" target="_blank">Convert MHTML to DOCX using DocSaveOptions</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/mhtml-to-docx/#output-stream-providers" target="_blank">Convert MHTML to DOCX using MemoryStreamProvider</a>

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