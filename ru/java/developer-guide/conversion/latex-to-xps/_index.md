---
translation: true
template: /templates/_template-java.md
title: LaTeX в XPS | Aspose.TeX для Java
linktitle: LaTeX в XPS
weight: 12
url: /java/latex-to-xps/
aliases: /java/другие-целевые-форматы/
description: Функциональность преобразования решения Aspose.TeX API для Java позволяет конвертировать файлы LaTeX в формат XPS. Изучите примеры кода.
lastmod: "2024-09-24"
---

{{<section overview>}}


Другой целевой формат — [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). Файл **XPS** физически представляет собой ZIP-пакет, содержащий содержимое документа с разбивкой на страницы, а также метаданные, необходимые для правильного отображения конкретными средствами просмотра (например, Windows XPS Viewer) и печати. Все данные в пакете организованы в виде файлов в каталогах. Некоторые из них содержат такие ресурсы, как изображения, шрифты и профили ICC. Другие представляют собой XML-файлы в различных конкретных схемах. К последним относятся файлы, содержащие сами данные документа. Данные документа представляют собой набор файлов – каждый файл содержит данные для отдельной страницы документа. Такие файлы состоят из одного элемента страницы и дерева дочерних элементов — *Canvas*, *Path* и *Glyphs*. *Canvas* — это элемент группировки, который может содержать другие *Canvas*, *Paths* и *Glyphs*. Его цель — контроль над внешним видом всех дочерних элементов как группы. Элементы *Path* используются для определения путей векторной графики. А элементы *Glyphs* используются для определения текстового содержимого. Все три элемента обладают свойствами, определяющими различные аспекты внешнего вида.

Существует библиотека [**Aspose.Page**](https://products.aspose.com/page/), которая предоставляет API для работы с документами XPS, а также для их преобразования в форматы PDF и растровых изображений.

## Как конвертировать LaTeX в XPS

Преобразование в XPS так же просто, как и [преобразование в форматы растровых изображений](/tex/{{lang.url-fragment}}java/latex-to-image/), за исключением того, что в дополнение к [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getSaveOptions--) нам нужно использовать экземпляр класса [XpsDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/XpsDevice).

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-LaTeXToXps-Simplest.java" >}}

### Альтернативный способ записи основного выходного файла XPS.

Есть еще один конструктор класса [XpsDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/XpsDevice#XpsDevice-java.io.OutputStream-), который позволяет нам получить результирующий XPS-файл альтернативным способом.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-LaTeXToXps-Alternative.java" >}}

Эффект тот же, что мы получаем [здесь](/tex/{{lang.url-fragment}}java/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file).

**Вы также можете ознакомиться с бесплатным преобразованием LaTeX в XPS [веб-приложение](https://products.aspose.app/tex/conversion/latex-to-xps), созданным на основе API [Aspose.TeX for .NET](https://products.aspose.com/tex/net/). [Здесь](https://products.aspose.com/tex/java/) — страница версии Java.**