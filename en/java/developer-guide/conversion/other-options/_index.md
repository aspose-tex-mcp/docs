---
translation: true
template: /templates/_template-java.md
title: Other managing TeX options | Java
linktitle: Other options
weight: 17
url: /java/other-options/
description: Conversion functionality of Aspose.TeX API solution for Java lets set the initial interaction mode in which the engine starts. Here are some code examples.
lastmod: "2024-09-20"
---

{{<section overview>}}


Each snippet creates LaTeX `TeXOptions` and configures one option. Pass these options to a `TeXJob`, supply suitable LaTeX input, and set an output working directory before running the job. Import `com.aspose.tex.TeXOptions`, `TeXConfig` and the classes used in the selected snippet: `Interaction`, `com.aspose.tex.rendering.XpsSaveOptions` or `PdfSaveOptions`, and `java.util.Calendar`/`GregorianCalendar` for the date example. Handle or declare exceptions in the calling method. The rasterization and font-subsetting snippets use `PdfSaveOptions`; render with a compatible `PdfDevice`. Apply a license as described in the [licensing guide](/tex/{{lang.url-fragment}}java/licensing/).

## How to set the interaction mode

As we mentioned [here](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes), **Aspose.TeX for Java** allows us to set the initial interaction mode in which the engine starts. Here's how we do it:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-InteractionMode.java" >}}

## How to set the job name

When we pass the main input file as a file name, we get output files with the same name, although with other extensions. The TeX engine calls the input file's name the *job name* and uses it for output files, except in cases when auxiliary files with explicitly specified other names are written. When we pass the main input file as a [stream](/tex/{{lang.url-fragment}}java/other-ways-of-main-input/#providing-the-main-input-file-to-the-tex-engine-as-a-stream), the TeX engine uses the default job name, which is *texput*.
In both cases, we can override the job name by assigning the appropriate conversion option.

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-JobName.java" >}}

## How to "stop time"

LaTeX has a feature to automatically generate a title from some definitions in the preamble. This title normally contains the current date. We may wish to freeze the date in some desired value. Here's how it can be done:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-DateTime.java" >}}

## How to ignore missing packages

A LaTeX file may reference packages that are unavailable in the Aspose.TeX for Java library. The engine normally stops with an error when trying to load such a package. Use `ignoreMissingPackages(true)` to skip unavailable packages. This does not provide the commands those packages would define; the input must not depend on those commands.

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-IgnoreMissingPackages.java" >}}

## How to avoid building ligatures

Normally, the TeX engine builds ligatures for certain pairs of characters if the font provides the data required to do so. We can instruct the engine to skip ligature building with the following code:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-NoLigatures.java" >}}

## How to repeat the job

As we have mentioned [above](/tex/{{lang.url-fragment}}net/latex-io/#latex-input) regarding labels and references, there are cases when we may want to run the same job twice. Here is how it can be done:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-Repeat.java" >}}

## How to turn math formulas to raster images

Sometimes we may need to have math formulas as raster images rather than typed in fonts. The following option can serve for this purpose:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RasterizeFormulas.java" >}}

## How to turn graphics to raster images

The ObjectTeX engine allows us to include graphic files in raster formats (PNG and JPG) as well as PS(EPS) and XPS(OXPS) formats. The last two formats usually contain vector elements and texts. To have them rasterized and included as solid images, we can use the following option:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RasterizeIncludedGraphics.java" >}}

## How to subset fonts

Font subsetting limits embedded fonts to the glyphs used in the document. Its effect on output size depends on the font and how the output device embeds it. Assign saving options before enabling `subsetFonts(true)`, as shown below:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-SubsetFonts.java" >}}