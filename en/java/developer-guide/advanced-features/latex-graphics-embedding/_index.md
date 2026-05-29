---
translation: true
template: /templates/_template-java.md
title: Embedding external graphics in LaTeX | Aspose.TeX for Java
linktitle: LaTeX embedded graphics
weight: 18	
url: /java/latex-graphics-embedding/
keywords: includegraphics latex, latex embed base64 graphics, latex base64 encoded graphics, write18, shell-escape, latex shell command
description: Learn how to embed external images (PNG, JPEG, EPS) into LaTeX documents using Aspose.TeX for Java. Master graphics path resolution via custom memory and file system streams.
lastmod: "2026-05-28"
---

{{<section overview>}}

## An alternative way to include images

Some TeX/LaTeX systems enable the inclusion of images that are not stored externally relative to the LaTeX file itself; instead, these images are embedded directly within the LaTeX file. However, since TeX/LaTeX files are plain text and cannot contain binary data, we need a method to represent binary data in a text format. This means that binary data must be encoded into a textual representation. The challenge is that a TeX engine cannot directly interpret these encoded images. In the end, images are included using the well-known `\includegraphics` command from the `graphicx` package, but this command is limited to handling external image files. Therefore, an external image file (along with an additional intermediary file) must still be created outside the LaTeX file, but that will only occur during typesetting. The advantage is that you only need to distribute the LaTeX file itself, rather than a set of files.

Alright, suppose we have somehow embedded an encoded image in the LaTeX file. How do we decode this image? Unfortunately, we can't decode it directly by reading it from the LaTeX file and writing it to an external image file. Instead, the text string that represents the encoded image must first be written to an external text file, which can then be decoded to generate the image file.

At this point, we can outline the following steps to achieve the desired outcome:

1. Encode the image.
2. Insert the text string representing the image data into the LaTeX file.
3. Write the text string representing the image data to an external file.
4. Decode the external file created in Step 3.
5. Include the decoded image.

The first two steps are carried out by the author of the LaTeX file. The TeX engine will handle the remaining steps, as long as it is properly instructed, of course.

Let's move on to **Step 1**. How can we encode our image to obtain a string of characters? One of the methods for doing this (and likely the most popular) is **Base64**.

## Encoding binary data using Base64

[**Base64**](https://en.wikipedia.org/wiki/Base64) is a group of binary-to-text encoding schemes that transforms binary data into a sequence of printable characters, using a set of 64 unique characters. Specifically, the source binary data is processed in groups of 6 bits, with each group mapped to one of 64 unique characters. Like all binary-to-text encoding schemes, Base64 is intended to facilitate the transmission of data stored in binary formats over channels that predominantly support text content.

This brief explanation shows that **Base64** is exactly what we need. To encode an image file to **Base64**, you can use a command line utility (if available on your operating system), standard or third-party features of nearly every programming language, or online tools like [Base64.guru](https://base64.guru/converter/encode/file) or similar.

## Embedding the encoded image into the LaTeX file

The string of characters generated from the encoding process must be placed in the standard LaTeX `filecontents` environment within the preamble of a LaTeX file, as follows:

```tex
\documentclass{article}
\begin{filecontents*}[overwrite]{sample-image.64}
iVBORw0KGgoAAAANSUhEUgAAAPgAAABdCAYAAAH/B5vAAAAAGXRFWHRTb2Z0d2FyZQBBZ......
\end{filecontents*}
\begin{document}
...
\end{document}
```

Here it is! **Step 2** is complete. We have successfully embedded the image within the LaTeX file! But what will happen when we run the typesetting of this file with LaTeX?

A LaTeX processor will write the string of characters from the environment to an external file named `sample-image.64`. Because of the `overwrite` option, the file will be overwritten if it already exists (e.g., if it was created during a previous run). This is how **Step 3** is also accomplished!

## Decoding a base64 string

**Step 4** of our plan is where the differences in TeX implementations come into play. Decoding a Base64 character string is performed by means of a more common thing known as the `\write18` feature.

### `\write18`

In classic TeX engines, `\write<number>(<token list>)` is the primitive used to write a *list of tokens*. When used, this primitive is followed by an integer. If the integer is negative, the tokens are written to the transcript (log) file. If the integer is greater than `15`, the tokens are sent to the terminal. If the integer falls within the range of `0..15`, the tokens are written to a file whose name is specified by a preceding occurrence of the `\openout` primitive. The `\openout<4-bit integer>=<file name>` primitive associates a file name with a number.

Newer TeX implementations, such as PDF TeX, allow the use of `\write18`. In this case, they interpret the `<token list>` as a command line to be executed in the operating system shell. Since this feature obviously poses a potential security risk, you might sense a hint of mystery whenever it is referenced in TeX-related documentation or on the Internet. For this reason, the PDF TeX/LaTeX executables offer command options to control acess to this feature.

Typically, there are three levels of accessibility: disabled, enabled with restrictions, and fully enabled.

In **Aspose.TeX**, there is a TeX job option called `ShellMode`, which can take one of two possible values: `NoShellEscape` and `ShellRestricted`. The `NoShellEscape` value indicates that the feature is disabled. The latter value means that any command requiring execution must be implemented by the user as an extension of the `Executable` class. We will not go into the specifics of such implementations here, but it is important to note that the `base64` command emulation is already implemented in Aspose.TeX and is included by default in the `Executables` collection property of the `TeXOptions` class instance.

### Decoding Base64-encoded data

To decode the contents of a file that is expected to contain Base64-encoded data, we normally would use the following command line:


```
base64 -d  FILE1 > FILE2
```

where FILE1 is the "encoded" file and `> FILE2` redirects the output to the file `FILE2`.

Therefore, we should include the following line in the body of our LaTeX file:


```tex
\immediate\write18{base64 -d  sample-image.64 > sample-image.png}
```

> The `\immediate` prefix is required to ensure that the `\write` operation is executed immediately when the TeX scanner encounters this primitive. Otherwise, it will be processed during the page ship-out.

If we run the typesetting of the file now, we will find that the image file `sample-image.png` has been created. Go ahead and open it in a viewer to check!

## Including the decoded image

As we noted at the beginning of the article, to include the decoded image, we use the well-known LaTeX command `\includegraphics`:


```tex
\includegraphics[options]{sample-image.png}
```

So, the complete (nearly) LaTeX file might appear as follows:


```tex
\documentclass{article}
\begin{filecontents*}[overwrite]{sample-image.64}
iVBORw0KGgoAAAANSUhEUgAAAPgAAABdCAYAAAH/B5vAAAAAGXRFWHRTb2Z0d2FyZQBBZ......
\end{filecontents*}
\begin{document}
  \write18{base64 -d  sample-image.64 > sample-image.png}
  \includegraphics[options]{sample-image.png}
\end{document}
```

And the Java code utilizing the **Aspose.TeX** API is similar to what can be found in other articles, with the exception of specifying the shell mode option:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-EmbeddedBase64EncodedImage.java" >}}

And now **Step 5** is complete. For truly comprehensive examples, explore our [Example project](https://github.com/aspose-tex/Aspose.TeX-for-Java).

**You may also check out the free conversion [web app](https://products.aspose.app/tex/conversion/latex/) built based on [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**