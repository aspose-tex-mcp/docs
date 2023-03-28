---
translation: true
template: /templates/_template-net-java.md
title:  Java HTML API - HTML and CSS Markup Parser and Translator
weight: 20
url: /java/ 
description: Read write modify parse translate and convert HTML, XHTML, MHTML, and EPUB file formats with Java library
---

{{<section banner>}}
---
h1: Java HTML Files Manipulation APIs
h2: Manipulate and Render HTML documents including CSS styles to PDF & Raster Image formats.
---

{{<section overview>}}
---
item1: Creating or opening an existing HTML document from different sources (Aspose.HTML.Examples.QuickStart.DocumentOpenTests in the examples project).
item2: "HTML Manipulation: creating, editing, removing and replacing HTML nodes via API."
item3: Saving HTML document.
item4: Extracting CSS styles for particular HTML node.
item5: Configuring a document sandbox that affects the processing of HTML documents.
item6: Navigation through an HTML document in different ways.
item7: "Converting HTML document into various supported formats: JPEG, PNG, BMP, TIFF, PDF, XPS, and more."
---

Aspose.HTML for Java is an advanced HTML manipulation API to manipulate and generate HTML within the Java applications. API allows to add, delete, replace nodes, extract CSS and navigate through a document via multiple ways. Moreover, API provides the capabilities to load EPUB and MHTML as well as offers the scripting which allows manipulating DOM via JavaScript.<br>
Aspose.HTML for Java supports inter-file format conversion to load HTML document and save the output in XPS, PDF and raster images including JPEG, PNG, BMP and more as well as provide encryption for PDF files.

{{<section documentation>}}
---
h2: API Features in Documentation
---

You can see the full list of Aspose.HTML features in our <a href="https://docs.aspose.com/html/java/getting-started/" target="_blank">documentation</a>. Using Aspose.HTML for Java library in your project allows you to perform the following tasks:


{{<section glance>}}
---
h3: At a Glance
description: An overview of API.
---

{{<section platform>}}
---
h3: Platform Independence
description: Aspose.HTML for Java supports Java 1.6, 1.7 and 1.8
---

{{<section formats>}}
---
h3: Supported File Formats
description: Aspose.HTML for Java [supported formats](https://docs.aspose.com/html/java/getting-started/supported-file-formats/) are listed below.
---

{{<section feature>}}
---
title: Advanced Java HTML Processing API Features
feature1: Create HTML pages from Scratch
feature2: Load existing file
feature3: Implement W3C specifications
feature4: Lightweight and standalone component
feature5: Insert, replace or delete nodes
feature6: Extract CSS styling information
feature7: Load EPUB and MHTML document formats
feature8: Render HTML to raster images
feature9: <a href="/html/{{lang.url-fragment}}java/conversion/">Convert HTML to PDF and XPS</a>
---

{{<section converter>}}
---
h2: Convert HTML to PDF and XPS Format
h3: Render HTML as fixed-layout formats - Java
---
   
API supports the rendering of HTML to most commonly used raster images including BMP, TIFF, JPEG, &amp; PNG, PDF, and XPS formats. Developers can customize by configuring PageSetup aspects for the resultant fixed-layout formats including page numbers to be rendered, resultant page size or setting the JPEG compression for the embedded images.

{{<section "code" i18n-exclude>}}
     
    // Load a file to be rendered
    HTMLDocument htmdoc = new HTMLDocument(dir + "template.html");

    // Render HTML to PDF & XPS
    HtmlRenderer renderer = new HtmlRenderer();

    renderer.render(new PdfDevice(new PdfRenderingOptions(), dir + "output.pdf"), htmdoc);
    renderer.render(new XpsDevice(new XpsRenderingOptions(), dir + "output.xps"), htmdoc);

{{<section online-converters>}}

You can try online <a href="https://products.aspose.app/html/conversion/html" rel="opener noopener noreferrer" target="_blank">HTML Converter.</a>

{{<section other-converters>}}

You can also convert HTML, XHTML, MHTML, Markdown, EPUB, or SVG into many other file formats including few listed below:

{{<section convert-image>}}
---
h2: Conversion to Raster Images
---

Aspose.HTML for Java offers the high fidelity rendering engine at its core which can convert HTML pages to most commonly used raster image formats including TIFF, BMP, PNG & JPEG without requiring any additional software or tool.

{{<section epub-mhtml>}}
---
h2: Manipulating EPUB and MHTML files
---

The library is capable of loading EPUB and MHTML files to perform various operations including the conversion to fixed-layout and raster image formats.

{{<section navigation>}}
---
h2: HTML Nodes Navigation
h3: Extract all nodes of type anchor - Java
---	
	
API supports navigation through the HTML file either by XPath,  elements or CSS selector queries and one can insert, extract, remove or replace nodes easily.

{{<section "code-navigation" i18n-exclude>}}
     
    // instance creation of HTMLDocument and loading HTML from URL
    HTMLDocument dct = new HTMLDocument("https://www.aspose.com");

    // get all anchor type nodes 
    NodeList nodelist = dct.getDocumentElement().querySelectorAll("a");

    // display anchor text &amp; href values for all nodes
    for (Node node : nodelist){

        HTMLAnchorElement anchor = (HTMLAnchorElement)node;
        System.out.println("Text: " + node.getTextContent() + " Href: " + anchor.getHref());
    }

{{<section sandbox>}}
---
h2: Configure Sandbox
---

The HTML API enables you to configure a document sandbox that affects the processing of HTML documents, that is; the CSS styles in some cases are dependent on screen size.

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
tabTitle: Why Aspose.HTML for Java?
name1: Customers List
name2: Success Stories
description: "Aspose.HTML offers individual HTML processing APIs for other popular development environments as listed below:"
---