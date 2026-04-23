---
translation: true
template: /templates/_template-net.md
title: LaTeX templates - quick‑start guide
linktitle: LaTeX templates
type: docs
weight: 100
url: /net/latex-templates/
description: Learn what LaTeX templates are, how to use and create them, where to download the most popular ones, and a fast workflow with ready‑to‑copy snippets.
keywords: LaTeX, template, class, style, Overleaf, CTAN, bibliography, Beamer, thesis, CV
lastmod: "2026-04-22"
---

{{<section overview>}}

# Guide to LaTeX templates

## What is a LaTeX template?

A LaTeX template bundles a **class** (`.cls`), **style** (`.sty`), example `.tex` files and supporting assets (logos, bibliography files, etc.) that define the layout, typography, and structure for a specific document type—journal article, thesis, CV, poster, slide deck, and more.

## How to use LaTeX templates

1. **Download** the zip or clone the repository.  
2. Open the main `.tex` file (often called `main.tex` or `article.tex`).  
3. Load the class or style supplied by the template and follow the README’s “structure” (title page, abstract, sections, bibliography).

```latex
\documentclass[options]{mytemplate}   % class supplied by the template
\usepackage{mytemplate}               % sometimes a .sty instead of .cls
\begin{document}
  \title{My Title}
  \author{Me}
  \maketitle
  % <content>
\end{document}
```

Compile with `pdflatex`, `latexmk -pdf`, or the Overleaf “Recompile” button.

## How to create your own template

| **Goal** | **Recommended file** | **Minimal skeleton** |
|------|------------------|-----------------|
| Full control over document structure | **Class** (`.cls`) | See code block below |
| Only extra macros or formatting | **Style** (`.sty`) | – |
| Distribution | Zip archive or GitHub repo (include class/style, optional `.bib`, logos, README) | – |

### Minimal class skeleton (`mytemplate.cls`)

```latex
% mytemplate.cls – a very simple article‑style class
\NeedsTeXFormat{LaTeX2e}
\ProvidesClass{mytemplate}[2025/12/03 v1.0 My custom class]
\LoadClass[12pt]{article}   % inherit from article

% ---- custom settings ----
\RequirePackage{geometry}
\geometry{margin=2cm}
\RequirePackage{fontspec}
\setmainfont{Latin Modern Roman}

% ---- user‑level commands ----
\newcommand\mytitle[1]{\centerline{\LARGE\bfseries #1}}
\endinput
```

Use it with `\documentclass{mytemplate}` in your document.

## Where to download LaTeX templates

- **Overleaf Gallery** – the biggest public collection (≈ 4 000 free templates).  
  <https://www.overleaf.com/gallery>
- **CTAN (Comprehensive TeX Archive Network)** – official repository for journal‑specific classes.  
  <https://ctan.org/>
- **GitHub / GitLab** – many authors publish open‑source thesis or conference templates.  
- University/Institute web pages – most schools host an “official” thesis/dissertation template.

## Most‑used / highly‑rated templates

| **#** | **Template** | **Typical use** |
|---|----------|-------------|
| 1 | **IEEEtran** (`ieeetran.cls`) | IEEE conference & journal papers |
| 2 | **Springer LNCS** (`llncs.cls`) | Lecture Notes in Computer Science |
| 3 | **Elsevier article** (`elsarticle.cls`) | Elsevier journals |
| 4 | **Modern Simple CV** | One‑page résumé |
| 5 | **Classic Thesis** (`classicthesis.sty`) | Book / thesis with elegant typography |
| 6 | **Beamer** (`beamer.cls`) | Slide presentations |
| 7 | **a0poster / tikzposter** | Large scientific posters |
| 8 | **University‑specific thesis** (e.g., `cambridgephd.cls`) | Institutional PhD/MSc theses |
| 9 | **Astronomy & Astrophysics** (`aa.cls`) | A&A journal articles |
|10 | **Basic Academic Journal Article** | Simple starter for articles (Overleaf) |

## Quick workflow for first‑time users

1. **Pick a template** → click “Open in Overleaf” **or** download the ZIP.  
2. **Edit placeholder fields** (`\title{}`, `\author{}`, etc.).  
3. **Compile** → PDF appears.  
4. If you work locally: unzip → run `latexmk -pdf main.tex` (or `pdflatex` + `biber` as required).  
5. **Export** the PDF or push the source to a Git repository for version control.

## Common pitfalls and tips

- **Missing packages** – install with your distribution’s manager (`tlmgr install <pkg>` or MiKTeX console).  
- **Out‑of‑date classes** – Overleaf uses the latest TeX Live; update your local TeX installation regularly.  
- **Bibliography engine** – many modern templates expect `biber`. Run `biber <basename>` after the first LaTeX pass.  
- **Branding assets** – replace logos, colour PDFs, or `.sty` files that define institutional colours.  
- **Custom commands** – keep them in a separate `.sty` file; you can then reuse the same layout across multiple papers.


## What about Aspose?

When you need to manipulate the PDFs generated from LaTeX (merge, watermark, or convert to other formats) in a .NET, Java, or Python application, libraries such as **Aspose.TeX** provide a language‑agnostic API for working with PDF files without requiring a full LaTeX toolchain.

---

### TL;DR heat sheet

```text
What?   → Pre‑built layout (class+style+assets)
Use?    → \documentclass{mytemplate} + follow README
Create? → Write .cls or .sty → pack assets → zip/GitHub
Get?    → Overleaf Gallery, CTAN, GitHub, university sites
Hot 10  → IEEEtran, llncs, elsarticle, modern‑simple‑cv,
          classicthesis, beamer, a0poster, UNICAMP thesis,
          aa.cls, Basic Academic Journal Article
```

Happy typesetting!