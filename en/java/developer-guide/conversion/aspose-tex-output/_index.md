---
translation: true
template: /templates/_template-java.md
title: Aspose.TeX's output interface | Java
linktitle: Aspose.TeX's output interface
weight: 16
url: /java/aspose-tex-output/
description: Conversion functionality of Aspose.TeX API solution for Java with TeX, as an output format is explained here with the code examples.
lastmod: "2024-09-20"
---

{{<section overview>}}

Please, refer to **Aspose.TeX for Java** [API reference](https://reference.aspose.com/tex/java/com.aspose.tex/) for formal definitions of I/O implementation.

The file system, ZIP and terminal examples typeset `hello-world.tex` to XPS. Set `inputDirectory` to a folder containing the TeX file and `outputDirectory` to an existing output folder. For ZIP output, set `outputZip` to a `java.nio.file.Path` in an existing folder. Import the Aspose.TeX classes used in the selected snippet, `com.aspose.tex.rendering.XpsDevice`, and the relevant `java.io` and `java.nio.file` classes. The calling method must handle or declare exceptions. Apply a license as described in the [licensing guide](/tex/{{lang.url-fragment}}java/licensing/) to avoid evaluation restrictions.

## The concept of the output directory

Since I/O primitives of the TeX language can only deal with file names, Aspose.TeX defines a directory as a mapping between names and bulks of data. The bulks of data are supposed to be files, streams, arrays, or whatever else.The API allows us to specify the input and output working directories separately. It provides the general [IOutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/) interface for the output, which the user can implement for their own purposes. It also provides its own implementations, which will be discussed below. The interface extends [IInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/), since the engine may first create and write a file, and then read it back. The interface's own method [getOuputFile()](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/#getOutputFile-java.lang.String-java.lang.String:A-) returns the stream to write to, as opposed to the stream to read returned by [getFile()](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-).

### Writing file output to the disk file system

As we mentioned [above](/tex/{{lang.url-fragment}}/java/conversion/), the most common value for the [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--) would likely be an instance of the [OutputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputfilesystemdirectory/) class.

Here's how we would set it:

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputFileSystemDirectory.java" >}}

This use case is quite simple, so we won't dwell on it for a long time.

### Writing file output to a ZIP archive

We can also create a file (or stream) and let the TeX engine use it as a ZIP archive to store the output files. Here it is:

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputZipDirectory.java" >}}

First, we create an output stream for the ZIP file. Then, after creating the conversion options, we set the [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--) option to be an instance of the [OutputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputzipdirectory/) class. The example stores `hello-world.xps` and `hello-world.log` in the archive. After the job, call `finish()` on the output directory before closing the underlying stream. The snippets keep their streams and working directories open until the job finishes and close them afterward.

## The concept of the output terminal

There's another important part of the output --- the terminal output. As for this one, **Aspose.TeX for Java** defines the general [IOutputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputterminal/) interface as having two methods. One of them returns a [BufferedWriter](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedWriter.html) instance. Another one returns an [OutputStream](https://docs.oracle.com/javase/6/docs/api/java/io/OutputStream.html) instance as the underlying stream. Provided implementations of the interface are discussed below.

### Writing terminal output to the console

To do this, we need to set the [TerminalOut](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getTerminalOut--) option to be an instance of the [OutputConsoleTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/outputconsoleterminal/) class.

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputConsoleTerminal.java" >}}

`OutputConsoleTerminal` is the default value of this option. The example explicitly selects it and writes terminal output to the console during conversion. All four examples use noninteractive execution; the file system and ZIP examples capture terminal output in memory.

### Writing terminal output to a file

Unlike the input terminal, **Aspose.TeX for Java** provides an implementation of the [IOutputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputterminal/), which allows us to write the terminal output to a file in some output directory.

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputFileTerminal.java" >}}

Set the output working directory before constructing `OutputFileTerminal`. It writes terminal output to [<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trm, here `hello-world.trm`, in that directory. This terminal file is separate from the TeX transcript `hello-world.log`. To write terminal output elsewhere, pass a different [IOutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/) implementation to the constructor.