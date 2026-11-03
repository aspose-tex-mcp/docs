---
translation: true
template: /templates/_template-net.md
title: LaTeX в XPS | .NET
linktitle: LaTeX в XPS
weight: 12
url: /net/latex-to-xps/
description: Функциональность преобразования решения Aspose.TeX API для .NET позволяет конвертировать файлы LaTeX в формат XPS.
lastmod: "2026-11-02"
---

{{<section overview>}}


Другой целевой формат — [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). Файл **XPS** физически представляет собой ZIP-пакет, содержащий содержимое документа с разбивкой на страницы, а также метаданные, необходимые для правильного отображения конкретными средствами просмотра (например, Windows XPS Viewer) и печати. Все данные в пакете представлены файлами. Некоторые из них являются двоичными и содержат такие ресурсы, как изображения, шрифты и профили ICC. Другие представляют собой XML-файлы в различных конкретных схемах. К последним относятся файлы, содержащие сами данные документа. Данные документа состоят из набора файлов – каждый файл содержит данные для отдельной страницы документа. Такие файлы состоят из одного элемента страницы и дерева дочерних элементов — *Canvas*, *Path* и *Glyphs*. *Canvas* — это элемент группировки, который может содержать другие *Canvas*, *Paths* и *Glyphs*. Он служит для управления внешним видом всех дочерних элементов как группы. Элементы *Path* используются для определения путей векторной графики. А элементы *Glyphs* используются для определения текстового содержимого. Все три элемента обладают свойствами, определяющими различные аспекты внешнего вида.

Существует библиотека [**Aspose.Page**](https://products.aspose.com/page/), которая предоставляет API для работы с документами XPS, а также для их преобразования в форматы PDF и растровых изображений.

## Как конвертировать LaTeX в XPS

Преобразование LaTeX в XPS так же просто, как и [преобразование в форматы растровых изображений](/tex/{{lang.url-fragment}}net/latex-to-image/), за исключением того, что для [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) ДОЛЖЕН быть установлен экземпляр класса [XpsSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpssaveoptions/) (по умолчанию или явно), и устройство ДОЛЖНО быть изменено на экземпляр класса [XpsDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/).

**Простейший пример преобразования**

В примере ниже показано, как преобразовать файл LaTeX в XPS за несколько шагов:

1. Создайте `TeXOptions` для формата ObjectLaTeX с помощью `TeXOptions.ConsoleAppOptions(TeXConfig.ObjectLaTeX)`.
2. Укажите выходной рабочий каталог, например `OutputFileSystemDirectory`.
3. Присвойте `SaveOptions` экземпляр `XpsSaveOptions`.
4. Запустите `TeXJob` для исходного файла `.tex` с `XpsDevice`. Файл XPS записывается в выходной рабочий каталог.

Этот код демонстрирует самый простой способ создания XPS-файла из LaTeX.

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToXPS-Simplest.cs" >}}

### Альтернативный способ записи основного выходного файла XPS.

Есть еще один конструктор класса [XpsDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/xpsdevice/), который позволяет нам получить результирующий XPS-файл альтернативным способом.

**Альтернативный пример преобразования**

В этом фрагменте кода показано использование конструктора `XpsDevice`, принимающего `Stream`. Шаги следующие:

1. Откройте поток, в который будет записан документ XPS (здесь — файловый поток; `MemoryStream` работает так же).
2. Создайте `TeXOptions`, укажите выходной рабочий каталог и присвойте `SaveOptions` экземпляр `XpsSaveOptions`, как в предыдущем примере.
3. Запустите `TeXJob` с `XpsDevice`, созданным с этим потоком. Документ XPS записывается в поток; остальные выходные файлы, например протокол, по-прежнему записываются в выходной рабочий каталог.

Этот подход полезен, когда документ XPS нужно записать в выбранный вами поток, например чтобы хранить его в памяти или отправить по сети.

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToXPS-Alternative.cs" >}}

Эффект тот же, что мы получаем [здесь](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-the-main-output-pdf-file).

**Вы также можете ознакомиться с бесплатным преобразованием LaTeX в XPS [веб-приложение](https://products.aspose.app/tex/conversion/latex-to-xps), созданным на основе [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**