---
translation: true
template: /templates/_template-merger.md
title: Merge HTML, MHTML, Markdown, and EPUB Online or Using C#
url: /net/merger/
description: Merge HTML, EPUB, Markdown, and MHTML files with few lines of C# code via .NET library. Check online HTML Merger for free!
feature: merger
---

{{<section banner>}}
---
h1: Merge HTML, MHTML, EPUB and MD files Online or Via C# 
h2: Use Mergers to combine multiple files into one quickly, clearly and safely.
---

{{<section overview>}}
---
h2: How to Merge HTML Files Using C#
---

In order to merge HTML, MHTML, EPUB and MD files, we will use [Aspose.HTML for.NET API](https://products.aspose.com/html/{{lang.url-fragment}}net/) which is a feature-rich, powerful and easy-to-use document manipulation API for the C# platform. You can choose a kind of Merger for different source files such as HTML, MHTML, EPUB, or Markdown, and save the files merging result to one of the following output formats: PDF, MHTML, XPS, TIFF or DOCX.<br>
Aspose.HTML for.NET API makes the HTML merging process easier for developers: loads files using [HTMLDocument](https://reference.aspose.com/html/net/aspose.html/htmldocument/) class; creates an instance of HTML [Renderer](https://reference.aspose.com/html/net/aspose.html.rendering/renderer/) and a required output device; uses the [Render()](https://reference.aspose.com/html/net/aspose.html.rendering/renderer-1/) method to merge all HTML documents. 

{{<section demos>}}
---
h2: Online HTML Merger
---

You can merge HTML files with Aspose.HTML for .NET API in real-time. HTML Merger lets you combine multiple HTML documents into a single file. You can select one of the following output formats: PDF, MHTML, XPS, TIFF or DOCX. Load files, merge and get results in a few seconds!

{{<section "app-pluging" i18n-exclude>}}

{{<app/merger HTML PDF XPS DOCX TIFF MHTML >}}
// Load HTML files
using var document1 = new Aspose.Html.HTMLDocument("first-document.html");
using var document2 = new Aspose.Html.HTMLDocument("second-document.html");

// Create an instance of HTML Renderer
using var renderer = new Aspose.Html.Rendering.HtmlRenderer();

// Create an instance of PDF device
using var device = new Aspose.Html.Rendering.Pdf.PdfDevice("output.pdf");

// Merge all HTML documents into PDF
renderer.Render(device, document1, document2);
{{</app/merger>}}

{{<section installing>}}
---
h2: Installing Aspose.HTML for .NET library
---

Aspose.HTML is an advanced web scraping and HTML parsing library. This library supports parsing of HTML5, CSS3, SVG and HTML Canvas to construct a Document Object Model (DOM) based on the WHATWG DOM Standard. You can use several ways to install the Aspose.HTML library for .NET on your system:</br>

1. Using the NuGet Package Manager GUI.
2. Using the Package Manager Console.
3. Installing Aspose.HTML for .NET through MSI.</br>  

Use the Aspose.HTML C# library to convert, merge, edit HTML documents, extract data from the web, and more! For more details about C# library installation, please refer to [Aspose.HTML Documentation.](https://docs.aspose.com/html/net/getting-started/installation/)

{{<section other-aspose>}}
---
h2: Other Supported Aspose.HTML for .NET API Features
---

Using Aspose.HTML, an advanced web scraping and HTML parsing library, you can create, edit, navigate through nodes, extract data, merge and convert HTML, XHTML, MD, EPUB, and MHTML files to PDF, XPS, DOCX, Images and other formats.