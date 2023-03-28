---
translation: true
template: /templates/_template-conversion-child-java.md
title: Convert EPUB to XPS - Java Code and Online Converter
description: Sample Java code for EPUB to XPS conversion. Use this example code to convert EPUB to XPS within any Web or Desktop Java based application.
url: /java/conversion/epub-to-xps/
family: html
platformtag: java
feature: conversion
informat: EPUB
outformat: XPS
otherformats: PDF XPS BMP GIF PNG TIFF JPEG
---

{{<section banner>}}
---
h1: Convert EPUB to XPS via Java
h2: High-fidelity conversion of EPUB pages as XPS file using server-side Java library or online.
---

{{<section overview>}}
---
h2: Convert EPUB to XPS Online
---

You can test the quality of EPUB to XPS conversion right in your browser! Please load an EPUB file from the local file system, select the required output format from the list and run the example. You will immediately get the result as a separate file. It’s fast, easy, secure and completely free! 

{{<section demos>}}
---
h2: Convert EPUB to XPS Using Java
h3: EPUB to XPS Java Conversion Source Code
p: "In order to convert EPUB to XPS, we’ll use [Aspose.HTML for Java](https://products.aspose.com/html/{{lang.url-fragment}}java/) API which is a feature-rich, powerful and easy to use document manipulation and conversion API for Java platform. EPUB conversions are often required to take advantage of other formats. You can transform EPUB to XPS programmatically with full control over a wide range of conversion parameters. Powerful Java library allows you to convert EPUB to popular formats quickly and in high quality!"
---

```cs
// Open an existing EPUB file for reading
try (java.io.FileInputStream fileInputStream = new java.io.FileInputStream("input.epub")) {
    
    // Call the convertEPUB method to convert EPUB to XPS
    com.aspose.html.converters.Converter.convertEPUB(
            fileInputStream,
            new com.aspose.html.saving.XpsSaveOptions(),
            "output.xps"
    );
}
```

{{<section steps>}}
---
h2: Steps to Convert EPUB to XPS via Java
---

If you would like to consider conversion functionality in your product or you want to convert EPUB to XPS programmatically, please see the Java code example above or learn the [Documentation chapters.](https://docs.aspose.com/html/java/converting-between-formats/) Developers can easily convert HTML file to XPS in just a few lines of code:

1.  Open an existing EPUB file for reading.
1.  Create a new XpsSaveOptions object.
1.  Call the convertEPUB() method to convert the EPUB file to XPS.
1.  The XPS file will be saved to the specified path.

{{<section online-converters>}}
---
h2: Free Online Converters
---

{{<section other-conversions>}}
---
title: Other Supported EPUB Conversions
subTitle: "You can also convert EPUB to many other file formats:"
---