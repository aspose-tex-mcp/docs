---
translation: true
template: /templates/_template-conversion-child-java.md
title: Convert MHTML to JPG - Java Code and Online Converter
description: Sample Java code for MHTML to JPG conversion. Use this example code to convert MHTML to JPG within any Web or Desktop Java based application
url: /java/conversion/mhtml-to-jpeg/
family: html
platformtag: java
feature: conversion
informat: MHTML
outformat: JPEG
otherformats: XPS BMP GIF PNG TIFF JPG PDF
---

{{<section banner>}}
---
h1: Convert MHTML to JPG via Java
h2: High-fidelity conversion of MHTML to JPG image format using server-side Java library or online.
---

{{<section overview>}}
---
h2: Convert MHTML to JPG Online
---

You can test the quality of MHTML to JPG conversion right in your browser! Please load an MHTML file from the local file system, select the required output format from the list and run the example. You will immediately get the result as a separate file. It’s fast, easy, secure and completely free! 

{{<section demos>}}
---
h2: Convert MHTML to JPG Using Java
h3: MHTML to JPG Java Conversion Source Code
p: "In order to convert MHTML to JPG, we’ll use [Aspose.HTML for Java](https://products.aspose.com/html/{{lang.url-fragment}}java/) API which is a feature-rich, powerful and easy to use document manipulation and conversion API for Java platform. MHTML conversions are often required to take advantage of other formats. You can transform MHTML to JPG programmatically with full control over a wide range of conversion parameters. Powerful Java library allows you to convert MHTML to popular formats quickly and in high quality!"
---

```cs
// Open an existing MHTML file for reading
try (java.io.FileInputStream fileInputStream = new java.io.FileInputStream("sample.mht")) {
    
    // Call the convertMHTML() method to convert the MHTML file to JPG image
    com.aspose.html.converters.Converter.convertMHTML(
            fileInputStream,
            new com.aspose.html.saving.ImageSaveOptions(
                    com.aspose.html.rendering.image.ImageFormat.Jpeg),
            "output.jpg"
    );
}
```

{{<section steps>}}
---
h2: Steps to Convert MHTML to JPG via Java
---

If you would like to consider conversion functionality in your product or you want to convert MHTML to JPG programmatically, please see the Java code example above or learn the [Documentation chapters.](https://docs.aspose.com/html/java/converting-between-formats/) Developers can easily convert MHTML file to JPG format in just a few lines of code:

1. Add a library reference to your Java project.
1. Open an existing MHTML file.
1. Create a new ImageSaveOptions object and specify ImageFormat.
1. Use the convertMHTML() method to convert MHTML document to a JPG image.

{{<section online-converters>}}
---
h2: Free Online Converters
---

{{<section other-conversions>}}
---
title: Other Supported MHTML Conversions
subTitle: "You can also convert MHTML to many other file formats:"
---