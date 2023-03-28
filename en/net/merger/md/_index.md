---
translation: true
template: /templates/_template-merger-child.md
title: Merge MD Files - Online Merger and C# code
description: Merge MD files online or using C#. Use Markdown Merger to combine multiple MD files into one quickly, clearly and safely.
url: /net/merger/md/
family: html
platformtag: net
feature: merger
informat: MD
tag: Html
outformat: PDF
otherformats: DOCX XPS TIFF
---

{{<section banner>}}
---
h1: Merge MD Files online or via C#
h2: Use Markdown Merger to combine multiple MD files into one quickly, clearly and safely.
---

{{<section overview>}}
---
h2: How to Merge MD Files?
---

[Aspose.HTML for .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) offers you tools to merge MD files online or programmatically via C#. Online Markdown Merger lets you merge multiple files into a single document in real-time right in your browser. If you want to use merging and conversion functionalities in your product or to merge MD documents programmatically, please [download Aspose.HTML C# library,](https://releases.aspose.com/html/net/) learn our [documentation](https://docs.aspose.com/html/net/converting-between-formats/fine-tuning-converters/#renderers) and consider the C# code examples. Powerful C# API allows you to merge MD files quickly and in high quality.
 
{{<section demos>}}
---
h2: Online Markdown Merger
---

Test the quality of MD files merging right in your browser! Please load files from the local file system, select the required output format and run the example! It's fast, easy, secure and completely free! You will immediately get the result as a separate file. So, quickly merge MD files and save the result to PDF, XPS, DOCX, or TIFF format online!

{{<section "app-pluging" i18n-exclude>}}

{{<app/merger MD PDF XPS DOCX TIFF >}}
// Prepare paths to source MD files
string sourcePath1 = Path.Combine(DataDir, "file1.md");
string sourcePath2 = Path.Combine(DataDir, "file2.md");            

// Convert Markdown to HTML
using var document1 = Aspose.Html.Converters.Converter.ConvertMarkdown(sourcePath1);
using var document2 = Aspose.Html.Converters.Converter.ConvertMarkdown(sourcePath2);

// Create an instance of HTML Renderer
using var renderer = new Aspose.Html.Rendering.HtmlRenderer();

// Create an instance of PDF device
using var device = new Aspose.Html.Rendering.Pdf.PdfDevice("output-md.pdf");

// Merge all HTML documents into PDF
renderer.Render(device, document1, document2);  

{{</app/merger>}}

{{<section steps>}}
---
h2: Steps to Merge MD to PDF in C#
---

Aspose.HTML for .NET API provides the Renderer class for rendering and merging Markdown documents. Using the Renderer instances directly, you can send multiple files to the output rendering device at once. Aspose.HTML API provides the following implementation of renderers: HtmlRenderer, SvgRenderer, MhtmlRenderer and EpubRenderer, which are used to render HTML, SVG, MHTML and EPUB documents, respectively.<br>
**Note:** Merging MD files goes through the stage of converting Markdown to HTML.
Please see the example above if you would like to merge MD documents programmatically. You can merge MD files with a few lines of C# code:

1. Convert Markdown to HTML files. Use the [ConvertMarkdown(`sourcePath`)](https://reference.aspose.com/html/net/aspose.html.converters/converter/convertmarkdown/#convertmarkdown_4) method to save Markdown as HTML documents. 
1. Create an instance of HTML [Renderer.](https://reference.aspose.com/html/net/aspose.html.rendering/renderer/) Use the [HtmlRenderer()](https://reference.aspose.com/html/net/aspose.html.rendering/htmlrenderer/htmlrenderer/) constructor.
1. In this step, you can choose a rendering device. API provides the following implementations: PdfDevice, XpsDevice, DocDevice and ImageDevice, which are used to generate PDF, XPS, DOCX and Image file formats, respectively.
1. If you want to merge HTML to PDF, create a PDF device. Use the [PdfDevice()](https://reference.aspose.com/html/net/aspose.html.rendering.pdf/pdfdevice/) constructor to initialise a new instance of the PdfDevice class. 
1. Call the [Render()](https://reference.aspose.com/html/net/aspose.html.rendering/renderer-1/) method to merge all HTML documents into PDF. 
1. Copy C# code for MD files merging and use it in your project.

{{<section format>}}
---
h2: What is MD File Format?
---

{{<section get-started>}}
---
h2: How to Install Aspose.HTML for .NET library
---

{{<section other-mergers>}}
---
title: Other Supported Mergers
---