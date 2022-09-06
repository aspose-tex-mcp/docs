---
title: Convert LaTeX to TIFF | Java 
description: LaTeX to TIFF conversion functionality. Integrate this on-premise Java library into your project or use cross-platform applications to convert LaTeX to TIFF.
keywords: latex to tiff api java, latex2tiff integrate
url: /java/conversion/latex-to-tiff/
family: tex
platformtag: java
feature: conversion
informat: LATEX
outformat: TIFF
otherformats: BMP XPS PDF JPEG
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true" >}}
{{< blocks/products/pf/agp/upper-banner-autogen h1="Java Api Solution to convert LaTeX to TIFF." h2=" Integrate LaTeX to TIFF conversion functionality of On-premise Java library into your own project.">}}
{{< blocks/products/pf/main-container >}}

{{% blocks/products/pf/agp/content h2="How to Convert LATEX to TIFF Using Java" %}}

In order to render LATEX to TIFF, we’ll use <a href="https://products.aspose.com/tex/java">Aspose.TeX for Java</a> API which is a feature-rich, powerful and easy to use conversion API for Java platform. You can download its latest version directly from <a href="https://repository.aspose.com/webapp/#/artifacts/browse/tree/General/repo/com/aspose/aspose-tex">Maven</a> and install it within your Maven-based project by adding the following configurations to the pom.xml.

{{% blocks/products/pf/agp/code-block title="Repository" offSpacer="true" %}}

```cs
<repository>
    <id>snapshots</id>
    <name>repo</name>
    <url>http://repository.aspose.com/repo/</url>
</repository>
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/code-block title="Dependency" offSpacer="true" %}}

```cs
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-tex</artifactId>
    <version>21.4</version>
</dependency>
```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="LATEX to TIFF Conversion on Java" %}}
1. Initialize [TeXOptions](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions) to create conversion options for Object LaTeX format
2. In order to set space, or area, where the TeX output will be written, set system working directory for the output using [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--)
3. Initialize the options for saving in TIFF format using [TiffSaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/TiffSaveOptions)
4. Run LaTeX to TIFF conversion using [TeXJob](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob) method
{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/feature-section-col title="System Requirements" %}}
{{% blocks/products/pf/agp/text %}}
Aspose.TeX for Java is supported on all major operating systems. Just make sure that you have the following prerequisites.
{{% /blocks/products/pf/agp/text %}}
- J2SE 8.0 (1.8) or above.
{{% /blocks/products/pf/agp/feature-section-col %}}
{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/agp/feature-section >}}
{{< app/tex/converter "C++ code example TeX to Images,XPS,PDF or SVG conversion" LTX TIFF JPEG PNG BMP PDF XPS SVG >}}
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
{{< /blocks/products/pf/agp/feature-section >}}
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