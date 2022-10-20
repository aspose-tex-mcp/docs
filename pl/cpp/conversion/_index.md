---
translation: true
template: /_templates/_conversion-cpp.md
title: Konwersja plików TeX (LaTeX) | C++
url: /cpp/conversion/
keywords: konwerter tex cpp api, konwerter tex c++ api
description: Rozwiązanie API konwersji TeX(LaTeX) w języku C++. Konwertuj pliki LaTeX do PDF, XPS i obrazów, w tym PNG, JPEG, TIFF, BMP z kilkoma linijkami kodu C++.
family: tex
platformtag: cpp
feature: conversion
---

{{<section banner>}}
---
h1: Konwertuj TeX-a i LaTeX-a
h2: "Rozwiązanie API konwertera TeX dla C++."
---

{{<section overview>}}
---
p1: "Aspose.TeX to interfejs API do systemu Object TeX, aby uzyskać szczegółowe informacje na temat pliku TeX, oto [Wprowadzenie do TeX](https://docs.aspose.com/tex/cpp/what-is-tex/). Programiści mogą łatwo konwertować TeX do formatów PDF, XPS, PNG, JPG, BMP i TIFF, integrując API dla C++. Poniżej znajduje się kilka przykładów kodu, które programiści mogą ulepszyć i zintegrować z rozwiązaniami LaTex."
p2: "Rozwiązanie API dla Javy umożliwia programową konwersję plików TeX i LaTeX, ale warto zobaczyć i wypróbować [konwertery międzyplatformowe](https://products.aspose.app/tex/conversion) opracowane na tych natywnych Pszczoła. Można tam również znaleźć [aplikacje](https://products.aspose.app/tex/applications) do tworzenia i edycji plików TeX, tabel, grafik, do łączenia plików w jeden z formatu PDF itp."
---

{{<section feature1>}}
---
title: "Konwertuj LaTeX na obrazy, XPS, PDF, SVG C++."
h3: "Przykład kodu C++ Konwersja TeX do obrazów, XPS, PDF lub SVG."
item1: "Interfejs API obsługuje BMP, JPEG, PDF, SVG, TIFF, XPS i PNG jako formaty wyjściowe. Aby przekonwertować pliki TeX do obrazów, PDF, XPS lub SVG, wykonaj następujące kroki:"
item2: "Utwórz wystąpienie [klasy TeXOptions](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options)."
item3: "Zdefiniuj typ i rozmiar obrazu za pomocą [*ImageDevice*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.image_device)."
item4: "Określ katalog roboczy systemu plików dla danych wyjściowych/wejściowych za pomocą [*OutputWorkingDirectory*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options#aa4f4ea6dab7db5ba1b40800495f16f63)/[*InputWorkingDirectory*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options#aa4f4ea6dab7db5ba1b40800495f16f63)."
item5: "Zainicjuj opcje zapisywania za pomocą [*BmpSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.bmp_save_options), [*PngSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.png_save_options), [*TiffSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.tiff_save_options), [*JpegSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.jpeg_save_options) lub [*PdfSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.pdf.pdf_save_options), [*SvgSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.svg.svg_save_options), [*XpsSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_save_options), który jest domyślny, nie trzeba ustawiać."
item6: "Uruchom konwersję za pomocą metody uruchamiania [*TeXJob()*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_job) dla [ImageDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.image_device) lub [PdfDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.pdf.pdf_device), [SvgDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.svg.svg_device), [XpsDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_device)."
item7: "Aspose.TeX for C++ działa dobrze w każdym środowisku programistycznym, które obsługuje C++, ale zalecane są następujące wymagania:"
item8: Microsoft Visual Studio 2015 lub nowszy.
item9: Pulpit Microsoft Windows (7, 8, 10).
item10: Serwerowe systemy operacyjne (2008, 2012) itp.
item11: Systemy Linux (Ubuntu-16.04 lub nowsze).
---


