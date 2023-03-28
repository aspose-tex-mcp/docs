---
translation: true
template: /templates/_template-conversion-child.md
title: Convert HTML to  XPS - C# code and Online Converter
description: Convert HTML to XPS online or with C#. Easily use C# API within any .NET application. Try online HTML to XPS Converter for free!
url: /net/conversion/html-to-xps/
family: html
platformtag: net
feature: conversion
informat: HTML
outformat: XPS
otherformats: PDF DOCX GIF JPEG PNG TIFF BMP XHTML MHTML MD 
---

{{<section banner>}}
---
h1: Convert HTML to XPS online or with C#
h2: Generate XPS from HTML source page using .NET API. Instantly convert HTML to XPS format with our free online converter.
---

{{<section overview>}}
---
h2: Convert HTML to XPS Using C#
---

HTML files are frequently used to create, edit, or communicate a lot of information. HTML to XPS conversion is often required to establish limited access to document editing or copying. XPS file format provides access rights management and gives high-quality printable documents. With [Aspose.HTML for .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) API, you can transform HTML to XPS programmatically with full control over a wide range of conversion parameters. There are various cases for HTML to XPS conversion like reading from a file, URL, WYSISYG Editor, string, or stream. Powerful C# API allows you to convert HTML to popular formats quickly and in high quality!

{{<section demos>}}
---
h2:  Online HTML Converter
---

Test the quality of HTML to XPS conversion right in your browser! Please load an HTML file from the local file system, select the required output format from the list and run the example. It's fast, easy, secure and completely free! The HTML to XPS conversion will be done with the default save options. You will immediately get the result as a separate file. So, quickly convert any webpage or HTML to XPS format online!

{{<section "app-pluging" i18n-exclude>}}

{{<app/converter HTML  XPS PDF MD "JPG|JPEG" GIF DOCX BMP TIFF PNG MHTML >}}
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
h2: Steps to Convert HTML to XPS in C#
---

If you would like to consider conversion functionality in your product or you want to convert HTML to XPS programmatically, please see the C# code example above or learn the Documentation chapter. In all cases, any conversion requires some mandatory steps:

1.  Load an HTML document using one of [HTMLDocument()](https://reference.aspose.com/html/net/aspose.html/htmldocument/) constructors. You can load HTML from a file, HTML code, stream, or URL.
1.  Create a new [XpsSaveOptions](https://reference.aspose.com/html/net/aspose.html.saving/xpssaveoptions/) object.
1.  Use the [ConvertHTML()](https://reference.aspose.com/html/net/aspose.html.converters/converter/converthtml/) method of the Converter class to save HTML as an XPS file. You need to pass the HTMLDocument, XpsSaveOptions, and output file path to the ConvertHTML() method.
1.  The XPS file will be saved to the specified path.

{{<section documentation>}}
---
h2: HTML to  XPS Conversion in Documentation
---

XPS is a document storage and viewing format developed by Microsoft. It has a set of advantages that support security features, such as digital signatures to provide greater document security and more. Please visit the documentation article [Convert HTML to XPS](https://docs.aspose.com/html/net/converting-between-formats/html-to-xps/) to learn more about Aspose.HTML for .NET API conversion features and to consider C# examples for the most common HTML to  XPS conversion scenarios. In the article, you find information on how to convert HTML to  XPS using ConvertHTML() methods, and how to apply XpsSaveOptions and ICreateStreamProvider parameters.

  -  <a href="https://docs.aspose.com/html/net/converting-between-formats/html-to-xps/#html-to-xps-by-a-single-line-of-code" target="_blank">Convert HTML to XPS by a single line of code</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/html-to-xps/#convert-html-to-xps-in-c-using-xpssaveoptions" target="_blank">Convert HTML to XPS using XpsSaveOptions</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/html-to-xps/#output-stream-providers" target="_blank">Convert HTML to XPS using MemoryStreamProvider</a>

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