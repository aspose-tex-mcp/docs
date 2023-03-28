---
translation: true
template: /templates/_template-conversion-java.md
title: Convert HTML, XHTML, Markdown, MHTML, EPUB and SVG via Java
url: /java/conversion/
description: Convert HTML to PDF, XPS, Markdown, XHTML, MHTML and Images with few lines of code via Java library.
---

{{<section banner>}}
---
h1: HTML Conversion Via Java 
h2: Convert HTML to PDF, XPS and Images including JPG,BMP, PNG, TIFF to build cross-platform Java applications.
---

{{<section overview>}}
---
h2: How to Convert HTML Using Java Library
---

Whenever there is need of batch conversion of HTML files as well as web page from the live URL to other formats including PDF, XPS, Images and other formats, **Java HTML Parser API** is there to handle all such cases. API provides [HTMLDocument](https://reference.aspose.com/html/java/com.aspose.html/HTMLDocument) to load the document, save options classes such as [PdfSaveOptions](https://reference.aspose.com/html/java/com.aspose.html.saving/pdfsaveoptions), [ImageSaveOptions](https://reference.aspose.com/html/java/com.aspose.html.saving/package-frame) etc for target file specific settings and a [Converter class](https://reference.aspose.com/html/java/com.aspose.html/package-frame) for rendering to output file.

{{<section documentation>}}
---
article1: Convert HTML to PDF
article2: Convert HTML to XPS
article3: Convert HTML to DOCX
article4: Convert HTML to MHTML
article5: Convert HTML to Markdown
article6: Convert HTML to Image
---

The [Aspose.Html.Converters](https://reference.aspose.com/html/java/com.aspose.html.converters/package-frame) Package implements easy access to conversion methods. It provides a wide range of HTML conversions to popular formats, such as PDF, XPS, JPEG, PNG, BMP, TIFF, GIF, MHTML, and MD. Please visit the documentation chapter [Converting Between Formats](https://docs.aspose.com/html/java/converting-between-formats/) to learn more about Aspose.HTML for Java API conversion features.

{{<section conversion1>}}
---
h2: HTML to PDF Conversion
title: Java Code for HTML to PDF Conversion
---

For single or multiple HTML files to PDF conversion programmatically, process is, load the source HTML file using HtmlDocument class, for specific PDF settings such as page size, margins, file permissions, CSS media-type, etc use the PdfSaveOptions class and lastly call the ConvertHTML() method of Converter class having HTMLDocument, PdfSaveOptions, and output file path as parameters.

{{<section "code-pdf" i18n-exclude>}}

```cs
// Initialize an HTML document from html file
HTMLDocument htmltoPdf = new HTMLDocument("sourceFile.html");
try {
    // Initialize PdfSaveOptions
    PdfSaveOptions pdfOpts = new PdfSaveOptions();

    // Convert HTML to PDF
    Converter.convertHTML(
            htmltoPdf,
            pdfOpts,
            "output.pdf"
    );
} finally {
    if (htmltoPdf != null) {
        htmltoPdf.dispose();
    }
}
```
{{<section conversion2>}}
---
h2: Convert HTML to Images
title: Java Code for Converting HTML to Image Formats
---

**Java html parser API** built for reading, extracting and manipulating HTML data, can render HTML data to image formats easily. Create API [ImageSaveOptions](https://reference.aspose.com/html/java/com.aspose.html.saving/ImageSaveOptions) class object that provides methods for all specific settings like setCompression, setFormat, setHorizontalResolution, setSmoothingMode, setVerticalResolution etc. And finally use Converter.convertHTML method for conversion, having HTMLDocument object, image options and target image as parameters.

{{<section "code-image" i18n-exclude>}}

```cs
// Initialize an HTML document from a file
HTMLDocument htmltoImages = new HTMLDocument("document.html");
try {
    // Initialize ImageSaveOptions having image format and format can be Png, Jpeg, Bmp, Gif, Tiff
    ImageSaveOptions imgOptions = new ImageSaveOptions(ImageFormat.Png);

    // Convert HTML to PNG
    Converter.convertHTML(htmltoImages, imgOptions, "output.png");
} finally {
    if (htmltoImages != null) {
        htmltoImages.dispose();
    }
}
```

{{<section other-conversions>}}
---
h2: Other Supported Conversions
---

You can also convert HTML, XHTML, MHTML, EPUB, Markdown, and SVG files into many other file formats including few listed below: