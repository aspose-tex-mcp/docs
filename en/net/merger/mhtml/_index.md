---
translation: true
template: /templates/_template-merger-child.md
title: Merge MHTML Files - Online Merger and C# code
description: Merge MHTML files online or using C#. Use MHTML Merger to combine multiple MHTML files into one quickly, clearly and safely.
url: /net/merger/mhtml/
family: html
platformtag: net
feature: merger
informat: MHTML
tag: Mhtml
outformat: PDF
otherformats: DOCX XPS TIFF
---

{{<section banner>}}
---
h1: Merge MHTML Files online or via C#
h2: Use MHTML Merger to combine multiple MHTML files into one quickly, clearly and safely.
---

{{<section overview>}}
---
h2: How to Merge MHTML Files?
---

[Aspose.HTML for .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) offers you tools to merge MHTML files online or programmatically via C#. Online MHTML Merger lets you merge multiple files into a single document in real-time right in your browser. If you want to use merging and conversion functionalities in your product or to merge MHTML programmatically, please [download Aspose.HTML C# library,](https://releases.aspose.com/html/net/) learn our [documentation](https://docs.aspose.com/html/net/converting-between-formats/fine-tuning-converters/#renderers) and consider the C# code examples. Powerful C# API allows you to merge MHTML files quickly and in high quality.
 
{{<section demos>}}
---
h2: Online MHTML Merger
---

Test the quality of MHTML merging right in your browser! Please load files from the local file system, select the required output format and run the example! It's fast, easy, secure and completely free! You will immediately get the result as a separate file. So, quickly merge MHTML files and save the result to PDF, XPS, DOCX, or TIFF  format online!

{{<section "app-pluging" i18n-exclude>}}

{{<app/merger MHTML PDF XPS TIFF DOCX >}}
// Open existing MHTML files for reading
using var stream1 = File.OpenRead(DataDir + "document1.mht");            
using var stream2 = File.OpenRead(DataDir + "document2.mht");

// Create an instance of MHTML Renderer
using var renderer = new Aspose.Html.Rendering.MhtmlRenderer();

// Create an instance of PDF device
using var device = new Aspose.Html.Rendering.Pdf.PdfDevice("output-mht.pdf");

// Merge all MHTML documents into PDF
renderer.Render(device, stream1, stream2);
{{</app/merger>}}

{{<section steps>}}
---
h2: Steps to Merge MHTML to PDF in C#
---

Aspose.HTML for .NET API provides the Renderer class for rendering and merging MHTML documents. Using the Renderer instances directly, you can send multiple files to the output rendering device at once. Aspose.HTML API provides the following implementation of renderers: HtmlRenderer, SvgRenderer, MhtmlRenderer and EpubRenderer, which are used to render HTML, SVG, MHTML and EPUB documents, respectively.<br>
Please see the example above if you would like to merge MHTML files programmatically. You can merge documents with a few lines of C# code:

1. Open an existing MHTML files.
1. Create an instance of MHTML [Renderer.](https://reference.aspose.com/html/net/aspose.html.rendering/renderer/) Use the [MhtmlRenderer()](https://reference.aspose.com/html/net/aspose.html.rendering/mhtmlrenderer/mhtmlrenderer/) constructor.
1. In this step, you can choose a rendering device. API provides the following implementations: PdfDevice, XpsDevice, DocDevice and ImageDevice, which are used to generate PDF, XPS, DOCX and Image file formats, respectively.
1. If you want to merge MHTML to PDF, create a PDF device. Use the [PdfDevice()](https://reference.aspose.com/html/net/aspose.html.rendering.pdf/pdfdevice/) constructor to initialise a new instance of the PdfDevice class. 
1. Call the [Render()](https://reference.aspose.com/html/net/aspose.html.rendering/renderer-1/) method to merge all MHTML documents into PDF. 
1. Copy C# code for MHTML files merging and use it in your project.

{{<section format>}}
---
h2: What is MHTML File Format
---

{{<section get-started>}}
---
h2: How to Install Aspose.HTML for .NET library
---

{{<section other-mergers>}}
---
title: Other Supported Mergers
---