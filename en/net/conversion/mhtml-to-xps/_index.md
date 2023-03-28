---
translation: true
template: /templates/_template-conversion-child.md
title: Convert MHTML to XPS - C# code and Online Converter
description: Convert MHTML to XPS in C#. Easily use C# API within any .NET application. Try online MHTML to XPS Converter for free!
url: /net/conversion/mhtml-to-xps/
family: html
platformtag: net
feature: conversion
informat: MHTML
outformat: XPS
otherformats: DOCX PDF GIF JPEG PNG TIFF BMP
---

{{<section banner>}}
---
h1: Convert MHTML to XPS online or via C#
h2: High-fidelity MHTML to XPS conversion using .NET API. Instantly convert MHTML to XPS format with our free online converter.
---

{{<section overview>}}
---
h2: Convert MHTML to XPS Using C#
---

To convert MHTML to XPS, we will use [Aspose.HTML for .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) API, which is a feature-rich, powerful and easy to use document manipulation and conversion API for the C# platform. MHTML conversions are often required to take advantage of other formats. Using our high-speed library, you can convert MHTML to XPS programmatically with full control over various conversion parameters. Powerful C# API allows you to convert MHTML to popular formats quickly and in high quality!

{{<section demos>}}
---
h2: Free Online MHTML Converter
---

Test the quality of MHTML to XPS conversion right in your browser! Please load an MHTML file from the local file system, select the required output format from the list and run the example. It's fast, easy, secure and completely free! The MHTML to XPS conversion will be done with the default save options. You will immediately get the result as a separate file. So, quickly convert any webpage or MHTML to XPS format online!

{{<section "app-pluging" i18n-exclude>}}

{{<app/converter MHTML XPS PDF DOCX "JPG|JPEG" GIF BMP TIFF PNG >}}
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
h2: Steps to Convert MHTML to XPS in C#
---

If you want to programmatically convert MHTML to XPS,  please follow a few required steps:

1.  Open an existing MHTML file.
1.  Create an instance of the [XpsSaveOptions](https://reference.aspose.com/html/net/aspose.html.saving/xpssaveoptions/) class.
1.  Use the [ConvertMHTML()](https://reference.aspose.com/html/net/aspose.html.converters/converter/convertmhtml/#convertmhtml_29) method of the [Converter](https://reference.aspose.com/html/net/aspose.html.converters/converter/) class to save MHTML as an XPS file. You need to pass the MHTML file stream, XpsSaveOptions, and output file path to the ConvertMHTML() method.
1.  The XPS file will be saved to the specified path.

{{<section documentation>}}
---
h2: MHTML to XPS Conversion in Documentation
---

XPS is a document storage and viewing format developed by Microsoft. It has a set of advantages that support security features, such as digital signatures to provide greater document security and more. Please visit the documentation article [Convert MHTML to XPS](https://docs.aspose.com/html/net/converting-between-formats/mhtml-to-xps/) to learn more about Aspose.HTML for .NET API conversion features and to consider C# examples for the most common MHTML to XPS conversion scenarios. In the article, you will find information on how to convert MHTML to XPS using ConvertMHTML() methods and how to apply XpsSaveOptions or ICreateStreamProvider parameters.

  -  <a href="https://docs.aspose.com/html/net/converting-between-formats/mhtml-to-xps/#mhtml-to-xps-by-two-lines-of-code" target="_blank">MHTML to XPS by two lines of code</a>
  -<a href="https://docs.aspose.com/html/net/converting-between-formats/mhtml-to-xps/#convert-mhtml-to-xps-using-xpssaveoptions" target="_blank">Convert MHTML to XPS using XpsSaveOptions</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/mhtml-to-xps/#output-stream-providers" target="_blank">Convert MHTML to XPS using MemoryStreamProvider</a>

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