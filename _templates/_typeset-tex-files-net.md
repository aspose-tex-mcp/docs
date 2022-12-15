---
template: true
title: {{i18n.title}}
description: {{i18n.description}}
url: {{i18n.url}}
informat: {{i18n.informat}}
family: tex
platformtag: net
---

{{<meta path="/{{lang}}/meta/features/default.md" section="faqtypesettex">}}

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
4. {{i18n.feature1.item4}}
5. {{i18n.feature1.item5}}
6. {{i18n.feature1.item6}}


{{% blocks/products/pf/agp/code-block title="{{i18n.feature1.h3}}" offSpacer="true" %}}
{{< highlight csharp >}}
    using Aspose.TeX.IO;
    using Aspose.TeX.Presentation.Xps;
    using Aspose.TeX.ResourceProviders;
    using System.IO;
    using System.Text;
{{< /highlight >}}

{{< highlight csharp >}}
    // Create the format provider using the file system input working directory.
    // We use the project output directory as our custom format file is supposed to be located there.
    using (FormatProvider formatProvider =
        new FormatProvider(new InputFileSystemDirectory(RunExamples.OutputDirectory), "customtex"))
    {
        // Create conversion options for a custom format upon ObjectTeX engine extension.
        TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX(formatProvider));
        options.JobName = "typeset-with-custom-format";
        // Specify the input working directory. This is not required here as we are providing the main input as a stream.
        // But it is required when the main input has dependencies (e.g. images).
        options.InputWorkingDirectory = new InputFileSystemDirectory(RunExamples.InputDirectory);
        // Specify a file system working directory for the output.
        options.OutputWorkingDirectory = new OutputFileSystemDirectory(RunExamples.OutputDirectory);

        // Run the job.
        new TeXJob(new MemoryStream(Encoding.ASCII.GetBytes(
                "Congratulations! You have successfully typeset this text with your own TeX format!\\end")),
                new XpsDevice(), options).Run();

        // For further output to look fine.
        options.TerminalOut.Writer.WriteLine();
    }
{{< /highlight >}}
{{% /blocks/products/pf/agp/code-block %}}
{{% /blocks/products/pf/feature-page-section %}}


{{% blocks/products/pf/agp/content %}}

<br><br>

<h2>{{<import path="/{{lang}}/partials/_faqs-features.md" section="faq-typesettex.h2">}}</h2>

<b>1. {{<import path="/{{lang}}/partials/_faqs-features.md" section="faq-typesettex.Q1">}}</b>

{{<import path="/{{lang}}/partials/_faqs-features.md" section="faq-typesettex.A1">}}

<b>2. {{<import path="/{{lang}}/partials/_faqs-features.md" section="faq-typesettex.Q2">}}</b>

{{<import path="/{{lang}}/partials/_faqs-features.md" section="faq-typesettex.A2">}}

<b>3. {{<import path="/{{lang}}/partials/_faqs-features.md" section="faq-typesettex.Q3">}}</b>

{{<import path="/{{lang}}/partials/_faqs-features.md" section="faq-typesettex.A3">}}

{{% /blocks/products/pf/agp/content %}}


{{< blocks/products/pf/agp/about-file-section >}}     
{{< blocks/products/pf/agp/about-file-text fileFormat="{{i18n.informat}}" section="{{i18n.informat}}" >}}
{{<import path="/{{lang}}/partials/_formats.md" section="{{i18n.informat}}">}}
{{< /blocks/products/pf/agp/about-file-text >}}


{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}} 