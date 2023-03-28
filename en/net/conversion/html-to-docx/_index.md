---
translation: true
template: /templates/_template-conversion-child.md
title: Convert HTML to DOCX - Online Converter and C# code
description: Convert HTML to DOCX online or with C#. Use HTML to DOCX Converter to save webpage as DOCX file quickly, clearly and safely.
url: /net/conversion/html-to-docx/
family: html
platformtag: net
feature: conversion
informat: HTML
outformat: DOCX
otherformats: PDF XPS GIF JPEG PNG TIFF BMP XHTML MHTML MD 
---

{{<section banner>}}
---
h1: Convert HTML to DOCX online or via C#
h2: Convert web pages to DOCX files with high accuracy, quickly, clearly, and safely.
---

{{<section overview>}}
---
h2: Convert HTML to DOCX Using C#
---

DOCX file format is one of the most widely used and is available through numerous programs. The DOCX file is highly editable, easy to use and manageable in size. It can be viewed, edited, searched and printed with MS Word or other Word Viewer & Editor. With [Aspose.HTML for .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) API, you can transform HTML to DOCX programmatically with full control over a wide range of conversion parameters. There are various cases for HTML to DOCX conversion like reading from a file, URL, WYSISYG Editor, string, or stream. Powerful C# API allows you to convert HTML to popular formats quickly and in high quality!

{{<section demos>}}
---
h2:  Online HTML Converter
---

Test the quality of HTML to DOCX conversion right in your browser! Please load an HTML file from the local file system, select the required output format from the list and run the example. It's fast, easy, secure and completely free! The HTML to DOCX conversion will be done with the default save options. You will immediately get the result as a separate file. So, quickly convert any webpage or HTML to DOCX format online!

{{<section "app-pluging" i18n-exclude>}}

{{<app/converter HTML DOCX PDF MD "JPG|JPEG" GIF BMP XPS TIFF PNG MHTML >}}
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
h2: Steps to Convert HTML to DOCX in C#
---

If you would like to consider conversion functionality in your product or you want to convert HTML to DOCX programmatically, please see the C# code example above or learn the Documentation chapter. In all cases, any conversion requires some mandatory steps:

1.  Load an HTML document using one of [HTMLDocument()](https://reference.aspose.com/html/net/aspose.html/htmldocument/) constructors. You can load HTML from a file, HTML code, stream, or URL.
1.  Create a new [DocSaveOptions](https://reference.aspose.com/html/net/aspose.html.saving/docsaveoptions/) object.
1.  Use the [ConvertHTML()](https://reference.aspose.com/html/net/aspose.html.converters/converter/converthtml/) method of the Converter class to save HTML as a DOCX file. You need to pass the HTMLDocument, DocSaveOptions, and output file path to the ConvertHTML() method.
1.  The DOCX file will be saved to the specified path.

{{<section documentation>}}
---
h2: HTML to DOCX Conversion in Documentation
---

HTML to DOCX conversion is often required to take advantage of DOCX format for specific tasks. This format is popular because it supports a wide range of formatting features and offers users a variety of options to write any type of document. Please visit the documentation article [Convert HTML to DOCX](https://docs.aspose.com/html/net/converting-between-formats/html-to-docx/) to learn more about Aspose.HTML for .NET API conversion features and to consider C# examples for the most common HTML to DOCX conversion scenarios. In the article, you find information on how to convert HTML to DOCX using ConvertHTML() methods, and how to apply DocSaveOptions and ICreateStreamProvider parameters.

  -  <a href="https://docs.aspose.com/html/net/converting-between-formats/html-to-docx/#html-to-docx-by-a-single-line-of-code" target="_blank">Convert HTML to DOCX by a single line of code</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/html-to-docx/#convert-html-to-docx-in-c-using-docsaveoptions" target="_blank">Convert HTML to DOCX using DocSaveOptions</a>
  - <a href="https://docs.aspose.com/html/net/converting-between-formats/html-to-docx/#output-stream-providers" target="_blank">Convert HTML to DOCX using MemoryStreamProvider</a>

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