---
translation: true
template: /_templates/_conversion-java.md
title: Konverze souborů TeX (LaTeX) | Java
url: /java/conversion/
description: TeX (LaTeX) konverze Java API řešení. Převeďte soubory LaTeX do PDF, XPS a obrázků včetně PNG, JPEG, TIFF, BMP pomocí několika řádků kódu Java.
keywords: tex conversion api java, tex converter java integrate
family: tex
platformtag: cpp
feature: conversion
---

{{<section banner>}}
---
h1: Převést TeX a LaTeX
h2: "TeX převodník API řešení pro Javu."
---

{{<section overview>}}
---
p1: "Aspose.TeX je API pro systém Object TeX, pro podrobnosti o souboru Tex zde je [Tex úvod](https://docs.aspose.com/tex/cpp/what-is-tex/). Vývojáři mohou snadno převést TeX do formátů PDF, XPS, PNG, JPG, BMP a TIFF integrací API pro Javu. Níže je několik ukázek kódu, které mohou programátoři vylepšit a integrovat do řešení Tex."
p2: "Řešení API pro Javu vám umožňuje převádět soubory TeX a LaTeX programově, ale může být užitečné vidět a vyzkoušet [převaděče mezi platformami](https://products.aspose.app/tex/conversion) vyvinuté na těchto nativních API. Najdete zde také [aplikace](https://products.aspose.app/tex/applications) pro vytváření a úpravu souborů TeX, tabulek, grafiky, slučování souborů do formátu PDF atd."
---

{{<section feature1>}}
---
title: "Převeďte LaTeX na obrázky, XPS, PDF, SVG pomocí Javy."
h3: "Příklad Java kódu převod TeX na obrázky, XPS, PDF nebo SVG."
item1: "API podporuje BMP, JPEG, PDF, SVG, TIFF, XPS a PNG jako výstupní formáty. Chcete-li převést soubory TeX na obrázky, PDF, XPS nebo SVG, postupujte takto:"
item2: "Vytvořte instanci [třídy TeXOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions)."
item3: "Zadejte pracovní adresář systému souborů pro výstup/vstup pomocí [*OutputWorkingDirectory*](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#setOutputWorkingDirectory-com.aspose.tex.IOutputWorkingDirectory-)/[*InputWorkingDirectory*](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#setInputWorkingDirectory-com.aspose.tex.IInputWorkingDirectory-)."
item4: "Inicializujte možnosti ukládání pomocí [*BmpSaveOptions*](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/BmpSaveOptions), [*PngSaveOptions*](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PngSaveOptions), [*TiffSaveOptions*](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/TiffSaveOptions) [*JpegSaveOptions*](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/JpegSaveOptions) nebo [*PdfSaveOptions*](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfSaveOptions), [*SvgSaveOptions*](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/SvgSaveOptions), [*XpsSaveOptions*](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/XpsSaveOptions), která je výchozí, není třeba ji nastavovat."
item5: "Spusťte převod pomocí metody Rum z [*TeXJob()*](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob) pro [ImageDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/ImageDevice) nebo [PdfDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfDevice), [SvgDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/SvgDevice), [XpsDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/XpsDevice)."
item6: "Aspose.TeX for Java funguje dobře v jakémkoli vývojovém prostředí, které podporuje Javu, ale důrazně doporučujeme dodržovat následující požadavky:"
item7: Plocha Microsoft Windows (7, 8, 10).
item8: Systémy Linux (Ubuntu-16.04 nebo novější).
item9: Mac OS X.
item10: J2SE 8.0 (1.8) nebo vyšší (například Java 10) verze Java.
---

