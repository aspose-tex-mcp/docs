---
translation: true
template: /templates/_template-conversion-child.md
title: Convert HTML to PNG - Online Converter and C# code
description: Convert HTML to PNG online or via C#. Save HTML page as PNG image in C# code. Try online HTML to PNG Converter for free!
url: /net/conversion/html-to-png/
family: html
platformtag: net
feature: conversion
informat: HTML
outformat: PNG
otherformats: PDF DOCX XPS JPEG GIF PNG TIFF BMP XHTML MHTML MD 
---

{{<section banner>}}
---
h1: Convert HTML to PNG online or with C#
h2: Convert web pages to PNG images with high accuracy, quickly, clearly, and safely.
---

{{<section overview>}}
---
h2: Convert HTML to PNG Using C#
---

HTML files are frequently used to create, edit, or communicate a lot of information. If you need to include HTML files in a PowerPoint presentation or send them by email, please convert them to the appropriate image format and use as you want! With [Aspose.HTML for .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) API, you can transform HTML to PNG programmatically with full control over a wide range of conversion parameters. There are various cases for HTML to PNG conversion like reading from a file, URL, WYSISYG Editor, string, or stream. Powerful C# API allows you to convert HTML to popular formats quickly and in high quality!

{{<section demos>}}
---
h2:  Online HTML Converter
---

Test the quality of HTML to PNG conversion right in your browser! Please load an HTML file from the local file system, select the required output format from the list and run the example. It's fast, easy, secure and completely free! The HTML to PNG conversion will be done with the default save options. You will immediately get the result as a separate file. So, quickly convert any webpage or HTML to PNG format online!

{{<section "app-pluging" i18n-exclude>}}

{{<app/converter HTML PNG "JPG|JPEG" BMP PDF MD GIF DOCX XPS TIFF MHTML >}}
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
h2: Steps to Convert HTML to PNG in C#
---

If you would like to consider conversion functionality in your product or you want to convert HTML to PNG programmatically, please see the C# code example above or learn the Documentation chapter. In all cases, any conversion requires some mandatory steps:

1.  Load an HTML document using one of [HTMLDocument()](https://reference.aspose.com/html/net/aspose.html/htmldocument/) constructors. You can load HTML from a file, HTML code, stream, or URL.
1.  Create a new [ImageSaveOptions](https://reference.aspose.com/html/net/aspose.html.saving/imagesaveoptions/) object.
1.  Use the [ConvertHTML()](https://reference.aspose.com/html/net/aspose.html.converters/converter/converthtml/) method of the Converter class to save HTML as a PNG file. You need to pass the HTMLDocument, ImageSaveOptions, and output file path to the ConvertHTML() method.
1.  The PNG file will be saved to the specified path.

{{<section documentation>}}
---
h2: HTML to PNG Conversion in Documentation
---

PNG is one of the most used image file formats. It supports lossless image compression which makes it popular among its users. Converting HTML files to the PNG image may be required, for example, if you want to add a web page in a PowerPoint presentation, insert it on a blog for your readers, or send it by e-mail. Please visit the documentation article [Convert HTML to PNG](https://docs.aspose.com/html/net/converting-between-formats/html-to-png/) to learn more about Aspose.HTML for .NET API conversion features and to consider C# examples for the most common HTML to PNG conversion scenarios. In the article, you find information on how to convert HTML to PNG using ConvertHTML() methods, and how to apply ImageSaveOptions and ICreateStreamProvider parameters.

  -  <a href="https://docs.aspose.com/html/net/converting-between-formats/html-to-png/#html-to-png-by-a-single-line-of-code" target="_blank">HTML to PNG by a single line of code</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/html-to-png/#convert-html-to-png-using-imagesaveoptions" target="_blank">Convert HTML to PNG using ImageSaveOptions</a>
   - <a href="https://docs.aspose.com/html/net/converting-between-formats/html-to-png/#output-stream-providers" target="_blank">Convert HTML to PNG using MemoryStreamProvider</a>  

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