---
title: LaTeX to PDF | Aspose.TeX for Python
linktitle: LaTeX to PDF
type: docs
weight: 11
url: /python-net/latex-to-pdf/
keywords: latex to pdf, latex pdf, convert latex to pdf
description: Learn how to convert TeX to PDF using the Aspose.TeX API solution for Python with this article, which provides a detailed explanation and code examples.
lastmod: "2021-10-14"
sitemap:
    changefreq: "weekly"
    priority: 0.8
submenu: menu-tex-for-python-net
---

## Converting LaTeX to PDF

Now, let's examine the Python code that offers the most straightforward approach to converting LaTeX to PDF format in depth.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToPdf-Simplest.py" >}}

To begin, we need to create an instance of the [TeXOptions](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/) class. The [console_app_options()](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/console_app_options/#aspose.tex.TeXConfig) method is the only static method that accomplishes this, so don't worry about its name. This method takes an [object_latex](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_latex/) instance of the [TeXConfig](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/) class, which is perfect for converting a [LaTeX file](/tex/net/latex-io/#latex-file). This configuration instructs the Object TeX engine to load the Object LaTeX format and be prepared to process the LaTeX file. The Object LaTeX format is essentially the same as the [LaTeX](/tex/net/what-is-latex/) format, but it utilizes [Object TeX](/tex/net/aspose-tex-and-object-tex/#object-tex) specific primitives to define the page metrics.

The first option that needs to be specified is [output_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/output_working_directory/), which determines the location where the TeX output will be saved. If needed, you can find more information on the [concept of the output directory in **Aspose.TeX**](/tex/net/aspose-tex-output/). In this particular case, we utilize the [OutputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputfilesystemdirectory/) class, which enables us to write the output to a designated directory or folder.

The second option requires an instance of the [SaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/saveoptions/) class, which determines how the [object model](/tex/net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) is transformed into the desired format. In our case, as we are converting LaTeX to PDF, it refers to an instance of the [PdfSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfsaveoptions/) class.

To convert a LaTeX file stored in the file system, we need to create an instance of the [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/) class using the [constructor](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#str-aspose.tex.presentation.Device-aspose.tex.TeXOptions) that takes the file's full path as a parameter. If we don't specify the full path, the engine will look for the file in the current directory (which is the script's working directory) and may not find it. However, we can omit the extension if our file has the `.tex` extension, as the engine will automatically append it. The second argument of the constructor is an instance of the [Device](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/device/) class. In our case, since we are converting LaTeX to PDF, it's an instance of the [PdfDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfdevice/) class. Finally, we pass the recently prepared conversion options as the last argument.

Now, all that remains is to [run](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/run/#) the job.

After the execution, regardless of whether it was successful or not, the first thing we will see is the terminal output. If the execution is successful, the output will look similar to this:

```text
This is ObjectTeX, Version 3.1415926-1.0 (Aspose.TeX 21.8)
entering extended mode

(<input_directory>\hello-world.ltx
LaTeX2e <2011/06/27>
(article.cls
Document Class: article 2007/10/19 v1.4h Standard LaTeX document class
(size10.clo))
No file hello-world.aux.
[1]
(<output_directory>\hello-world.aux) )
Output written on hello-world.pdf (1 page).
Transcript written on hello-world.log.
```

In the folder we specified as the output directory, we will find the transcript file and, **here it is!**, the main output PDF file, among other results of the engine's work.

## An alternative way to write the main output PDF file

The *PdfDevice* class has another [constructor](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfdevice/__init__/#io.RawIOBase) that allows us to obtain the resulting PDF file differently.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToPdf-Alternative.py" >}}

The main output PDF file will be named `any-name.pdf` and will be located in the specified directory. However, unlike the [image output](/tex/python-net/latex-to-image/#an-alternative-way-to-write-the-main-output-png-files), there will be no other PDF files in the output directory specified by the conversion options. The exception is if `any-name.pdf` is located in the same file system directory assigned to the *output_working_directory* option using *OutputFileSystemDirectory*.

## About input options

If our main input file requires dependencies, such as packages that are not included in the basic LaTeX system and supported packages, it is necessary to set the [required_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/) option in a similar way as we set the *output_working_directory* option and place the dependencies in that directory. The dependencies can be organized in subdirectories as desired. Additionally, if we have our own files to include in the typesetting process, such as external graphics files, we must also set the [input_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/input_working_directory/) using the path to the location where those files are stored. We can also place the main input file inside the input directory and specify the relative path in the `run()` method, or specify no path at all if the main input file is in the root. For more details about the input directory concept in **Aspose.TeX for Python** and the provided implementations, please refer to [here](/tex/python-net/aspose-tex-input/).

There are also [other TeX job options](/tex/python-net/other-options/) discussed.

**You can also explore the free [web app for LaTeX-to-PDF conversion](https://products.aspose.app/tex/conversion/latex-to-pdf), which is developed using the [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**