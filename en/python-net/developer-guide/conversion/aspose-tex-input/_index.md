---
translation: true
template: /templates/_template-python-net.md
title: Aspose.TeX's input interface | Python
linktitle: Aspose.TeX's input interface
weight: 15
url: /python-net/aspose-tex-input/
description: Conversion functionality of Aspose.TeX API solution for Python with TeX, as an input format is explained here with the code examples.
lastmod: "2024-09-20"
---

{{<section overview>}}

> For formal definitions of the I/O implementation in **Aspose.TeX for Python**, please consult the [API reference](https://reference.aspose.com/tex/python-net/aspose.tex.io/).

## The idea behind the input directory

Given that the I/O primitives of the TeX language can only handle file names, **Aspose.TeX for Python** defines a directory as a mapping between names and collections of data. These collections of data can be files, streams, arrays, or any other type. The API allows for separate specification of input and output working directories. It provides the general [InputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputworkingdirectory/) class, which users can implement for their specific needs. Additionally, the API provides built-in implementations, which will be discussed later. The interface includes the [get_file()](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/get_file/#str-bool) method, which retrieves the data stream and determines the full file name based on a given name, which serves as the mapping key.

### Retrieving file input from the disk file system

Here is the approach we would take:

Set `ASPOSE_TEX_OUTPUT_DIR` to an output directory, or use the default `output`. Apply a license first as described in [Licensing](/tex/{{lang.url-fragment}}python-net/licensing/).

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputFileSystemDirectory.py" >}}

Set `ASPOSE_TEX_INPUT_DIR` to a folder containing `hello-world.tex` (default: `input`). The example uses plain TeX with `TeXConfig.object_tex()` and produces `hello-world.xps` and `hello-world.log`. Use this input:

```tex
Hello, World!
\end
```

### Retrieving file input from a ZIP archive

Another option is to store the input files in a ZIP archive and treat it as an input directory. In such a scenario, the following steps should be followed:

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputZipDirectory.py" >}}

Set `ASPOSE_TEX_INPUT_ZIP` to an archive containing `in/hello-world.tex`; the default is `zip-in.zip`. Open it in binary mode (`rb`) and keep the stream open until the job finishes.

To begin with, we create the stream that contains the ZIP file. Subsequently, after creating the conversion options, we assign an instance of the [InputZipDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputzipdirectory/) class to the [input_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/input_working_directory/) property. The second parameter of the constructor represents the base path within the archive. If we desire the entire archive to function as the input directory, we should provide an empty string as the argument.

## The idea behind the input terminal

Now let's consider the concept of terminal input. **Aspose.TeX for Python** defines the general [IInputTerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputterminal/) interface specifically for this purpose, which includes a single property that returns an instance of [TerminalReader](https://reference.aspose.com/tex/python-net/aspose.tex.io/terminalreader/) implementation. The available implementations will be discussed later on.

### Getting terminal input from the console

To achieve this, we need to assign an instance of the [InputConsoleTerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputconsoleterminal/) class to the [terminal_in](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/terminal_in/) option.

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputConsoleTerminal.py" >}}

The example reads a line using the TeX command `\read` and writes it to `texput.xps`. Run it in a terminal and enter a line such as `Terminal input works!`, or supply that line through standard input. `SCROLL_MODE` allows this explicit input request.
