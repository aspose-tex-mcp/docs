---
translation: true
template: /templates/_template-conversion-child.md
title: Convert MHTML to JPEG - C# code and Online Converter
description: Convert MHTML to JPEG in C#. Save MHTML page as JPEG image using C# code. Try online MHTML to JPEG Converter for free!
url: /net/conversion/mhtml-to-jpeg/
family: html
platformtag: net
feature: conversion
informat: MHTML
outformat: JPEG
otherformats: DOCX PDF XPS BMP GIF PNG TIFF
---

{{<section banner>}}
---
h1: Convert MHTML to JPEG online or via C#
h2: High-fidelity MHTML to JPEG conversion using .NET API. Instantly convert MHTML to JPEG format with our free online converter.
---

{{<section overview>}}
---
h2: Convert MHTML to JPEG Using C#
---

To convert MHTML to JPEG, we will use [Aspose.HTML for .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) API, which is a feature-rich, powerful and easy to use document manipulation and conversion API for the C# platform. MHTML conversions are often required to take advantage of other formats. Using our high-speed library, you can convert MHTML to JPEG image programmatically with full control over various conversion parameters. Powerful C# API allows you to convert MHTML to popular formats quickly and in high quality!

{{<section demos>}}
---
h2: Free Online MHTML Converter
---

Test the quality of MHTML to JPEG conversion right in your browser! Please load an MHTML file from the local file system, select the required output format from the list and run the example. It's fast, easy, secure and completely free! The MHTML to JPEG conversion will be done with the default save options. You will immediately get the result as a separate file. So, quickly convert any webpage or MHTML to JPEG format online!

{{<section "app-pluging" i18n-exclude>}}

{{<app/converter MHTML "JPG|JPEG" GIF TIFF PNG BMP DOCX PDF XPS >}}
using Aspose.Html;
using Aspose.Html.Converters;
using Aspose.Html.Saving;

    using var stream = File.OpenRead("sample.mht");
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
    Converter.ConvertMHTML(stream, options, "output.{{output lower}}");   
{{</app/converter>}} 


{{<section steps>}}
---
h2: Steps to Convert MHTML to JPEG in C#
---

If you want to programmatically convert MHTML to JPEG,  please follow a few required steps:

1.  Open an existing MHTML file.
1.  Create a new [ImageSaveOptions](https://reference.aspose.com/html/net/aspose.html.saving/imagesaveoptions/) object with JPEG ImageFormat. By default, the Format property is [PNG.](https://reference.aspose.com/html/net/aspose.html.rendering.image/imageformat/)
1.  Use the [ConvertMHTML()](https://reference.aspose.com/html/net/aspose.html.converters/converter/convertmhtml/) method of the Converter class to save MHTML as a JPEG image.
1.  The JPEG file will be saved to the specified path.

{{<section documentation>}}
---
h2: MHTML to JPEG Conversion in Documentation
---

JPEG is one of the most commonly used image formats. Its uniqueness is the controlled loss of quality during compression. This compression feature allows you to quickly and efficiently share JPG images and use them widely on the Web, computers, and mobile devices. MHTML to JPEG conversion allows you to save an MHTML document as a JPEG image. Please visit the documentation article [Convert MHTML to Image](https://docs.aspose.com/html/net/converting-between-formats/mhtml-to-image/) to learn more about Aspose.HTML for .NET API conversion features and to consider C# examples for the most common MHTML to JPEG conversion scenarios. In the article, you will find information on how to <a href="https://docs.aspose.com/html/net/converting-between-formats/mhtml-to-image/#convert-mhtml-to-jpg-using-imagesaveoptions" target="_blank">Convert MHTML to JPG</a> using ConvertMHTML() methods and how to apply ImageSaveOptions or [ICreateStreamProvider](https://reference.aspose.com/html/net/aspose.html.io/icreatestreamprovider/) parameters.

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
title: Other Supported MHTML Conversions
subTitle: "You can also convert MHTML to many other file formats:"
---