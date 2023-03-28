---
translation: true
template: /templates/_template-conversion.md
title: Convert HTML, XHTML, Markdown, MHTML, EPUB and SVG Online or Using C#
url: /net/conversion/
description: Convert HTML to PDF, DOCX, XPS, Markdown, XHTML, MHTML and Images with few lines of C# code via .NET library. Check online HTML Converter for free!
---

{{<section banner>}}
---
h1: HTML Conversion online or via C# 
h2: Convert hypertext markup language HTML to PDF, XHTML, MHTML, Markdown, XPS, DOCX and Images including BMP, JPG, PNG, TIFF to build cross-platform .NET applications
---

{{<section overview>}}
---
h2: How to Convert HTML Using C#
---

Hypertext markup language HTML is the language of the Web. Currently, most information is present on websites in form of webpages. So converting this HTML-based information into other formats like PDF, XPS, Microsoft® Word, Markdown and image formats is a common scenario. [.NET HTML API](https://products.aspose.com/html/net/) makes the conversion process easier for developers. It loads the file using HTMLDocument class, creates the relevant save options object and uses the [Converter class](https://reference.aspose.com/html/net/aspose.html.converters/converter/) relevant conversion method.</br></br> 
Any conversion you want to perform involves loading an HTML document and saving it in the supported format. It can be different scenarios, but it can be made with a few required steps:</br>
 1. Load an HTML document into a Document object using one of [HTMLDocument()](https://reference.aspose.com/html/net/aspose.html/htmldocument/) constructors. You can load HTML from a file, HTML code, stream, or URL.
 2. Create a Save Options object.
 3. Invoke one of the [ConvertHTML()](https://reference.aspose.com/html/net/aspose.html.converters/converter/converthtml/) methods and pass the required parameters to it.

{{<section demos>}}
---
h2: Online HTML Converter
---

You can convert HTML with Aspose.HTML for .NET API in real-time. The following C# example demonstrates how to convert an HTML document. Please load a file from the local file system, select the output format and run the example. You will immediately get the result. You can try Free Online Converters <a href="https://products.aspose.app/html/conversion/html" rel="opener noopener noreferrer" target="_blank">here.</a>

{{<section "app-pluging" i18n-exclude>}}

{{<app/converter HTML PDF DOCX MD BMP "JPG|JPEG" PNG GIF TIFF XPS>}}
using Aspose.Html;
using Aspose.Html.Converters;
using Aspose.Html.Saving;

    using var document = new HTMLDocument("input.{{input lower}}");
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
{{#if_output 'BMP' 'JPG' 'GIF' 'PNG' 'TIFF'}}
    var options = new ImageSaveOptions(ImageFormat.{{output camel}});
{{/if_output}}
    Converter.ConvertHTML(document, options, "output.{{output lower}}");
{{</app/converter>}}

{{<section documentation>}}
---
h2: 
article1: Convert HTML to PDF
article2: Convert HTML to XPS
article3: Convert HTML to DOCX
article4: Convert HTML to MHTML
article5: Convert HTML to Markdown
article6: Convert HTML to BMP
article7: Convert HTML to PNG
article8: Convert HTML to JPG
article9: Convert HTML to TIFF
---

The main highlight of Aspose.HTML .NET API is a conversion feature. Converting between formats is required for various reasons: to work in a familiar, convenient format or to take advantage of different formats for specific tasks. The [Aspose.Html.Converters](https://reference.aspose.com/html/net/aspose.html.converters/) namespace implements easy access to conversion methods. It provides a wide range of HTML conversions to popular formats, such as PDF, XPS, DOCX, JPEG, PNG, BMP, TIFF, GIF, MHTML, and MD. Please visit the documentation chapter [Converting Between Formats](https://docs.aspose.com/html/net/converting-between-formats/) to learn more about Aspose.HTML for .NET API conversion features.

{{<section installing>}}
---
h2: Installing Aspose.HTML for .NET library
---

This library supports parsing of HTML5, CSS3, SVG and HTML Canvas to construct a Document Object Model (DOM) based on the WHATWG DOM Standard. You can use several ways to install the Aspose.HTML library for .NET on your system:</br>

1. Using the NuGet Package Manager GUI.
2. Using the Package Manager Console.
3. Installing Aspose.HTML for .NET through MSI.</br>  

For more details about C# library installation, please refer to [Aspose.HTML Documentation](https://docs.aspose.com/html/net/getting-started/installation/).

{{<section other-conversions>}}
---
h2: Other Supported Conversions
---

You can also convert HTML, XHTML, MHTML, EPUB, Markdown, and SVG files into many other file formats including few listed below: