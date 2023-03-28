---
translation: true
template: /templates/_template-conversion-child-java.md
title: Convert MD to HTML - Java Code and Online Converter
description: Sample Java code for MD to HTML conversion. Use this example code to convert MD to HTML within any Web or Desktop Java based application.
url: /java/conversion/md-to-html/
family: html
platformtag: java
feature: conversion
informat: MD
outformat: HTML
otherformats: XPS BMP GIF PNG TIFF JPG MHTML
---

{{<section banner>}}
---
h1: Convert MD to HTML via Java
h2: High-fidelity conversion of MD to HTML format using server-side Java library or online.
---

{{<section overview>}}
---
h2: Convert MD to HTML Online
---

You can test the quality of MD to HTML conversion right in your browser! Please load an MD file from the local file system, select the required output format from the list and run the example. You will immediately get the result as a separate file. It’s fast, easy, secure and completely free! 

{{<section demos>}}
---
h2: Convert MD to HTML Using Java
h3: MD to HTML Java Conversion Source Code
p: "In order to convert MD to HTML, we’ll use [Aspose.HTML for Java](https://products.aspose.com/html/{{lang.url-fragment}}java/) API which is a feature-rich, powerful and easy to use document manipulation and conversion API for Java platform. Markdown conversions are often required to take advantage of other formats. You can transform MD to HTML programmatically with full control over a wide range of conversion parameters. Powerful Java library allows you to convert Markdown to popular formats quickly and in high quality!"
---

```cs
// Prepare a simple Markdown example
String code = "### Hello World\n" +
              "\r\n\n" +
              "\n" +
              "[visit applications](https://products.aspose.app/html/family)\n";
// Create a Markdown file
try (java.io.FileWriter fileWriter = new java.io.FileWriter("document.md")) {
    fileWriter.write(code);
}

// Convert Markdown to HTML document
com.aspose.html.converters.Converter.convertMarkdown(
        "document.md",
        "document.html"
);
```

{{<section steps>}}
---
h2: Steps to Convert MD to HTML via Java
---

If you would like to consider conversion functionality in your product or you want to convert MD to HTML programmatically, please see the Java code example above or learn the [Documentation chapters.](https://docs.aspose.com/html/java/converting-between-formats/) Developers can easily convert Markdown file to HTML format in just a few lines of code:

1. Add a library reference to your Java project.
1. Create or initialize a source Markdown file.
1. Convert Markdown to HTML. Use the convertMarkdown() method to save Markdown as an HTML document.

{{<section online-converters>}}
---
h2: Free Online Converters
---

{{<section other-conversions>}}
---
title: Other Supported MD Conversions
subTitle: "You can also convert Markdown to many other file formats:"
---