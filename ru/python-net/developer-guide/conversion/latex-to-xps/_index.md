---
translation: true
template: /templates/_template-python-net.md
title: LaTeX в XPS | Aspose.TeX для Python
linktitle: LaTeX в XPS
weight: 12
url: /python-net/latex-to-xps/
aliases: /python-net/other-target-formats/
description: Решение Aspose.TeX API для Python предоставляет функции преобразования для преобразования файлов LaTeX в формат XPS.
lastmod: "2024-09-24"
---

{{<section overview>}}

Другой целевой формат — [**XPS**](https://docs.aspose.com/page/net/what-is-xps-file/). Файл [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification) по сути представляет собой ZIP-пакет, содержащий содержимое документа с разбивкой на страницы, а также необходимые метаданные для правильного отображения конкретными программами просмотра (например, Windows XPS Viewer) и печати. Пакет состоит из различных файлов, некоторые из которых являются двоичными и содержат такие ресурсы, как изображения, шрифты и профили ICC. Другие представляют собой XML-файлы в определенных схемах, включая файлы, содержащие сами данные документа. Данные документа разделены на несколько файлов, каждый из которых представляет отдельную страницу документа. Эти файлы состоят из одного элемента страницы и дерева дочерних элементов, включая *Canvas*, *Path* и *Glyphs*. Элемент *Canvas* — это элемент группировки, который может содержать другие *Canvas*, *Paths* и *Glyphs* и управляет внешним видом всех дочерних элементов как группы. Элементы *Path* используются для определения путей векторной графики, а элементы *Glyphs* используются для определения текстового содержимого. Все три элемента обладают свойствами, определяющими различные аспекты внешнего вида.

Существует библиотека [**Aspose.Page**](https://products.aspose.com/page/), которая предлагает API для работы с документами XPS, а также позволяет конвертировать эти документы в форматы PDF и растровых изображений.

## Преобразование LaTeX в XPS

Процесс преобразования LaTeX в XPS столь же прост, как и [преобразование в форматы растровых изображений](/tex/{{lang.url-fragment}}python-net/latex-to-image/). Однако для этого необходимо установить [save_options](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/save_options/) на экземпляр класса [XpsSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.xps/xpssaveoptions/) (по умолчанию или явно) и изменить устройство на экземпляр класса [XpsDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.xps/xpsdevice/).

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToXps-Simplest.py" >}}

### Альтернативный способ записи основного выходного файла XPS.

Для класса *XpsDevice* доступен альтернативный конструктор, который позволяет получить результирующий файл XPS другим способом.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToXps-Alternative.py" >}}

Эффект тот же, что мы получаем [здесь](/tex/{{lang.url-fragment}}python-net/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file).

**Вы также можете изучить бесплатное [веб-приложение для преобразования LaTeX в XPS](https://products.aspose.app/tex/conversion/latex-to-xps), разработанное с использованием [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**