---
translation: true
template: /templates/_template-python-net.md
title: Alternative methods to supply main TeX input file | Python
linktitle: Other ways to provide the main TeX input file
weight: 14
url: /python-net/other-ways-of-main-input/
description: Aspose.TeX API solution for Python includes a Constructor that accepts a stream as the first argument, providing conversion functionality.
lastmod: "2024-09-20"
---

{{<section overview>}}

## Supplying the main input file to the TeX engine using a stream

So far, we have only learned how to provide the [main input file](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) to the TeX engine as a file name, whether in its full form or in a shortened form, with or without an extension. However, there is [another constructor](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#io.RawIOBase-aspose.tex.presentation.Device-aspose.tex.TeXOptions) available in the [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/) class that accepts a stream as the first argument. This is useful if, for some reason, the main input file is not in the form of a file on the disk file system. Here is an example of how it can be implemented:

Set `ASPOSE_TEX_OUTPUT_DIR` to an output directory, or use the default `output`. Apply a license first as described in [Licensing](/tex/{{lang.url-fragment}}python-net/licensing/).

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputStream.py" >}}

This example uses a complete LaTeX document and `TeXConfig.object_latex`. The binary stream remains open for the duration of the job; the output is XPS.

Note that all output files will be named `texput`. This is because the engine does not have access to any other name. `texput` is the default job name. You can find more detailed information about job names [TeX output](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) and [How to set the job name](/tex/{{lang.url-fragment}}net/other-options/#how-to-set-the-job-name) paragraphs.

## Inputting the main TeX input file through the terminal

There is [one more constructor](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#aspose.tex.presentation.Device-aspose.tex.TeXOptions) available in the [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/) class that does not allow us to specify the input at all. You might be wondering what such a TeX job would process. In this case, we would need to use an input terminal. The TeX engine will prompt us to enter the file name from the terminal.

Here is the code:

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-MainInputTerminal.py" >}}

Set `ASPOSE_TEX_INPUT_DIR` to a folder containing the following plain TeX file named `hello-world.tex` (default folder: `input`):

```tex
Hello, World!
\end
```

This terminal example uses `TeXConfig.object_tex()`. When prompted, enter `hello-world.tex` and press Enter, or supply that filename through standard input. The job creates `hello-world.xps` and `hello-world.log`.
