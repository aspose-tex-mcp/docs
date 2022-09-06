---
title: Convert TeX to TIFF | .NET 
description: TeX to TIFF conversion functionality. Integrate this on-premise .NET library into your project or use cross-platform applications to convert TeX to TIFF.
keywords: tex to tiff api net, tex2tiff integrate c#
url: /net/conversion/tex-to-tiff/
family: tex
platformtag: net
feature: conversion
informat: TEX
outformat: TIFF
otherformats: BMP PNG JPEG PDF SVG XPS
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true" >}}
{{< blocks/products/pf/agp/upper-banner-autogen h1=".NET Api Solution to convert TeX to TIFF." h2=" Integrate TeX to TIFF conversion functionality of On-premise .NET library into your own project.">}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="TEX to TIFF Conversion on .NET" %}}
1. Initialize [TeXOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/)
2. Specify the file system working directory for the output using [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/)
3. Initialize the options for saving in TIFF format using [TiffSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.image/)
4. Run TeX to TIFF conversion using [TeXJob](https://reference.aspose.com/tex/net/aspose.tex/texjob/) method
{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/feature-section-col title="Get Started with .NET TeX API" %}}
Install from command line as ```nuget install Aspose.TeX``` or via Package Manager Console of Visual Studio with ```Install-Package Aspose.TeX```.

Alternatively, get the offline MSI installer or DLLs in a ZIP file from [downloads](https://downloads.aspose.com/tex/net).
{{% /blocks/products/pf/agp/feature-section-col %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/agp/feature-section >}}
{{< app/tex/converter "C++ code example TeX to Images,XPS,PDF or SVG conversion" LTX TIFF BMP PNG JPEG>}}
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX);
options.OutputWorkingDirectory = new OutputFileSystemDirectory(RunExamples.OutputDirectory);
options.SaveOptions = new {{output camel}}SaveOptions();
new TeXJob(Path.Combine(RunExamples.InputDirectory, "{{inputFile}}"), new ImageDevice(), options).Run();
{{< /app/tex/converter >}}
{{< /blocks/products/pf/agp/feature-section>}}
{{< /blocks/products/pf/main-wrap-class>}}

{{< blocks/products/pf/agp/about-file-autogen >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Learning Resources" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Documentation" href="https://docs.aspose.com/tex/cpp" >}}
{{< blocks/products/pf/slr-element name="Source Code" href="https://github.com/aspose-tex/Aspose.TeX-for-C" >}}
{{< blocks/products/pf/slr-element name="API References" href="https://reference.aspose.com/tex/cpp" >}}
{{< blocks/products/pf/slr-element name="Tutorial Videos" href="https://www.youtube.com/user/asposevideo" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Product Support" tabId="support" >}}
{{< blocks/products/pf/slr-element name="Free Support" href="https://forum.aspose.com/c/tex" >}}
{{< blocks/products/pf/slr-element name="Paid Support" href="https://helpdesk.aspose.com/" >}}
{{< blocks/products/pf/slr-element name="Blog" href="https://blog.aspose.com/category/tex/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Why Aspose.TeX for C++?" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="Customers List" href="https://about.aspose.com/customers/" >}}
{{< blocks/products/pf/slr-element name="Success Stories" href="https://about.aspose.com/customers/success-stories/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< /blocks/products/pf/support-learning-resources >}}

{{< blocks/products/pf/agp/other-supported-autogen >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

