---
translation: true
template: /templates/_template-net.md
title: C# HTML Parser - .NET API for HTML files Processing 
weight: 20
url: /net/ 
description: C# .NET API to read, write, modify, edit, merge and convert HTML, XHTML, MHTML, EPUB, Markdown, and SVG.
---

{{<section banner>}}
---
h1: C# API to Parse HTML Files
h2: Class library for working with real-world HTML. Create, edit, extract data, merge and convert HTML pages to PDF, DOCX, XPS, Images and other formats.
---

{{<section overview>}}
---
item1: <a href="https://docs.aspose.com/html/net/working-with-documents/creating-a-document/" target="_blank">Create or load HTML-based documents</a> from a file, URL, string, or stream.
item2: <a href="https://docs.aspose.com/html/net/converting-between-formats/" target="_blank">Convert documents</a> between popular formats.
item3: <a href="https://docs.aspose.com/html/net/message-handlers/" target="_blank">Create custom message handlers</a> to do a specific task.
item4: <a href="https://docs.aspose.com/html/net/how-to-articles/how-to-use-xpath/" target="_blank">Navigate HTML documents</a> using XPath Query or CSS Selector. 
item5: <a href="https://docs.aspose.com/html/net/working-with-documents/editing-a-document/" target="_blank">Edit HTML files</a> by inserting new nodes, removing, or editing the content of existing nodes.
item6: <a href="https://docs.aspose.com/html/net/converting-between-formats/fine-tuning-converters/" target="_blank">Render documents</a> with high quality, 
item7: and more.
---

Aspose.HTML for .NET is an advanced HTML processing API to perform a wide range of management and manipulation tasks within cross-platform applications. API is designed to create, modify, extract data, convert and render HTML documents without any external software. Also, it supports popular file formats such as EPUB, MHTML, XML, SVG, and Markdown and rendering to PDF, DOCX, XPS and Image file formats. Aspose.HTML for .NET is written completely in C# and can be used to build any type of 32-bit or 64-bit .NET application including ASP.NET, WCF, WinForms & .NET Core. Moreover, the HTML Document Object Model is integrated with embedded formats and specifications such as CSS, HTML Canvas, SVG, XPath and JavaScript out-of-the-box that extend the manipulation functional and rendering quality.

{{<section documentation>}}
---
h2: API Features in Documentation
---

You can see the full list of Aspose.HTML features in our <a href="https://docs.aspose.com/html/net/getting-started/" target="_blank">documentation</a>. Using Aspose.HTML C# library in your project allows you to perform the following tasks:


{{<section glance>}}
---
h3: At a Glance
description: An overview of Aspose.HTML for .NET API.
---

{{<section platform>}}
---
h3: Platform Independence
description: Aspose.HTML for .NET supports the .NET framework & .NET Standard.
---

{{<section formats>}}
---
h3: Supported File Formats
description: Aspose.HTML for .NET [supported formats](https://docs.aspose.com/html/net/getting-started/supported-file-formats/) are listed below.
---

{{<section feature>}}
---
title: Advanced .NET HTML API Features
feature1: Create HTML pages from Scratch
feature2: Load existing HTML from file, stream or URL
feature3: Implement W3C specifications
feature4: Implement templates using template merger
feature5: Fill the template with various data sources
feature6: Render HTML Canvas 2D to PDF
feature7: <a href="/html/{{lang.url-fragment}}net/editor/">Add, replace or remove nodes</a>
feature8: <a href="/html/{{lang.url-fragment}}net/web-scraper/">Scrape data from HTML documents</a>
feature9: Load EPUB and MHTML file formats
feature10: <a href="/html/{{lang.url-fragment}}net/conversion/html-to-image/">Convert HTML to Image file formats</a>
feature11: Render multiple documents at once
feature12: <a href="/html/{{lang.url-fragment}}net/conversion/md-to-html/">Implement Markdown to HTML converter</a>
feature13: Apply header and footer during HTML to PDF conversion
feature14: <a href="/html/{{lang.url-fragment}}net/web-scraper/">Navigate HTML using XPath Query or CSS Selector</a>
feature15: <a href="/html/{{lang.url-fragment}}net/conversion/">Wide range of conversions between formats</a>
feature16: <a href="/html/{{lang.url-fragment}}net/generators/">Generate HTML Code</a>
feature17: <a href="/html/{{lang.url-fragment}}net/downloader/">Extract Data from the Web</a>
feature18: <a href="/html/{{lang.url-fragment}}net/merger/">Merge HTML, MHTML, EPUB, and MD files</a>
feature19: <a href="/html/{{lang.url-fragment}}net/editor/mhtml/">Edit MHTML</a>
feature20: <a href="/html/{{lang.url-fragment}}net/editor/md/">Edit Markdown</a>
---

{{<section converter>}}
---
h2: Convert HTML to PDF, Image and Other Formats in C#
h3: Convert HTML to PDF - C#
---
   
C# API allows with just a few lines of code to implement HTML to PDF, HTML to Image or any other conversion for your .NET applications. The conversion process is simple and reliable, thus making Aspose.HTML for .NET API a perfect choice.

{{<section "code" i18n-exclude>}}
     
using Aspose.HTML;
using Aspose.HTML.Saving;
using Aspose.HTML.Converters;
...
    
    // Load an HTML file to be converted
    using var document = new HTMLDocument("input.html")
    
    // Create an instance of the PdfSaveOptions class
    var pdfSaveOptions = new PdfSaveOptions();    
    
    // Convert HTML to PDF
    Converter.ConvertHTML(document, pdfSaveOptions, "output.pdf");
    

{{<section online-converters>}}

You can try online <a href="https://products.aspose.app/html/conversion/html" rel="opener noopener noreferrer" target="_blank">HTML Converter.</a>

{{<section other-converters>}}

You can also convert HTML, XHTML, MHTML, Markdown, EPUB, or SVG into many other file formats including few listed below:

{{<section merger>}}
---
h2: Merge HTML, MHTML, EPUB and MD files
---

Aspose.HTML for .NET API makes the files' merging process easier for developers: loads files using <a href="https://reference.aspose.com/html/net/aspose.html/htmldocument/" rel="noopener noreferrer" target="_blank">HTMLDocument</a> class; creates an instance of <a href="https://reference.aspose.com/html/net/aspose.html.rendering/renderer/" rel="noopener noreferrer" target="_blank">Renderer</a> and a required output device; uses the <a href="https://reference.aspose.com/html/net/aspose.html.rendering/renderer-1/" rel="noopener noreferrer" target="_blank">Render()</a> method to merge all HTML documents.
<br>
Moreover, you can merge files in real-time! Combine HTML, MHTML, Markdown, and EPUB, into PDF, XPS, DOCX, TIFF and many other file formats:

{{<section edit-html>}}
---
h2: Editing HTML Files
---

Aspose.HTML for .NET allows you to create and edit HTML documents using a Document Object Model (DOM). The DOM is a programming interface for HTML documents that represents the document (as nodes and objects) as a node tree, where each node represents part of the document. Aspose.HTML for .NET API lets you connect to the page and can change the document structure, style, and content. You can modify the document by inserting new nodes and removing or editing existing nodes' content.<br><br>
    
The .NET HTML API assists developers to read, modify, navigate and edit (X)HTML documents. Some file editing functions that the Aspose.HTML for .NET API can perform are the following:<br>
 - navigate HTML documents by using various methods, such as, element traversal, document traversal, XPath queries, and CSS selector queries,<br>
 - remove and replace HTML nodes,<br>
 - extract and edit CSS from HTML, <br>
 - configure a document sandbox and more.<br><br>

 You can easily edit documents, generate HTML code and scrape data from the Web online or programmatically using the following tools:

{{<section markdown>}}
---
h2: Markdown Support
h3: Convert HTML to Markdown - C#
h3-md: Convert Markdown to HTML - C#
---

Markdown is a markup language with a plain-text-formatting syntax. Markdown is often used as a format for documentation and readme files since it allows writing in an easy-to-read and easy-to-write style. Aspose.HTML provides a powerful and flexible Markdown Converter that can convert in both directions from Markdown to HTML and from HTML to Markdown. Moreover, the converter API has a set of predefined rules, so you can convert HTML to Markdown using the authentic Markdown syntax, GitLab Flavored Markdown modification or even configure the rules for your needs.

{{<section markdown-reverse>}}

The reverse conversion is that simple! Using the Aspose.HTML class library in your C# application, you can easily convert Markdown into an HTML file with just one line of code!

{{<section "code-markdown1" i18n-exclude>}}
     
using Aspose.Html;
using Aspose.HTML.Saving;
...
    
	// Load an HTML file
	using var document = new HTMLDocument("document.html");

	// Convert HTML to Markdown using a set of features supported by GitLab Flavored Markdown
	document.Save("output.md", MarkdownSaveOptions.Git);

{{<section "code-markdown2" i18n-exclude>}}
     
using Aspose.Html.Converters;
...	

	// Convert Markdown to HTML
	Converter.ConvertMarkdown("document.md", "output.html");

{{<section markdown-online>}}

Try online <a href="https://products.aspose.app/html/conversion/md" rel="opener noopener noreferrer" target="_blank">Markdown Converter!</a> You can convert Markdown to PDF, XPS, DOCX, JPG, PNG, BMP, TIFF, GIF, and MHTML. Upload, transform your documents and get results in a few seconds. You don't need any additional software.<br><br>

Aspose.HTML for .NET library provides Markdown parsing API for the C# platform. You can сreate, edit, save, merge, convert MD  files to other file formats, and add links, lists, code blocks, images and other elements into Markdown files by following the links:

{{<section epub-mhtml>}}
---
h2: Electronic Books and Web Archives
h3-epub: Convert EPUB to PDF - C#
h3-mhtml: Convert MHTML to PDF - C#
---

Aspose.HTML for .NET is capable of loading EPUB and MHTML files to perform various operations including the conversion to fixed-layout and raster image formats.


{{<section "code-epub" i18n-exclude>}}
     
using Aspose.Html.Converters;
using Aspose.Html.Saving;
...
    
	// Open an existing EPUB file for reading
     using var stream = File.OpenRead("input.epub");     
    
     // Create an instance of PdfSaveOptions
     var options = new PdfSaveOptions();
    
     // Call the ConvertEPUB method to convert EPUB to PDF
     Converter.ConvertEPUB(stream, options, "output.pdf"); 	 

{{<section "code-mhtml" i18n-exclude>}}
     
using Aspose.Html.Converters;
using Aspose.Html.Saving;
...   
	
	 // Open an existing MHTML file for reading
     using var stream = File.OpenRead("input.mht");     
    
     // Create an instance of PdfSaveOptions
     var options = new PdfSaveOptions();
    
     // Call the ConvertMHTML method to convert MHTML to PDF
     Converter.ConvertMHTML(stream, options, output.pdf); 

{{<section epub-mhtml-online>}}

You can try online <a href="https://products.aspose.app/html/conversion/mhtml" rel="opener noopener noreferrer" target="_blank">MHTML Converter</a> and online<a href="https://products.aspose.app/html/conversion/epub" rel="opener noopener noreferrer" target="_blank"> EPUB Converter.</a> Our browser-based converting tools work from all platforms, including Windows, Linux, Mac OS, Android and iOS. Converters are compatible with all PC devices, smartphones and tablets.

{{<section web-scraping>}}
---
h2: Web Scraping
h3: Simple Web Data Extraction - C#
---	
	
Web scraping, also well known as web harvesting, web data extraction or web crawling, is a technique to extract data from a website. Aspose.HTML doesn't support a Web Scraping module out-of-the-box. However, using Aspose.HTML API that is entirely based on W3C specification and supports XPath and CSS Selector queries you can easily inspect the content of any HTML document and create your own Web Scraping solution.<br><br>

Aspose.HTML for .NET offers you <a href="/html/{{lang.url-fragment}}net/web-scraper/">Web Scraper,</a> a free and easy-to-use tool that can navigate a website and extract data you need. We made web scraping quick and effective. Data extraction runs in your browser and does not require installing anything on your computer. Start data scraping now! 

{{<section "code-web-scraping" i18n-exclude>}}
     
using Aspose.Html;
...

    // Create an instance of the HTML document with a website as a parameter
    using var document = new Aspose.Html.HTMLDocument("https://en.wikipedia.org/wiki/Aspose_API");

    // Get all anchor-elements
    var elements = document.QuerySelectorAll("a");

    // Dump the anchor-element data to the console
    elements.Cast&lt;HTMLAnchorElement&gt;().ToList().ForEach(x =&gt;
        {
            System.Console.WriteLine("[Href]: " + x.Href);
            System.Console.WriteLine("[Content]: " + x.TextContent);
        });

{{<section online-web-scraping>}}

Aspose.HTML offers free online <a href="https://products.aspose.app/html/data-scrapers" rel="opener noopener noreferrer" target="_blank">Data Scrapers Apps</a> that are a way to get data from websites. Our Apps are safe, work on any platform and do not require any software installation. Data Scrapers can be used for image extracting, getting keywords from a webpage, etc. They are easy and clear to use, yet forceful and reliable.

{{<section other-aspose>}}
---
title: Other Supported Aspose.HTML for .NET API Features
subTitle: "Use the Aspose.HTML C# library to convert, merge, edit HTML documents, extract data from the web, and more!"
---

{{<section learning>}}
---
tabTitle: Learning Resources
name1: Documentation
name2: Source Code
name3: API References
---

{{<section support>}}
---
tabTitle: Product Support
name1: Free Support
name2: Paid Support
name3: Blog
name4: Release Notes
---

{{<section why>}}
---
tabTitle: Why Aspose.HTML for .NET?
name1: Customers List
name2: Success Stories
description: "Aspose.HTML offers individual HTML processing APIs for other popular development environments as listed below:"
---