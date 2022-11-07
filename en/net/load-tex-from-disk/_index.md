---
translation: true
template: /_templates/_load-tex-from-disk-net.md
title: Loading TeX from a disk | .NET API Solution
url: /net/load-tex-from-disk/
description: ".NET API Solution to work with TeX. Learn on the example how to load a TeX file from disk with a few lines of C# code."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Load TeX source files from disk
h2: ".NET API Solution to load TeX/LaTeX files from disk"
---

{{<section overview>}}
---
p1: "TeX is known as a typesetting language. It means that you do not format your text in the document, but enter the plain text along with the commands. As an output, you will get the formatted file of the needed(specified) format. [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) is the central core of the publication set system (computer typesetting). A TeX job runs on an explicitly specified TeX file. To get more understanding of TeX input and output learn the [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) of the Documentation."
p2: "As it is known, the main purpose of TeX is to help create mathematical or technical text writing. But before any manipulations, the file should be first loaded. Here you will find code snippets explaining how to load TeX source files from disk using file system directories for input and output, outputting to XPS device, writing terminal output to console."
p3: "To run the examples we need:"
p4: "Aspose.TeX for .NET API which is a feature-rich, powerful and easy-to-use document manipulation and conversion API for C# platform."
p5: "Open the NuGet package manager, and search for Aspose.TeX and install. You may also use the following command from the Package Manager Console."
---

{{<section feature1>}}
---
title: Steps to load TeX from a disk C#.
h3: "C# Code for loading TeX"
item1: "Create conversion options for a custom format upon ObjectTeX engine extension using [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Method of [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Class."
item2: "Specify a file system working directory for the input. Use the [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) Class for this."
item3: "Specify a file system working directory for the output using [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) Class."
item4: "Specify the console as the output terminal using [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/) Class."
item5: "Specify a memory terminal as an output terminal if you need. For this use [*OutputMemoryTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputmemoryterminal/) Class."
item6: "Run the job [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Method for [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item7: Refine the output.
---