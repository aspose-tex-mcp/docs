---
translation: true
template: /templates/_template-java.md
linktitle: 1. Input and output
title: Input and output encodings | Aspose.TeX for Java
weight: 10
url: /java/latex-font-encodings/
keywords: latex, latex fonts, latex font encodings, nfss
description: This article briefly explains the concepts of input and output encodings in LaTeX. It also mentions the New Font Selection Scheme (NFSS).
lastmod: "2024-09-20"
---

{{<section overview>}}

If we press a key on a keyboard, some numeric code will be generated representing a certain character. An input encoding maps a character to its corresponding code. For example, on a German keyboard, accented characters (such as 'a-umlaut' character) may be mapped to different codes under different operating systems.

A document stored in a computer file contains only character codes, but the information about the input encoding is not explicitly included. Therefore, if you transfer a file to a different environment, such as, from the United Stated to the United Kingdom, you might find that the dollar signs in your document are suddenly interpreted as pound symbols when you view your file with some program that makes the wrong assumption about the input encoding.

The `inputenc` package, developed by the LaTeX Project Team, was intended to help with input encoding problems. It allows users to explicitly specify the input encoding used for documents or parts of documents. This mechanism makes it safe to transfer documents from one LaTeX installation to another achieving identical printed results.

The `inputenc` package interprets character codes in the file and maps them to an *internal LaTeX representation*, which uniquely covers all characters representable in LaTeX. During further processing, such as writing to some auxiliary file, LaTeX uses this internal representation, thereby avoiding any misinterpretation.

However, sooner or later, LaTeX has to associate these internal character representations with *glyphs* (character shapes in certain fonts), so another mapping is required. There are at most 256 glyphs in any TeX font. These glyphs are not addressed by name, but by 8-bit numbers representing the positions of the glyphs in the font. This means that we have to map from a large unique naming space into several small ones, and these glyph positions may vary widely, which is not surprising.

So, even though we preserved the meaning of the dollar sign from the external file to LaTeX's internals, we might still find wrong shapes on paper if we selected a font for printing that has an unexpected glyph in the position we assumed was reserved for a dollar sign. One of the tasks of **NFSS** (LaTeX's **New Font Selection Scheme**) is to make sure either that any LaTeX internal character representation is properly rendered or, if that is impossible for some reason, that the user receives a proper error message.

If a font contains accented characters as individual glyphs, rather than only base characters plus accents (from which TeX builds accented characters internally), then using these glyphs is preferable since they usually have a better appearance. Another (technical) reason for using these composite glyphs is that the `\accent` primitive will suppress hyphenation.

To suit different cases, a command like `\'e` (LaTeX's internal representation for the 'e-acute' character) sometimes has to initiate complicated actions involving the `\accent` primitive, and sometimes it just informs the paragraph builder that it needs the glyph from a certain *slot* (position) in the current font.

All this is achieved through the concept of *output encodings*, which are mappings of LaTeX's internal character representations to appropriate glyph positions or to glyph-building actions, depending on the actual glyphs available in the font used for typesetting.

The following articles discuss release 2 of NFSS, which became part of standard LaTeX in 1994.
