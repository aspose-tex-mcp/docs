---
template: true
title: {{i18n.title}}
description: {{i18n.description}}
url: {{i18n.url}}
family: tex
platformtag: cpp
feature: conversion
---

{{<meta path="/{{lang}}/meta/conversion/default.md" section="faq">}}

{{< blocks/products/pf/main-wrap-class isAutogenPage="true" >}}
{{< blocks/products/pf/agp/upper-banner-autogen h1="{{i18n.banner.h1}}" h2="{{i18n.banner.h2}}">}}

{{< blocks/products/pf/main-container pfName="Aspose.TeX" subTitlepfName="for C++" >}}

{{< blocks/products/pf/sub-menu logoImageSrc="https://www.aspose.cloud/templates/aspose/img/products/tex/aspose_tex-for-cpp.svg" liveDemosLink="https://products.aspose.app/tex/applications" PricingLink="https://purchase.aspose.com/pricing/tex/cpp" buyLink="https://purchase.aspose.com/buy" docsLink="https://docs.aspose.com/tex/cpp/" installationsDocsLink="https://docs.aspose.com/tex/cpp/installation/" nugetLink="https://www.nuget.org/packages/Aspose.TeX/" nugetPackageName="Aspose.TeX" mavenRepoLink="" directDownloadLink="https://releases.aspose.com/tex/cpp/" >}}

{{% blocks/products/pf/agp/content %}}
{{i18n.overview.p1}}

{{i18n.overview.p2}}
{{% /blocks/products/pf/agp/content %}}


{{% blocks/products/pf/feature-page-section  h2="{{i18n.feature1.title}}" %}}

<p>{{i18n.feature1.item1}}</p>

1. {{i18n.feature1.item2}}
2. {{i18n.feature1.item3}}
3. {{i18n.feature1.item4}}
4. {{i18n.feature1.item5}}
5. {{i18n.feature1.item6}}

<p>{{i18n.feature1.item7}}</p>

-  {{i18n.feature1.item8}}
-  {{i18n.feature1.item9}}
-  {{i18n.feature1.item10}}
-  {{i18n.feature1.item11}}

{{% /blocks/products/pf/feature-page-section %}}

{{< blocks/products/pf/agp/feature-section >}}
{{< app/tex/converter "{{i18n.feature1.h3}}" TeX PDF XPS SVG "JPEG|JPG" PNG TIFF BMP >}}
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

{{< blocks/products/pf/feature-page-options pairs="tex-to-pdf tex-to-xps tex-to-svg tex-to-png tex-to-bmp tex-to-tiff tex-to-jpeg latex-to-pdf latex-to-xps latex-to-svg latex-to-png latex-to-bmp latex-to-tiff latex-to-jpeg" >}}

{{% blocks/products/pf/agp/content %}}

<br><br>

<h2>{{<import path="/{{lang}}/partials/_faqs.md" section="faq-converter.h2">}}</h2>

<b>1. {{<import path="/{{lang}}/partials/_faqs.md" section="faq-converter.Q1">}}</b>

{{<import path="/{{lang}}/partials/_faqs.md" section="faq-converter.A1">}}

<b>2. {{<import path="/{{lang}}/partials/_faqs.md" section="faq-converter.Q2">}}</b>

{{<import path="/{{lang}}/partials/_faqs.md" section="faq-converter.A2">}}

<b>3. {{<import path="/{{lang}}/partials/_faqs.md" section="faq-converter.Q3">}}</b>

{{<import path="/{{lang}}/partials/_faqs.md" section="faq-converter.A3">}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="{{<import path="/{{lang}}/partials/_content.md" section="learningresources.tabTitle">}}" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="{{<import path="/{{lang}}/partials/_content.md" section="learningresources.name1">}}" href="https://docs.aspose.com/tex/cpp/" >}}
{{< blocks/products/pf/slr-element name="{{<import path="/{{lang}}/partials/_content.md" section="learningresources.name2">}}" href="https://github.com/aspose-tex/Aspose.TeX-for-C" >}}
{{< blocks/products/pf/slr-element name="{{<import path="/{{lang}}/partials/_content.md" section="learningresources.name3">}}" href="https://reference.aspose.com/tex/cpp/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="{{<import path="/{{lang}}/partials/_content.md" section="support.tabTitle">}}" tabId="support" >}}
{{< blocks/products/pf/slr-element name="{{<import path="/{{lang}}/partials/_content.md" section="support.name1">}}" href="https://forum.aspose.com/c/tex/47" >}}
{{< blocks/products/pf/slr-element name="{{<import path="/{{lang}}/partials/_content.md" section="support.name2">}}" href="https://helpdesk.aspose.com/" >}}
{{< blocks/products/pf/slr-element name="{{<import path="/{{lang}}/partials/_content.md" section="support.name3">}}" href="https://blog.aspose.com/categories/aspose.tex-product-family/" >}}
{{< blocks/products/pf/slr-element name="Release Notes" href="https://docs.aspose.com/tex/cpp/release-notes/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="{{<import path="/{{lang}}/partials/_content.md" section="why.tabTitlecpp">}}" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="{{<import path="/{{lang}}/partials/_content.md" section="why.name1">}}" href="https://about.aspose.com/customers/" >}}
{{< blocks/products/pf/slr-element name="{{<import path="/{{lang}}/partials/_content.md" section="why.name2">}}" href="https://about.aspose.com/customers/success-stories/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< /blocks/products/pf/support-learning-resources >}}

{{< blocks/products/pf/download-section downloadFreeTrialLink="https://releases.aspose.com/tex/cpp/" pricingInformationLink="https://purchase.aspose.com/pricing/tex/cpp" >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class>}} 