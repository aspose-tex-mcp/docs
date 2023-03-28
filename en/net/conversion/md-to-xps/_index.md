---
translation: true
template: /templates/_template-conversion-child.md
title: Convert MD to XPS - Online Converter and C# code
description: Sample C# code for MD to XPS conversion. Easily use C# API within any .NET application. Try online MD to XPS Converter for free!
url: /net/conversion/md-to-xps/
family: html
platformtag: net
feature: conversion
informat: MD
outformat: XPS
otherformats: PDF DOCX JPEG BMP GIF PNG TIFF HTML
howto: howtoMd
---

{{<section banner>}}
---
h1: Convert MD to XPS online or via C#
h2: High-fidelity MD to XPS conversion using server-side .NET APIs. Instantly convert MD to XPS format with our free online converter!
---

{{<section overview>}}
---
h2: Convert MD to XPS Using C#
---

In order to convert MD to XPS, we’ll use [Aspose.HTML for .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) API which is a feature-rich, powerful and easy to use document manipulation and conversion API for the C# platform. Conversions from Markdown to other formats go through the Markdown to HTML conversion stage. .NET developers can easily load & convert MD to XPS in just a few lines of code. Powerful C# API allows you to convert MD to popular formats quickly and in high quality!

{{<section demos>}}
---
h2: Online MD Converter
---

Test the quality of MD to XPS conversion right in your browser! It's fast, easy, secure and completely free! The following C# example demonstrates how to convert an MD document. We describe the source code for reading MD from a file and then converting MD to XPS with default saving options. Please load MD from the local file system, select the output format and run the example. You will immediately get the result as a separate file.

{{<section "app-pluging" i18n-exclude>}}

{{<app/converter MD XPS DOCX "JPG|JPEG" GIF BMP TIFF PNG PDF >}}
using Aspose.Html;
using Aspose.Html.Converters;
using Aspose.Html.Saving;

    using var document = Converter.ConvertMarkdown("input.md");
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
    Converter.ConvertHTML(document, options, "output.{{output lower}}");   
{{</app/converter>}}


{{<section steps>}}
---
h2: Steps to Convert MD to XPS in C#
---

1.  Specify a path to a source Markdown file.
1.  Convert Markdown to HTML. Use the [ConvertMarkdown(`sourcePath`)](https://reference.aspose.com/html/net/aspose.html.converters/converter/convertmarkdown/#convertmarkdown_4) method to save Markdown as an HTML document.
1.  Create a new [XpsSaveOptions](https://reference.aspose.com/html/net/aspose.html.saving/xpssaveoptions/) object.
1.  Use the [ConvertHTML()](https://reference.aspose.com/html/net/aspose.html.converters/converter/converthtml/) method to render the intermediary HTML document to an XPS file. You need to pass the HTMLDocument, DocSaveOptions, and output file path to the ConvertHTML() method.

{{<section documentation>}}
---
h2: MD to XPS Conversion in Documentation
---

Markdown is often used as a format for documentation and readme files since it allows writing in an easy-to-read and easy-to-write style. XPS is a document storage and viewing format developed by Microsoft. It has a set of advantages that support security features, such as digital signatures to provide greater document security and more. MD to XPS conversion is often required to take advantage of XPS format for specific tasks. Please visit the documentation article [Convert Markdown to XPS](https://docs.aspose.com/html/net/converting-between-formats/markdown-to-xps/) to learn more about Aspose.HTML for .NET API conversion features and to consider C# examples for the most common MD to XPS conversion scenarios. In the article, you will find information on how to convert Markdown to XPS using ConvertMarkdown() methods and how to apply XpsSaveOptions.

 - <a href="https://docs.aspose.com/html/net/converting-between-formats/markdown-to-xps/#convert-markdown-to-xps" target="_blank">Convert Markdown to XPS</a>
 - <a href="https://docs.aspose.com/html/net/converting-between-formats/markdown-to-xps/#convert-markdown-to-xps-using-xpssaveoptions" target="_blank">Convert Markdown to XPS using XpsSaveOptions</a>

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
title: Other Supported MD Conversions
subTitle: "You can also convert MD to many other file formats:"
---