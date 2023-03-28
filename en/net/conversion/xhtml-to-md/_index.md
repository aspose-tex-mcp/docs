---
translation: true
template: /templates/_template-conversion-child.md
title: Convert XHTML to MD
description: Convert XHTML to MD in C#. Save XHTML as Markdown file using C# code. Try online XHTML to MD Converter for free!
url: /net/conversion/xhtml-to-md/
family: html
platformtag: net
feature: conversion
informat: XHTML
outformat: MD
otherformats: PDF XPS DOCX GIF JPEG PNG TIFF BMP HTML MHTML
howto: howtoXhtml
---

{{<section banner>}}
---
h1: Convert XHTML to MD online or via C#
h2: Generate MD from XHTML source page using .NET API. Instantly convert XHTML to MD format with our free online converter!
---

{{<section overview>}}
---
h2: Convert XHTML to MD Using C#
---

Markdown is a markup language with a plain-text-formatting syntax. Its design allows it to be easily converted to many output formats, but initially, it was created to convert only to HTML. Aspose.HTML class library provides a reversed conversion from (X)HTML to Markdown. With [Aspose.HTML for .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) API, you can convert XHTML to MD programmatically with full control over conversion parameters. Any conversion you want to perform involves loading an XHTML document and saving it in Markdown format. Powerful C# API allows you to convert XHTML to MD quickly and in high quality!

{{<section demos>}}
---
h2: Free Online XHTML Converter
---

Test the quality of XHTML to MD conversion right in your browser! Please load an XHTML file from the local file system, select the required output format from the list and run the example. It's fast, easy, secure and completely free! The XHTML to MD conversion will be done with the default save options. You will immediately get the result as a separate file. So, quickly convert any webpage or XHTML to MD format online!

{{<section "app-pluging" i18n-exclude>}}

{{<app/converter XHTML MD BMP TIFF PNG "JPG|JPEG" GIF PDF XPS DOCX MHTML >}}
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
h2: Steps to Convert XHTML to MD in C#
---

If you want to convert XHTML to MD programmatically, please see the C# code example above or learn the Documentation chapter. In all cases, any XHTML to MD conversion requires some mandatory steps:

1.  Load an XHTML file using one of HTMLDocument() constructors of the [HTMLDocument](https://reference.aspose.com/html/net/aspose.html/htmldocument/) class.
1.  Create a new [MarkdownSaveOptions](https://reference.aspose.com/html/net/aspose.html.saving/markdownsaveoptions/) object. 
1.  Use the [ConvertHTML()](https://reference.aspose.com/html/net/aspose.html.converters/converter/converthtml/) method of the Converter class to save XHTML as a Markdown file.
1.  The MD file will be saved to the specified path.

{{<section documentation>}}
---
h2: (X)HTML Conversion in Documentation
---

Aspose.HTML for .NET API allows you to convert (X)HTML to other popular formats quickly and with high quality. Please visit the documentation chapter <a href="https://docs.aspose.com/html/net/converting-between-formats/" target="_blank">Converting Between Formats</a> to learn more about the API conversion features. The chapter describes popular converters, as well as C# examples for the most common conversion scenarios.

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