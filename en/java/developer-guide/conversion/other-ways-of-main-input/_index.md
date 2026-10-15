---
translation: true
template: /templates/_template-java.md
title: Other ways to provide main TeX input file | Java
linktitle: Other ways to provide the main TeX input file
weight: 14
url: /java/other-ways-of-main-input/
description: Conversion functionality of Aspose.TeX API solution for Java has a Constructor which accepts a stream as the first argument. Here are some code examples.
lastmod: "2024-09-20"
---

{{<section overview>}}

## Providing the main input file to the TeX engine as a stream

Up to this point, we only knew how to pass the [main input file](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) to the TeX engine as a file name, whether fully specified or in short form, whether with an extension or without it. But there's another [constructor](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#TeXJob-java.io.InputStream-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-) of the `TeXJob` class, which accepts a stream as the first argument. This is convenient if for some reason we have the main input file in a form other than a file on the disk file system. Here's how we can deal with it:

Set `outputDirectory` to an existing output folder. Import the Aspose.TeX classes used in the snippets, `com.aspose.tex.rendering.XpsDevice`, `com.aspose.tex.rendering.XpsSaveOptions` and, for stream input, `java.io.ByteArrayInputStream` and `java.nio.charset.StandardCharsets`. The calling method must handle or declare exceptions. Apply a license as described in the [licensing guide](/tex/{{lang.url-fragment}}java/licensing/) to avoid evaluation restrictions. The stream example contains a complete LaTeX document, so it needs no input working directory. Streams and devices remain open until the job finishes and are closed or disposed afterward.

{{< gist "aspose-com-gists" "889663554934c807ebc90e12d08bc8d0" "Example-StreamInput-LaTeX.java" >}}

When stream input has no explicitly assigned job name, the engine uses the default name *texput*. This example creates `texput.xps` and `texput.log`. Set `options.setJobName(...)` to choose another job name. See [here](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) and [here](/tex/{{lang.url-fragment}}java/other-options/#how-to-set-the-job-name) for details about job names.

## Entering the main TeX input file from the terminal

There's yet another [constructor](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#TeXJob-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-)  of the `TeXJob` class, which doesn't allow us to specify the input at all. So what is such a TeX job going to process, you may wonder? This time we will need an input terminal. The TeX engine will ask us to enter the file name from the terminal.

Set `inputDirectory` to a folder containing a complete LaTeX document named `hello-world.ltx`, and `outputDirectory` to an existing output folder. Run this example in a console, enter `hello-world.ltx` at the `**` prompt and press Enter. It creates `hello-world.xps` and writes terminal output to the console. Both examples use `NonstopMode` for processing, but the terminal constructor still needs the initial filename. For unattended execution, provide an `IInputTerminal` implementation or use file/stream input.

Here is the code:

{{< gist "aspose-com-gists" "889663554934c807ebc90e12d08bc8d0" "Example-MainInputTerminal.java" >}}

As soon as it is run, the engine sticks, waiting for us to enter the file name (with or without a path, with or without an extension):


![Terminal Window](/tex/images/java/Conversion-MainInputTerminal.png)

And this is how it would look on the output terminal which is the console:

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