---
translation: true
template: /templates/_template-python-net.md
title: LaTeX to image | Python
linktitle: LaTeX to image
weight: 10
url: /python-net/latex-to-image/
aliases: 
- /python-net/latex-to-png/
- /python-net/latex-to-svg/
keywords: latex to png, latex png, latex to image, latex image, latex to jpg, latex jpg, latex to jpeg, latex jpeg, latex to tiff, latex tiff, latex to bmp, latex bmp
description: To convert TeX to image formats using Aspose.TeX API solution for Python learn this article to see that describes how to do this and the code examples.
lastmod: "2024-09-20"
---

{{<section overview>}}

**Aspose.TeX for Python** provides us with the capability to convert LaTeX files into various raster image formats.

## Converting LaTeX to PNG

Now, let's examine the Python code that offers the most straightforward approach to converting LaTeX to PNG format in depth.

Set `ASPOSE_TEX_INPUT_FILE` to your LaTeX file and `ASPOSE_TEX_OUTPUT_DIR` to the output directory, or edit the paths in the example. The defaults are `hello-world.ltx` and `output`. Apply a license first as described in [Licensing](/tex/{{lang.url-fragment}}python-net/licensing/). The examples resolve additional input files beside the main document and use noninteractive processing.

{{< gist "aspose-com-gists" "3616f5e300517031e6a4ae4158e24776" "Aspose.TeX.Examples-Conversion-LaTeXToPng-Simplest.py" >}}

To start with, we need to create an instance of the [TeXOptions](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/) class using the [console_app_options()](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/console_app_options/#aspose.tex.TeXConfig)   method. Don't worry about the name, it's just the static method that creates the instance. This method takes the [object_latex](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_latex/) instance of the [TeXConfig](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/) class, which is perfect for converting a [LaTeX file](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). This configuration sets up the Object TeX engine to load the Object LaTeX format and be ready to process the LaTeX file. The Object LaTeX format is essentially the same as the [LaTeX format](/tex/{{lang.url-fragment}}net/what-is-latex/), but it uses [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) specific primitives to define the page metrics.

The first of the necessary options is [output_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/output_working_directory/), which specifies the location where the TeX output will be saved. If interested, you can learn more information about the concept of the [output directory in **Aspose.TeX for Python**](/tex/{{lang.url-fragment}}python-net/aspose-tex-output/). In this particular example, we utilize the [OutputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputfilesystemdirectory/) class to write the output to a specific directory or folder.

The second option is an instance of the [SaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/saveoptions/) class, which is responsible for managing the conversion from the [object model](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) to the desired format. In this case, since we are converting LaTeX to PNG, we use the [PngSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.image/pngsaveoptions/) class instance, which allows us to specify the resolution of the output images.

Next, we create an instance of the [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/) class. In this case, since we want to convert a LaTeX file stored in the file system, we use [this version of the constructor](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#str-aspose.tex.presentation.Device-aspose.tex.TeXOptions)  . We need to provide the full path to the file, otherwise, the engine will look for it in the current directory (which is the script's working directory) and may not find it. However, the `.tex` extension can be omitted as the engine will automatically append it. The second argument of the constructor is an instance of the [Device](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/device/) class. Since we are converting LaTeX to PNG, it's an [ImageDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.image/imagedevice/) class instance, which is common to all supported image formats. Finally, we pass the prepared conversion options as the last argument.

Now, all that remains is to [run](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/run/#) the job.

The example captures terminal output in `OutputMemoryTerminal` rather than printing it to the console. The output directory also contains a `.log` transcript. A successful conversion produces a transcript similar to this (version details may differ):


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
Output written on hello-world.png (1 page).
Transcript written on hello-world.log.
```

The results of the engine's work can be found in the output directory that we specified. This will include the transcript file and, most importantly, the main output PNG image file(s).

## An alternative way to write the main output PNG file(s)

There is an alternative method to obtain image data as an array of byte arrays, where each array in the second dimension represents the image data for a separate page.

{{< gist "aspose-com-gists" "3616f5e300517031e6a4ae4158e24776" "Aspose.TeX.Examples-Conversion-LaTeXToPng-Alternative.py" >}}

The example sets `device_writes_images = False` on `PngSaveOptions` before assigning it to `options.save_options`. It writes the returned page bytes as `page-1.png`, `page-2.png`, and so on. The device therefore does not create duplicate PNG files.

## Regarding input options

If our main input file requires dependencies, such as packages that are not included in the basic LaTeX system or supported packages, we need to set the [required_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/) option in a similar way to how we set the *output_working_directory* option and place the dependencies in that directory. The dependencies can be organized in subdirectories as needed. If we have our files to include in the typesetting process, such as external graphics files, we also need to set the [input_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/input_working_directory/) to the location where those files are stored. We can also place the main input file within the input directory and pass the relative path to the `TeXJob` constructor, or specify no path at all if the main input file is in the root directory. There are also more details about the [input directory concept](/tex/{{lang.url-fragment}}python-net/aspose-tex-input/) in **Aspose.TeX** and the provided implementations described.

Also learn the [other TeX job options here](/tex/{{lang.url-fragment}}python-net/other-options/).

**You can also explore the free [web app](https://products.aspose.app/tex/conversion/latex-to-png) for LaTeX-to-PNG conversion, which is developed using the [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**

Below, we will briefly explain the conversion of LaTeX to other supported raster image formats, without diving into too much detail as there are no significant differences. The only variation lies in the type of the [save_options](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/save_options/) property in the conversion options.

## Converting LaTeX to JPG

{{< gist "aspose-com-gists" "3616f5e300517031e6a4ae4158e24776" "Aspose.TeX.Examples-Conversion-LaTeXToJpeg.py" >}}

**You can also explore the free [web app for LaTeX-to-JPG conversion](https://products.aspose.app/tex/conversion/latex-to-jpg), which is developed using the [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**

## Converting LaTeX to TIFF

{{< gist "aspose-com-gists" "3616f5e300517031e6a4ae4158e24776" "Aspose.TeX.Examples-Conversion-LaTeXToTiff.py" >}}

**You can also explore the free [web app for LaTeX-to-TIFF conversion](https://products.aspose.app/tex/conversion/latex-to-tiff), which is developed using the [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**

## Converting LaTeX to BMP

{{< gist "aspose-com-gists" "3616f5e300517031e6a4ae4158e24776" "Aspose.TeX.Examples-Conversion-LaTeXToBmp.py" >}}

**You can also explore the free [web app for LaTeX-to-BMP conversion](https://products.aspose.app/tex/conversion/latex-to-bmp), which is developed using the [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**


## Converting LaTeX to SVG

Another supported target format is [**SVG**](https://en.wikipedia.org/wiki/SVG). **Scalable Vector Graphics (SVG)** is an XML-based vector image format that is used to define two-dimensional graphics. It supports interactivity and animation.

**SVG** images are stored in XML text files and defined in a vector graphics format. This means that **SVG** images can be scaled in size without losing quality, and **SVG** files themselves can be searched, indexed, scripted, and compressed. The XML text files can be created and edited using text editors or vector graphics editors, and they can be rendered by the most commonly used web browsers.

The [**Aspose.SVG**](https://products.aspose.com/svg/) API offers a range of features for working with **SVG**, such as creating, loading, editing, and converting **SVG** documents.

Converting LaTeX to SVG is just as straightforward as [converting to raster image formats](/tex/{{lang.url-fragment}}python-net/latex-to-image/), with the only difference being that the [save_options](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/save_options/) must be set to an instance of the [SvgSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.svg/svgsaveoptions/) class and the device must be changed to an instance of the [SvgDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.svg/svgdevice/) class.

{{< gist "aspose-com-gists" "3616f5e300517031e6a4ae4158e24776" "Aspose.TeX.Examples-Conversion-LaTeXToSvg-Simplest.py" >}}

**You can also explore the free [web app for LaTeX-to-SVG conversion](https://products.aspose.app/tex/conversion/latex-to-svg), which is developed using the [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**