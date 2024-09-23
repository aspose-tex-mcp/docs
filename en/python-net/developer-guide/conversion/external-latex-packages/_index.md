---
translation: true
template: /templates/_template-python-net.md
title: External LaTeX packages | Python
linktitle: External LaTeX packages
weight: 19
url: /python-net/external-latex-packages/
description: Aspose.TeX API for Python supports the use of external packages that are not included in the library itself, such as the fancybox and pgfplots packages
lastmod: "2024-09-20"
---

{{<section overview>}}

## External LaTeX packages

The **Aspose.TeX** library comes with a variety of [common LaTeX packages](/tex/{{lang.url-fragment}}net/embedded-packages/), so there is no need to manually provide these packages to the TeX engine. However, there may be situations where your LaTeX file requires a package that is not included in the library's "bundle" of packages. In such cases, you can try providing the necessary input, such as the source files of the required package, through the [required_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/) option of the [TeXOptions](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/) class instance. We will explore how this works with two examples.

### Required input provided in an unpacked form (the `fancybox` package).

Suppose we have the following basic LaTeX file named `required-input-fs.tex`, which is part of our [example solution](https://GitHub.com/aspose-tex/Aspose.TeX-for-Python-.NET):

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

The 3rd line of the file indicates that it requires the `fancybox` package, which is not included in the "native" support. Let's assume we have the source file for the `fancybox` package. Since it is a simple package consisting of a single file, we can place this file anywhere in our file system and specify the directory path as follows:


```Python
options.required_input_directory = InputFileSystemDirectory('path-to-directory-where-fancybox.sty-located')
```

Once we run a TeX job with this option (remember to adjust the other options as necessary), we will obtain the output document, which in this case is a PNG image.

![Output Document](/tex/images/python-net/Conversion-RequiredInputFs.png)

Here is the complete source code for the example:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-RequiredInput-FileSystem.py" >}}

### Providing required input in an archived form (the `pgfplots` package)

Now, suppose we have the following LaTeX file named `required-input-zip.tex`, which is also a simple file from our example solution:


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

On the third line, it can be observed that the file necessitates the `pgfplots` package, which is not "natively" supported. Once again, assuming that we possess the source files for the `pgfplots` package, these files are quite numerous and are located in two different directories within the installation directory of any LaTeX typesetting application. The `pgfplots` folder can be found in both the `\tex\generic` and `\tex\latex` directories. For the Aspose.TeX library to function correctly, it is necessary to provide the contents of both these folders as input. To achieve this, we desire to package these source files into a ZIP archive. Below is the desired layout of the archive:

![Archive’s Layout](/tex/images/python-net/pgfplots-zip-layout.png)

And here is the method by which we define the accessibility to these source files:

```Python
with open("path-to-zip-with-pgfplots-sources") as zipStream:
    ...
    options.required_input_directory = InputZipDirectory(zipStream)
    ...
```

After running a TeX job with this option, we get the output document:

![Output Document](/tex/images/python-net/Conversion-RequiredInputZip.png)

Here is the complete source code for the example:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-RequiredInput-Zip.py" >}}

> **_NOTE:_** The result was verified using the `pgfplots` package version 1.18.1. While the version of the `pfg` package included in the **Aspose.TeX** library is 3.1.9a.

<!--
### Using external font packages

Typically, LaTeX distributions come with a predefined set of fonts that can be used for typesetting. However, in addition to these default fonts, **Aspose.TeX** also includes several non-standard font packages such as `amsfonts`, `eurosym`, and `wasysym`. As we discussed earlier, Aspose.TeX also supports the use of external packages, although most of our previous discussion focused on packages that do not include fonts.

The **Aspose.TeX**'s *Object TeX* engine extension requires font maps, which are text files in a specific format with the `.map` extension, to determine the corresponding physical fonts for each TeX's internal font name. These font maps need to be loaded into TeX's memory during the initialization phase and should be included in the package you are using. As the engine is not aware of the names of all font maps, it searches for files with the `.map` extension. Therefore, when providing a value for the [required_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/) option, the implementation of the [IInputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/) interface should allow access to collections of file names by extension. Additionally, this implementation should also implement the [IFileCollector](https://reference.aspose.com/tex/python-net/aspose.tex.io/ifilecollector/) interface. The standard implementations, such as [InputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputfilesystemdirectory/) and [InputZipDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputzipdirectory/), already fulfill these requirements.

Below is an example of a custom required input directory that demonstrates how to implement the [IFileCollector](https://reference.aspose.com/tex/python-net/aspose.tex.io/ifilecollector/) interface. This example focuses on collecting file names by extension and intentionally omits the details of file storage and retrieval.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-RequiredInputDirectory.py" >}}
-->

### Restrictions

If you come across a package that is developed under the *LaTeX3e* kernel anв is required by your LaTeX file, it is unlikely to work with the **Aspose.TeX** library. This is because the library is based on the *LaTeX2e* kernel.

In addition, there may be cases where a package required by your LaTeX file directly uses device-dependent primitive commands that are not supported by the **Aspose.TeX** library's *Object TeX* engine. In such cases, the package will not work with the library.
