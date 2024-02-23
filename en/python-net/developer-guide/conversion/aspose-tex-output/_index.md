---
title: Aspose.TeX's output interface | Python
linktitle: Aspose.TeX's output interface
type: docs
weight: 16
url: /python-net/aspose-tex-output/
description: Here is an explanation of the conversion functionality of the Aspose.TeX API solution for Python, with TeX as the output format, along with some code examples.
submenu: menu-tex-for-python-net
---


> For formal definitions of I/O implementation, please refer to the [API reference](https://reference.aspose.com/tex/python-net/aspose.tex.io/) of **Aspose.TeX for Python**.

## The idea behind the output directory

Aspose.TeX defines a directory as a mapping between names and bulks of data, where the bulks of data can be files, streams, arrays, or other types of data. The API allows for the specification of separate input and output working directories. For the output, the API provides the general [IOutputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/ioutputworkingdirectory/) interface, which can be implemented by the user for their specific needs. Additionally, the API provides ready-to-use implementations, which will be discussed below. The *IOutputWorkingDirectory* interface extends [IInputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/), as the engine may first create and write a file, and then read it back. The interface includes the [get_output_file()](https://reference.aspose.com/tex/python-net/aspose.tex.io/ioutputworkingdirectory/get_output_file/#str) method, which returns the stream to write to, in contrast to the [get_file()](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/get_file/#str-bool) method, which returns the stream to read from.

### Saving the output as a file in the disk file system

As mentioned [above](/tex/net/latex-to-png/), the [output_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/output_working_directory/) is commonly set as an instance of the [OutputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputfilesystemdirectory/) class.

Here's how we would set it:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-OutputFileSystemDirectory.py" >}}

This particular use case is straightforward, so there is no need to delve into it further.

### Saving the output as a ZIP archive file.

Another option is to create a file or stream and use it as a ZIP archive to store the output files. Here is an example:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-OutputZipDirectory.py" >}}

To begin, we create an output stream for the ZIP file. Then, after creating the conversion options, we set the *output_working_directory* option to be an instance of the [OutputZipDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputzipdirectory/) class.

## The idea behind the output terminal

The terminal output is another important aspect of the output. For this, **Aspose.TeX for Python** defines the general [IOutputTerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/ioutputterminal/) interface, which has a single property that returns an instance of the [TerminalWriter](https://reference.aspose.com/tex/python-net/aspose.tex.io/terminalwriter/) implementation. The available implementations will be discussed below.

### Writing the terminal output to the console

To achieve this, we need to set the [terminal_out](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/terminal_out/) option as an instance of the [OutputConsoleTerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputconsoleterminal/) class.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-OutputConsoleTerminal.py" >}}

Once again, this is the default value of the option, so there is no real need to specify it. Therefore, this section is provided solely for demonstration purposes.

### Writing terminal output to a file

In contrast to the input terminal, **Aspose.TeX for Python** includes an implementation of the *IOutputTerminal* interface that enables us to write the terminal output to a file within a specified output directory.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-OutputFileTerminal.py" >}} 

In this case, we instruct the TeX engine to write the terminal output to a file named [<job_name>](/tex/net/tex-io/#tex-output).trm, which will be located in the same output directory as the rest of the output. However, this is not mandatory. We can also provide any other instance of an implementation of *IOutputTerminal* to the constructor.