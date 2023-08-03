---
title: 1. Introduction to AMS-LATEX | LaTeX manual
type: docs
weight: 10
url: /java/introduction-to-ams-latex/
keywords: ams-latex, amsmath, amsmath options, amsopn, amstext, amscd, amsthm, amsxtra, upref
description: This article is a brief introduction into amsmath package and briefly covers its options as well as available subpackages and extensions.
lastmod: "2023-04-14"
sitemap:
    changefreq: "weekly"
    priority: 0.8
---

*AMS*-LATEX version 1.0 was released in 1990 and presented the original conversion to LaTeX of the math capabilities in Michael Spivak's *AMS*-TEX by Frank Mittelbach and Rainer Schopf, who worked as consultants to the *AMS*, with assistance from Michael Downes of the *AMS* tech staff. In 1994, the further work was done with David M. Jones.

*Amsmath* package accepts a few options that mainly affect the positioning of *limits* on various math operators or the positioning of equation tags.

## Available *amsmath* package options

The following three options may be used as global document options (specified in the `\documentclass` command) or as *amsmath* package options when it is loaded with the `\usepackage` command.

|||
|---|---|
| `reqno` **(default)** | Place equation numbers (tags) on the right. |
| `leqno` | Place equation numbers (tags) on the left (default, when using the *AMS*-LATEX document classes). |
| `fleqn` | Position equations at a fixed indent from the left margin rather than centered in the text column. |

## Available subpackages

In the *AMS*-LATEX distribution, you can also find components that can be loaded independently by the `\usepackage` command. The following smaller packages provide some features of the *amsmath* package:

|||
|---|---|
| `amsopn` | Provides `\DeclareMathOperator` for defining new operator names such as `\Ker` and `\esssup`. |
| `amstext` | Provides the `\text` command for typesetting a fragment of text in the correct type size. |

## Extension packages

The packages listed below provide additional features and must be loaded explicitly.

|||
|---|---|
| `amscd` | Defines some commands to make it easier to generate commutative diagrams. |
| `amsthm` | Provides a method to declare theorem-like structures and offers a `proof` environment. |
| `amsxtra` | Provides certain odds and ends that are needed for historical compatibility, such as `\fracwithdelims`, `\accentedsymbol`, and commands for placing accents as superscripts. |
| `upref` | Makes `\ref` print cross-reference numbers in an upright/Roman font regardless of context. |