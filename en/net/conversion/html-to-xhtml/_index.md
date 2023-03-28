---
translation: true
template: /templates/_template-conversion-child.md
title: Convert HTML to XHTML - Online Converter and C# code
description: Convert HTML to XHTML online or with C#. Use HTML to XHTML Converter to save webpage as XHTML file quickly, clearly and safely.
url: /net/conversion/html-to-xhtml/
family: html
platformtag: net
feature: conversion
informat: HTML
outformat: XHTML
otherformats: DOCX PDF XPS GIF JPEG PNG TIFF BMP MHTML MD
howto: howtoHtmlXhtml
---

{{<section banner>}}
---
h1: Convert HTML to XHTML online or with C#
h2: Use HTML to XHTML Converter to save webpage as XHTML file quickly, clearly and safely.
---

{{<section overview>}}
---
h2: Convert HTML to XHTML Using C#
---

XHTML was designed to be more structured, less scripting, and generic, using all the existing facilities of XML and more device-independent. To convert HTML to XHTML, we’ll use [Aspose.HTML for .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) API, which is a feature-rich, powerful and easy to use document manipulation and conversion API for the C# platform. You can transform HTML to XHTML programmatically with full control over a wide range of conversion parameters. There are various cases for HTML to XHTML conversion like reading from a file, URL, WYSISYG Editor, string, or stream. Powerful C# API allows you to convert HTML to popular formats quickly and in high quality!

{{<section demos>}}
---
h2: Online HTML Converter
---

Test the quality of HTML conversion right in your browser! Please load an HTML file from the local file system, select the required output format from the list and run the example. It's fast, easy, secure and completely free! The HTML conversion will be done with the default save options. You will immediately get the result as a separate file. So, quickly convert any webpage or HTML file online!

{{<section "app-pluging" i18n-exclude>}}

{{<app/converter HTML XHTML MHTML PDF MD "JPG|JPEG" GIF DOCX BMP XPS TIFF PNG>}}
using Aspose.Html;
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
{{#if_output 'BMP' 'JPG' 'GIF' 'PNG' 'TIFF' 'PDF' 'MHTML' 'MD' 'XPS' 'DOCX'}}
    Aspose.Html.Converters.Converter.ConvertHTML(document, options, "output.{{output lower}}"); 
{{/if_output}}
{{#if_output 'XHTML'}} 
    document.Save("output.xhtml", new HTMLSaveOptions() { DocumentType = HTMLSaveOptions.XHTML}); 
{{/if_output}}     
{{</app/converter>}} 

{{<section steps>}}
---
h2: Steps to Convert HTML to XHTML in C#
---

If you would like to consider conversion functionality in your product or you want to convert HTML to XHTML programmatically, please see the C# code example above or learn the Documentation chapter. There are various cases for HTML to XHTML conversion like reading from a URL/Web Page or from a saved file. We describe the source code for reading HTML from a file and then converting HTML to XHTML using Save() method. Please take the following mandatory steps:

1.  Load an HTML document into a Document object using the [HTMLDocument(`string`)](https://reference.aspose.com/html/net/aspose.html/htmldocument/htmldocument/) constructor. You can load HTML from a file, HTML code, stream, or URL.
1.  Call the [Save(`path`, `HTMLSaveOptions`)](https://reference.aspose.com/html/net/aspose.html/htmldocument/save/) method.  You need to pass the output file path with XHTML file extension and saveoptions object to the Save() method.
1.  The XHTML file will be saved to the specified path.

{{<section documentation>}}
---
h2: HTML Conversion in Documentation
---

Converting between formats is required for various reasons: to work in a familiar, convenient format or to take advantage of different formats for specific tasks. Aspose.HTML for .NET API allows you to convert HTML to other popular formats quickly and with high quality. Please visit the documentation chapter <a href="https://docs.aspose.com/html/net/converting-between-formats/" target="_blank">Converting Between Formats</a> to learn more about Aspose.HTML for .NET API conversion features. The chapter describes popular converters, as well as C# examples for the most common conversion scenarios.

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