---
translation: true
template: /_templates/_output-to-disk-net.md
title: Write TeX output to disk | .NET API Solution
url: /net/output-to-disk/
description: ".NET API Solution to work with TeX. Learn on the example how to create custom output for TeX file  with a few lines of C# code. "
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Write TeX output to disk
h2: "Save the result of TeX file conversion as disk via C# .NET"
---

{{<section overview>}}
---
p1: "TeX is known as a typesetting language which means that you do not format your text in the document, but enter the plain text along with the commands. As it is known from the article [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) of the Documentation, the TeX job runs on an explicitly specified TeX file. There you may also find out information on TeX interaction modes and primitives related to TeX input and output."
p2: "The main usage of TeX is to help with the creation of mathematical or technical text writing. But when the file is already created and you do not want any further manipulations on it, you may want to convert it to a different, more popular, format."
p3: "On this page, you will find a code example explaining using file system directories for input and output, outputting to XPS device, overriding the job name, writing terminal output to disk. In simple words, it is a conversion with the writing of the output to the disk. To run such operation we need:"
p4: "Aspose.TeX for .NET API which is a feature-rich, powerful and easy-to-use document manipulation and conversion API for C# platform."
p5: "Open the NuGet package manager, and search for Aspose.TeX and install. You may also use the following command from the Package Manager Console."
---

{{<section feature1>}}
---
title: "Steps to write terminal output to disk C#:"
h3: "C# Code for converting TeX and writing the output to the disk"
item1: "Create conversion options upon ObjectTeX engine extension using [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Method of [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Class."
item2: "Specify a job name if you do not want the first argument of the TeXJob constructor to be taken as a job name."
item3: "Specify a file system working directory for the input. Use the [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) Class for this."
item4: "Specify a file system working directory for the output with the help of the entities of the [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) Class."
item5: "Specify that the terminal output must be written to a file in the output working directory."
item6: "Run the job [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Method for [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
---