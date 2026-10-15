---
translation: true
template: /templates/_template-java.md
title: LaTeX to image | Java
linktitle: LaTeX to image
weight: 10
url: /java/latex-to-image/
aliases: 
- /java/latex-to-png/
- /java/latex-to-svg/
keywords: latex to png, latex png, latex to image, latex image, latex to jpg, latex jpg, latex to jpeg, latex jpeg, latex to tiff, latex tiff, latex to bmp, latex bmp
description: To convert TeX to image formats using Aspose.TeX API solution for Java learn this article that describes how to do this and the code examples.
lastmod: "2024-09-20"
---

{{<section overview>}}

**Aspose.TeX for Java** provides features for converting LaTeX files to a number of raster image formats.

## How to convert LaTeX to PNG

Let's take a closer look at the Java code providing the simplest way to convert LaTeX to PNG format.

Set `inputFile` to the full path of your LaTeX file, such as `hello-world.ltx`, and `outputDirectory` to an existing output folder. Import the classes from `com.aspose.tex` and `com.aspose.tex.rendering` used in each snippet. The calling method must handle or declare exceptions. Apply a license as described in the [licensing guide](/tex/{{lang.url-fragment}}java/licensing/) to avoid evaluation restrictions. The examples select noninteractive processing and close output resources. The PNG example sets the resolution to 300 DPI. For the single-page input `hello-world.ltx`, the automatic output files are `hello-world.png`, `hello-world.jpg`, `hello-world.tif`, `hello-world.bmp`, or `hello-world.svg`, depending on the selected format.

{{< gist "aspose-com-gists" "9d6b3df9df43d8caf00a0d519c504cf5" "Example-ConvertLaTeXToPNG-Simplest.java" >}}

So, the first thing we need to do (sometimes not the very first, as we will find out later) is to create an instance of the [TeXOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/) class. The only static method that does this is [consoleAppOptions()](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#consoleAppOptions-com.aspose.tex.TeXConfig-), so let's not bother with the meaning of its name. The method takes the [objectLaTeX() instance](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/#objectLaTeX--) of the [TeXConfig](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/) class, which is exactly suitable for converting a [LaTeX file](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). This configuration instructs the Object TeX engine to load the Object LaTeX format and to be ready to accept the LaTeX file. Object LaTeX format is actually just the [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/) format, except that it uses [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) specific primitives to set up the page metrics.

The first of the required options is [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--) which defines the space, or area, where the TeX output will be written. [Here](/tex/{{lang.url-fragment}}java/aspose-tex-output/) are the details about the output directory concept in **Aspose.TeX for Java**. In this example, we use the [OutputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputfilesystemdirectory/) class, which allows us to write the output to the specified directory, or folder.

The second option is a [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/saveoptions/) class instance which will control the transformation of the [object model](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) to the target format. Since we are converting LaTeX to PNG, it's the [PngSaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/pngsaveoptions/) class instance, which allows us to specify the resolution of the output images.

Next, we need to create an instance of the [TeXJob](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/) class. Wanting to convert a LaTeX file stored in the file system, we use [this](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#TeXJob-java.lang.String-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-) version of the constructor. We should specify the full path to the file. Otherwise, the engine will look for it in the current directory (which is defined [here](https://docs.oracle.com/javase/7/docs/api/java/io/File.html)) and most likely will not find it. Nevertheless, we may omit the extension if our file has the *.tex* one. The engine will append it automatically. The second argument of the constructor is a [Device](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/device/) class instance. Since we are converting LaTeX to PNG, it's an [ImageDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/imagedevice/) class (which is common to all supported image formats) instance. As the last argument, we pass the recently prepared conversion options.

All that we have to do now is to [run](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#run--) the job.

Regardless of whether the run was successful or not, the first result that we'll see will be the terminal output. In case of success, it looks something like this:


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

We will find other products of the engine's run in the folder that we specified as the output directory. Those will be the transcript (.log) file and, **Voila!**, the main output PNG image file(s).

## An alternative way to write the main output PNG file(s)

There is another way to get image data as an array of byte arrays, each array in the second dimension represents image data for a separate page.

{{< gist "aspose-com-gists" "9d6b3df9df43d8caf00a0d519c504cf5" "Example-ConvertLaTeXToPNG-Alternative.java" >}}

The manual example also requires `java.nio.file.Files` and `java.nio.file.Paths`. It saves page data from `ImageDevice.getResult()` as `page-1.png`, `page-2.png`, and so on. Because it sets `deviceWritesImages(false)`, automatic PNG output is disabled and the manually saved pages are not duplicated in the output directory. This differs from [PDF stream output](/tex/{{lang.url-fragment}}java/latex-to-pdf/#an-alternative-way-to-write-the-main-output-pdf-file), where the stream defines the destination of a single PDF document.

## About input options

In case our main input file requires dependencies, for example, packages, that are not included in the basic LaTeX system and supported packages, we MUST set the [RequiredInputDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getRequiredInputDirectory--) option the similar way we set the [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--) option and put the dependencies in that directory. Dependencies may be arbitrarily organized in subdirectories. In case we have our own files to include along the typesetting process, say external graphics files, we MUST also set the [InputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getInputWorkingDirectory--) using the path to the location where those files are collected. We may also place the main input file somewhere inside the input directory and pass the relative path to the `TeXJob` constructor (or specify no path at all if the main input file is in the root). [Here](/tex/{{lang.url-fragment}}java/aspose-tex-input/) are the details about the input directory concept in **Aspose.TeX for Java** and provided implementations.

Other TeX job options are discussed [here](/tex/{{lang.url-fragment}}java/other-options/).

**You may also check out the free LaTeX-to-PNG conversion [web app](https://products.aspose.app/tex/conversion/latex-to-png) built based on [Aspose.TeX for .NET](https://products.aspose.com/tex/net/) API. [Here](https://products.aspose.com/tex/java/) is the Java version page.**

Below, we discuss the LaTeX conversion to other supported raster image formats. We won't go into details just because there aren't actually any details. The only difference is in the type of the [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getSaveOptions--) property in the conversion options.

## How to convert LaTeX to JPG

{{< gist "aspose-com-gists" "9d6b3df9df43d8caf00a0d519c504cf5" "Example-ConvertLaTeXToJPEG.java" >}}

**You may also check out the free LaTeX-to-JPG conversion [web app](https://products.aspose.app/tex/conversion/latex-to-jpg) built based on [Aspose.TeX for .NET](https://products.aspose.com/tex/net/) API. [Here](https://products.aspose.com/tex/java/) is the Java version page.**

## How to convert LaTeX to TIFF

{{< gist "aspose-com-gists" "9d6b3df9df43d8caf00a0d519c504cf5" "Example-ConvertLaTeXToTIFF.java" >}}

**You may also check out the free LaTeX-to-TIFF conversion [web app](https://products.aspose.app/tex/conversion/latex-to-tiff) built based on [Aspose.TeX for .NET](https://products.aspose.com/tex/net/) API. [Here](https://products.aspose.com/tex/java/) is the Java version page.**

## How to convert LaTeX to BMP

{{< gist "aspose-com-gists" "9d6b3df9df43d8caf00a0d519c504cf5" "Example-ConvertLaTeXToBMP.java" >}}

**You may also check out the free LaTeX-to-BMP conversion [web app](https://products.aspose.app/tex/conversion/latex-to-bmp) built based on [Aspose.TeX for .NET](https://products.aspose.com/tex/net/) API. [Here](https://products.aspose.com/tex/java/) is the Java version page.**


## How to convert LaTeX to SVG

And yet another supported target format is [**SVG**](https://en.wikipedia.org/wiki/SVG). **Scalable Vector Graphics (SVG)** is an XML-based vector image format for defining two-dimensional graphics, having support for interactivity and animation.

**SVG** images are defined in a vector graphics format and stored in XML text files. This means that **SVG** images can be scaled in size without loss of quality, and **SVG** files can be searched, indexed, scripted, and compressed. The XML text files can be created and edited with text editors or vector graphics editors. Thay are rendered by the most-used web browsers.

Also, there is the [**Aspose.SVG**](https://products.aspose.com/svg/) library that has various features based on the **SVG** format. These include creating, loading, editing and converting **SVG** documents.

The conversion to SVG is just as simple as the [conversion to raster image formats](/tex/{{lang.url-fragment}}java/latex-to-image/), except that in addition to the [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getSaveOptions--), we have to change the device to an instance of the [SvgDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/svgdevice/) class.

{{< gist "aspose-com-gists" "9d6b3df9df43d8caf00a0d519c504cf5" "Example-ConvertLaTeXToSVG-Simplest.java" >}}

**You may also check out the free LaTeX-to-SVG conversion [web app](https://products.aspose.app/tex/conversion/latex-to-svg) built based on [Aspose.TeX for .NET ](https://products.aspose.com/tex/net/). [Here](https://products.aspose.com/tex/java/) is the Java version page.**