---
translation: true
template: /templates/_template-conversion-child.md
title: Convert XHTML to DOCX
description: Convert XHTML to DOCX in C#. Save XHTML as DOCX file using C# code. Try online XHTML to DOCX Converter for free!
url: /net/conversion/xhtml-to-docx/
family: html
platformtag: net
feature: conversion
informat: XHTML
outformat: DOCX
otherformats: PDF XPS GIF JPEG PNG TIFF BMP HTML MHTML MD
howto: howtoXhtml
---

{{<section banner>}}
---
h1: Convert XHTML to DOCX online or via C#
h2: Generate DOCX from XHTML source page using .NET API. Instantly convert XHTML to DOCX format with our free online converter!
---

{{<section overview>}}
---
h2: Convert XHTML to DOCX Using C#
---

DOCX file format is one of the most widely used and is available through numerous programs. The DOCX file is highly editable, easy to use and manageable in size. It can be viewed, edited, searched and printed with MS Word or other Word Viewer & Editor. With [Aspose.HTML .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) API, you can convert XHTML to DOCX programmatically with full control over conversion parameters. Any conversion you want to perform involves loading an XHTML document and saving it in the supported format. Powerful C# API allows you to convert XHTML to DOCX quickly and in high quality!

{{<section demos>}}
---
h2: Free Online XHTML Converter
---

Test the quality of XHTML to DOCX conversion right in your browser! Please load an XHTML file from the local file system, select the required output format from the list and run the example. It's fast, easy, secure and completely free! The XHTML to DOCX conversion will be done with the default save options. You will immediately get the result as a separate file. So, quickly convert any webpage or XHTML to DOCX format online!

{{<section "app-pluging" i18n-exclude>}}

{{<app/converter XHTML DOCX BMP TIFF PNG "JPG|JPEG" GIF PDF XPS MD MHTML>}}
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
h2: Steps to Convert XHTML to DOCX in C#
---

If you want to convert XHTML to DOCX programmatically, please see the C# code example above or learn the Documentation chapter. In all cases, any XHTML conversion requires some mandatory steps:

1.  Load an XHTML file using one of HTMLDocument() constructors of the [HTMLDocument](https://reference.aspose.com/html/net/aspose.html/htmldocument/) class.
1.  Create a new [DocSaveOptions](https://reference.aspose.com/html/net/aspose.html.saving/docsaveoptions/) object.
1.  Use the [ConvertHTML()](https://reference.aspose.com/html/net/aspose.html.converters/converter/converthtml/) method of the Converter class to save XHTML as a DOCX file.
1.  The DOCX file will be saved to the specified path.

{{<section documentation>}}
---
h2: (X)HTML Conversion in Documentation
---

XHTML to DOCX conversion is often required to take advantage of DOCX format for specific tasks. DOCX format is popular because it supports a wide range of formatting features and offers users a variety of options to write any type of document. Aspose.HTML for .NET API allows you to convert (X)HTML to other popular formats quickly and with high quality. Please visit the documentation chapter <a href="https://docs.aspose.com/html/net/converting-between-formats/" target="_blank">Converting Between Formats</a> to learn more about the API conversion features. The chapter describes popular converters, as well as C# examples for the most common conversion scenarios.

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