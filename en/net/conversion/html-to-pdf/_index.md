---
translation: true
template: /templates/_template-conversion-child.md
title: Convert HTML to PDF - Online Converter and C# code 
description: Convert HTML to PDF online or with C#. Use HTML to PDF Converter to save webpage as PDF file quickly, clearly and safely.
url: /net/conversion/html-to-pdf/
family: html
platformtag: net
feature: conversion
informat: HTML
outformat: PDF
otherformats: DOCX XPS GIF JPEG PNG TIFF BMP XHTML MHTML MD 
---

{{<section banner>}}
---
h1: Convert HTML to PDF online or via C#
h2: Convert web pages to PDF files with high accuracy, quickly, clearly, and safely.
---

{{<section overview>}}
---
h2: Convert HTML to PDF Using C#
---

Converting HTML to PDF is often required to protect documents from unwanted editing and copying, to prepare documents for printing or sending by e-mail, etc. With [Aspose.HTML for .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) API, you can transform HTML to PDF programmatically with full control over a wide range of conversion parameters. There are various cases for HTML to PDF conversion like reading from a file, URL, WYSISYG Editor, string, or stream. Powerful C# API allows you to convert HTML to popular formats quickly and in high quality!

{{<section demos>}}
---
h2: Online HTML Converter
---

Test the quality of HTML to PDF conversion right in your browser! Please load an HTML file from the local file system, select the required output format from the list and run the example. It's fast, easy, secure and completely free! The HTML to PDF conversion will be done with the default save options. You will immediately get the result as a separate file.

{{<section "app-pluging" i18n-exclude>}}

{{<app/converter HTML PDF MD "JPG|JPEG" GIF DOCX BMP XPS TIFF PNG MHTML >}}
using Aspose.Html;
using Aspose.Html.Converters;
using Aspose.Html.Saving;

    using var document = new HTMLDocument("{{input lower}}");
{{#if_output 'PDF'}}
    var options = new PdfSaveOptions();
{{/if_output}}
{{#if_output 'MHTML'}}
    var options = new MHTMLSaveOptions();
{{/if_output}}
{{#if_output 'DOCX'}}
    var options = new DocSaveOptions();
{{/if_output}}
{{#if_output 'XPS'}}
    var options = new XpsSaveOptions();
{{/if_output}}
{{#if_output 'MD'}}
    var options = new MarkdownSaveOptions();
{{/if_output}}
{{#if_output 'BMP' 'JPG' 'GIF' 'PNG' 'TIFF'}}
    var options = new ImageSaveOptions(ImageFormat.{{output param2 camel}});
{{/if_output}}
    Converter.ConvertHTML(document, options, "output.{{output lower}}");   
{{</app/converter>}} 


{{<section steps>}}
---
h2: Steps to Convert HTML to PDF in C#
---

If you would like to consider conversion functionality in your product or you want to convert HTML to PDF programmatically, please see the C# code example above or learn the Documentation chapter. In all cases, any conversion requires some mandatory steps:

1.  Load an HTML document using one of [HTMLDocument()](https://reference.aspose.com/html/net/aspose.html/htmldocument/) constructors. You can load HTML from a file, HTML code, stream, or URL.
1.  Create a new [PdfSaveOptions](https://reference.aspose.com/html/net/aspose.html.saving/pdfsaveoptions/) object.
1.  Use the [ConvertHTML()](https://reference.aspose.com/html/net/aspose.html.converters/converter/converthtml/) method of the Converter class to save HTML as a PDF file. You need to pass the HTMLDocument, PdfSaveOptions, and output file path to the ConvertHTML() method.
1.  The PDF file will be saved to the specified path.

{{<section documentation>}}
---
h2: HTML to PDF Conversion in Documentation
---

HTML files are frequently used to create, edit, or communicate a lot of information. HTML to PDF conversion is often required to protect documents from unwanted editing or copying, produce official documentation, prepare files for printing or sending by e-mail, etc.  Please visit the documentation article [Convert HTML to PDF](https://docs.aspose.com/html/net/converting-between-formats/html-to-pdf/) to learn more about Aspose.HTML for .NET API conversion features and to consider C# examples for the most common HTML to PDF conversion scenarios. In the article, you find information on how to convert HTML to PDF using ConvertHTML() methods, and how to apply PdfSaveOptions and ICreateStreamProvider parameters.

  -  <a href="https://docs.aspose.com/html/net/converting-between-formats/html-to-pdf/#html-to-pdf-by-a-single-line-of-code" target="_blank">Convert HTML to PDF by a single line of code</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/html-to-pdf/#convert-html-to-pdf-in-c-using-pdfsaveoptions" target="_blank">Convert HTML to PDF using PdfSaveOptions</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/html-to-pdf/#output-stream-providers" target="_blank">Convert HTML to PDF using MemoryStreamProvider</a>

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
title: Other Supported HTML Conversions
subTitle: "You can also convert HTML to many other file formats:"
---