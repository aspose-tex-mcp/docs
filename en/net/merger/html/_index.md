---
translation: true
template: /templates/_template-merger-child.md
title: Merge HTML Files - Online Merger and C# code
description: Merge HTML online or using C#. Use HTML Merger to combine multiple HTML files into one quickly, clearly and safely.
url: /net/merger/html/
family: html
platformtag: net
feature: merger
informat: HTML
tag: Html
outformat: PDF
otherformats: DOCX XPS TIFF MHTML
---

{{<section banner>}}
---
h1: Merge HTML Files online or via C#
h2: Use HTML Merger to combine multiple HTML files into one quickly, clearly and safely.
---

{{<section overview>}}
---
h2: How to Merge HTML Files?
---

[Aspose.HTML for .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) offers you tools to merge HTML files online or programmatically via C#. Online HTML Merger lets you merge multiple HTML files into a single document in real-time right in your browser. If you want to use merging and conversion functionalities in your product or to merge HTML programmatically, please [download Aspose.HTML C# library,](https://releases.aspose.com/html/net/) learn our [documentation](https://docs.aspose.com/html/net/converting-between-formats/fine-tuning-converters/#renderers) and consider the C# code examples. Powerful C# API allows you to merge HTML files quickly and in high quality.
 
{{<section demos>}}
---
h2: Online HTML Merger
---

Test the quality of HTML merging right in your browser! Please load HTML files from the local file system or a URL, select the required output format and run the example! It's fast, easy, secure and completely free! You will immediately get the result as a separate file. So, quickly merge HTML files and save the result to PDF, XPS, DOCX, TIFF or MHTML format online!

{{<section "app-pluging" i18n-exclude>}}

{{<app/merger HTML PDF XPS DOCX TIFF MHTML >}}
using (var document1 = new Aspose.Html.HTMLDocument("first-document.html"))
using (var document2 = new Aspose.Html.HTMLDocument("second-document.html"))
{
    // Create an instance of HTML Renderer
    using (var renderer = new Aspose.Html.Rendering.HtmlRenderer())
    {
        // Create an instance of PDF device
        using (var device = new Aspose.Html.Rendering.Pdf.PdfDevice("output.pdf"))
        {
            // Merge all HTML documents into PDF
            renderer.Render(device, document1, document2);
        }
    }
}
{{</app/merger>}}

{{<section steps>}}
---
h2: Steps to Merge HTML to PDF in C#
---

Aspose.HTML for .NET API provides the Renderer class for rendering and merging HTML documents. Using the Renderer instances directly, you can send multiple files to the output rendering device at once. Aspose.HTML API provides the following implementation of renderers: HtmlRenderer, SvgRenderer, MhtmlRenderer and EpubRenderer, which are used to render HTML, SVG, MHTML and EPUB documents, respectively.<br>
Please see the example above if you would like to merge HTML programmatically. You can merge HTML files with a few lines of C# code:

1. Load HTML documents using one of the [HTMLDocument()](https://reference.aspose.com/html/net/aspose.html/htmldocument/) constructors. You can load HTML from a file, HTML code, stream, or URL.
1. Create an instance of HTML [Renderer.](https://reference.aspose.com/html/net/aspose.html.rendering/renderer/) Use the [HtmlRenderer()](https://reference.aspose.com/html/net/aspose.html.rendering/htmlrenderer/htmlrenderer/) constructor.
1. In this step, you can choose a rendering device. API provides the following implementations: PdfDevice, XpsDevice, DocDevice and ImageDevice, which are used to generate PDF, XPS, DOCX and Image file formats, respectively.
1. If you want to merge HTML to PDF, create a PDF device. Use the [PdfDevice()](https://reference.aspose.com/html/net/aspose.html.rendering.pdf/pdfdevice/) constructor to initialise a new instance of the PdfDevice class. 
1. Call the [Render()](https://reference.aspose.com/html/net/aspose.html.rendering/renderer-1/) method to merge all HTML documents into PDF. 
1. Copy C# code for HTML files merging and use it in your project.

{{<section format>}}
---
h2: What is HTML File Format
---

{{<section get-started>}}
---
h2: How to Install Aspose.HTML for .NET library
---

{{<section other-mergers>}}
---
title: Other Supported Mergers
---