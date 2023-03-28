---
translation: true
template: /templates/_template-conversion-child.md
title: Convert XHTML to GIF
description: Convert XHTML to GIF in C#. Save XHTML as GIF file using C# code. Try online XHTML to GIF Converter for free!
url: /net/conversion/xhtml-to-gif/
family: html
platformtag: net
feature: conversion
informat: XHTML
outformat: GIF
otherformats: PDF DOCX XPS JPEG PNG TIFF BMP HTML MHTML MD
howto: howtoXhtml 
---

{{<section banner>}}
---
h1: Convert XHTML to GIF online or via C#
h2: Generate GIF image from XHTML source page using .NET API. Instantly convert XHTML to GIF format with our free online converter!
---

{{<section overview>}}
---
h2: Convert XHTML to GIF Using C#
---

The main highlight of [Aspose.HTML .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) API is a conversion feature. Using our powerful library, you can convert XHTML to GIF format programmatically with full control over various conversion parameters. Any conversion you want to perform involves loading an XHTML document and saving it in the supported format. Powerful C# API allows you to convert XHTML to popular formats quickly and in high quality!

{{<section demos>}}
---
h2: Free Online XHTML Converter
---

Test the quality of XHTML to GIF conversion right in your browser! Please load an XHTML file from the local file system, select the required output format from the list and run the example. It's fast, easy, secure and completely free! The XHTML to GIF conversion will be done with the default save options. You will immediately get the result as a separate file. So, quickly convert any webpage or XHTML to GIF format online!

{{<section "app-pluging" i18n-exclude>}}

{{<app/converter XHTML GIF BMP TIFF PNG "JPG|JPEG" PDF XPS DOCX MD MHTML>}}
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
h2: Steps to Convert XHTML to GIF in C#
---

If you want to convert XHTML to GIF programmatically, please see the C# code example above or learn the Documentation chapter. In all cases, any XHTML conversion requires some mandatory steps:

1. Load an XHTML document using one of [HTMLDocument()](https://reference.aspose.com/html/net/aspose.html/htmldocument/) constructors.
1. Create a new [ImageSaveOptions](https://reference.aspose.com/html/net/aspose.html.saving/imagesaveoptions/) object with GIF ImageFormat. By default, the Format property is [PNG.](https://reference.aspose.com/html/net/aspose.html.rendering.image/imageformat/) 
1.  Use the [ConvertHTML()](https://reference.aspose.com/html/net/aspose.html.converters/converter/converthtml/) method to save XHTML as a GIF image. You need to pass the HTMLDocument, ImageSaveOptions, and output file path to the ConvertHTML() method.
1.  The GIF file will be saved to the specified path.

{{<section documentation>}}
---
h2: (X)HTML Conversion in Documentation
---

Converting between formats is required for various reasons: to work in a familiar, convenient format or to take advantage of different formats for specific tasks. Aspose.HTML for .NET API allows you to convert (X)HTML to other popular formats quickly and with high quality. Please visit the documentation chapter <a href="https://docs.aspose.com/html/net/converting-between-formats/" target="_blank">Converting Between Formats</a> to learn more about Aspose.HTML for .NET API conversion features. The chapter describes popular converters, as well as C# examples for the most common conversion scenarios.

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