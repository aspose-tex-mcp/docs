---
translation: true
template: /_templates/_typeset-tex-files-net.md
title: TeX typesetting functionality | .NET API
url: /net/typeset-tex-files/
description: ".NET API Solution to work with TeX. Learn on the example how to create TeX typesets with a few lines of C# code."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Typeset TeX files
h2: "Typeset a TeX file using a custom TeX format C# .NET"
---

{{<section overview>}}
---
p1: "TeX is known as one of the data markup languages and/or a typesetting language at the same time. It means that you do not format your text in the document, but enter the plain text along with the commands. As an output, you will get the formatted file of the needed(specified) format. [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) is the central core of the publication set system (computer typesetting)."
p2: "To get more understanding of TeX typesetting learn the [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) of the Documentation. And on this page you will find code snippets explaining how to typeset a TeX file using a custom TeX format."
p3: "To run the examples we need:"
p4: "Aspose.TeX for .NET API which is a feature-rich, powerful and easy-to-use document manipulation and conversion API for C# platform."
p5: "Open the NuGet package manager, and search for Aspose.TeX and install. You may also use the following command from the Package Manager Console."
---

{{<section feature1>}}
---
title: Steps to typeset TeX using C#.
h3: "C# Code for typesetting TeX"
item1: "Create the format provider using the [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) Class. "
item2: "Create conversion options for a custom format upon ObjectTeX engine extension using [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Method of [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Class."
item3: "Specify the input working directory if the main input is not provided as a stream. Use the [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) Class for this."
item4: "Specify a file system working directory for the output. Use the [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) Class for this."
item5: "Run the job [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Method for [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item6: Refine the output.
---