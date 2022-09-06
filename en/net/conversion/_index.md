---
title: TeX (LaTeX) Files Conversion | .NET
url: /net/conversion/
description: TeX and LaTeX conversion functionality. Convert TeX / LaTeX files to PDF, SVG, XPS, and image formats including PNG, JPEG, TIFF, and BMP using this .NET API solution.
keywords: tex conversion api c#, tex converter c# integrate
---

{{< blocks/products/pf/feature-page-wrap >}}
{{< blocks/products/pf/feature-page-header h1="TeX / LaTeX Files Conversion Via C#" h2="Convert TeX / LaTeX Files to XPS, SVG, PDF and Images to build cross-platform .NET applications." >}}

{{% blocks/products/pf/feature-page-summary %}}


Aspose.TeX is an API to the Object TeX system, for detail of Tex file, here is the [Tex introduction](https://docs.aspose.com/tex/net/what-is-tex/). Developers can easily convert TeX to PDF, XPS, PNG, JPG, BMP and TIFF formats by integrating the API. Below are few code sample that programmers can enhance and integrate within TeX solutions.



{{% /blocks/products/pf/feature-page-summary  %}}

{{% blocks/products/pf/feature-page-section  h2="Convert TeX to Images or Pdf, Svg, Xps formats." %}}
To convert TeX files to Images, Pdf, Xps or Svg process next steps. 
1. Create instance of the [TeXOptions class](https://reference.aspose.com/tex/net/aspose.tex/texoptions/). 
2. Specify the file system working directory for the output/input using [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) / [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/inputworkingdirectory/) 
3. Initialize the options for saving using [BmpSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.image/bmpsaveoptions/), 
[PngSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.image/pngsaveoptions/), 
[TiffSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.image/tiffsaveoptions/),
[JpegSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.image/jpegsaveoptions/)
 or [PDfSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/), 
[SvgSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.svg/svgsaveoptions/), 
[XpsSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpssaveoptions/), which is default, not need to set.
4. Run conversion using [TeXJob](https://reference.aspose.com/tex/net/aspose.tex/texjob/) method for 
[ImageDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.image/imagedevice/) or
[PdfDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/),
[SvgDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.svg/svgdevice/),
[XpsDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/).

{{% /blocks/products/pf/feature-page-section %}}

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/agp/feature-section >}}
{{< app/tex/converter "C++ code example TeX to Images,XPS,PDF or SVG conversion" TeX PDF XPS SVG "JPEG|JPG" PNG TIFF BMP >}}
// Create conversion options for Object TeX format on Object TeX engine extension.
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX);

// Specify the file system working directory for the output.
options.OutputWorkingDirectory = new OutputFileSystemDirectory(RunExamples.OutputDirectory);

// Initialize the options for saving in {{output upper}} format.
options.SaveOptions = new {{output camel}}SaveOptions();

// Run TeX to {{output upper}} conversion.
{{#if_output 'XPS' 'PDF' 'SVG'}}
new TeXJob(Path.Combine(RunExamples.InputDirectory, "{{inputFile}}"), new {{output camel}}Device(), options).Run();
{{/if_output}}
{{#if_output 'BMP' 'JPEG' 'PNG' 'TIFF'}}
new TeXJob(Path.Combine(RunExamples.InputDirectory, "{{inputFile}}"), new ImageDevice(), options).Run();
{{/if_output}}
{{< /app/tex/converter >}}
{{< /blocks/products/pf/agp/feature-section>}}
{{< /blocks/products/pf/main-wrap-class>}}

{{< blocks/products/pf/feature-page-options pairs="tex-to-pdf tex-to-xps tex-to-svg tex-to-png tex-to-bmp tex-to-tiff tex-to-jpeg latex-to-pdf latex-to-xps latex-to-svg latex-to-png latex-to-bmp latex-to-tiff latex-to-jpeg" >}}
