---
translation: true
template: /templates/_template-conversion-child-java.md
title: Convert HTML to MD - Java Code and Online Converter
description: Sample Java code for HTML to MD conversion. Use this example code to convert HTML to MD within any Web or Desktop Java based application.
url: /java/conversion/html-to-md/
family: html
platformtag: java
feature: conversion
informat: HTML
outformat: MD
otherformats: XPS BMP GIF PNG TIFF JPG PDF
---

{{<section banner>}}
---
h1: Convert HTML to MD via Java
h2: High-fidelity conversion of HTML pages to Markdown file using server-side Java library or online.
---

{{<section overview>}}
---
h2: Convert HTML to MD Online
---

You can test the quality of HTML to MD conversion right in your browser! Please load an HTML file from the local file system, select the required output format from the list and run the example. You will immediately get the result as a separate file. It’s fast, easy, secure and completely free! 

{{<section demos>}}
---
h2: Convert HTML to MD Using Java
h3: HTML to MD Java Conversion Source Code
p: "In order to convert HTML to MD, we’ll use [Aspose.HTML for Java](https://products.aspose.com/html/{{lang.url-fragment}}java/) API which is a feature-rich, powerful and easy to use document manipulation and conversion API for Java platform. HTML conversions are often required to take advantage of other formats. You can transform HTML to MD programmatically with full control over a wide range of conversion parameters. Powerful Java library allows you to convert HTML to popular formats quickly and in high quality!"
---

```cs
// Load HTML document
HTMLDocument document = new HTMLDocument("document.html");

// Call convertHTML() method to convert HTML to Markdown.
com.aspose.html.converters.Converter.convertHTML(
        "document.html",
        new com.aspose.html.saving.MarkdownSaveOptions(),
        "output.md"
); 
```

{{<section steps>}}
---
h2: Steps to Convert HTML to MD via Java
---

If you would like to consider conversion functionality in your product or you want to convert HTML to MD programmatically, please see the Java code example above or learn the [Documentation chapters.](https://docs.aspose.com/html/java/converting-between-formats/) Developers can easily convert HTML file to Markdown in just a few lines of code:

1. Add a library reference to your Java project.
1.  Open an existing HTML file.
1.  Create a new MarkdownSaveOptions object.
1.  Call the convertHTML() method to convert HTML to MD.
1.  The MD file will be saved to the specified path.

{{<section online-converters>}}
---
h2: Free Online Converters
---

{{<section other-conversions>}}
---
title: Other Supported HTML Conversions
subTitle: "You can also convert HTML to many other file formats:"
---