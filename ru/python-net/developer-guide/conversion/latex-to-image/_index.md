---
translation: true
template: /templates/_template-python-net.md
title: LaTeX в изображение | Python через .NET
linktitle: LaTeX для изображения
weight: 10
url: /python-net/latex-to-image/
keywords: латех в png, латех png, латех в изображение, латехное изображение, латех в jpg, латех jpg, латех в jpeg, латех jpeg, латех в tiff, латех tiff, латех в bmp, латех bmp
description: Чтобы преобразовать TeX в форматы изображений с помощью Aspose.TeX API для Python, изучите эту статью, чтобы увидеть, как это сделать, и примеры кода.
lastmod: "2024-09-24"
---

{{<section overview>}}

**Aspose.TeX for Python** предоставляет нам возможность конвертировать файлы LaTeX в различные форматы растровых изображений.

## Преобразование LaTeX в PNG

Теперь давайте подробно рассмотрим код Python, который предлагает наиболее простой подход к преобразованию LaTeX в формат PNG.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToPng-Simplest.py" >}}

Для начала нам нужно создать экземпляр класса [TeXOptions](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/) с помощью метода [console_app_options()](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/console_app_options/#aspose.tex.TeXConfig)  . Не беспокойтесь об имени, это просто статический метод, который создает экземпляр. Этот метод использует экземпляр [object_latex](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_latex/) класса [TeXConfig](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/), который идеально подходит для преобразования [файла LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Эта конфигурация настраивает механизм Object TeX для загрузки формата Object LaTeX и готовности к обработке файла LaTeX. Формат Object LaTeX по сути аналогичен [формату LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), но для определения показателей страницы он использует специфические примитивы [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex).

Первая из необходимых опций — [output_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/output_working_directory/), которая определяет место, где будут сохранены выходные данные TeX. Если интересно, вы можете узнать дополнительную информацию о концепции [каталога вывода в **Aspose.TeX for Python**](/tex/{{lang.url-fragment}}python-net/aspose-tex-output/). В этом конкретном примере мы используем класс [OutputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputfilesystemdirectory/) для записи вывода в определенный каталог или папку.

Второй вариант — это экземпляр класса [SaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/saveoptions/), который отвечает за управление преобразованием из [объектной модели](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) в нужный формат. В этом случае, поскольку мы конвертируем LaTeX в PNG, мы используем экземпляр класса [PngSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.image/pngsaveoptions/), который позволяет нам указать разрешение выходных изображений.

Далее мы создаем экземпляр класса [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/). В данном случае, поскольку мы хотим преобразовать файл LaTeX, хранящийся в файловой системе, мы используем [эту версию конструктора](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#str-aspose.tex.presentation.Device-aspose.tex.TeXOptions)  . Нам необходимо указать полный путь к файлу, иначе движок будет искать его в текущем каталоге (который является рабочим каталогом скрипта) и может не найти. Однако расширение `.tex` можно опустить, поскольку движок автоматически добавит его. Второй аргумент конструктора — это экземпляр класса [Device](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/device/). Поскольку мы конвертируем LaTeX в PNG, это экземпляр класса [ImageDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.image/imagedevice/), который является общим для всех поддерживаемых форматов изображений. Наконец, мы передаем подготовленные параметры преобразования в качестве последнего аргумента.

Теперь остается только [запустить](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/run/#) задание.

После выполнения задания, независимо от его успеха или неудачи, первым результатом, с которым мы столкнемся, является вывод терминала. В случае успешного запуска вывод будет выглядеть следующим образом:


```text
This is ObjectTeX, Version 3.1415926-1.0 (Aspose.TeX 21.8)
entering extended mode

(<input_directory>\hello-world.ltx
LaTeX2e <2011/06/27>
(article.cls
Document Class: article 2007/10/19 v1.4h Standard LaTeX document class
(size10.clo))
No file hello-world.aux.
[1]
(<output_directory>\hello-world.aux) )
Output written on hello-world.png (1 page).
Transcript written on hello-world.log.
```

Результаты работы движка можно найти в указанном нами выходном каталоге. Сюда будет входить файл стенограммы и, что наиболее важно, основной выходной файл(ы) изображений PNG.

## Альтернативный способ записи основного выходного файла PNG.

Существует альтернативный метод получения данных изображения в виде массива байтовых массивов, где каждый массив во втором измерении представляет данные изображения для отдельной страницы.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToPng-Alternative.py" >}}

Файл(ы) «page-n.png» можно записать по любому указанному пути. В отличие от [Вывод PDF](/tex/{{lang.url-fragment}}python-net/latex-to-pdf/#an-alternative-way-to-write-the-main-output-pdf-file), эти файлы PNG дублируют выходные файлы PNG, записанные в выходной каталог.

## По поводу вариантов ввода

Если наш основной входной файл требует зависимостей, таких как пакеты, которые не включены в базовую систему LaTeX, или поддерживаемые пакеты, нам нужно установить параметр [required_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/) аналогично тому, как мы устанавливаем параметр *output_working_directory* и поместите зависимости в этот каталог. При необходимости зависимости можно организовать в подкаталогах. Если у нас есть файлы, которые нужно включить в процесс верстки, например внешние графические файлы, нам также необходимо установить [input_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/input_working_directory/) в место хранения этих файлов. Мы также можем поместить основной входной файл во входной каталог и указать относительный путь в методе run() или вообще не указывать путь, если основной входной файл находится в корневом каталоге. Также есть более подробная информация о [концепции входного каталога](/tex/{{lang.url-fragment}}python-net/aspose-tex-input/) в **Aspose.TeX** и описанных реализациях.

Также изучите [другие варианты работы в TeX здесь](/tex/{{lang.url-fragment}}python-net/other-options/).

**Вы также можете изучить бесплатное [веб-приложение](https://products.aspose.app/tex/conversion/latex-to-png) для преобразования LaTeX в PNG, разработанное с использованием [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**

Ниже мы кратко объясним преобразование LaTeX в другие поддерживаемые форматы растровых изображений, не вдаваясь в подробности, поскольку существенных различий нет. Единственное изменение заключается в типе свойства [save_options](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/save_options/) в параметрах преобразования.

## Преобразование LaTeX в JPG

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToJpeg.py" >}}

**Вы также можете изучить бесплатное [веб-приложение для преобразования LaTeX в JPG](https://products.aspose.app/tex/conversion/latex-to-jpg), разработанное с использованием [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**

## Преобразование LaTeX в TIFF

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToTiff.py" >}}

**Вы также можете изучить бесплатное [веб-приложение для преобразования LaTeX в TIFF](https://products.aspose.app/tex/conversion/latex-to-tiff), разработанное с использованием [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**

## Преобразование LaTeX в BMP

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToBmp.py" >}}

**Вы также можете изучить бесплатное [веб-приложение для преобразования LaTeX в BMP](https://products.aspose.app/tex/conversion/latex-to-bmp), разработанное с использованием [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**


## Преобразование LaTeX в SVG

Другой поддерживаемый целевой формат — [**SVG**](https://en.wikipedia.org/wiki/SVG). **Масштабируемая векторная графика (SVG)** — это формат векторных изображений на основе XML, который используется для определения двухмерной графики. Он поддерживает интерактивность и анимацию.

Изображения **SVG** хранятся в текстовых файлах XML и определяются в формате векторной графики. Это означает, что изображения **SVG** можно масштабировать без потери качества, а сами файлы **SVG** можно искать, индексировать, создавать сценарии и сжимать. Текстовые файлы XML можно создавать и редактировать с помощью текстовых редакторов или редакторов векторной графики, а также обрабатывать их с помощью наиболее часто используемых веб-браузеров.

API [**Aspose.SVG**](https://products.aspose.com/svg/) предлагает ряд функций для работы с **SVG**, таких как создание, загрузка, редактирование и преобразование **SVG** документов.

Преобразование LaTeX в SVG так же просто, как и [преобразование в форматы растровых изображений](/tex/{{lang.url-fragment}}python-net/latex-to-image/), с той лишь разницей, что для параметра [save_options](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/save_options/) должен быть установлен экземпляр класса [SvgSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.svg/svgsaveoptions/) и устройство необходимо изменить на экземпляр класса [SvgDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.svg/svgdevice/).

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToSvg-Simplest.py" >}}

**Вы также можете изучить бесплатное [веб-приложение для преобразования LaTeX в SVG](https://products.aspose.app/tex/conversion/latex-to-svg), разработанное с использованием [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**