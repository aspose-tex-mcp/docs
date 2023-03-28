---
translation: true
template: /templates/_template-conversion-child-java.md
title: Convert HTML to XPS via Java
description: Sample Java code for HTML to XPS conversion. Use this example code to convert HTML to XPS within any Web or Desktop Java based application.
url: /java/conversion/html-to-xps/
family: html
platformtag: java
feature: conversion
informat: HTML
outformat: XPS
otherformats: XPS BMP GIF PNG TIFF JPG PDF
---

{{<section banner>}}
---
h1: Convert HTML to XPS via Java
h2: High-fidelity conversion of HTML pages as XPS file using server-side Java library or online.
---

{{<section overview>}}
---
h2: Convert HTML to XPS Online
---

You can test the quality of HTML to XPS conversion right in your browser! Please load an HTML file from the local file system, select the required output format from the list and run the example. You will immediately get the result as a separate file. It’s fast, easy, secure and completely free! 

{{<section demos>}}
---
h2: Convert HTML to XPS Using Java
h3: HTML to XPS Java Conversion Source Code
p: "In order to convert HTML to XPS, we’ll use [Aspose.HTML for Java](https://products.aspose.com/html/{{lang.url-fragment}}java/) API which is a feature-rich, powerful and easy to use document manipulation and conversion API for Java platform. HTML conversions are often required to take advantage of other formats. You can transform HTML to XPS programmatically with full control over a wide range of conversion parameters. Powerful Java library allows you to convert HTML to popular formats quickly and in high quality!"
---

```cs
// Initialize HTML document from a file
HTMLDocument htmltoxps = new HTMLDocument("document.html");
try {
    // Initialize XpsSaveOptions
    XpsSaveOptions xpsOptions = new XpsSaveOptions();

    // Convert HTML to XPS
    Converter.convertHTML(
            htmltoxps,
             xpsOptions,
            "output.xps"
    );
} finally {
    if (htmltoxps != null) {
        htmltoxps.dispose();
    }
}  
```

{{<section steps>}}
---
h2: Steps to Convert HTML to XPS via Java
---

If you would like to consider conversion functionality in your product or you want to convert HTML to XPS programmatically, please see the Java code example above or learn the [Documentation chapters.](https://docs.aspose.com/html/java/converting-between-formats/) Developers can easily convert HTML file to XPS in just a few lines of code:

1.  Add a library reference to your Java project.
1.  Open an existing HTML file.
1.  Create a new XpsSaveOptions object.
1.  Call the convertHTML() method to convert HTML to XPS.
1.  The XPS file will be saved to the specified path.

{{<section online-converters>}}
---
h2: Free Online Converters
---

{{<section other-conversions>}}
---
title: Other Supported HTML Conversions
subTitle: "You can also convert HTML to many other file formats:"
---