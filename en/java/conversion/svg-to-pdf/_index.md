---
translation: true
template: /templates/_template-conversion-child-java.md
title: Convert SVG to PDF - Java Code and Online Converter
description: Sample Java code for SVG to PDF conversion. Use this example code to convert SVG to PDF within any Web or Desktop Java based application
url: /java/conversion/svg-to-pdf/
family: html
platformtag: java
feature: conversion
informat: SVG
outformat: PDF
otherformats: XPS BMP GIF PNG TIFF JPG
---

{{<section banner>}}
---
h1: Convert SVG to PDF via Java
h2: High-fidelity conversion of SVG to PDF format using server-side Java library or online.
---

{{<section overview>}}
---
h2: Convert SVG to PDF Online
---

You can test the quality of SVG to PDF conversion right in your browser! Please load an SVG file from the local file system, select the required output format from the list and run the example. You will immediately get the result as a separate file. It’s fast, easy, secure and completely free! 

{{<section demos>}}
---
h2: Convert SVG to PDF Using Java
h3: SVG to PDF Java Conversion Source Code
p: "In order to convert SVG to PDF, we’ll use [Aspose.HTML for Java](https://products.aspose.com/html/{{lang.url-fragment}}java/) API which is a feature-rich, powerful and easy to use document manipulation and conversion API for Java platform. SVG conversions are often required to take advantage of other formats. You can transform SVG to PDF programmatically with full control over a wide range of conversion parameters. Powerful Java library allows you to convert SVG to popular formats quickly and in high quality!"
---

```cs
// Initialize an SVG document from a file
com.aspose.html.dom.svg.SVGDocument document = new com.aspose.html.dom.svg.SVGDocument("document.svg");
try {
    // Initialize PdfSaveOptions
    com.aspose.html.saving.PdfSaveOptions options = new com.aspose.html.saving.PdfSaveOptions();

    // Convert SVG to PDF
    com.aspose.html.converters.Converter.convertSVG(
            document,
            options,
            "output.pdf"
    );
} finally {
    if (document != null) {
        document.dispose();
    }
}
```

{{<section steps>}}
---
h2: Steps to Convert SVG to PDF via Java
---

If you would like to consider conversion functionality in your product or you want to convert SVG to PDF programmatically, please see the Java code example above or learn the [Documentation chapters.](https://docs.aspose.com/html/java/converting-between-formats/) Developers can easily convert SVG file to PDF format in just a few lines of code:

1. Add a library reference to your Java project.
1. Load SVG file.
1. Create a new PdfSaveOptions object.
1. Use the convertSVG() method to convert SVG document to a PDF file.

{{<section online-converters>}}
---
h2: Free Online Converters
---

{{<section other-conversions>}}
---
title: Other Supported SVG Conversions
subTitle: "You can also convert SVG to many other file formats:"
---