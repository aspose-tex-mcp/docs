---
translation: true
template: /_templates/_customize-input-net.md
title: Create custom input TeX | .NET API Solution
url: /net/customize-input/
description: ".NET API Solution to work with TeX. Learn on the example how to create custom input for TeX file  with a few lines of C# code."
keywords: custom input tex net api, C# api to customize tex
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Customize input
h2: ".NET API Solution to customize input of TeX files"
---

{{<section overview>}}
---
p1: "TeX is known as a typesetting language. It means that you do not format your text in the document, but enter the plain text along with the commands. As it is described in the article [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) of the Documentation, TeX job runs on an explicitly specified TeX file. So, we include this file in the input of a certain TeX job."
p2: "On this page you will find a code example explaining how to customize input  of TeX source files taking into account that the input should follow TeX syntax and, ideally, contain only commands known to the engine."
p3: "To customize .tex files input we need:"
p4: "Aspose.TeX for .NET API which is a feature-rich, powerful and easy-to-use document manipulation and conversion API for C# platform."
p5: "Open the NuGet package manager, and search for Aspose.TeX and install. You may also use the following command from the Package Manager Console."
---

{{<section feature1>}}
---
title: "Steps to customize TeX input C#:"
h3: "C# Code for TeX input customization"
item1: "Using [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Method of [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Class, create TeX engine options for no format upon ObjectTeX engine extension."
item2: "Using [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) Class, specify a file system working directory for the input."
item3: "With the help of the [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/) Method, create the customized format."
---