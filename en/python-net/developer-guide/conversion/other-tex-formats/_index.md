---
translation: true
template: /templates/_template-python-net.md
title: Other TeX conversion output formats | Python
linktitle: Other TeX formats
weight: 18
url: /python-net/other-tex-formats/
description: The Aspose.TeX API solution for Python provides functionality that allows you convert LaTeX files and custom TeX files. Here are a few code examples.
lastmod: "2024-09-20"
---

{{<section overview>}}

It is unlikely that you would currently need to convert a TeX file written in a format other than LaTeX. However, if you are studying the TeX language or TeX's internals for any reason, it is still possible. In any case, **Aspose.TeX for Python** enables you to convert files written in *Plain TeX* format and also allows you to create custom formats and typeset documents designed in these formats.

To begin, we will create a custom format.

## Creating a custom format

Let's keep in mind that the format file is a binary representation of the TeX engine's internal state.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-CreateCustomTeXFormatFile.py" >}}

As you can see, the code bears a resemblance to the code for converting a TeX file. However, there are a few distinctions.

Firstly, in this case, we utilize the [TeXConfig.object_ini_tex](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_ini_tex/) job configuration. This configuration ensures that the engine's state is "virgin", meaning that the internal parameters have their default values, and the set of control sequences aligns with the set of primitives. In our example, the set of primitives is expanded [in the Aspose.TeX and Object TeX article](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex).

Following that, we proceed with setting up the input and output working directories as usual. The input working directory should include the main format source file and all its dependencies.

And the second major difference is the method by which we execute the job. In this case, we utilize the static [create_format()](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/create_format/#str-aspose.tex.TeXOptions) method, which, in conjunction with the options, requires the name of the main source file to be identical to the format name.

## Typesetting a TeX file in your custom format

Now that we have created our own TeX format, we can proceed to typeset a TeX file written in this format. Here is the code:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-TypesetWithCustomTeXFormat.py" >}}

To specify the format, we need to create an instance of the [FormatProvider](https://reference.aspose.com/tex/python-net/aspose.tex.resourceproviders/formatprovider/) class. In the options constructor, we use the [TeXConfig.object_tex()](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_tex/#aspose.tex.resourceproviders.FormatProvider) configuration, which requires our format provider as an argument and loads the format on top of the "virgin" state of the engine.

The remaining code should be familiar to you, as it utilizes the features that were discussed earlier in this [guide](/tex/{{lang.url-fragment}}net/conversion/).

## Typesetting a TeX file in Plain TeX format

If we remove the format provider from the code shown above, the engine will load the default format, which is [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/) in its fourth sense. Therefore, if you have a TeX file written in the Plain TeX format, you can convert it to any supported target format using this approach.