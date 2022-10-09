---
template: true
title: {{i18n.title}}
description: {{i18n.description}}
url: {{i18n.url}}
family: tex
platformtag: cpp
feature: conversion
informat: {{i18n.informat}}
outformat: {{i18n.outformat}}
otherformats: {{i18n.otherformats}}
---

{{<meta path="/{{lang}}/meta/conversion/default.md" section="faqchild">}}

{{< blocks/products/pf/main-wrap-class isAutogenPage="true" >}}
{{< blocks/products/pf/agp/upper-banner-autogen h1="{{i18n.banner.h1}}" h2="{{i18n.banner.h2}}">}}

{{< blocks/products/pf/main-container pfName="Aspose.TeX" subTitlepfName="for C++" >}}

{{< blocks/products/pf/sub-menu logoImageSrc="https://www.aspose.cloud/templates/aspose/img/products/tex/aspose_tex-for-cpp.svg" liveDemosLink="https://products.aspose.app/tex/applications" PricingLink="https://purchase.aspose.com/pricing/tex/cpp" buyLink="https://purchase.aspose.com/buy" docsLink="https://docs.aspose.com/tex/cpp/" installationsDocsLink="https://docs.aspose.com/tex/cpp/installation/" nugetLink="https://www.nuget.org/packages/Aspose.TeX/" nugetPackageName="Aspose.TeX" mavenRepoLink="" directDownloadLink="https://releases.aspose.com/tex/cpp/" >}}

{{% blocks/products/pf/agp/content h2="{{i18n.overview.title}}" %}}

<p>{{i18n.overview.p1}}</p>
<p>{{i18n.overview.p2}}</p>
<p>{{i18n.overview.p3}}</p>

-  <p>{{i18n.overview.p4}}</p>
-  <p>{{i18n.overview.p5}}</p>

{{% /blocks/products/pf/agp/content %}}


{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="{{i18n.feature1.title}}" %}}

<p>{{i18n.feature1.item1}}</p>

1. {{i18n.feature1.item2}}
2. {{i18n.feature1.item3}}
3. {{i18n.feature1.item4}}
4. {{i18n.feature1.item5}}

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/feature-section-col title="{{i18n.feature2.title}}" %}}

-  {{i18n.feature2.item1}}
-  {{i18n.feature2.item2}}

{{% /blocks/products/pf/agp/feature-section-col %}}


{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/agp/feature-section >}}
{{< app/tex/converter "{{i18n.widget.title}}" {{i18n.widget.formats}}>}}
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX);
options.OutputWorkingDirectory = new OutputFileSystemDirectory(RunExamples.OutputDirectory);
options.SaveOptions = new {{output camel}}SaveOptions();
new TeXJob(Path.Combine(RunExamples.InputDirectory, "{{inputFile}}"), new ImageDevice(), options).Run();
{{< /app/tex/converter >}}
{{< /blocks/products/pf/agp/feature-section>}}
{{< /blocks/products/pf/main-wrap-class>}}

{{% blocks/products/pf/agp/content %}}

<br><br>

<h2>{{<import path="/{{lang}}/partials/_faqs.md" section="faq-converter-child.h2">}}</h2>

<b>1. {{<import path="/{{lang}}/partials/_faqs.md" section="faq-converter-child.Q1">}}</b>

{{<import path="/{{lang}}/partials/_faqs.md" section="faq-converter-child.A1">}}

<b>2. {{<import path="/{{lang}}/partials/_faqs.md" section="faq-converter-child.Q2">}}</b>

{{<import path="/{{lang}}/partials/_faqs.md" section="faq-converter-child.A2">}}

<b>3. {{<import path="/{{lang}}/partials/_faqs.md" section="faq-converter-child.Q3">}}</b>

{{<import path="/{{lang}}/partials/_faqs.md" section="faq-converter-child.A3">}}

<b>4. {{<import path="/{{lang}}/partials/_faqs.md" section="faq-converter-child.Q4">}}</b>

{{<import path="/{{lang}}/partials/_faqs.md" section="faq-converter-child.A4">}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/about-file-section >}}     
{{< blocks/products/pf/agp/about-file-text fileFormat="{{i18n.informat}}" section="{{i18n.informat}}" >}}
{{<import path="/{{lang}}/partials/_formats.md" section="{{i18n.informat}}">}}
{{< /blocks/products/pf/agp/about-file-text >}}

{{< blocks/products/pf/agp/about-file-text fileFormat="{{i18n.outformat}}" section="{{i18n.outformat}}" >}}
{{<import path="/{{lang}}/partials/_formats.md" section="{{i18n.outformat}}">}}
{{< /blocks/products/pf/agp/about-file-text >}} 
{{< /blocks/products/pf/agp/about-file-section >}}	

{{< blocks/products/pf/agp/other-supported-autogen >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class>}} 