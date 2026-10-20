---
translation: true
template: /templates/_template-java.md
title: External LaTeX packages | Aspose.TeX for Java
linktitle: External LaTeX packages
weight: 30
url: /java/external-latex-packages/
description: Aspose.TeX API for Java allows the use of external packages, i.e. the ones that aren't included in the library itself like fancybox or pgfplots packages.
lastmod: "2024-09-20"
---

{{<section overview>}}

## External LaTeX packages

There is a number of [common LaTeX packages](/tex/{{lang.url-fragment}}net/embedded-packages/) included in the **Aspose.TeX** library for Java. So you don't have to take care about how to provide these packages to the library's TeX engine. But sometimes (maybe often) your LaTeX file may require a package beyond the "natively" supported "bundle" of packages. In this case, you can try to provide the required input, i.e. required package's source files, using the [setRequiredInputDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#setRequiredInputDirectory-com.aspose.tex.IInputWorkingDirectory-) method of the [TeXOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/) class instance. We will see how this works with two examples.

Set `inputFile` to the full path of the corresponding LaTeX document and `outputDirectory` to an existing output folder. Both conversion examples produce PNG at 150 DPI. Import the Aspose.TeX classes used in the selected snippet, `com.aspose.tex.rendering.ImageDevice`, `com.aspose.tex.rendering.PngSaveOptions` and, for ZIP input, `java.io.InputStream` and `java.nio.file.Files`. Handle or declare exceptions in the calling method. Apply a license as described in the [licensing guide](/tex/{{lang.url-fragment}}java/licensing/).

### Unpacked required input (`fancybox` package)

Let's say we have the following simple LaTeX file, which is `required-input-fs.tex` from our [example solution](https://GitHub.com/aspose-tex/Aspose.TeX-for-Java):

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
  \begin{Beqnarray}
  y & = & x^2 \\
  a^2 + 2ab + b^2 & = & (a + b)^2 \\
  \int_0^\infty e^{-ax} dx & = & \frac{1}{a}
  \end{Beqnarray}
}
\end{document}
```

The third line requires the external `fancybox` package. Set `packagesDirectory` to a local folder containing `fancybox.sty` and its dependencies. The complete example below assigns this folder to `RequiredInputDirectory` and produces a PNG image. The device and working directories remain open until the job finishes and are then disposed or closed.

![Output Document](/tex/images/java/Conversion-RequiredInputFs.png)

Here is the complete source code for the example:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RequiredInput-FileSystem.java" >}}

### Archived required input (`pgfplots` package)

Let's now assume that we have the following also quite simple LaTeX file, which is `required-input-zip.tex` from our example solution:


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

On the 3rd line, we see that the file requires the `pgfplots` package, which is also not "natively" supported. Again, we assume that we have the `pgfplots` package source files. It's quite a large set of files that are divided between two locations if you find them in the installation directory of any LaTeX typesetting application. You can find `pgfplots` folder at both `\tex\generic` and `\tex\latex` folders. And the contents of both these folders must be provided as required input to the Aspose.TeX library. We want these source file to be packaged in a ZIP archive, so here is the archive's layout:

![archive’s layout](/tex/images/java/pgfplots-zip-layout.png)

Set `packagesZip` to a `java.nio.file.Path` pointing to the archive containing both the generic and LaTeX package sources. The complete Java example below opens it with `Files.newInputStream(...)` and assigns an `InputZipDirectory` to `RequiredInputDirectory`. The empty base-path argument selects the whole archive. Keep the ZIP stream and directory open until the TeX job finishes, then close them. The result is a PNG image with the two plots.

![Output document](/tex/images/java/Conversion-RequiredInputZip.png)

Here is the complete source code for the example:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RequiredInput-Zip.java" >}}

> **_NOTE:_** The result was verified using the `pgfplots` package version 1.18.1. While the version of the `pfg` package included in the **Aspose.TeX** library is 3.1.9a.

### Using external font packages

Typically, LaTeX distributions come with a selection of default fonts that can be used for typesetting. In addition to these fonts, **Aspose.TeX** offers several non-standard font packages, such as `amsfonts`, `eurosym`, and `wasysym`. As mentioned earlier, **Aspose.TeX** also supports the use of external packages, although our focus has mainly been on packages that do not include fonts.

The *Object TeX* engine extension in **Aspose.TeX** requires font maps, which are text files with the `.map` extension that specify the physical fonts corresponding to each TeX's internal font name. These font maps need to be loaded into TeX's memory during the initialization phase and must be included in the package files. Since the engine is not aware of the names of all font maps, it searches for any files with the `.map` extension. Therefore, the implementation of the [IInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/) interface used as the value of the [RequiredInputDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getRequiredInputDirectory--) option must provide a way to access collections of file names based on their extension. Specifically, this implementation must also implement the [IFileCollector](https://reference.aspose.com/tex/java/com.aspose.tex/ifilecollector/) interface. The standard implementations, [InputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputfilesystemdirectory/) and [InputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputzipdirectory/), already fulfill this requirement.

The following custom `RequiredInputDirectory` implements both interfaces and reads explicitly registered local files. Save it as `RequiredInputDirectory.java` with its included imports. Register each file with `storeFileName(...)`, then assign the instance using `options.setRequiredInputDirectory(...)` and close it after the job. It is a flat registry: filenames must be unique when requested without a full path. Extension matching is case-insensitive; the optional collection path selects a file-system directory. Register all required package, font-map, metric and physical font files. File collection makes maps discoverable; it does not supply missing font data.

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RequiredInputDirectory.java" >}}

### Restrictions

A package required by your LaTeX file may be developed under the *LaTeX3e* kernel. Such a package will most likely not work with the **Aspose.TeX** library since the latter is based on the *LaTeX2e* kernel.

Also, a package required by your LaTeX file may directly call device-dependent primitive commands that are not supported by the **Aspose.TeX** library's *Object TeX* engine. Such a package, unfortunately, will not work for sure.
