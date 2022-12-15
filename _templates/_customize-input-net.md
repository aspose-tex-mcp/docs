---
template: true
title: {{i18n.title}}
description: {{i18n.description}}
url: {{i18n.url}}
informat: {{i18n.informat}}
family: tex
platformtag: net
---

{{<meta path="/{{lang}}/meta/features/default.md" section="faqcustominput">}}

{{< blocks/products/pf/main-wrap-class isAutogenPage="true" >}}
{{< blocks/products/pf/agp/upper-banner-autogen h1="{{i18n.banner.h1}}" h2="{{i18n.banner.h2}}">}}

{{< blocks/products/pf/main-container pfName="Aspose.TeX" subTitlepfName="for .NET" >}}

{{< blocks/products/pf/sub-menu logoImageSrc="https://www.aspose.cloud/templates/aspose/img/products/tex/aspose_tex-for-net.svg" liveDemosLink="https://products.aspose.app/tex/applications" PricingLink="https://purchase.aspose.com/pricing/tex/net" buyLink="https://purchase.aspose.com/buy" docsLink="https://docs.aspose.com/tex/net/" directDownloadLink="https://releases.aspose.com/tex/net/" >}}

{{% blocks/products/pf/feature-page-summary %}}

{{i18n.overview.p1}}

{{i18n.overview.p2}}

<p>{{i18n.overview.p3}}</p>

-  <p>{{i18n.overview.p4}}</p>
-  <p>{{i18n.overview.p5}}</p>

{{% blocks/products/pf/agp/code-block title="Package Manager Console Command" offSpacer="true" %}}

```cs

    PM> Install-Package Aspose.TeX

```

{{% /blocks/products/pf/agp/code-block %}}
{{% /blocks/products/pf/feature-page-summary  %}}

{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/feature-page-section  h2="{{i18n.feature1.title}}" %}}

1. {{i18n.feature1.item1}}
2. {{i18n.feature1.item2}}
3. {{i18n.feature1.item3}}

{{% blocks/products/pf/agp/code-block title="{{i18n.feature1.h3}}" offSpacer="true" %}}
{{< highlight csharp >}}
    using Aspose.TeX.IO;
{{< /highlight >}}

{{< highlight csharp >}}
    // Create TeX engine options for no format upon ObjectTeX engine extension.
    TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectIniTeX);
    // Specify a file system working directory for the input.
    options.InputWorkingDirectory = new InputFileSystemDirectory(RunExamples.InputDirectory);

    // Run format creation.
    TeXJob.CreateFormat("customtex", options);
{{< /highlight >}}
{{% /blocks/products/pf/agp/code-block %}}
{{% /blocks/products/pf/feature-page-section %}}


{{% blocks/products/pf/agp/content %}}

<br><br>

<h2>{{<import path="/{{lang}}/partials/_faqs-features.md" section="faq-custominput.h2">}}</h2>

<b>1. {{<import path="/{{lang}}/partials/_faqs-features.md" section="faq-custominput.Q1">}}</b>

{{<import path="/{{lang}}/partials/_faqs-features.md" section="faq-custominput.A1">}}

<b>2. {{<import path="/{{lang}}/partials/_faqs-features.md" section="faq-custominput.Q2">}}</b>

{{<import path="/{{lang}}/partials/_faqs-features.md" section="faq-custominput.A2">}}

<b>3. {{<import path="/{{lang}}/partials/_faqs-features.md" section="faq-custominput.Q3">}}</b>

{{<import path="/{{lang}}/partials/_faqs-features.md" section="faq-custominput.A3">}}

<b>4. {{<import path="/{{lang}}/partials/_faqs-features.md" section="faq-custominput.Q4">}}</b>

{{<import path="/{{lang}}/partials/_faqs-features.md" section="faq-custominput.A4">}}

{{% /blocks/products/pf/agp/content %}}


{{< blocks/products/pf/agp/about-file-section >}}     
{{< blocks/products/pf/agp/about-file-text fileFormat="{{i18n.informat}}" section="{{i18n.informat}}" >}}
{{<import path="/{{lang}}/partials/_formats.md" section="{{i18n.informat}}">}}
{{< /blocks/products/pf/agp/about-file-text >}}


{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}} 