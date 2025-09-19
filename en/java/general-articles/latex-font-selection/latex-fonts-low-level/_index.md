---
translation: true
template: /templates/_template-java.md
linktitle: Low-level interface
title: 5. The low-level interface
weight: 50
url: /java/latex-fonts-low-level/
keywords: latex, latex fonts, latex font substitution, latex font families, latex font series, latex font shapes
description: This article covers the LaTeX low-level font interface that is mostly used in command definitions.
lastmod: "2024-09-20"
---

{{<section overview>}}

In contrast to the high-level font commands, which are intended for use in a document, the low-level commands are mainly for defining new commands in packages or in the document preamble. To make the best use of such commands, it is helpful to understand the internal organization of fonts in LaTeX's font selection scheme (NFSS).

On one hand, the goal of LaTeX's font selection scheme is to allow rational font selection with algorithms guided by the principles of generic markup. For this purpose, it would be desirable to allow independent changes to as many font attributes as possible. On the other hand, font families in real life normally contain only a subset of the myriad imaginable font attribute combinations. Thus, allowing independent changes in too many attributes results in too many combinations for which no real external font is available, and a default has to be substituted.

Internally, LaTeX keeps track of five independent font attributes: the *current encoding*, the *current family*, the *current series*, the *current shape*, and the *current size*. The encoding attribute was introduced in NFSS release 2 when it became clear that support for multiple languages would not be possible without maintaining the character-encoding scheme independently of the other font attributes.

The values of these attributes determine the font currently in use. LaTeX also maintains a large set of tables used to associate attribute combinations with external fonts (i.e., `.tfm` files that contain the data required for LaTeX to do its job). Font selection is then done in two steps:

1.	A number of font attributes are changed using the low-level commands `\fontencoding`, `\fontfamily`, `\fontseries`, `\fontshape`, and `\fontsize`.

2.	The font corresponding to these new attribute settings is selected by calling the `\selectfont` command.

The second step consists of several actions. First, LaTeX checks whether the font corresponding to the desired attribute settings is known to the system (i.e., the `.tfm` file is already loaded), and if so, this font is selected. Otherwise, the internal tables are searched to find the external font name associated with these settings. If such a font name is found, the corresponding `.tfm` file is read into memory, and then the font is selected for typesetting. If the font name is not found, LaTeX tries to find an alternative font, as explained later in this article.


## 5.1. Setting individual font attributes

There is one command for every font attribute to change its current value. All these commands accept more or less any character string as an argument, but only a few values make sense. These values are not hard-wired into NFSS, but rather are conventions set up in the internal tables. The following sections introduce the naming conventions used in the standard LaTeX set-up, but anyone can change this set-up by adding new font declarations in the internal tables. Normally, anyone setting up new fonts for use with LaTeX should try to honor these conventions whenever possible because only a consistent naming convention can guarantee that appropriate fonts are selected in a generically marked-up document.

If you want to select a specific font using this interface - for example, Computer Modern Dunhill bold condensed italic 14pt - a knowledge of the interface conventions alone is not enough since no external font exists for every combination of attribute values. You could try to specify something like the following:


```tex
\fontencoding{OT1}\fontfamily{cmdh}\fontseries{bc}\fontshape{it}%
\fontsize{14}{16pt}\selectfont
```

This code would be correct according to the naming conventions, as we will see below. However, due to the fact that this attribute combination does not correspond to a real font, LaTeX would have to substitute a different font. The substitution mechanism may choose a font that is quite different from the one desired, so you should consult the font tables to check whether the desired combination is available. Here are more details on the [font substitution process](/tex/{{lang.url-fragment}}java/latex-fonts-low-level/#53-automatic-substitution-of-fonts).

### Choosing the font family

The font family is selected by the command `\fontfamily`. As its argument, it takes a character string that refers to a font family declared in the internal tables. The character string was defined when these tables were set up and is usually a short letter sequence - for example, `cmr` for the Computer Modern Roman family. The family names should not be longer than five letters because they will be combined with possibly three more letters to form a file name, which on some systems can have at most eight letters.

### Choosing the font series

The `\fontseries` command changes the series attribute. The series combines a weight and a width in its argument, which means that it is impossible to change the width of the current font independently of its weight. This is acceptable because it is unlikely ever necessary to change weight or width individually. On the contrary, a change in weight is often accompanied by a change in width in the designer's specification. This is not much of a surprise since weight changes alter the horizontal appearance of the letters and thus require adjustments in the expansion (width) to produce a well-balanced look.

The names for both the weight and the width are abbreviated in the series names, so that each combination is unique. These naming conventions are shown in the table below. Any instance of `m` (standing for medium in weight or width) is omitted, except when both weight and width are medium, in which case a single `m` is used. For example, bold expanded would be `bx`, whereas medium expanded would be `x` and bold medium would be `b`.

![Font series naming conventions](/tex/images/java/tutorial/latex-font-selection-5-1.png)

### Choosing the font shape

The `\fontshape` command changes the shape attribute. For standard shapes, one- and two-letter abbreviations are used. These shapes are listed in the table below:

![Font shapes naming conventions](/tex/images/java/tutorial/latex-font-selection-5-2.png)

### Choosing the font size

The command `\fontsize{<size>}{<skip>}` changes the font size. It takes two arguments: the `<size>` to switch to and the baseline `<skip>` (the distance between baselines for this size). Font sizes are normally measured in points, so by convention, the unit is omitted. The same is true for the second argument. However, if the baseline skip should be a rubber length, you have to specify a unit. Therefore, a valid size change could be requested by


```tex
\fontsize{14.4}{17}\selectfont
```

Even if such a request is valid, there may be no corresponding external font in this size. In such a case, LaTeX will try to find a nearby size if its internal tables allow size correction or report an error otherwise.

If you use fonts existing in arbitrary sizes, you can select any size you want, of course:


```tex
\fontsize{1in}{1.2in}\selectfont A text in an arbitrary font size
```

### Choosing the encoding

The `\fontencoding` command is used to change the encoding. The argument is the internal name for the desired encoding. This name must be known to LaTeX, either as one of the predefined encodings (loaded by kernel) or as declared with the `\DeclareFontEncoding` command. Here is more information about [declaring font encodings](/tex/{{lang.url-fragment}}java/latex-fonts-setup/#64-how-to-declare-a-new-font-encoding-scheme). Standard font encoding names are listed in the table below:

![Standard font encoding names](/tex/images/java/tutorial/latex-font-selection-5-3.png)

NFSS is based on the assumption that most (or better, all) fonts for the text are available in the same encoding as long as they are used to typeset in the same language. In other words, encoding changes should be necessary only if you are switching from one language to another. In this case, the language support packages (e.g., from the `babel` system) are normally supposed to take care of encodings behind the scenes.

In the following example, we change the encoding manually by defining an environment `Cyr` for typesetting in Cyrillic. In this environment, both the font encoding and the input encoding are locally changed. Of course, for proper language support, additional work would be required, such as changing the hyphenation rules. The encodings are declared to LaTeX by loading them with the `fontenc` package. `T2A` specifies one of the standard Cyrillic encodings. `T1` becomes the default encoding since it is loaded last.

![Encondings exmple source code](/tex/images/java/tutorial/latex-font-selection-5-4.png)

![Encondings exmple output](/tex/images/java/tutorial/latex-font-selection-5-5.png)

Unfortunately, `T1` cannot be fully implemented for most PostScript fonts. Five characters in the following example are likely to be displayed as blobs of ink, indicating missing glyphs in the font. Note that the 'per thousand' and 'per ten thousand' symbols are actually formed by joining a percent sign and one or two additional small zeros; only the latter glyph is missing.


```tex
\usepackage[T1]{fontenc}
-----------------------------------------
\fontfamily{cmr}\selectfont
\j{} \ng{} \NG{} \textperthousand{}\textpertenthousand \par
\fontfamily{ptm}\selectfont
\j{} \ng{} \NG{} \textperthousand{}\textpertenthousand{}

```

![T1 for PostScript fonts](/tex/images/java/tutorial/latex-font-selection-5-5.png)

## 5.2. Setting multiple font attributes

While designing page styles or layout-oriented commands, you often want to select a particular font - that is, you need to specify values for all attributes. For this, LaTeX provides the command `\usefont`, which takes four arguments: the encoding, family, series, and shape. The command updates those attributes and then calls `\selectfont`. If you want to specify the size and baseline skip as well, place a `\fontsize` command before `\usefont`. For example,


```tex
\fontsize{14}{16pt}\usefont{OT1}{cmdh}{bc}{it}
```

would produce the same result as the following commands:


```tex
\fontencoding{OT1}\fontfamily{cmdh}\fontseries{bc}\fontshape{it}%
\fontsize{14}{16pt}\selectfont
```

LaTeX also provides the `\DeclareFixedFont` declaration, which can be used to define new commands that switch to a completely fixed font. Such commands are very fast because they do not have to look up any internal tables. Therefore, they are very useful in command definitions that have to switch back and forth between fonts. For example, if we want to declare a command for typesetting certain text in script size, we can do so as follows:


```tex
\DeclareFixedFont\ScriptSizeFont{\encodingdefault}{\familydefault}
    {\seriesdefault}{\shapedefault}{7pt}
\newcommand\theScript[1]{{\ScriptSizeFont #1}}
```

You can see that `\DeclareFixedFont` has six arguments. The name of the command to be defined is followed by the five font attributes in the NFSS classifications. Instead of passing fixed values (except for the size), the built-in hooks that describe the main document font are used. Therefore, in the example above `\ScriptSizeFont` still depends on the overall layout of the document. However, once the definition is executed, its meaning is frozen, so later changes to the defaults will not change the `\ScriptSizeFont` font.

## 5.3. Automatic substitution of fonts

When a font change request cannot be carried out because the combination is not known to LaTeX, it tries to recover by using a font with similar attributes. Here is what happens in detail: if the combination of encoding scheme, family, series, and shape is not declared, LaTeX tries to find a known combination by first changing the shape attribute to a default. If the resulting combination is still unknown, it tries changing the series to a default. As a last resort, it changes the family to a default value. Finally, it looks up the internal table entry to find the requested size. For example, if you ask for `\ttfamily\bfseries\itshape` - a typewriter font in a bold series and italic shape (which usually does not exist) - then you will get a typewriter font in medium series and upright shape because LaTeX first resets the shape before resetting the series. In such a case, if you prefer a typewriter font with italic shape, you have to announce your preferences to LaTeX using the `sub` function, which is explained in the [How to set up new fonts](/tex/{{lang.url-fragment}}java/latex-fonts-setup/) article.

The substitution process never changes the encoding scheme because any alteration can produce incorrect characters in the output. As you might recall, the encoding scheme defines how to interpret the input characters, while the other attributes define how the output should look. Therefore, it would not be appropriate if, for example, a pound sign was replaced with a dollar sign in a contract just because the software tried to be clever.

Thus, every encoding scheme must have a default family, series, and shape, and at least the combination consisting of the encoding scheme together with the corresponding defaults must have a definition inside LaTeX.

## 5.4. How to use low-level commands in the document

The low-level commands described in the preceding sections are intended to be used in the definitions of high-level commands, either in document class or package files, or in the document preamble.

If you can use high-level commands like `\textsf`, you should avoid using the low-level commands directly in the document whenever possible. The reason is that the low-level commands are very precise instructions to switch to a particular font, whereas high-level commands can be customized using packages or declarations in the preamble. Suppose, you have selected Computer Modern Sans in your document using `\fontfamily{cmss}\selectfont`. If you later decide to typeset the whole document with fonts from the PSNFSS bundle - say, Times - applying a package would change only those parts of the document that do not contain explicit `\fontfamily` commands.
