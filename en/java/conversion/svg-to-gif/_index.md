---
translation: true
template: /templates/_template-conversion-child-java.md
title: Convert SVG to GIF - Java Code and Online Converter
description: Sample Java code for SVG to GIF conversion. Use this example code to convert SVG to GIF within any Web or Desktop Java based application
url: /java/conversion/svg-to-gif/
family: html
platformtag: java
feature: conversion
informat: SVG
outformat: GIF
otherformats: XPS BMP GIF PNG TIFF JPG
---

{{<section banner>}}
---
h1: Convert SVG to GIF via Java
h2: High-fidelity conversion of SVG to GIF image format using server-side Java library or online.
---

{{<section overview>}}
---
h2: Convert SVG to GIF Online
---

You can test the quality of SVG to GIF conversion right in your browser! Please load an SVG file from the local file system, select the required output format from the list and run the example. You will immediately get the result as a separate file. It’s fast, easy, secure and completely free! 

{{<section demos>}}
---
h2: Convert SVG to GIF Using Java
h3: SVG to GIF Java Conversion Source Code
p: "In order to convert SVG to GIF, we’ll use [Aspose.HTML for Java](https://products.aspose.com/html/{{lang.url-fragment}}java/) API which is a feature-rich, powerful and easy to use document manipulation and conversion API for Java platform. SVG conversions are often required to take advantage of other formats. You can transform SVG to GIF programmatically with full control over a wide range of conversion parameters. Powerful Java library allows you to convert SVG to popular formats quickly and in high quality!"
---

```cs
// Prepare SVG code and save it to a file
String code = "<svg xmlns='http://www.w3.org/2000/svg'>\n" +
              "<circle cx='50' cy='50' r='40' stroke='black' stroke-width='3' fill='red' />\n" +
              "</svg>\n";
try (java.io.FileWriter fileWriter = new java.io.FileWriter("document.svg")) {
    fileWriter.write(code);
}

// Initialize an SVG document from the file
com.aspose.html.dom.svg.SVGDocument document = new com.aspose.html.dom.svg.SVGDocument("document.svg");
try {
    // Initialize ImageSaveOptions
    com.aspose.html.saving.ImageSaveOptions options = new com.aspose.html.saving.ImageSaveOptions(com.aspose.html.rendering.image.ImageFormat.Gif);

    // Convert SVG to GIF
    com.aspose.html.converters.Converter.convertSVG(
            document,
            options,
            "output.gif"
    );
} finally {
    if (document != null) {
        document.dispose();
    }
}
```

{{<section steps>}}
---
h2: Steps to Convert SVG to GIF via Java
---

If you would like to consider conversion functionality in your product or you want to convert SVG to GIF programmatically, please see the Java code example above or learn the [Documentation chapters.](https://docs.aspose.com/html/java/converting-between-formats/) Developers can easily convert SVG file to GIF image in just a few lines of code:

1. Add a library reference to your Java project.
1. Initialize an SVG document from a file.
1. Create a new ImageSaveOptions object.
1. Use the convertSVG() method to convert SVG document to a GIF image file.

{{<section online-converters>}}
---
h2: Free Online Converters
---

{{<section other-conversions>}}
---
title: Other Supported SVG Conversions
subTitle: "You can also convert SVG to many other file formats:"
---