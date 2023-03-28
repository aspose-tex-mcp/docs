---
translation: true
template: /templates/_template-merger-child.md
title: Merge EPUB Files - Online Merger and C# code
description: Merge EPUB files online or using C#. Use EPUB Merger to combine multiple EPUB files into one quickly, clearly and safely.
url: /net/merger/epub/
family: html
platformtag: net
feature: merger
informat: EPUB
tag: Epub
outformat: PDF
otherformats: DOCX XPS TIFF
---

{{<section banner>}}
---
h1: Merge EPUB Files online or via C#
h2: Use EPUB Merger to combine multiple EPUB files into one quickly, clearly and safely.
---

{{<section overview>}}
---
h2: How to Merge EPUB files?
---

[Aspose.HTML for .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) offers you tools to merge EPUB files online or programmatically via C#. Online EPUB Merger allows you to merge multiple EPUB files into a single document in real-time right in your browser. If you want to use merging and conversion functionalities in your product or to merge EPUB programmatically, please [download Aspose.HTML C# library,](https://releases.aspose.com/html/net/) learn our [documentation](https://docs.aspose.com/html/net/converting-between-formats/fine-tuning-converters/#renderers) and consider the C# code examples. Powerful C# API allows you to merge EPUB files quickly and in high quality.
 
{{<section demos>}}
---
h2: Online EPUB Merger
---

Test the quality of EPUB Merger right in your browser! Please load EPUB files from the local file system, select the required output format and run the example! It's fast, easy, secure and completely free! You will immediately get the result as a separate file. So, quickly merge EPUB files and save the result to PDF, XPS, DOCX, or TIFF format online!

{{<section "app-pluging" i18n-exclude>}}

{{<app/merger EPUB PDF DOCX XPS TIFF >}}
// Open an existing EPUB files for reading
using var stream1 = File.OpenRead(DataDir + "input1.epub");
using var stream2 = File.OpenRead(DataDir + "input2.epub");

// Create an instance of EPUB Renderer
using var renderer = new Aspose.Html.Rendering.EpubRenderer();

// Create an instance of PDF device
using var device = new Aspose.Html.Rendering.Pdf.PdfDevice("output-epub.pdf");
                
// Merge all EPUB documents into PDF
renderer.Render(device, stream1, stream2);
{{</app/merger>}}

{{<section steps>}}
---
h2: Steps to Merge EPUB to PDF in C#
---

Aspose.HTML for .NET API provides the Renderer class for rendering and merging EPUB documents. Using the Renderer instances directly, you can send multiple files to the output rendering device at once. Aspose.HTML API provides the following implementation of renderers: HtmlRenderer, SvgRenderer, MhtmlRenderer and EpubRenderer, which are used to render HTML, SVG, MHTML and EPUB documents, respectively.<br>
Please see the C# example above if you would like to merge EPUB fils programmatically:

1. Open an existing EPUB files.
1. Create an instance of EPUB [Renderer.](https://reference.aspose.com/html/net/aspose.html.rendering/renderer/) Use the [EpubRenderer()](https://reference.aspose.com/html/net/aspose.html.rendering/epubrenderer/) constructor.
1. In this step, you can choose a rendering device. API provides the following implementations: PdfDevice, XpsDevice, DocDevice and ImageDevice, which are used to generate PDF, XPS, DOCX and Image file formats, respectively.
1. If you want to merge EPUB to PDF, create a PDF device. Use the [PdfDevice()](https://reference.aspose.com/html/net/aspose.html.rendering.pdf/pdfdevice/) constructor to initialise a new instance of the PdfDevice class. 
1. Call the [Render()](https://reference.aspose.com/html/net/aspose.html.rendering/renderer-1/) method to merge all EPUB documents into PDF. 
1. Copy C# code for EPUB files merging and use it in your project.

{{<section format>}}
---
h2: What is EPUB File Format
---

{{<section get-started>}}
---
h2: How to Install Aspose.HTML for .NET library
---

{{<section other-mergers>}}
---
title: Other Supported Mergers
---