---
translation: true
template: /templates/_template-conversion-child.md
title: Convert HTML to MD - Online Converter and C# code
description: Convert HTML to MD online or with C#. Use HTML to MD Converter to save webpage as MD file quickly, clearly and safely.
url: /net/conversion/html-to-md/
family: html
platformtag: net
feature: conversion
informat: HTML
outformat: MD
otherformats: PDF DOCX XPS GIF JPEG PNG TIFF BMP XHTML MHTML 
---

{{<section banner>}}
---
h1: Convert HTML to MD online or via C#
h2: Generate MD from HTML source page using .NET API. Instantly convert HTML to MD format with our free online converter.
---

{{<section overview>}}
---
h2: Convert HTML to MD Using C#
---

Markdown is a markup language with a plain-text-formatting syntax. Its design allows it to be easily converted to many output formats, but initially, it was created to convert only to HTML. Aspose.HTML class library provides a reversed conversion from HTML to Markdown. With [Aspose.HTML for .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) API, you can transform HTML to MD programmatically with full control over a wide range of conversion parameters. There are various cases for HTML to MD conversion like reading HTML from a file, URL, WYSISYG Editor, string, or stream. Powerful C# API allows you to convert HTML to popular formats quickly and in high quality!

{{<section demos>}}
---
h2:  Online HTML Converter
---

Test the quality of HTML to MD conversion right in your browser! Please load an HTML file from the local file system, select the required output format from the list and run the example. It's fast, easy, secure and completely free! The HTML to MD conversion will be done with the default save options. You will immediately get the result as a separate file. So, quickly convert any webpage or HTML to MD format online!

{{<section "app-pluging" i18n-exclude>}}

{{<app/converter HTML MD PDF "JPG|JPEG" GIF DOCX BMP XPS TIFF PNG MHTML >}}
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
h2: Steps to Convert HTML to MD in C#
---

If you would like to consider conversion functionality in your product or you want to convert HTML to MD programmatically, please see the C# code example above or learn the Documentation chapter. In all cases, any conversion requires some mandatory steps:

1.  Load an HTML document using one of [HTMLDocument()](https://reference.aspose.com/html/net/aspose.html/htmldocument/) constructors. You can load HTML from a file, HTML code, stream, or URL.
1.  Create a new [MarkdownSaveOptions](https://reference.aspose.com/html/net/aspose.html.saving/markdownsaveoptions/) object.
1.  Use the [ConvertHTML()](https://reference.aspose.com/html/net/aspose.html.converters/converter/converthtml/) method of the Converter class to save HTML as a Markdown file. You need to pass the HTMLDocument, MarkdownSaveOptions, and output file path to the ConvertHTML() method.
1.  The MD file will be saved to the specified path.

{{<section documentation>}}
---
h2: HTML to Markdown Conversion in Documentation
---

Please visit the documentation article [Convert HTML to Markdown](https://docs.aspose.com/html/net/converting-between-formats/html-to-markdown/) to learn more about Aspose.HTML for .NET API conversion features and to consider C# examples for the most common HTML to MD conversion scenarios. In the article, you find information on how to convert HTML to MD using ConvertHTML() methods, and how to apply MarkdownSaveOptions and ICreateStreamProvider parameters.

  -  <a href="https://docs.aspose.com/html/net/converting-between-formats/html-to-markdown/#html-to-markdown-by-a-few-lines-of-code" target="_blank">HTML to Markdown by a few lines of code</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/html-to-markdown/#convert-html-to-markdown-in-c-using-markdownsaveoptions" target="_blank">Convert HTML to Markdown using MarkdownSaveOptions</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/html-to-markdown/#limitation" target="_blank">Conversion Limitation</a>

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