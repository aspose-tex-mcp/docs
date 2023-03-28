---
translation: true
template: /templates/_template-conversion-child.md
title: Convert MD to JPEG - C# code and Online Converter
description: Sample C# code for MD to JPEG conversion. Easily use C# API within any .NET application. Try online MD to JPEG Converter for free!
url: /net/conversion/md-to-jpeg/
family: html
platformtag: net
feature: conversion
informat: MD
outformat: JPEG
otherformats: PDF DOCX XPS BMP GIF PNG TIFF HTML
howto: howtoMd
---

{{<section banner>}}
---
h1: Convert MD to JPEG online or via C#
h2: High-fidelity MD to JPEG conversion using server-side .NET APIs. Instantly convert MD to JPEG format with our free online converter!
---

{{<section overview>}}
---
h2: Convert MD to JPEG Using C#
---

In order to convert MD to JPEG, we’ll use [Aspose.HTML for .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) API which is a feature-rich, powerful and easy to use document manipulation and conversion API for the C# platform. Conversions from Markdown to other formats go through the Markdown to HTML conversion stage. .NET developers can easily load & convert MD to JPEG in just a few lines of code. Powerful C# API allows you to convert MD to popular formats quickly and in high quality!

{{<section demos>}}
---
h2: Online MD Converter
---

Test the quality of MD to JPEG conversion right in your browser! It's fast, easy, secure and completely free! The following C# example demonstrates how to convert an MD document. We describe the source code for reading MD from a file and then converting MD to JPEG with default saving options. Please load MD from the local file system, select the output format and run the example. You will immediately get the result as a separate file.

{{<section "app-pluging" i18n-exclude>}}

{{<app/converter MD "JPG|JPEG" GIF BMP XPS TIFF PNG PDF DOCX >}}
using Aspose.Html;
using Aspose.Html.Converters;
using Aspose.Html.Saving;

    using var document = Converter.ConvertMarkdown("input.md");
{{#if_output 'PDF'}}
    var options = new PdfSaveOptions();
{{/if_output}}
{{#if_output 'DOCX'}}
    var options = new DocSaveOptions();
{{/if_output}}
{{#if_output 'XPS'}}
    var options = new XpsSaveOptions();
{{/if_output}}
{{#if_output 'BMP' 'JPG' 'GIF' 'PNG' 'TIFF'}}
    var options = new ImageSaveOptions(ImageFormat.{{output param2 camel}});
{{/if_output}}
    Converter.ConvertHTML(document, options, "output.{{output lower}}");   
{{</app/converter>}}


{{<section steps>}}
---
h2: Steps to Convert MD to JPEG in C#
---

1.  Specify a path to a source Markdown file.
1.  Convert Markdown to HTML. Use the [ConvertMarkdown(`sourcePath`)](https://reference.aspose.com/html/net/aspose.html.converters/converter/convertmarkdown/#convertmarkdown_4) method to save Markdown as an HTML document.
1.  Create a new [ImageSaveOptions](https://reference.aspose.com/html/net/aspose.html.saving/imagesaveoptions/) object with JPEG ImageFormat. By default, the Format property is [PNG.](https://reference.aspose.com/html/net/aspose.html.rendering.image/imageformat/)
1.  Use the [ConvertHTML()](https://reference.aspose.com/html/net/aspose.html.converters/converter/converthtml/) method to render the intermediary HTML document to a JPEG image. You need to pass the HTMLDocument, ImageSaveOptions, and output file path to the ConvertHTML() method.

{{<section documentation>}}
---
h2: MD to JPEG Conversion in Documentation
---

JPEG is one of the most commonly used image formats. Its uniqueness is the controlled loss of quality during compression. Thus, it may sometimes be necessary to convert MD to JPEG image. Please visit the documentation article [Convert Markdown to Image](https://docs.aspose.com/html/net/converting-between-formats/markdown-to-image/) to learn more about Aspose.HTML for .NET API conversion features and to consider C# examples for the most common MD to JPEG conversion scenarios. In the article, you will find information on how to <a href="https://docs.aspose.com/html/net/converting-between-formats/markdown-to-image/#convert-markdown-to-jpg" target="_blank">Convert Markdown to JPG</a> using ConvertMarkdown() methods and how to apply ImageSaveOptions.

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
title: Other Supported MD Conversions
subTitle: "You can also convert MD to many other file formats:"
---