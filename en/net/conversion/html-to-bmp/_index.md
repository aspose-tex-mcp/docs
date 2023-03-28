---
translation: true
template: /templates/_template-conversion-child.md
title: Convert HTML to BMP - C# code and Online Converter
description: Convert HTML to BMP online or using C#. Save HTML page as BMP image in C# code. Try online HTML to BMP Converter for free!
url: /net/conversion/html-to-bmp/
family: html
platformtag: net
feature: conversion
informat: HTML
outformat: BMP
otherformats: PDF DOCX XPS GIF JPEG PNG TIFF BMP XHTML MHTML MD 
---

{{<section banner>}}
---
h1: Convert HTML to BMP online or via C#
h2: Convert web pages to BMP files with high accuracy, quickly, clearly, and safely.
---

{{<section overview>}}
---
h2: Convert HTML to BMP Using C#
---

HTML files are frequently used to create, edit, or communicate a lot of information. If you need to include HTML files in a PowerPoint presentation or send them by email, please convert them to the appropriate image format and use as you want! With [Aspose.HTML for .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) API, you can transform HTML to BMP programmatically with full control over a wide range of conversion parameters. There are various cases for HTML to BMP conversion like reading from a file, URL, WYSISYG Editor, string, or stream. Powerful C# API allows you to convert HTML to popular formats quickly and in high quality!

{{<section demos>}}
---
h2: Online HTML Converter
---

Test the quality of HTML to BMP conversion right in your browser! Please load an HTML file from the local file system, select the required output format from the list and run the example. It's fast, easy, secure and completely free! The HTML to BMP conversion will be done with the default save options. You will immediately get the result as a separate file. So, quickly convert any webpage or HTML to BMP format online!

{{<section "app-pluging" i18n-exclude>}}

{{<app/converter HTML BMP PDF MD "JPG|JPEG" GIF DOCX XPS TIFF PNG MHTML >}}
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
h2: How to Convert HTML to BMP in C#
---

If you would like to consider conversion functionality in your product or you want to convert HTML to BMP programmatically, please see the C# code example above or learn the Documentation chapter. In all cases, any conversion requires some mandatory steps:

1.  Load an HTML document using one of [HTMLDocument()](https://reference.aspose.com/html/net/aspose.html/htmldocument/) constructors. You can load HTML from a file, HTML code, stream, or URL.
1.  Create a new [ImageSaveOptions](https://reference.aspose.com/html/net/aspose.html.saving/imagesaveoptions/) object with BMP ImageFormat. By default, the Format property is PNG.
1.  Use the [ConvertHTML()](https://reference.aspose.com/html/net/aspose.html.converters/converter/converthtml/) method of the Converter class to save HTML as a BMP file. You need to pass the HTMLDocument, ImageSaveOptions, and output file path to the ConvertHTML() method.
1.  The BMP file will be saved to the specified path.

{{<section documentation>}}
---
h2: HTML to BMP Conversion in Documentation
---

BMP files are bitmap image files that are used to store high-quality bitmap digital images. Thus, it may sometimes be necessary to convert HTML to BMP. Please visit the documentation article [Convert HTML to BMP](https://docs.aspose.com/html/net/converting-between-formats/html-to-bmp/) to learn more about Aspose.HTML for .NET API conversion features and to consider C# examples for the most common HTML to BMP conversion scenarios. In the article, you find information on how to convert HTML to BMP using ConvertHTML() methods, and how to apply ImageSaveOptions and ICreateStreamProvider parameters.

  -  <a href="https://docs.aspose.com/html/net/converting-between-formats/html-to-bmp/#convert-html-to-bmp" target="_blank">Convert HTML to BMP</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/html-to-bmp/#convert-html-to-bmp-in-c-using-imagesaveoptions" target="_blank">Convert HTML to BMP using ImageSaveOptions</a>  

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