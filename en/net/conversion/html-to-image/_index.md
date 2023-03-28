---
translation: true
template: /templates/_template-conversion-child.md
title: Convert HTML to Image - Online Converter and C# code
description: Convert HTML to Image online or with C#. Use HTML to Image Converter to save webpage as an image file quickly, clearly and safely.
url: /net/conversion/html-to-image/
family: html
platformtag: net
feature: conversion
informat: HTML
outformat: Image 
otherformats: PDF DOCX XPS JPEG GIF PNG TIFF BMP XHTML MHTML MD 
---

{{<section banner>}}
---
h1: Convert HTML to Image online or via C#
h2: Convert web pages to image files with high accuracy, quickly, clearly, and safely.
---

{{<section overview>}}
---
h2: Convert HTML to Image Using C#
---

HTML files are frequently used to create, edit, or communicate a lot of information. If you need to include HTML files in a PowerPoint presentation or send them by email, please convert them to the appropriate image format and use as you want! With [Aspose.HTML for .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) API, you can transform HTML to Image programmatically with full control over a wide range of conversion parameters. There are various cases for HTML to Image conversion like reading HTML from a file, URL, WYSISYG Editor, string, or stream. Powerful C# API allows you to convert HTML to popular formats quickly and in high quality!

{{<section demos>}}
---
h2:  Online HTML Converter
---

Test the quality of HTML to Image conversion right in your browser! Please load an HTML file from the local file system, select the required output format from the list and run the example. It's fast, easy, secure and completely free! The HTML to Image conversion will be done with the default save options. You will immediately get the result as a separate file. So, quickly convert any webpage or HTML to Image format online!

{{<section "app-pluging" i18n-exclude>}}

{{<app/converter HTML "JPG|JPEG" BMP PDF MD  GIF DOCX XPS TIFF PNG MHTML >}}
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
h2: Steps to Convert HTML to Image in C#
---

If you would like to consider conversion functionality in your product or you want to convert HTML to Image programmatically, please see the C# code example above or learn the Documentation chapter. In all cases, any conversion requires some mandatory steps:

1.  Load an HTML document using one of [HTMLDocument()](https://reference.aspose.com/html/net/aspose.html/htmldocument/) constructors. You can load HTML from a file, HTML code, stream, or URL.
1.  Create a new [ImageSaveOptions](https://reference.aspose.com/html/net/aspose.html.saving/imagesaveoptions/) object and specify ImageFormat. By default, the Format property is PNG.
1.  Use the [ConvertHTML()](https://reference.aspose.com/html/net/aspose.html.converters/converter/converthtml/) method of the Converter class to save HTML as an image file. You need to pass the HTMLDocument, ImageSaveOptions, and output file path to the ConvertHTML() method.
1.  The Image file will be saved to the specified path.

{{<section documentation>}}
---
h2: HTML to Image Conversion in Documentation
---

Please visit the documentation chapter [Converting Between Formats](https://docs.aspose.com/html/net/converting-between-formats/) to learn more about Aspose.HTML for .NET API conversion features and to consider C# examples for the most common HTML to Image conversion scenarios. In the articles, you find information on how to convert HTML to Image using ConvertHTML() methods, and how to apply ImageSaveOptions or [ICreateStreamProvider](https://reference.aspose.com/html/net/aspose.html.io/icreatestreamprovider/) parameters.

 - <a href="https://docs.aspose.com/html/net/converting-between-formats/html-to-jpg/#html-to-jpg-by-a-single-line-of-code" target="_blank">HTML to JPG by a single line of code</a>
 - <a href="https://docs.aspose.com/html/net/converting-between-formats/html-to-jpg/#convert-html-to-jpg-using-imagesaveoptions" target="_blank">Convert HTML to JPG using ImageSaveOptions</a>
 - <a href="https://docs.aspose.com/html/net/converting-between-formats/html-to-jpg/#output-stream-providers" target="_blank">Convert HTML to JPG using MemoryStreamProvider</a>
 - <a href="https://docs.aspose.com/html/net/converting-between-formats/html-to-png/" target="_blank">Convert HTML to PNG</a>
 - <a href="https://docs.aspose.com/html/net/converting-between-formats/html-to-bmp/" target="_blank">Convert HTML to BMP</a>
 - <a href="https://docs.aspose.com/html/net/converting-between-formats/html-to-tiff/" target="_blank">Convert HTML to TIFF</a>
 - <a href="https://docs.aspose.com/html/net/converting-between-formats/html-to-gif/" target="_blank">Convert HTML to GIF</a> 

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