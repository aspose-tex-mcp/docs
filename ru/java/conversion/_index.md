---
translation: true
template: /_templates/_conversion-java.md
title: Преобразование файлов TeX (LaTeX) | Java
url: /java/conversion/
description: Решение Java API преобразования TeX (LaTeX). Преобразование файлов LaTeX в PDF, XPS и изображения, включая PNG, JPEG, TIFF, BMP, с помощью нескольких строк кода Java.
keywords: tex convert api java, tex convert java интеграции
family: tex
platformtag: cpp
feature: conversion
---

{{<section banner>}}
---
h1: Конвертировать TeX и LaTeX
h2: "Решение API конвертера TeX для Java."
---

{{<section overview>}}
---
p1: "Aspose.TeX — это API для системы Object TeX. Для получения подробной информации о Tex-файле см. [Введение в Tex](https://docs.aspose.com/tex/cpp/what-is-tex/). Разработчики могут легко конвертировать TeX в форматы PDF, XPS, PNG, JPG, BMP и TIFF, интегрировав API для Java. Ниже приведены несколько примеров кода, которые программисты могут улучшить и интегрировать в решения Tex."
p2: "Предлагаемое здесь API-решение для Java позволяет программно конвертировать файлы TeX и LaTeX, но вам может быть полезно посмотреть и попробовать [кросс-платформенные конвертеры](https://products.aspose.app/tex/conversion), разработанные на основе этих нативных API. Там вы также можете найти [приложения](https://products.aspose.app/tex/applications) для создания и редактирования файлов TeX, таблиц, графики, для объединения файлов в один из формата PDF и т. д."
---

{{<section feature1>}}
---
title: "Конвертируйте LaTeX в изображения, XPS, PDF, SVG с помощью Java."
h3: "Пример кода Java Преобразование TeX в изображения, XPS, PDF или SVG."
item1: "API поддерживает BMP, JPEG, PDF, SVG, TIFF, XPS и PNG в качестве выходных форматов. Чтобы преобразовать файлы TeX в изображения, PDF, XPS или SVG, выполните следующие действия:"
item2: "Создайте экземпляр [класса TeXOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions)."
item3: "Укажите рабочий каталог файловой системы для вывода/ввода с помощью [*OutputWorkingDirectory*](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#setOutputWorkingDirectory-com.aspose.tex.IOutputWorkingDirectory-)/[*InputWorkingDirectory*](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#setInputWorkingDirectory-com.aspose.tex.IInputWorkingDirectory-)."
item4: "Инициализируйте параметры сохранения с помощью [*BmpSaveOptions*](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/BmpSaveOptions), [*PngSaveOptions*](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PngSaveOptions), [*TiffSaveOptions*](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/TiffSaveOptions) [*JpegSaveOptions*](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/JpegSaveOptions) или [*PdfSaveOptions*](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfSaveOptions), [*SvgSaveOptions*](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/SvgSaveOptions), [*XpsSaveOptions*](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/XpsSaveOptions), значение по умолчанию, устанавливать не нужно."
item5: "Запустите преобразование, используя метод Rum [*TeXJob()*](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob) для [ImageDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/ImageDevice) или [PdfDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfDevice), [SvgDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/SvgDevice), [XpsDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/XpsDevice)."
item6: "Aspose.TeX для Java хорошо работает в любой среде разработки, поддерживающей Java, но настоятельно рекомендуется соблюдать следующие требования:"
item7: Рабочий стол Microsoft Windows (7, 8, 10).
item8: Системы Linux (Ubuntu-16.04 или новее).
item9: Mac OS X.
item10: J2SE 8.0 (1.8) или выше (например, Java 10) Версия Java.
---

