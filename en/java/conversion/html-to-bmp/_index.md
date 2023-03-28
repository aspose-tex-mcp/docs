---
translation: true
template: /templates/_template-conversion-child-java.md
title: Convert HTML to BMP via Java
description: Sample Java code for HTML to BMP conversion. Use this example code to convert HTML to BMP within any Web or Desktop Java based application.
url: /java/conversion/html-to-bmp/
family: html
platformtag: java
feature: conversion
informat: HTML
outformat: BMP
otherformats: XPS BMP GIF PNG TIFF JPG PDF
---

{{<section banner>}}
---
h1: Convert HTML to BMP via Java
h2: High-fidelity conversion of HTML pages as BMP image using server-side Java library.
---

{{<section overview>}}
---
h2: Convert HTML to BMP Online
---

You can test the quality of HTML to BMP conversion right in your browser! Please load an HTML file from the local file system, select the required output format from the list and run the example. You will immediately get the result as a separate file. It’s fast, easy, secure and completely free! 

{{<section demos>}}
---
h2: Convert HTML to BMP Using Java
h3: HTML to BMP Java Conversion Source Code
p: "In order to convert HTML to BMP, we’ll use [Aspose.HTML for Java](https://products.aspose.com/html/{{lang.url-fragment}}java/) API which is a feature-rich, powerful and easy to use document manipulation and conversion API for Java platform. HTML conversions are often required to take advantage of other formats. You can transform HTML to BMP programmatically with full control over a wide range of conversion parameters. Powerful Java library allows you to convert HTML to popular formats quickly and in high quality!"
---

```cs
// Initialize an HTMLDocument from HTML file
HTMLDocument document = new HTMLDocument("document.html");

// Initialize ImageSaveOptions with BMP format
ImageSaveOptions options = new ImageSaveOptions(ImageFormat.Bmp);

// Convert HTML to BMP
Converter.convertHTML(document, options, "output.bmp"); 
```

{{<section steps>}}
---
h2: Steps to Convert HTML to BMP via Java
---

If you would like to consider conversion functionality in your product or you want to convert HTML to BMP programmatically, please see the Java code example above or learn the [Documentation chapters.](https://docs.aspose.com/html/java/converting-between-formats/) Developers can easily convert HTML file to BMP in just a few lines of code:

1.  Open an existing HTML file.
1.  Create a new ImageSaveOptions object.
1.  Call the convertHTML() method to convert HTML to BMP.
1.  The BMP file will be saved to the specified path.

{{<section online-converters>}}
---
h2: Free Online Converters
---

{{<section other-conversions>}}
---
title: Other Supported HTML Conversions
subTitle: "You can also convert HTML to many other file formats:"
---