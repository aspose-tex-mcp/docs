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

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-InputFileSystemDirectory.py" >}}

This particular use case is fairly straightforward, so we can move on from it now.

### Retrieving file input from a ZIP archive

Another option is to store the input files in a ZIP archive and treat it as an input directory. In such a scenario, the following steps should be followed:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-InputZipDirectory.py" >}}

To begin with, we create the stream that contains the ZIP file. Subsequently, after creating the conversion options, we assign an instance of the [InputZipDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputzipdirectory/) class to the [input_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/input_working_directory/) property. The second parameter of the constructor represents the base path within the archive. If we desire the entire archive to function as the input directory, we should provide an empty string as the argument.

## The idea behind the input terminal

Now let's consider the concept of terminal input. **Aspose.TeX for Python** defines the general [IInputTerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputterminal/) interface specifically for this purpose, which includes a single property that returns an instance of [TerminalReader](https://reference.aspose.com/tex/python-net/aspose.tex.io/terminalreader/) implementation. The available implementations will be discussed later on.

### Getting terminal input from the console

To achieve this, we need to assign an instance of the [InputConsoleTerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputconsoleterminal/) class to the [terminal_in](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/terminal_in/) option.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-InputConsoleTerminal.py" >}}

However, to be honest, this is the default value for the option, so there is no real need to explicitly specify it. Given the absence of other implementations, this section is purely for demonstration purposes.

In theory, if we have an interactive TeX file (or script) with predictable behavior, it might be desirable to implement a version of the input terminal that includes a corresponding script to respond to the TeX engine's requests. Feel free to give it a try when you have the opportunity!
