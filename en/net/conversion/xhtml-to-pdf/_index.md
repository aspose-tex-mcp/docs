---
translation: true
template: /templates/_template-conversion-child.md
title: Convert XHTML to PDF - C# code and Online Converter
description: Convert XHTML to PDF online or via C#. Save XHTML as PDF file using C# code. Try online XHTML to PDF Converter for free!
url: /net/conversion/xhtml-to-pdf/
family: html
platformtag: net
feature: conversion
informat: XHTML
outformat: PDF
otherformats: XPS DOCX GIF JPEG PNG TIFF BMP HTML MHTML MD
howto: howtoXhtml
---

{{<section banner>}}
---
h1: Convert XHTML to PDF online or via C#
h2: Use XHTML to PDF Converter to save XHTML page as PDF file quickly, clearly and safely.
---

{{<section overview>}}
---
h2: Convert XHTML to PDF Using C#
---

Converting XHTML to PDF is often required to protect documents from unwanted editing and copying, to prepare documents for printing or sending by e-mail, etc. With [Aspose.HTML for .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) API, you can convert XHTML to PDF programmatically with full control over conversion parameters. Any conversion you want to perform involves loading an XHTML document and saving it in PDF format. Powerful C# API allows you to convert XHTML to PDF quickly and in high quality!

{{<section demos>}}
---
h2: Free Online XHTML Converter
---

Test the quality of XHTML to PDF conversion right in your browser! Please load an XHTML file from the local file system, select the required output format from the list and run the example. It's fast, easy, secure and completely free! The XHTML to PDF conversion will be done with the default save options. You will immediately get the result as a separate file. So, quickly convert any webpage or XHTML to PDF format online!

{{<section "app-pluging" i18n-exclude>}}

{{<app/converter XHTML PDF BMP TIFF PNG "JPG|JPEG" GIF PDF XPS DOCX MHTML MD >}}
using Aspose.Html;
using Aspose.Html.Converters;
using Aspose.Html.Saving;

    using var document = new HTMLDocument("{{input lower}}");
{{#if_output 'PDF'}}
    var options = new PdfSaveOptions();
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
{{#if_output 'MHTML'}}
    var options = new MHTMLSaveOptions();
{{/if_output}}
{{#if_output 'BMP' 'JPG' 'GIF' 'PNG' 'TIFF'}}
    var options = new ImageSaveOptions(ImageFormat.{{output param2 camel}});
{{/if_output}}
    Converter.ConvertHTML(document, options, "output.{{output lower}}");   
{{</app/converter>}} 


{{<section steps>}}
---
h2: Steps to Convert XHTML to PDF in C#
---

If you want to convert XHTML to PDF programmatically, please see the C# code example above or learn the Documentation chapter. In all cases, any XHTML to PDF conversion requires some mandatory steps:

1.  Load an XHTML file using one of HTMLDocument() constructors of the [HTMLDocument](https://reference.aspose.com/html/net/aspose.html/htmldocument/) class.
1.  Create a new [PdfSaveOptions](https://reference.aspose.com/html/net/aspose.html.saving/pdfsaveoptions/) object. 
1.  Use the [ConvertHTML()](https://reference.aspose.com/html/net/aspose.html.converters/converter/converthtml/) method of the Converter class to save XHTML as a PDF file.
1.  The PDF file will be saved to the specified path.

{{<section documentation>}}
---
h2: (X)HTML Conversion in Documentation
---

XHTML to PDF conversion is often required to establish limited access to document editing or copying, to produce official documentation or send some information, for example, by email. Aspose.HTML for .NET API allows you to convert (X)HTML to other popular formats quickly and with high quality. Please visit the documentation chapter <a href="https://docs.aspose.com/html/net/converting-between-formats/" target="_blank">Converting Between Formats</a> to learn more about the API conversion features. The chapter describes popular converters, as well as C# examples for the most common conversion scenarios.

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
title: Other Supported XHTML Conversions
subTitle: "You can also convert XHTML to many other file formats:"
---