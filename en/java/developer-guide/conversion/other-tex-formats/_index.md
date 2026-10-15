---
translation: true
template: /templates/_template-java.md
title: Other TeX conversion output formats | Java
linktitle: Other TeX formats
weight: 18
url: /java/other-tex-formats/
description: The conversion functionality of Aspose.TeX API solution for Java allows converting LaTeX files and your own custom TeX files. Here are some code examples.
lastmod: "2024-09-20"
---

{{<section overview>}}

It's highly unlikely that you will currently want to convert a TeX file written in any other format than LaTeX. But this is possible if you are studying the TeX language and/or internals for some reason. Anyway, **Aspose.TeX for Java** allows you to convert files written in Plain TeX format. It also allows you to create custom formats and typeset documents designed in these formats.

We will start with creating a custom format.

## Creating a custom format

Let's remember that the format file is a binary dump of the TeX engine's internal state.

Set `inputDirectory` to a folder containing `customtex.tex` and its dependencies, and `outputDirectory` to an existing output folder. The format source must end with `\dump`; this example creates `customtex.fmt` in the output folder. Import the Aspose.TeX classes used in the snippets and, for typesetting, `com.aspose.tex.rendering.XpsDevice`, `java.io.ByteArrayInputStream` and `java.nio.charset.StandardCharsets`. The calling method must handle or declare exceptions. Apply a license as described in the [licensing guide](/tex/{{lang.url-fragment}}java/licensing/) to avoid evaluation restrictions.

{{< gist "aspose-com-gists" "d21a098d3848236e0c258661f5bbc0ae" "Example-CreateCustomTeXFormat.java" >}}

As you can see, the code is similar to the code for converting a TeX file. But there are a few differences.

First, here we use the [TeXConfig.objectIniTeX()](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/#objectIniTeX--)  job configuration. This is a special configuration that leaves the engine's state "virgin", i.e., the internal parameters have their default values, and the set of control sequences coincides with the set of primitives. In our example, the set of primitives is extended in the sense mentioned [here](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex).

Next, we set up the input and output working directories as usual. The input working directory needs to contain the main format source file and all its dependencies.

And the second key difference is the way we run the job. This time we use the static [createFormat()](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#createFormat-java.lang.String-com.aspose.tex.TeXOptions-)  method, which together with the options takes the name of the main source file, that must be the same as the format name.

## Typesetting a TeX file in your custom format

Now that we have our own TeX format, we want to typeset a TeX file written in this format. Here is the code:

Set `formatDirectory` to the folder containing the previously created `customtex.fmt`, and `outputDirectory` to an existing output folder. The example typesets a self-contained text stream to `typeset-with-custom-format.xps`, so no input working directory is needed. Set an input working directory when the main input has dependencies, such as images.

{{< gist "aspose-com-gists" "d21a098d3848236e0c258661f5bbc0ae" "Example-TypesetWithCustomTeXFormat.java" >}}

Obviously, we have to specify the format somehow. First of all, we need to create an instance of the [FormatProvider](https://reference.aspose.com/tex/java/com.aspose.tex/formatprovider/) class. Then, in the options constructor, we use the [TeXConfig.objectTeX(FormatProvider)](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/#objectTeX-com.aspose.tex.FormatProvider-) configuration, which takes our format provider as an argument and loads the format on top of the "virgin" state of the engine.

Both examples use noninteractive execution and capture terminal output in memory. The typesetting example closes the input stream, disposes the XPS device and closes the working directory and format provider after the job. These features are discussed earlier in this [guide](/tex/{{lang.url-fragment}}java/conversion/).

## Typesetting a TeX file in Plain TeX format

If we use `TeXConfig.objectTeX()` without a format provider, the engine will load the default format, which is [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/) in its fourth sense. Thus, if you have a TeX file written in Plain TeX format, this way you may convert it to any supported target format.