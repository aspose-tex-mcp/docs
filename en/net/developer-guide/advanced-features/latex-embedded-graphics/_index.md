---
translation: true
template: /templates/_template-net.md
title: LaTeX embedded graphics | Include graphics in the LaTeX code
linktitle: LaTeX embedded graphics
weight: 18	
url: /net/latex-embedded-graphics/
keywords: includegraphics latex, latex embed base64 graphics, latex base64 encoded graphics, write18, shell-escape, latex shell command
description: This article covers how to include base64-encoded images in the LaTeX source code, as well as the \write18 feature that makes this possible.
lastmod: "2024-09-20"
---

{{<section overview>}}

## Another way to include images

Some TeX/LaTeX systems allow for including images that are not stored externally with respect to the LaTeX file itself, but rather included directly within the LaTeX file. However, since TeX/LaTeX files are plain text files and thus cannot contain binary data, we need a way to represent binary data in text form. In other words, binary data must be encoded into some text representation. The problem is that a TeX engine cannot interpret such encoded images directly. In fact, including an image is accomplished using the good old `\includegraphics` command from the `graphicx` package. However, this command can only deal with external image files. Yes, an external image file (along with another intermediary file) will still be created outside the LaTeX file. The key point is that you only need to distribute the LaTeX file alone.

Okay, let's say that we somehow placed an encoded image in the LaTeX file. But how do we get the image decoded? Unfortunately, we cannot decode the file by reading it from the LaTeX file and writing it to the external image file. The text string representing the encoded image must first be written to an external text file, which can then be decoded to produce an image file.

By now, we can outline the following steps to get the desired result:

1. Encode the image.
2. Inject the text string representing the image data into the LaTeX file.
3. Output the text string representing the image data to an external file.
4. Decode the external file from Step 3.
5. Include the decoded image.

The first two steps are completed by the author of the LaTeX file. A TeX engine will take care of the remaining steps, provided that it is correctly instructed, of course.

Let's start from the very beginning. How can we encode our image to obtain a string of characters? One of the methods for doing this (and probably the most popular) is **Base64**.

## Encoding binary data using Base64

[**Base64**](https://en.wikipedia.org/wiki/Base64) is a group of binary-to-text encoding schemes that transforms binary data into a sequence of printable characters, limited to a set of 64 unique characters. More specifically, the source binary data is taken 6 bits at a time, then this group of 6 bits is mapped to one of 64 unique characters. As with all binary-to-text encoding schemes, **Base64** is designed to carry data stored in binary formats across channels that only reliably support text content.

We can see from this short explanation that **Base64** is what we need. To encode an image file to **Base64**, you can use a command line utility (if available on your OS), standard or third-party features of almost every programming language, or online tools such as [Base64.guru](https://base64.guru/converter/encode/file) or similar.

## Placing the encoded image into the LaTeX file

The string of characters that you obtain as a result of encoding must be placed in the standard LaTeX `filecontents` environment in the preamble of a LaTeX file as follows:


```tex
\documentclass{article}
\begin{filecontents*}[overwrite]{sample-image.64}
iVBORw0KGgoAAAANSUhEUgAAAPgAAABdCAYAAAH/B5vAAAAAGXRFWHRTb2Z0d2FyZQBBZ......
\end{filecontents*}
\begin{document}
...
\end{document}
```

Here it is. Step 2 is accomplished. We have the image inside the LaTeX file! But what will happen when we run the typesetting of this file with LaTeX?

A LaTeX processor will write the string of characters in the environment to an external file named `sample-image.64`. Due to the use of the `overwrite` option, the file will be overwritten if it already exists (e.g., if it was produced by a previous run). And that's what accomplishes Step 3 as well!

## Decoding a base64 string

Step 4 of our plan is where the differences in TeX implementations come into play. Decoding a Base64 character string is done by means of a more common thing known as the `\write18` feature.

### `\write18`

In classic TeX engines, `\write<number>(<token list>)` is the primitive that writes a *list of tokens*. When used, this primitive is followed by an integer. If this number is negative, the tokens are written to the transcript (log) file. If the number is greater than `15`, the tokens are written to the terminal. If the number is in the range `0..15`, the tokens are written to a file whose name is specified by a preceding occurrence of the `\openout` primitive. The `\openout<4-bit integer>=<file name>` primitive maps a file name to a number.

Newer TeX implementations (such as PDF TeX) allow the use of `\write18`. In this case, they interpret the `<token list>` as a command line to be executed in the OS shell. Since this feature is obviously a potential backdoor, you might sense a touch of mystery whenever it is mentioned in TeX-related documentation or on the Internet. For this reason, the PDF TeX/LaTeX executables have command options to manage the accessibility of this feature.

Generally, there are three levels of accessibility: disabled, enabled with restrictions, and fully enabled.

In **Aspose.TeX**, there is a TeX job option called `ShellMode`, but there are only two suitable values: `NoShellEscape` and `ShellRestricted`. The `NoShellEscape` value means that the feature is disabled. The second value indicates that any command that needs to be executed must be implemented by the user as an extension of the `Executable` class. Here, we will not delve into the details of such implementations, but we will mention that the `base64` command emulation is already implemented in Aspose.TeX. By default, you can find its prototype instance in the `Executables` collection property of the `TeXOptions` class instance.

### Decoding Base64-encoded data

To decode the contents of a file that is supposed to be some Base64-encoded data, we normally would use the following command line:


```
base64 -d  FILE1 > FILE2
```

where FILE1 is the "encoded" file and `> FILE2` means that the output must be redirected to the file `FILE2`.

Thus, in the body of our LaTeX file, we should add the following line:


```tex
\immediate\write18{base64 -d  sample-image.64 > sample-image.png}
```

> The `\immediate` prefix is required to ensure that the `\write` operation is performed as soon as the primitive command is encountered by the TeX scanner. Otherwise, it will be processed at the time of page ship-out.

If we run the typesetting of the file now, we will see that the image file `sample-image.png` is created. Come on, open it in a viewer to check!

## Including the decoded image

As we mentioned at the beginning of the article, to include the decoded image, we use the well-known LaTeX command `\includegraphics`:


```tex
\includegraphics[options]{sample-image.png}
```

So, the complete (nearly) LaTeX file might look as follows:


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

And the C# code using the **Aspose.TeX** API is similar to that in other articles, except for specifying the `ShellMode` option:

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-EmbeddedBase64EncodedImage.cs" >}}

And now we are done with the **Step 5**. For truly complete examples, explore our [Example project](https://github.com/aspose-tex/Aspose.TeX-for-.NET).

**You may also check out the free conversion [web app](https://products.aspose.app/tex/conversion/latex/) built based on [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**