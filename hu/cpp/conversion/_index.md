---
translation: true
template: /_templates/_conversion-cpp.md
title: TeX (LaTeX) fájlok konvertálása | C++
url: /cpp/conversion/
keywords: tex konverter cpp api, tex konverter c++ api
description: TeX(LaTeX) konverziós C++ API megoldás. Konvertálja a LaTeX fájlokat PDF, XPS és képek formátumba, beleértve PNG, JPEG, TIFF, BMP, néhány soros C++ kódot.
family: tex
platformtag: cpp
feature: conversion
---

{{<section banner>}}
---
h1: Konvertálja a TeX-et és a LaTeX-et
h2: "TeX konverter API megoldás C++-hoz."
---

{{<section overview>}}
---
p1: "Az Aspose.TeX egy API az Object TeX rendszerhez, a Tex fájl részleteiért lásd a [Tex bevezetését](https://docs.aspose.com/tex/cpp/what-is-tex/). A fejlesztők könnyedén konvertálhatják a TeX-et PDF, XPS, PNG, JPG, BMP és TIFF formátumokká a C++ API integrálásával. Az alábbiakban néhány kódminta található, amelyeket a programozók javíthatnak és integrálhatnak a LaTex megoldásokba."
p2: "Az itt található Java API-megoldás lehetővé teszi a TeX- és LaTeX-fájlok programozott konvertálását, de hasznos lehet megnézni és kipróbálni a [cross-platform Converters](https://products.aspose.app/tex/conversion) ezeken a natív verziókon fejlesztetteket. API-k. Itt [alkalmazásokat](https://products.aspose.app/tex/applications) is találhat TeX-fájlok, táblázatok, grafikák létrehozásához és szerkesztéséhez, fájlok PDF formátumba való egyesítéséhez stb."
---

{{<section feature1>}}
---
title: "A LaTeX konvertálása képekre, XPS-re, PDF-re, SVG C++-ra."
h3: "C++ kód példa TeX-ből képekre, XPS-re, PDF-re vagy SVG-re."
item1: "Az API támogatja a BMP, JPEG, PDF, SVG, TIFF, XPS és PNG kimeneti formátumokat. A TeX fájlok képek, PDF, XPS vagy SVG formátumokká konvertálásához hajtsa végre a következő lépéseket:"
item2: "Hozza létre a [TeXOptions osztály] példányát (https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options)."
item3: "Határozza meg a kép típusát és méretét az [*ImageDevice*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.image_device) segítségével."
item4: "Adja meg a fájlrendszer munkakönyvtárát a kimenethez/bemenethez az [*OutputWorkingDirectory*] segítségével (https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options#aa4f4ea6dab7db5ba1b40800495f16f63) /D:i /reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options#aa4f4ea6dab7db5ba1b40800495f16f63)."
item5: "Inicializálja a mentési beállításokat a [*BmpSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.bmp_save_options), [*PngSaveOptions*](https://reference) segítségével .aspose.com/tex/cpp/class/aspose.te_x.presentation.image.png_save_options), [*TiffSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.tiff_save_options), [*JpegSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.jpeg_save_options) vagy [*PdfSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.pdf.pdf_save_options), [*SvgSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.svg.svg_save_options), [*XpsSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_save_options), amely alapértelmezett, nem kell beállítani."
item6: "Futtassa a konverziót a [*TeXJob()*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_job) futtatási módszerével [ImageDevice](https://reference.aspose.com) /tex/cpp/class/aspose.te_x.presentation.image.image_device) vagy [PdfDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.pdf.pdf_device), [ SvgDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.svg.svg_device), [XpsDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_device)."
item7: "Az Aspose.TeX for C++ jól működik minden olyan fejlesztői környezetben, amely támogatja a C++-t, de a következő követelmények nagyon ajánlottak:"
item8: Microsoft Visual Studio 2015 vagy újabb.
item9: Microsoft Windows asztali (7, 8, 10).
item10: Szerver operációs rendszerek (2008, 2012) stb.
item11: Linux rendszerek (Ubuntu-16.04 vagy újabb).
---


