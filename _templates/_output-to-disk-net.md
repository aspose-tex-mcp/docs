---
template: true
title: {{i18n.title}}
description: {{i18n.description}}
url: {{i18n.url}}
informat: {{i18n.informat}}
family: tex
platformtag: net
---

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
{{< /highlight >}}

{{< highlight csharp >}}
    // Create conversion options for default ObjectTeX format upon ObjectTeX engine extension.
    TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
    // Specify a job name. Otherwise, the first argument of the TeXJob constructor will be taken as a job name.
    options.JobName = "overriden-job-name";
    // Specify a file system working directory for the input.
    options.InputWorkingDirectory = new InputFileSystemDirectory(RunExamples.InputDirectory);
    // Specify a file system working directory for the output.
    options.OutputWorkingDirectory = new OutputFileSystemDirectory(RunExamples.OutputDirectory);
    // Specify that the terminal output must be written to a file in the output working directory.
    // The file name is <job_name>.trm.
    options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);

    // Run the job.
    TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
    job.Run();
{{< /highlight >}}
{{% /blocks/products/pf/agp/code-block %}}
{{% /blocks/products/pf/feature-page-section %}}


{{< blocks/products/pf/agp/about-file-section >}}     
{{< blocks/products/pf/agp/about-file-text fileFormat="{{i18n.informat}}" section="{{i18n.informat}}" >}}
{{<import path="/{{lang}}/partials/_formats.md" section="{{i18n.informat}}">}}
{{< /blocks/products/pf/agp/about-file-text >}}


{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}} 