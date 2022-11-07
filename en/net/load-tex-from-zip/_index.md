---
translation: true
template: /_templates/_load-tex-from-zip-net.md
title: Loading TeX from ZIP | .NET API Solution
url: /net/load-tex-from-zip/
description: ".NET API Solution to work with TeX. Learn on the example how to load a TeX file from ZIP with a few lines of C# code."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Load TeX source files from ZIP
h2: ".NET API Solution to load TeX  files from ZIP archive"
---

{{<section overview>}}
---
p1: "TeX is known as a typesetting language. It means that you do not format your text in the document, but enter the plain text along with the commands. As an output, you will get the formatted file of the needed(specified) format. To get more understanding of TeX input and output learn the [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) of the Documentation."
p2: "As it is known, the main purpose of TeX is to help create mathematical or technical text writing. But before any manipulations, the file should be first loaded. Here you will find code snippets explaining how to load TeX source files from ZIP using ZIP directories for input and output, outputting to PDF device, writing terminal output to console."
p3: "To load .tex files we need:"
p4: "Aspose.TeX for .NET API which is a feature-rich, powerful and easy-to-use document manipulation and conversion API for C# platform."
p5: "Open the NuGet package manager, and search for Aspose.TeX and install. You may also use the following command from the Package Manager Console."
---

{{<section feature1>}}
---
title: "Steps to load TeX from a ZIP archive C#:"
h3: "C# Code for loading TeX"
item1: "Open the stream on the ZIP archive to use it as the input working directory."
item2: "Open the stream on the ZIP archive to use it as the output working directory."
item3: "Create conversion options for default ObjectTeX format upon ObjectTeX engine extension using [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Method of [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Class."
item4: "Specify a ZIP archive working directory for the input or/and specify a path inside the archive. Use constructors of the [*InputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/) Class for this."
item5: "Specify a ZIP archive working directory for the output or/and specify a path inside the archive. Use constructors of the [*outputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/) Class for this."
item6: "Specify the console as the output terminal using [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/) Class."
item7: "Define the saving options using [*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/) Class."
item8: "Run the job [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Method for [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item9: Refine the output.
---