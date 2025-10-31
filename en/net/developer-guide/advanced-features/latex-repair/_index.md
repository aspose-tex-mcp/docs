---
translation: true
template: /templates/_template-net.md
title: LaTeX file repair | Aspose.TeX for .NET
linktitle: LaTeX file repair
weight: 30
url: /net/latex-repair/
description: Aspose.TeX API solution for .NET LaTeX repair is described in this article. Learn the code examples on how to use the functionality.
lastmod: "2024-09-20"
---

{{<section overview>}}

## How to check and repair a LaTeX file

If you have a text file that you think is a LaTeX file and you want it to be typeset, but you are not sure if it is really a LaTeX file (perhaps you are new to the LaTeX world), you may try using the checking and repairing LaTeX feature provided by the Aspose.TeX API for .NET. In the following example, we will check and repair a sample file, `invalid-latex.tex`, from the Aspose.TeX for .NET example project.

First of all, it is worth mentioning that although the sample file seems to use the TeX syntax, it does not have the structure required by LaTeX. As you may know, a LaTeX file must have a preamble that starts with the `\documentclass` command and a body within the `document` environment, i.e. between `\begin{document}` and `\end{document}`.

Let's now look at the C# code sample.

{{< gist "aspose-com-gists" "7f54d335270200ebf5987d071bad028a" "Examples_LaTeXRepairerExample" >}}

As with a regular TeX job, we first create an object that contains the options of the process we are about to run. Most of them are the same as the options of a regular TeX job. Indeed, the [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/inputworkingdirectory/) is the space from which the input files should be read. We don't use it here because we provide the full path to the main input file in the file system, and no custom files are supposed to be included in the main input file. Then, [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/outputworkingdirectory/) is the space where the output files should be written. [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/requiredinputdirectory/), if assigned, points to the space where you may store LaTeX packages that are not embedded in the Aspose.TeX library. The [GuessPackageCallback](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/guesspackagecallback/) property will be discussed later.

After assigning the options, we simply run the process!

So, what is the checking and repairing process like? Firstly, the API searches the input file for a `\documentclass` occurrence. If it fails, it assumes that `\documentclass{article}` must be inserted at the very beginning of the file. This fact is reflected in the repair report file (`.log`).

Then, it starts scanning the adjusted input file from the very beginning. The TeX engine charged with the LaTeX format may throw an error at some point, signaling that no `\begin{document}` has been found so far, although it should have already occurred. Thus, the position at which `\begin{document}` must be inserted is defined and reflected in the report.

As the engine scans the file further, it may find undefined commands or environments. The API can make assumptions on [embedded required packages](/tex/{{lang.url-fragment}}net/embedded-packages/) (those that define the commands and environments that are not defined until these packages are included) for some of the most common commands and environments. However, there is a way to make such assumptions externally by implementing the [IGuessPackageCallback](https://reference.aspose.com/tex/net/aspose.tex.features/iguesspackagecallback/) interface. An instance of such a class should be assigned to the `GuessPackageCallback` option.

Here is a very simple example that just maps the `\head` command to the `fancyhdr` package:


{{< gist "aspose-com-gists" "7f54d335270200ebf5987d071bad028a" "Examples_PackageGuessingCallback" >}}


As for the sample file, the engine first encounters the `\chapter` command, which is not defined in the `article` document class but is defined in the `book` document class. The API adjusts the document class so that the final version of the fixed file will start with `\documentclass{book}`. Then, the engine finds the aforementioned `\lhead` command and decides that `\usepackage{fancyhdr}` must be inserted in the preamble. The `\href` and `\includegraphics` commands that occur later on make the Repairer insert `\usepackage{hyperref}` and `\usepackage{graphics}` in the preamble, respectively. These decisions are based on the API's internal mappings. Again, all such fixes are logged in the report file.

Finally, the engine abnormally terminates since the normal ending of a LaTeX document is missing. This makes the Repairer append `\end{document}` to the end of the file and reflect this fact in the report.

Once the fixed version of the original file is built, the Repairer runs the TeX job on it for the final check. In our example, this run does not find any critical errors, so the fixed version may be typeset more or less as expected.

Here is the full report:


```
Trying to repair the original file...
--------------------------------------------------------------------------------
\documentclass is missing in the original file. Inserted at the beginning.
\begin{document} is missing in the original file. Inserted at line 3, pos. 0.
The command \chapter at line 3, pos. 0 is undefined. Consider using \usepackage{package_name} in the preamble,
    where 'package_name' is the name of the package which defines this command.
The command \lhead at line 5, pos. 0 is undefined. \usepackage{fancyhdr} is inserted in the preamble
    since the 'fancyhdr' package supposedly defines the command.
The command \href at line 8, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 17, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 20, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 27, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 32, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \includegraphics at line 54, pos. 2 is undefined. \usepackage{graphicx} is inserted in the preamble
    since the 'graphicx' package supposedly defines the command.
The command \href at line 67, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 95, pos. 57 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 96, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 98, pos. 100 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
\end{document} is missing in the original file. Inserted at the end.

Checking the repaired file...
--------------------------------------------------------------------------------
There are no critical errors in the fixed file.
```

**You may also check out our free [**AI LaTeX Repairer**](https://products.aspose.ai/tex/latex-repairer) web app, which is built based on the feature implemented within [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) and involves a more advanced implementation of the `IGuessPackageCallback` interface.**