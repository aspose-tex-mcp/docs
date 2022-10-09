---
translation: true
template: /_templates/_conversion-java.md
title: TeX (LaTeX) fájlok konvertálása | Java
url: /java/conversion/
description: TeX(LaTeX) konverziós Java API megoldás. Konvertálja a LaTeX fájlokat PDF, XPS és képek formátumba, beleértve a PNG, JPEG, TIFF, BMP fájlokat néhány soros Java kóddal.
keywords: tex converter api java, tex konverter java integrate
family: tex
platformtag: cpp
feature: conversion
---

{{<section banner>}}
---
h1: Konvertálja a TeX-et és a LaTeX-et
h2: "TeX konverter API megoldás Java-hoz."
---

{{<section overview>}}
---
p1: "Az Aspose.TeX egy API az Object TeX rendszerhez, a Tex fájl részleteiért lásd a [Tex bevezetését](https://docs.aspose.com/tex/cpp/what-is-tex/). A Java API integrálásával a fejlesztők könnyedén konvertálhatják a TeX-et PDF, XPS, PNG, JPG, BMP és TIFF formátumokká. Az alábbiakban néhány kódminta található, amelyeket a programozók javíthatnak és integrálhatnak a Tex megoldásokba."
p2: "Az itt található Java API-megoldás lehetővé teszi a TeX- és LaTeX-fájlok programozott konvertálását, de hasznos lehet megnézni és kipróbálni a [cross-platform Converters](https://products.aspose.app/tex/conversion) ezeken a natív verziókon fejlesztetteket. API-k. Itt [alkalmazásokat](https://products.aspose.app/tex/applications) is találhat TeX-fájlok, táblázatok, grafikák létrehozásához és szerkesztéséhez, fájlok PDF formátumba való egyesítéséhez stb."
---

{{<section feature1>}}
---
title: "A LaTeX konvertálása Képek, XPS, PDF, SVG formátumokká Java segítségével."
h3: "Java kód példa TeX-ből képekre, XPS-re, PDF-re vagy SVG-re."
item1: "Az API támogatja a BMP, JPEG, PDF, SVG, TIFF, XPS és PNG kimeneti formátumokat. A TeX fájlok képek, PDF, XPS vagy SVG formátumokká konvertálásához hajtsa végre a következő lépéseket:"
item2: "Hozza létre a  példányát [TeXOptions osztály](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions)."
item3: "Adja meg a fájlrendszer munkakönyvtárát a kimenethez/bemenethez az [*OutputWorkingDirectory*](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#setOutputWorkingDirectory-com.aspose.tex.IOutputWorkingDirectory) segítségével)/[*InputWorkingDirectory*](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#setInputWorkingDirectory-com.aspose.tex.IInputWorkingDirectory-)."
item4: "Inicializálja a mentési beállításokat a [*BmpSaveOptions*](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/BmpSaveOptions), [*PngSaveOptions*](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PngSaveOptions), [*TiffSaveOptions*](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/TiffSaveOptions) [*JpegSaveOptions*](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/JpegSaveOptions) vagy [*PdfSaveOptions*](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfSaveOptions), [*SvgSaveOptions*](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/SvgSaveOptions), [*XpsSaveOptions*](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/XpsSaveOptions), amely alapértelmezett, nem kell beállítani."
item5: "Futtassa az átalakítást a [*TeXJob()*](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob) Rum metódusával az [ImageDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/ImageDevice) vagy [PdfDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfDevice), [SvgDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/SvgDevice), [XpsDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/XpsDevice)."
item6: "Az Aspose.TeX for Java jól működik minden olyan fejlesztői környezetben, amely támogatja a Java-t, de a következő követelmények nagyon ajánlottak:"
item7: Microsoft Windows asztali (7, 8, 10).
item8: Linux rendszerek (Ubuntu-16.04 vagy újabb).
item9: Mac OS X.
item10: J2SE 8.0 (1.8) vagy újabb (például Java 10) Java verzió.
---

