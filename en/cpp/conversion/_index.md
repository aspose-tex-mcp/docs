---
title: TeX (LaTeX) Files Conversion | C++
url: /cpp/conversion/
keywords: tex converter cpp api, tex converter c++ api
description: TeX(LaTeX) conversion C++ API solution. Convert LaTeX files to PDF, XPS and Images including PNG, JPEG, TIFF, BMP with few lines of C++ code.
---

{{< blocks/products/pf/feature-page-wrap >}}
{{< blocks/products/pf/feature-page-header h1="LaTeX Files Conversion Via C++" h2="Convert LaTeX Files to XPS, PDF and Images to build cross-platform applications." >}}

{{% blocks/products/pf/feature-page-summary %}}


Aspose.TeX is an API to the Object TeX system, for detail of Tex file, here is the [Tex introduction](https://docs.aspose.com/tex/cpp/what-is-tex/). Developers can easily convert TeX to PDF, XPS, PNG, JPG, BMP and TIFF formats by integrating the API. Below are few code samples that programmers can enhance and integrate within LaTex solutions.



{{% /blocks/products/pf/feature-page-summary  %}}

{{% blocks/products/pf/feature-page-section  h2="Convert LaTeX to Images, XPS, PDF, SVG" %}}

To convert TeX files to Images, Pdf, Xps or Svg process next steps. 
1. Create instance of the [TeXOptions class](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options).
2. Specify the file system working directory for the output/input using [OutputWorkingDirectory](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options#aa4f4ea6dab7db5ba1b40800495f16f63)  / [InputWorkingDirectory](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options#aa4f4ea6dab7db5ba1b40800495f16f63)
3. Initialize the options for saving using [BmpSaveOptions](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.bmp_save_options),
[PngSaveOptions](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.png_save_options), 
[TiffSaveOptions](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.tiff_save_options),
[JpegSaveOptions](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.jpeg_save_options)
 or [PdfSaveOptions](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.pdf.pdf_save_options), 
[SvgSaveOptions](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.svg.svg_save_options), 
[XpsSaveOptions](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_save_options), which is default, not need to set.
4. Run conversion using Run method of [TeXJob](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_job) for 
[ImageDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.image_device) or
[PdfDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.pdf.pdf_device),
[SvgDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.svg.svg_device),
[XpsDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_device).

{{% /blocks/products/pf/feature-page-section %}}

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/agp/feature-section >}}
{{< app/tex/converter "C++ code example TeX to Images,XPS,PDF or SVG conversion" TeX PDF XPS SVG "JPEG|JPG" PNG TIFF BMP >}}
    // Create typesetting options for default ObjectTeX format on ObjectTeX engine extension.
    System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::ObjectTeX());

    // Specify a file system working directory for input and output.
    options->set_InputWorkingDirectory(System::MakeObject<InputFileSystemDirectory>(RunExamples::InputDirectory));
    options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));

    // Initialize the options for saving in {{output upper}} format. 
    // Similary use relevant Image options for other image formats
    options->set_SaveOptions(System::MakeObject<{{output camel}}SaveOptions>());

    // Specify memory stream as output terminal, if you don't terminal output to be written to console.
    //options->set_TerminalOut(System::MakeObject<OutputMemoryTerminal>());

    // Run typesetting.
{{#if_output 'XPS' 'PDF' 'SVG'}}
    System::MakeObject<Aspose::TeX::TeXJob>(u"{{inputFile}}", System::MakeObject<{{output camel}}Device>(), options)->Run();
{{/if_output}}
{{#if_output 'BMP' 'JPEG' 'PNG' 'TIFF'}}
    System::MakeObject<Aspose::TeX::TeXJob>(u"{{inputFile}}", System::MakeObject<ImageDevice>(), options)->Run();
{{/if_output}}
{{< /app/tex/converter >}}
{{< /blocks/products/pf/agp/feature-section>}}
{{< /blocks/products/pf/main-wrap-class>}}

{{< blocks/products/pf/feature-page-options pairs="tex-to-pdf tex-to-xps tex-to-svg tex-to-png tex-to-bmp tex-to-tiff tex-to-jpeg latex-to-pdf latex-to-xps latex-to-svg latex-to-png latex-to-bmp latex-to-tiff latex-to-jpeg" >}}
