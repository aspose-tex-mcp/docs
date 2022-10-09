---
translation: true
template: /_templates/_conversion-cpp.md
title: Преобразование файлов TeX (LaTeX) | С++
url: /cpp/conversion/
keywords: tex Converter cpp API, tex Converter C++ API
description: Решение TeX(LaTeX) для преобразования C++ API. Преобразование файлов LaTeX в PDF, XPS и изображения, включая PNG, JPEG, TIFF, BMP, с помощью нескольких строк кода C++.
family: tex
platformtag: cpp
feature: conversion
---

{{<section banner>}}
---
h1: Конвертировать TeX и LaTeX
h2: "Решение API конвертера TeX для C++."
---

{{<section overview>}}
---
p1: "Aspose.TeX — это API для системы Object TeX. Для получения подробной информации о Tex-файле см. [Введение в Tex](https://docs.aspose.com/tex/cpp/what-is-tex/). Разработчики могут легко конвертировать TeX в форматы PDF, XPS, PNG, JPG, BMP и TIFF, интегрировав API для C++. Ниже приведены несколько примеров кода, которые программисты могут улучшить и интегрировать в решения LaTex."
p2: "Предлагаемое здесь API-решение для Java позволяет программно конвертировать файлы TeX и LaTeX, но вам может быть полезно посмотреть и попробовать [кросс-платформенные конвертеры](https://products.aspose.app/tex/conversion), разработанные на основе этих нативных API. Там вы также можете найти [приложения](https://products.aspose.app/tex/applications) для создания и редактирования файлов TeX, таблиц, графики, для объединения файлов в один из формата PDF и т. д."
---

{{<section feature1>}}
---
title: "Конвертируйте LaTeX в изображения, XPS, PDF, SVG C++."
h3: "Пример кода C++ Преобразование TeX в изображения, XPS, PDF или SVG."
item1: "API поддерживает BMP, JPEG, PDF, SVG, TIFF, XPS и PNG в качестве выходных форматов. Чтобы преобразовать файлы TeX в изображения, PDF, XPS или SVG, выполните следующие действия:"
item2: "Создайте экземпляр [класса TeXOptions](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options)."
item3: "Определите тип и размер изображения, используя [*ImageDevice*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.image_device)."
item4: "Укажите рабочий каталог файловой системы для вывода/ввода, используя [*OutputWorkingDirectory*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options#aa4f4ea6dab7db5ba1b40800495f16f63)/[*InputWorkingDirectory*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options#aa4f4ea6dab7db5ba1b40800495f16f63)."
item5: "Инициализируйте параметры сохранения с помощью [*BmpSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.bmp_save_options), [*PngSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.png_save_options), [*TiffSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.tiff_save_options), [*JpegSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.jpeg_save_options) или [*PdfSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.pdf.pdf_save_options), [*SvgSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.svg.svg_save_options), [*XpsSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_save_options), значение по умолчанию, устанавливать не нужно."
item6: "Запустите преобразование, используя метод запуска [*TeXJob()*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_job) для [ImageDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.image_device) или [PdfDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.pdf.pdf_device), [ SvgDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.svg.svg_device), [XpsDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_device)."
item7: "Aspose.TeX for C++ хорошо работает в любой среде разработки, поддерживающей C++, но настоятельно рекомендуется соблюдать следующие требования:"
item8: Microsoft Visual Studio 2015 или более поздней версии.
item9: Рабочий стол Microsoft Windows (7, 8, 10).
item10: Серверные операционные системы (2008, 2012) и др.
item11: Системы Linux (Ubuntu-16.04 или новее).
---


