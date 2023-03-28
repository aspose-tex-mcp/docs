---
translation: true
template: /templates/_template-conversion-child-java.md
title: Convert XHTML to PDF - Java Code and Online Converter
description: Sample Java code for XHTML to PDF conversion. Use this example code to convert XHTML to PDF within any Web or Desktop Java based application.
url: /java/conversion/xhtml-to-pdf/
family: html
platformtag: java
feature: conversion
informat: XHTML
outformat: PDF
otherformats: XPS BMP GIF PNG TIFF JPG
---

{{<section banner>}}
---
h1: Convert XHTML to PDF via Java
h2: High-fidelity conversion of XHTML pages to PDF file using server-side Java library or online.
---

{{<section overview>}}
---
h2: Convert XHTML to PDF Online
---

You can test the quality of XHTML to PDF conversion right in your browser! Please load an XHTML file from the local file system, select the required output format from the list and run the example. You will immediately get the result as a separate file. It’s fast, easy, secure and completely free! 

{{<section demos>}}
---
h2: Convert XHTML to PDF Using Java
h3: XHTML to PDF Java Conversion Source Code
p: "In order to convert XHTML to PDF, we’ll use [Aspose.HTML for Java](https://products.aspose.com/html/{{lang.url-fragment}}java/) API which is a feature-rich, powerful and easy to use document manipulation and conversion API for Java platform. XHTML conversions are often required to take advantage of other formats. You can transform XHTML to PDF programmatically with full control over a wide range of conversion parameters. Powerful Java library allows you to convert XHTML to popular formats quickly and in high quality!"
---

```cs
// Load XHTML document
HTMLDocument document = new HTMLDocument("template.xhtml");

// Convert XHTML to PDF
Converter.convertHTML(
    document,
    new PdfSaveOptions(),
    "output.pdf"
);   
```

{{<section steps>}}
---
h2: Steps to Convert XHTML to PDF via Java
---

If you would like to consider conversion functionality in your product or you want to convert XHTML to PDF programmatically, please see the Java code example above or learn the [Documentation chapters.](https://docs.aspose.com/html/java/converting-between-formats/) Developers can easily convert XHTML file to PDF format in just a few lines of code:

1.  Add a library reference to your Java project.
1.  Initialize an HTMLDocument from an XHTML file.
1.  Create a new PdfSaveOptions object.
1.  Call the convertHTML() method to convert XHTML to PDF.
1.  The PDF file will be saved to the specified path.

{{<section online-converters>}}
---
h2: Free Online Converters
---

{{<section other-conversions>}}
---
title: Other Supported XHTML Conversions
subTitle: "You can also convert XHTML to many other file formats:"
---