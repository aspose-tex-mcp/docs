---
translation: true
template: /templates/_template-java.md
title: Advanced Features | Aspose.TeX for Java
linktitle: Advanced Features
weight: 20
url: /java/advanced-features/
description: Aspose.TeX API solution features for Java built on the basis of Object TeX/LaTeX implementation are gathered in this chapter.
lastmod: "2026-05-28"
---

{{<section overview>}}


Welcome to the advanced engineering guide for Aspose.TeX for Java. Apart from the standard document compilation, the Aspose.TeX engine provides low-level hooks into file-system abstraction, custom macro packages, memory-stream tracking, and headless server optimization. This section discusses Aspose.TeX's features built on the basis of Object TeX/LaTeX implementation.

**LaTeX figure rendering** in Aspose.TeX for Java documentation page explains how to extract and render isolated LaTeX fragments (such as drawings, plots, or structural graphics) as standalone images completely independent from a full document page layout. The API includes this feature as a structural generalization of the math formula rendering engine. 

**LaTeX graphics embedding** page explains how to import and embed external image assets (such as charts, diagrams, or photographs) into a TeX document during compilation using Aspose.TeX for Java API.

The page highlights two ways to handle this via the IInputWorkingDirectory interface:

- File System Approach: Using PhysicalFileSystemInputWorkingDirectory to point the engine to a physical directory on a local disk where the images reside.

- Stream/Memory Approach: Implementing a custom stream provider to fetch images directly from memory, cloud storage, or databases using the filename as a lookup key.

**LaTeX math formula rendering** page explains how to render isolated LaTeX mathematical formulas into standalone graphics (PNG or SVG) completely independent of a full document, which is ideal for embedding formulas into web applications, desktop UIs, or database storage.

**LaTeX file repair** page introduces the `LaTeXRepairer` feature, which programmatically validates, structures, and fixes malformed or incomplete text files that are missing mandatory LaTeX components. This allows corrupt or poorly structured TeX files to compile successfully without manual intervention.  