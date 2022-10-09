---
translation: true
template: /_templates/_conversion-cpp.md
title: Konverze souborů TeX (LaTeX) | C++
url: /cpp/conversion/
keywords: tex converter cpp api, tex converter c++ api
description: TeX (LaTeX) konverze C++ API řešení. Převeďte soubory LaTeX do PDF, XPS a obrázků včetně PNG, JPEG, TIFF, BMP pomocí několika řádků kódu C++.
family: tex
platformtag: cpp
feature: conversion
---

{{<section banner>}}
---
h1: Převést TeX a LaTeX
h2: "TeX převodník API řešení pro C++."
---

{{<section overview>}}
---
p1: "Aspose.TeX je API pro systém Object TeX, pro podrobnosti o souboru Tex zde je [Tex úvod](https://docs.aspose.com/tex/cpp/what-is-tex/). Vývojáři mohou snadno převést TeX do formátů PDF, XPS, PNG, JPG, BMP a TIFF integrací API pro C++. Níže je několik ukázek kódu, které mohou programátoři vylepšit a integrovat do řešení LaTex."
p2: "Řešení API pro Javu vám umožňuje převádět soubory TeX a LaTeX programově, ale může být užitečné vidět a vyzkoušet [převaděče mezi platformami](https://products.aspose.app/tex/conversion) vyvinuté na těchto nativních API. Najdete zde také [aplikace](https://products.aspose.app/tex/applications) pro vytváření a úpravu souborů TeX, tabulek, grafiky, slučování souborů do formátu PDF atd."
---

{{<section feature1>}}
---
title: "Převeďte LaTeX na obrázky, XPS, PDF, SVG C++."
h3: "Příklad kódu C++ převod TeX do obrázků, XPS, PDF nebo SVG."
item1: "API podporuje BMP, JPEG, PDF, SVG, TIFF, XPS a PNG jako výstupní formáty. Chcete-li převést soubory TeX na obrázky, PDF, XPS nebo SVG, postupujte takto:"
item2: "Vytvořte instanci [třídy TeXOptions](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options)."
item3: "Definujte typ a velikost obrázku pomocí [*ImageDevice*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.image_device)."
item4: "Zadejte pracovní adresář systému souborů pro výstup/vstup pomocí [*OutputWorkingDirectory*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options#aa4f4ea6dab7db5ba1b40800495f16f63)/[*InputWorkingDirectory*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options#aa4f4ea6dab7db5ba1b40800495f16f63)."
item5: "Inicializujte možnosti ukládání pomocí [*BmpSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.bmp_save_options), [*PngSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.png_save_options), [*TiffSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.tiff_save_options), [ JpegSaveOptions](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.jpeg_save_options) nebo [*PdfSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.pdf.pdf_save_options), [*SvgSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.svg.svg_save_options), [*XpsSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_save_options), která je výchozí, není třeba ji nastavovat."
item6: "Spusťte převod pomocí metody spuštění [*TeXJob()*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_job) pro [ImageDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.image_device) nebo [PdfDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.pdf.pdf_device), [SvgDevice](https ://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.svg.svg_device), [XpsDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.prezentace.xps.xps_zařízení)."
item7: "Aspose.TeX pro C++ funguje dobře v jakémkoli vývojovém prostředí, které podporuje C++, ale důrazně doporučujeme dodržovat následující požadavky:"
item8: Microsoft Visual Studio 2015 nebo novější.
item9: Plocha Microsoft Windows (7, 8, 10).
item10: Serverové operační systémy (2008, 2012) atd.
item11: Systémy Linux (Ubuntu-16.04 nebo novější).
---


