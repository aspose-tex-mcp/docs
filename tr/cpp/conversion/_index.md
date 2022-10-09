---
translation: true
template: /_templates/_conversion-cpp.md
title: TeX (LaTeX) Dosyaları Dönüştürme | C++
url: /cpp/conversion/
keywords: tex dönüştürücü cpp api, tex dönüştürücü c++ api
description: TeX(LaTeX) dönüştürme C++ API çözümü. LaTeX dosyalarını birkaç satır C++ koduyla PNG, JPEG, TIFF, BMP dahil olmak üzere PDF, XPS ve Görüntülere dönüştürün.
family: tex
platformtag: cpp
feature: conversion
---

{{<section banner>}}
---
h1: TeX ve LaTeX'i Dönüştür
h2: "C++ için TeX dönüştürücü API Çözümü."
---

{{<section overview>}}
---
p1: "Aspose.TeX, Object TeX sistemine yönelik bir API'dir, Tex dosyasının ayrıntıları için burada [Tex tanıtımı](https://docs.aspose.com/tex/cpp/what-is-tex/). Geliştiriciler, C++ için API'yi entegre ederek TeX'i kolayca PDF, XPS, PNG, JPG, BMP ve TIFF biçimlerine dönüştürebilir. Aşağıda, programcıların geliştirip LaTex çözümlerine entegre edebileceği birkaç kod örneği verilmiştir."
p2: "Buradaki Java için API çözümü, TeX ve LaTeX dosyalarını programlı olarak dönüştürmenize olanak tanır, ancak bu yerel sürümlerde geliştirilen [platformlar arası Dönüştürücüleri](https://products.aspose.app/tex/conversion) görüp denemeyi yararlı bulabilirsiniz. API'ler. Burada ayrıca TeX dosyaları, tablolar, grafikler oluşturmak ve düzenlemek, dosyaları PDF formatında birleştirmek vb. için [uygulamalar](https://products.aspose.app/tex/applications) bulabilirsiniz."
---

{{<section feature1>}}
---
title: "LaTeX'i Görüntüler, XPS, PDF, SVG C++'a dönüştürün."
h3: "C++ kod örneği TeX to Images,XPS,PDF veya SVG dönüşümü."
item1: "API, çıktı biçimleri olarak BMP, JPEG, PDF, SVG, TIFF, XPS ve PNG'yi destekler. TeX dosyalarını Görüntüler, PDF, XPS veya SVG'ye dönüştürmek için sonraki adımları uygulayın:"
item2: "[TeXOptions Sınıfı](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options) örneğini oluşturun."
item3: "[*ImageDevice*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.image_device) kullanarak görüntü türünü ve boyutunu tanımlayın."
item4: "[*OutputWorkingDirectory*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options#aa4f4ea6dab7db5ba1b40800495f16f63)/[*InputWorkingDirectory*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options#aa4f4ea6dab7db5ba1b40800495f16f63)."
item5: "[*BmpSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.bmp_save_options), [*PngSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.png_save_options), [*TiffSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.tiff_save_options), [*JpegSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.jpeg_save_options) veya [*PdfSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.pdf.pdf_save_options), [*SvgSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.svg.svg_save_options), [*XpsSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_save_options), ayarlanması gerekmez."
item6: "[ImageDevice](https://reference.aspose.com) için [*TeXJob()*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_job) Çalıştırma [ImageDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.image_device) veya [PdfDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.pdf.pdf_device), [ SvgDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.svg.svg_device), [XpsDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_device)."
item7: "Aspose.TeX for C++, C++'ı destekleyen herhangi bir geliştirme ortamında iyi çalışır, ancak aşağıdaki gereksinimler şiddetle tavsiye edilir:"
item8: Microsoft Visual Studio 2015 veya üzeri.
item9: Microsoft Windows masaüstü (7, 8, 10).
item10: Sunucu işletim sistemleri (2008, 2012), vb.
item11: Linux sistemleri (Ubuntu-16.04 veya üstü).
---


