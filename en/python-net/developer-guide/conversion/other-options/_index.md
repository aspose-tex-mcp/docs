---
title: Other managing TeX options | Python
linktitle: Other options
type: docs
weight: 17
url: /python-net/other-options/
description: Aspose.TeX API solution for Python includes conversion functionality that allows you to set the initial interaction mode in which the engine starts.
submenu: menu-tex-for-python-net
---

## Setting the interaction mode

As mentioned [in TeX interaction parapraph](/tex/net/tex-io/#tex-interaction-modes), **Aspose.TeX for Python** provides the capability to set the initial interaction mode in which the engine starts. Here is an example of how it can be done:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-InteractionMode.py" >}}

## Setting the job name

When the main input file is provided as a file name, the resulting output files will have the same name but with different extensions. The TeX engine refers to the input file's name as the *job name* and uses it for the output files. The exception is auxiliary files with explicitly specified file names. However, when the main input file is passed as a [stream](/tex/python-net/other-ways-of-main-input/#supplying-the-main-input-file-as-a-stream), the TeX engine uses the default job name, which is *texput*. In both scenarios, overriding the job name by assigning the appropriate conversion option is possible.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-JobName.py" >}}

## "Stopping time"

To automatically generate a title from certain definitions in the preamble, LaTeX offers a feature that typically includes the current date. However, there might be instances where we want to fix the date to a specific value. Here is a method to achieve that:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-DateTime.py" >}}

## Ignoring missing packages

If we have a LaTeX file that includes references to packages that are not supported by the **Aspose.TeX for Python** library, the TeX engine will encounter an error and stop when attempting to load these packages. To prevent this, we can utilize the following option:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-IgnoreMissingPackages.py" >}}

## How to avoid building ligatures

By default, the TeX engine constructs ligatures for specific character pairs if the font contains the necessary data. However, we can instruct the engine to bypass ligature construction using the following code:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-NoLigatures.py" >}}

## Repeating the job

As mentioned [in LaTeX input file paragraph](/tex/net/latex-io/#latex-input-file), labels and references, there are situations where we may need to run the same job twice. Here is a method to accomplish that:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-Repeat.py" >}}

## Turning math formulas into raster images

If there is a need to convert math formulas into raster images instead of rendering them with fonts, the following option can be used for this purpose:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-RasterizeFormulas.py" >}}

## Turning graphics into raster images

The ObjectTeX engine provides the capability to include graphic files in raster formats such as PNG and JPG, as well as PS (EPS) and XPS (OXPS) formats. The latter two formats typically contain vector elements and text. If we want to rasterize and include them as solid images, we can utilize the following option:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-RasterizeIncludedGraphics.py" >}}

## Subsetting fonts

If we desire to decrease the size of the output file, we can employ font subsetting, which entails that the fonts in the resulting document will not include data for those glyphs that are not present in the document. Here is a solution to achieve this:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-SubsetFonts.py" >}}