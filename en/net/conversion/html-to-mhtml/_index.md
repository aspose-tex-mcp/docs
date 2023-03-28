---
translation: true
template: /templates/_template-conversion-child.md
title: Convert HTML to MHTML - Online Converter and C# code
description: Convert HTML to MHTML online or with C#. Use HTML to MHTML Converter to save webpage as MHTML file quickly, clearly and safely.
url: /net/conversion/html-to-mhtml/
family: html
platformtag: net
feature: conversion
informat: HTML
outformat: MHTML
otherformats: DOCX PDF XPS GIF JPEG PNG TIFF BMP XHTML MD 
---

{{<section banner>}}
---
h1: Convert HTML to MHTML online or via C#
h2: Use HTML to MHTML Converter to save webpage as MHTML file quickly, clearly and safely.
---

{{<section overview>}}
---
h2: Convert HTML to MHTML Using C#
---

HTML files are frequently used to create, edit, or communicate a lot of information. The advantage of saving HTML as MHTML is that all of the web page elements are kept intact in a single file. MHTML contains an underlying HTML document and its embedded images, media, and other resources. With [Aspose.HTML for .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) API, you can transform HTML to MHTML programmatically with full control over a wide range of conversion parameters. There are various cases for HTML to MHTML conversion like reading from a file, URL, WYSISYG Editor, string, or stream. Powerful C# API allows you to convert HTML to popular formats quickly and in high quality!

{{<section demos>}}
---
h2:  Online HTML Converter
---

Test the quality of HTML to MHTML conversion right in your browser! Please load an HTML file from the local file system, select the required output format from the list and run the example. It's fast, easy, secure and completely free! The HTML to MHTML conversion will be done with the default save options. You will immediately get the result as a separate file. So, quickly convert any webpage or HTML to MHTML format online!

{{<section "app-pluging" i18n-exclude>}}

{{<app/converter HTML MHTML PDF MD "JPG|JPEG" GIF DOCX BMP XPS TIFF PNG >}}
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
h2: Steps to Convert HTML to MHTML in C#
---

If you would like to consider conversion functionality in your product or you want to convert HTML to MHTML programmatically, please see the C# code example above or learn the Documentation chapter. In all cases, any conversion requires some mandatory steps:

1.  Load an HTML document using one of [HTMLDocument()](https://reference.aspose.com/html/net/aspose.html/htmldocument/) constructors. You can load HTML from a file, HTML code, stream, or URL.
1.  Create a new [MHTMLSaveOptions](https://reference.aspose.com/html/net/aspose.html.saving/mhtmlsaveoptions/) object.
1.  Use the [ConvertHTML()](https://reference.aspose.com/html/net/aspose.html.converters/converter/converthtml/) method of the Converter class to save HTML as an MHTML file. You need to pass the HTMLDocument, MHTMLSaveOptions, and output file path to the ConvertHTML() method.
1.  The MHTML file will be saved to the specified path.

{{<section documentation>}}
---
h2: HTML to MHTML Conversion in Documentation
---

MHTML combines normal HTML with external resources like images, animations, audio, etc., into one file with the .mht file extension. Aspose.HTML for .NET API allows you to convert HTML to MHTML format quickly and with high quality. Please visit the documentation article [Convert HTML to MHTML](https://docs.aspose.com/html/net/converting-between-formats/html-to-mhtml/) to learn more about Aspose.HTML for .NET API conversion features and to consider C# examples for the most common HTML to MHTML conversion scenarios. In the article, you find information on how to convert HTML to MHTML using ConvertHTML() methods, and how to apply MHTMLSaveOptions and ICreateStreamProvider parameters.

  -  <a href="https://docs.aspose.com/html/net/converting-between-formats/html-to-mhtml/#html-to-mhtml-by-a-single-line-of-code" target="_blank">Convert HTML to MHTML by a single line of code</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/html-to-mhtml/#convert-html-to-mhtml-in-c-using-mhtmlsaveoptions" target="_blank">Convert HTML to MHTML using MHTMLSaveOptions</a>  

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