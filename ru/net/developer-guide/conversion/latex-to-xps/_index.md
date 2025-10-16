---
translation: true
template: /templates/_template-net.md
title: LaTeX в XPS | .NET
linktitle: LaTeX в XPS
weight: 12
url: /net/latex-to-xps/
description: Функциональность преобразования решения Aspose.TeX API для .NET позволяет конвертировать файлы LaTeX в формат XPS.
lastmod: "2024-09-24"
---

{{<section overview>}}


Другой целевой формат — [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). Файл **XPS** физически представляет собой ZIP-пакет, содержащий содержимое документа с разбивкой на страницы, а также метаданные, необходимые для правильного отображения конкретными средствами просмотра (например, Windows XPS Viewer) и печати. Все данные в пакете представлены файлами. Некоторые из них являются двоичными и содержат такие ресурсы, как изображения, шрифты и профили ICC. Другие представляют собой XML-файлы в различных конкретных схемах. К последним относятся файлы, содержащие сами данные документа. Данные документа состоят из набора файлов – каждый файл содержит данные для отдельной страницы документа. Такие файлы состоят из одного элемента страницы и дерева дочерних элементов — *Canvas*, *Path* и *Glyphs*. *Canvas* — это элемент группировки, который может содержать другие *Canvas*, *Paths* и *Glyphs*. Он служит для управления внешним видом всех дочерних элементов как группы. Элементы *Path* используются для определения путей векторной графики. А элементы *Glyphs* используются для определения текстового содержимого. Все три элемента обладают свойствами, определяющими различные аспекты внешнего вида.

Существует библиотека [**Aspose.Page**](https://products.aspose.com/page/), которая предоставляет API для работы с документами XPS, а также для их преобразования в форматы PDF и растровых изображений.

## Как конвертировать LaTeX в XPS

Преобразование LaTeX в XPS так же просто, как и [преобразование в форматы растровых изображений](/tex/{{lang.url-fragment}}net/latex-to-image/), за исключением того, что для [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) ДОЛЖЕН быть установлен экземпляр класса [XpsSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpssaveoptions/) (по умолчанию или явно), и устройство ДОЛЖНО быть изменено на экземпляр класса [XpsDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/).

**Простейший пример преобразования**

В примере ниже показано, как преобразовать файл LaTeX в XPS за несколько шагов:

1. Создайте экземпляр `TexDocument`.
2. Загрузите исходный файл `.tex` с помощью `TexDocument.Load`.
3. (Необязательно) настройте `XpsSaveOptions`, например, параметры сжатия.
4. Сохраните документ в XPS, вызвав `document.Save` с `XpsDevice`.

Этот код демонстрирует самый простой способ создания XPS-файла из LaTeX.

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-LaTeXToXps-Simplest.cs" >}}

### Альтернативный способ записи основного выходного файла XPS.

Есть еще один конструктор класса [XpsDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/xpsdevice/), который позволяет нам получить результирующий XPS-файл альтернативным способом.

**Альтернативный пример преобразования**

В этом фрагменте кода показано использование конструктора `XpsDevice`, принимающего `Stream`. Шаги следующие:

1. Создайте `TexDocument` и загрузите исходный файл LaTeX.
2. Создайте `MemoryStream` для хранения выходных данных XPS.
3. Создайте экземпляр `XpsDevice` с потоком.
4. Сохраните документ на устройстве, после чего вы сможете использовать поток (например, отправить его по сети или сохранить в базе данных).

Этот подход полезен, когда данные XPS нужны в памяти, а не в виде файла на диске.

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-LaTeXToXps-Alternative.cs" >}}

Эффект тот же, что мы получаем [здесь](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file).

**Вы также можете ознакомиться с бесплатным преобразованием LaTeX в XPS [веб-приложение](https://products.aspose.app/tex/conversion/latex-to-xps), созданным на основе [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**