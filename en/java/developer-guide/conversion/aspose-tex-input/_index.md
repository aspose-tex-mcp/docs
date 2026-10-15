---
translation: true
template: /templates/_template-java.md
title: Aspose.TeX's input interface | Java
linktitle: Aspose.TeX's input interface
weight: 15
url: /java/aspose-tex-input/
description: Conversion functionality of Aspose.TeX API solution for Java with TeX, as an input format is explained here with the code examples.
lastmod: "2024-09-20"
---

{{<section overview>}}

Please, refer to **Aspose.TeX for Java** [API reference](https://reference.aspose.com/tex/java/com.aspose.tex/) for formal definitions of I/O implementation.

The file system and ZIP examples typeset `hello-world.tex` to `hello-world.xps`. Set `inputDirectory` to a folder containing the TeX file and `outputDirectory` to an existing output folder. For ZIP input, set `inputZip` to a `java.nio.file.Path` pointing to an archive containing `in/hello-world.tex`. Import the Aspose.TeX classes used in the selected snippet, `com.aspose.tex.rendering.XpsDevice`, and the relevant `java.io` and `java.nio.file` classes. The calling method must handle or declare exceptions. Apply a license as described in the [licensing guide](/tex/{{lang.url-fragment}}java/licensing/) to avoid evaluation restrictions.

## The concept of the input directory

Since I/O primitives of the TeX language can only deal with file names, **Aspose.TeX for Java** defines a directory as a mapping between names and bulks of data. The bulks of data are supposed to be files, streams, arrays, or whatever else.The API allows us to specify the input and output working directories separately. It provides the general [IInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/) interface, which the user can implement for their own purposes. It also provides its own implementations, which will be discussed below. The interface defines the [getFile()](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-) method, which returns the data stream and determines the full name of the file, while taking some, hypothetically different, name as the first argument, which, in fact, is the mapping key.

### Getting file input from the disk file system

Here's how we would do it:

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-InputFileSystemDirectory.java" >}}

This use case is quite simple, so we won't dwell on it for a long time.

### Getting file input from a ZIP archive

We can also put the input files in a ZIP archive and consider it an input directory. In this case, we should proceed as follows:

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-InputZipDirectory.java" >}}

First, we create the stream containing the ZIP file. Then, after creating the conversion options, we set the [InputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getInputWorkingDirectory--) option to be an instance of the [InputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputzipdirectory/) class. The second argument of the constructor is the base path inside the archive. If we want the entire archive to be an input directory, we should pass the empty string. The example keeps the ZIP stream and input directory open until the TeX job finishes, then closes them. It uses noninteractive execution and captures terminal output in memory.

## The concept of the input terminal

Now let's remember that there is also the terminal input. As for this one, **Aspose.TeX for Java** defines the general [IInputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/iinputterminal/) interface as having two methods. One of them returns a  [BufferedReader](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedReader.html) instance. Another method returns an [InputStream](https://docs.oracle.com/javase/6/docs/api/java/io/InputStream.html) as the underlying stream. Provided implementations of the interface are discussed below.

### Getting terminal input from the console

To do this, we need to set the [TerminalIn](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getTerminalIn--) option to be an instance of the [InputConsoleTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/inputconsoleterminal/) class.

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-InputConsoleTerminal.java" >}}

`InputConsoleTerminal` is the default value of this option. This snippet only demonstrates terminal configuration; it does not run a job. A job that requests terminal input needs input from the user or a custom terminal implementation. The file system and ZIP examples above use noninteractive execution with complete input files.

Theoretically, if we have an interactive TeX file (or script) with predictable behavior, we may want to implement a version of the input terminal that would contain a complementary script for responding to the TeX engine's requests. Try your hand when you have time!