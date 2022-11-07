---
translation: true
template: /_templates/_customize-output-net.md
title: Create custom output TeX | .NET API Solution
url: /net/customize-output/
description: ".NET API Solution to work with TeX. Read the example how to create custom output for TeX file with a few lines of C# code."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Customize output
h2: ".NET API Solution to customize output of TeX files"
---

{{<section overview>}}
---
p1: "TeX is known as a typesetting language. It means that you do not format your text in the document, but enter the plain text along with the commands."
p2: "The article [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) of the Documentation teaches us that a TeX file may not contain any data to typeset but only control sequences. Yet it usually contains such data, and a file in the target format has the typeset text. The file will also have the same name as the file specified as the input and is the main output file. For the original TeX, this is a file in DVI format.  We will call the name of both input and output files without extending the job name."
p3: "On this page, you will find a code example explaining creating a custom TeX format file where you can see how to customize the output of TeX files. To customize .tex files output we need:"
p4: "Aspose.TeX for .NET API which is a feature-rich, powerful and easy-to-use document manipulation and conversion API for C# platform."
p5: "Open the NuGet package manager, and search for Aspose.TeX and install. You may also use the following command from the Package Manager Console."
---

{{<section feature1>}}
---
title: "Steps to customize TeX output C#:"
h3: "C# Code for TeX output customization"
item1: "With the help of the [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Method of [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Class, create TeX engine options for no format upon ObjectTeX engine extension."
item2: "Use [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) Class to specify a file system working directory for the input."
item3:  "Use [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) Class to specify a file system working directory for the output."
item4: "To create the new format use [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/) Method."
item5: Refine the output.
---