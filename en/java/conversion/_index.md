---
title: TeX (LaTeX) Files Conversion | Java
url: /java/conversion/
description: TeX(LaTeX) conversion Java API solution. Convert LaTeX files to PDF, XPS and Images including PNG, JPEG, TIFF, BMP with few lines of Java code.
keywords: tex conversion api java, tex converter java integrate
---

{{< blocks/products/pf/feature-page-wrap >}}
{{< blocks/products/pf/feature-page-header h1="TeX / LaTeX Files Conversion Via Java" h2="Convert TeX / LaTeX Files to XPS, SVG, PDF and Images to build cross-platform Java applications." >}}

{{% blocks/products/pf/feature-page-summary %}}


Aspose.TeX is an API to the Object TeX system, for detail of Tex file, here is the [Tex introduction](https://docs.aspose.com/tex/net/what-is-tex/). Developers can easily convert TeX to PDF, XPS, PNG, JPG, BMP and TIFF formats by integrating the API. Below are few code sample that programmers can enhance and integrate within TeX solutions.



{{% /blocks/products/pf/feature-page-summary  %}}

{{% blocks/products/pf/feature-page-section  h2="Convert TeX to Images or Pdf, Svg, Xps formats." %}}
To convert TeX files to Images, Pdf, Xps or Svg process next steps. 
1. Create instance of the [TeXOptions class](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions). 
2. Specify the file system working directory for the output/input using [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#setOutputWorkingDirectory-com.aspose.tex.IOutputWorkingDirectory-)  / [InputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#setInputWorkingDirectory-com.aspose.tex.IInputWorkingDirectory-) 
3. Initialize the options for saving using [BmpSaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/BmpSaveOptions), 
[PngSaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PngSaveOptions), 
[TiffSaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/TiffSaveOptions),
[JpegSaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/JpegSaveOptions)
 or [PDfSaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfSaveOptions), 
[SvgSaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/SvgSaveOptions), 
[XpsSaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/XpsSaveOptions), which is default, not need to set.
4. Run conversion using Rum method of [TeXJob](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob) for 
[ImageDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/ImageDevice) or
[PdfDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfDevice),
[SvgDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/SvgDevice),
[XpsDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/XpsDevice).
{{% /blocks/products/pf/feature-page-section %}}

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/agp/feature-section >}}
{{< app/tex/converter "C++ code example TeX to Images,XPS,PDF or SVG conversion" TeX PDF XPS SVG "JPEG|JPG" PNG TIFF BMP >}}
// Create conversion options for Object TeX format on Object TeX engine extension.
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectLaTeX());

// Specify the file system working directory for the output.
options.setOutputWorkingDirectory(new OutputFileSystemDirectory(Utils.getOutputDirectory()));

// Initialize the options for saving in {{output upper}} format.
// Use relevant image save options
options.setSaveOptions(new {{output camel}}SaveOptions());

// Run TeX to {{output upper}} conversion.
{{#if_output 'XPS' 'PDF' 'SVG'}}
new TeXJob(Utils.getInputDirectory() + "{{inputFile}}", new {{output camel}}Device(), options).run();
{{/if_output}}
{{#if_output 'BMP' 'JPEG' 'PNG' 'TIFF'}}
new TeXJob(Utils.getInputDirectory() + "{{inputFile}}", new ImageDevice(), options).run();
{{/if_output}}

{{< /app/tex/converter >}}
{{< /blocks/products/pf/agp/feature-section>}}
{{< /blocks/products/pf/main-wrap-class>}}

{{< blocks/products/pf/feature-page-options pairs="tex-to-pdf tex-to-xps tex-to-svg tex-to-png tex-to-bmp tex-to-tiff tex-to-jpeg latex-to-pdf latex-to-xps latex-to-svg latex-to-png latex-to-bmp latex-to-tiff latex-to-jpeg" >}}
