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

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-InputStream.py" >}}

Note that all output files will be named `texput`. This is because the engine does not have access to any other name. `texput` is the default job name. You can find more detailed information about job names [TeX output](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) and [How to set the job name](/tex/{{lang.url-fragment}}net/other-options/#how-to-set-the-job-name) paragraphs.

## Inputting the main TeX input file through the terminal

There is [one more constructor](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#aspose.tex.presentation.Device-aspose.tex.TeXOptions) available in the [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/) class that does not allow us to specify the input at all. You might be wondering what such a TeX job would process. In this case, we would need to use an input terminal. The TeX engine will prompt us to enter the file name from the terminal.

Here is the code:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-MainInputTerminal.py" >}}

As soon as it's run, the engine will pause and wait for us to input the file name (with or without a path, and with or without an extension):


![Terminal Window](/tex/images/python-net/.png)

And here is how it would appear on the output terminal (console):

```text
This is ObjectTeX, Version 3.1415926-1.0 (Aspose.TeX 21.8)
entering extended mode
**<path_to_the_file>/hello-world.ltx
(<path_to_the_file>/hello-world.ltx
LaTeX2e <2011/06/27>
(article.cls
Document Class: article 2007/10/19 v1.4h Standard LaTeX document class
(size10.clo))
No file hello-world.aux.
[1]
(<output_directory>\hello-world.aux) )
Output written on hello-world.xps (1 page).
Transcript written on hello-world.log.
```