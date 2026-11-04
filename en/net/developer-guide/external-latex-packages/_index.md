---
translation: true
template: /templates/_template-net.md
title: External LaTeX packages | Aspose.TeX for .NET
linktitle: External LaTeX packages
weight: 20
url: /net/external-latex-packages/
description: Aspose.TeX API for .NET allows using external packages, i.e. the ones not included in the library itself like fancybox and pgfplots packages.
keywords: external latex packages, aspose tex, .net tex, latex packages, fancybox, pgfplots, required input directory, input zip, custom input directory, tex conversion
lastmod: "2026-11-04"
---

{{<section overview>}}

## External LaTeX packages

The **Aspose.TeX** library includes a number of [common LaTeX packages](/tex/{{lang.url-fragment}}net/embedded-packages/). So you don't have to worry about how to provide these packages to the library's TeX engine. But sometimes (or quite often) your LaTeX file may require a package beyond the "natively" supported "bundle" of packages. If this is the case, you can try to provide the required input, i.e. required package's source files, via the [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) option of the [TeXOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) class instance. We will see how this works with two examples.

### Unpacked required input (`fancybox` package)

Let's say we have the following simple LaTeX file, which is `required-input-fs.tex` from our [example solution](https://GitHub.com/aspose-tex/Aspose.TeX-for-.NET):


```tex
\documentclass{article}
\usepackage[a6paper,landscape]{geometry}
\usepackage{fancybox}
\begin{document}
Test: \fbox{
  \begin{Bitemize}[b]
  \item First item
  \item A second one\\ on two lines
  \item(2pt) A third with extra space
  \end{Bitemize}
}
\par\bigskip
Test: \fbox{
  \begin{Beqnarray}[t]
  y & = & x^2 \\
  a^2 + 2ab + b^2 & = & (a + b)^2 \\
  \int_0^\infty e^{-ax} dx & = & \frac{1}{a}
  \end{Beqnarray}
}
\end{document}
```

On the 3rd line, we can see that the file requires the `fancybox` package, which is not "natively" supported. Let's also assume that we have the `fancybox` package source file. It is a simple package, so it really consists of a single file. We can place this file anywhere in our file system and specify the directory path as simply as shown below:


```C#
options.RequiredInputDirectory = new InputFileSystemDirectory("path-to-directory-where-fancybox.sty-located");
```

After running a TeX job with this option (don't forget to adjust the other options as needed), we get the output document (i.e., a PNG image).

![Output Document](/tex/images/net/Conversion-RequiredInputFs.png)

Here is the complete source code for the example:

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-RequiredInput-FileSystem.cs" >}}

### Archived required input (`pgfplots` package)

Let's now say that we have the following also quite simple LaTeX file, which is `required-input-zip.tex` from our example solution:


```tex
\documentclass{article}
\usepackage[margin=0.25in]{geometry}
\usepackage{pgfplots}
\pgfplotsset{width=10cm,compat=1.18}
\begin{document}

First example is 2D and 3D math expressions plotted side-by-side.

%Here begins the 2D plot
\begin{tikzpicture}
\begin{axis}
\addplot[color=red]{exp(x)};
\end{axis}
\end{tikzpicture}
%Here ends the 2D plot
\hskip 5pt
%Here begins the 3D plot
\begin{tikzpicture}
\begin{axis}
\addplot3[
    surf,
]
{exp(-x^2-y^2)*x};
\end{axis}
\end{tikzpicture}
%Here ends the 3D plot

\end{document}
```


On the 3rd line, we can see that the file requires the `pgfplots` package, which is also not "natively" supported. Again, we assume that we have the `pgfplots` package source files. It's quite a large number of files that are divided between two locations if you find them in the installation directory of any LaTeX typesetting application. You can find `pgfplots` folder at both `\tex\generic` and `\tex\latex` folders. And the contents of both these folders must be provided as required input to the Aspose.TeX library. We want these source file to be packaged in a ZIP archive, so here is the archive's layout:

![Archive’s Layout](/tex/images/net/pgfplots-zip-layout.png)

And this is how we specify the access to these source files:


```C#
using (Stream zipStream = File.Open("path-to-zip-with-pgfplots-sources"), FileMode.Open))
{
    ...
    options.RequiredInputDirectory = new InputZipDirectory(zipStream);
    ...
}
```

After running a TeX job with this option, we get the output document:

![Output Document](/tex/images/net/Conversion-RequiredInputZip.png)

Here is the complete source code for the example:

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-RequiredInput-Zip.cs" >}}

> **_NOTE:_** The result was verified using the `pgfplots` package version 1.18.1. While the version of the `pfg` package included in the **Aspose.TeX** library is 3.1.9a.

### Employing external font packages

As a rule, LaTeX distributions provide a set of default fonts available for typesetting. Except these fonts, **Aspose.TeX** includes a number of non-standard font packages. For example, `amsfonts`, `eurosym`, and `wasysym`. As we saw above, Aspose.TeX also allows to employ external packages. But mostly we were talking about packages that don't contain fonts.

The **Aspose.TeX**'s *Object TeX* engine extension needs font maps (which are text files in a certain format with the `.map` extension by convention) to determine which physical fonts correspond to each TeX's internal font name. These font maps must be loaded into TeX's memory during the initialization phase. And, of course, they must be present among the files of the package you are plugging in. Since the engine doesn't know the names of all font maps, it looks for all files with the `.map` extension. Therefore, an implementation of the [IInputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/) interface that is used as a value of the [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) option must provide a way to access collections of file names by extension. More specifically, this implementation must also implement the [IFileCollector](https://reference.aspose.com/tex/net/aspose.tex.io/ifilecollector/) interface. The standard implementations - [InputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) and [InputZipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/) - already do it.

Below, we provide an illustrative example of a custom required input directory that also implements the [IFileCollector](https://reference.aspose.com/tex/net/aspose.tex.io/ifilecollector/) interface. While focusing on collecting file names by extension, we intentionally omit the details of file storage and retrieval.

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-RequiredInputDirectory.cs" >}}

### Restrictions

It may happen that a package required by your LaTeX file is developed under the *LaTeX3e* kernel. Such a package will most likely not work with the **Aspose.TeX** library since the latter is based on the *LaTeX2e* kernel.

It may also happen that a package required by your LaTeX file directly calls device-dependent primitive commands that are not supported by the **Aspose.TeX** library's *Object TeX* engine. Such a package, unfortunately, will not work for sure.

## Building a LaTeX embedded packages optimization AI Agent

If you need to create an AI agent that optimizes content for the built-in package inventory without sluggish dynamic network retrievals or file-system searches during generation, you can use the workflow described below.
Instead of forcing an LLM to guess which packages are safe or fast to use, the agent targets this specific, pre-compiled package inventory to avoid missing package errors.

![The AI Agent Embedded Document Assembly Architecture](/tex/images/net/tutorial/blockscheme-for-ai-latex-package-optimization.png) 

1. Layout intention extraction (LLM analysis layer)
The user supplies unstructured multi-format data or conversational directives. The LLM maps requests directly to the Aspose embedded package list (`colortbl` for row shading, `geometry` for margins, and `multirow` for cells spanning several rows).

2. AST isolation and preamble injection 
Rather than writing bloated package imports, the agent checks the code requirements against the embedded package list.
It writes only the required `\usepackage` commands into the preamble.

3. Stream sandboxing and execution (Aspose.TeX Engine Node)
The LaTeX source is passed to a `TeXJob` as a stream, with `TeXOptions` created for `TeXConfig.ObjectLaTeX`. `TeXJob.Run()` is synchronous, so the agent runs it in a background worker.

```tex
\usepackage[a4paper,margin=0.5in]{geometry}
\usepackage{amsmath,multirow,colortbl}
```

4. Asset serialization (Output rendering layer)
The job writes the result with an output device, such as `PdfDevice` or `SvgDevice`, and the agent returns it to the client.
