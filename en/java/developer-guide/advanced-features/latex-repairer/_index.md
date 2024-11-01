---
translation: true
template: /templates/_template-java.md
title: LaTeX file repair | Aspose.TeX for Java
linktitle: LaTeX file repair
weight: 30
url: /java/latex-repair/
description: LaTeX file repairer feature within Aspose.TeX API for Java is described in this article. Learn the code examples of how to use the functionality.
lastmod: "2024-09-20"
---

{{<section overview>}}

## How to check and repair a LaTeX file

If you are unsure whether a text file is a LaTeX file and want it to be typeset, you can utilize the checking and repairing LaTeX feature offered by the Aspose.TeX API for Java. In the example below, we will check and repair a sample file, `invalid-latex.tex`, from the Aspose.TeX for Java example project.

To begin with, it is important to note that the sample file seems to employ the TeX syntax but lacks the structure required by LaTeX. As you may know, a LaTeX file must include a preamble that begins with the \documentclass command, as well as a body enclosed within the document environment, specifically between \begin{document} and \end{document}.

Let's now look at the Java code sample.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-LaTeXRepairer.java" >}}

Similar to a regular TeX job, we start by creating an object that holds the options for the process we are about to run. Most of these options are the same as those for a regular TeX job. Indeed, calling the [setInputWorkingDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setInputWorkingDirectory-com.aspose.tex.IInputWorkingDirectory-) method, we specify the space from which the input files should be read. However, in this example, we don't use it here because we provide the full path to the main input file in the file system, and no custom files are to be included in the main input file. Next, we call the [setOutputWorkingDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setOutputWorkingDirectory-com.aspose.tex.IOutputWorkingDirectory-) method to specify the space where the output files should be written. If called, the [setRequiredInputDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setRequiredInputDirectory-com.aspose.tex.IInputWorkingDirectory-) method makes options point to the space where you may store LaTeX packages that are not embedded in the Aspose.TeX library. Finally, the [setGuessPackageCallback()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setGuessPackageCallback-com.aspose.tex.features.IGuessPackageCallback-) method will be discussed later on.

Once the options have been assigned, we can proceed with running the process.

So, what is the checking and repairing process like? It begins with the API searching for a `\documentclass` occurrence in the input file. If it is not found, the API assumes that `\documentclass{article}` should be inserted at the start of the file. This information is recorded in the repair report file (.log).

Next, the process begins scanning the adjusted input file from the beginning. The TeX engine equipped with the LaTeX format may, at some point, throw an error indicating that `\begin{document}` has not yet been found when it should have already. This way, the position at which `\begin{document}` must be inserted is defined and reflected in the report.

While further scanning the file, the engine may come across undefined commands or environments. In such cases, the API can make assumptions on [embedded required packages](/tex/{{lang.url-fragment}}net/embedded-packages/) (those that define the commands and environments that are not defined until these packages are included) for some of the most common commands and environments. However, it is possible to make such assumptions externally by a class that implements the [IGuessPackageCallback](https://reference.aspose.com/tex/java/com.aspose.tex.features/iguesspackagecallback/) interface. Once you have developed such a class, an instance of it should be passed to the process by calling the `setGuessPackageCallback()` method.

Here is a basic example that simply maps the `\head` command to the `fancyhdr` package:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-LaTeXRepairer-PackageGuessingCallback.java" >}}

As for the sample file, the engine first encounters the `\chapter` command, which is not defined in the `article` document class but is defined in the `book` document class. The API adjusts the document class so that the final version of the repaired file will begin with `\documentclass{book}`. Then, the engine finds the aforementioned `\lhead` command and determines that `\usepackage{fancyhdr}` must be inserted in the preamble. The `\href` and `\includegraphics` commands that occur later in the file make the Repairer insert `\usepackage{hyperref}` and `\usepackage{graphics}` in the preamble, respectively. These decisions are made based on the API's internal mappings. As before, all these repairs are logged in the report file.

Finally, the engine abnormally terminates because the proper conclusion of a LaTeX document is missing. As a result, the Repairer appends `\end{document}` to the end of the file and includes this information in the report.

After creating the fixed version of the original file, the Repairer runs a TeX job on it for the final verification. In our example, this run does not detect any critical errors, so the fixed version can be typeset more or less as expected.

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