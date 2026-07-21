---
translation: true
template: /templates/_template-python-net.md
title: LaTeX в PDF | Python через .NET
linktitle: LaTeX в PDF
weight: 11
url: /python-net/latex-to-pdf/
keywords: латех в pdf, латех pdf, конвертировать латех в pdf
description: Узнайте, как конвертировать TeX в PDF с помощью решения Aspose.TeX API для Python, из этой статьи, в которой приведены подробные объяснения и примеры кода.
lastmod: "2024-09-24"
---

{{<section overview>}}

## Преобразование LaTeX в PDF

Теперь давайте подробно рассмотрим код Python, который предлагает наиболее простой подход к преобразованию LaTeX в формат PDF.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToPdf-Simplest.py" >}}

Для начала нам нужно создать экземпляр класса [TeXOptions](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/). Метод [console_app_options()](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/console_app_options/#aspose.tex.TeXConfig)   — единственный статический метод, который выполняет эту задачу, поэтому не беспокойтесь о его названии. Этот метод принимает экземпляр [object_latex](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_latex/) класса [TeXConfig](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/), который идеально подходит для преобразования [файла LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Эта конфигурация предписывает механизму Object TeX загрузить формат Object LaTeX и подготовиться к обработке файла LaTeX. Формат Object LaTeX по существу аналогичен формату [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), но в нем используются специфические примитивы [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) для определения показателей страницы.

Первая опция, которую необходимо указать, — это [output_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/output_working_directory/), которая определяет место, где будут сохранены выходные данные TeX. При необходимости вы можете найти дополнительную информацию о [концепции выходного каталога в **Aspose.TeX**](/tex/{{lang.url-fragment}}net/aspose-tex-output/). В данном конкретном случае мы используем класс [OutputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputfilesystemdirectory/), который позволяет нам записывать выходные данные в указанный каталог или папку.

Для второго варианта требуется экземпляр класса [SaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/saveoptions/), который определяет, как [объектная модель](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) преобразуется в нужный формат. В нашем случае, когда мы конвертируем LaTeX в PDF, он относится к экземпляру класса [PdfSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfsaveoptions/).

Чтобы преобразовать файл LaTeX, хранящийся в файловой системе, нам нужно создать экземпляр класса [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/), используя [конструктор](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#str-aspose.tex.presentation.Device-aspose.tex.TeXOptions)  , который принимает полный путь к файлу в качестве параметра. Если мы не укажем полный путь, движок будет искать файл в текущем каталоге (который является рабочим каталогом скрипта) и может не найти его. Однако мы можем опустить расширение, если наш файл имеет расширение .tex, поскольку движок автоматически добавит его. Второй аргумент конструктора — это экземпляр класса [Device](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/device/). В нашем случае, поскольку мы конвертируем LaTeX в PDF, это экземпляр класса [PdfDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfdevice/). Наконец, в качестве последнего аргумента мы передаем недавно подготовленные параметры преобразования.

Теперь остается только [запустить](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/run/#) задание.

После выполнения, независимо от того, было оно успешным или нет, первое, что мы увидим — это вывод терминала. Если выполнение прошло успешно, вывод будет выглядеть примерно так:

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
Output written on hello-world.pdf (1 page).
Transcript written on hello-world.log.
```

В папке, которую мы указали в качестве выходной, мы найдем файл расшифровки и, **вот он!**, основной выходной PDF-файл, а также другие результаты работы движка.

## Альтернативный способ записи основного выходного PDF-файла.

Класс *PdfDevice* имеет еще один [конструктор](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfdevice/__init__/#io.RawIOBase), который позволяет нам получить результирующий PDF-файл другим способом.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToPdf-Alternative.py" >}}

Основной выходной PDF-файл будет называться «любое имя.pdf» и будет расположен в указанном каталоге. Однако, в отличие от [вывода изображения](/tex/{{lang.url-fragment}}python-net/latex-to-image/#an-alternative-way-to-write-the-main-output-png-files), в выходном каталоге, указанном параметрами преобразования, не будет других PDF-файлов. Исключением является случай, когда `any-name.pdf` находится в том же каталоге файловой системы, который назначен для параметра *output_working_directory* с помощью *OutputFileSystemDirectory*.

## О параметрах ввода

Если наш основной входной файл требует зависимостей, таких как пакеты, которые не включены в базовую систему LaTeX, и поддерживаемые пакеты, необходимо установить параметр [required_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/) аналогично тому, как мы установили параметр *output_working_directory* и поместите зависимости в этот каталог. Зависимости могут быть организованы в подкаталогах по желанию. Кроме того, если у нас есть собственные файлы для включения в процесс верстки, например внешние графические файлы, мы также должны установить [input_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/input_working_directory/), используя путь к месту, где хранятся эти файлы. Мы также можем поместить основной входной файл во входной каталог и указать относительный путь в методе run() или вообще не указывать путь, если основной входной файл находится в корне. Более подробную информацию о концепции входного каталога в **Aspose.TeX for Python** и предоставленных реализациях можно найти [здесь](/tex/{{lang.url-fragment}}python-net/aspose-tex-input/).

Также обсуждаются [другие варианты работы в TeX](/tex/{{lang.url-fragment}}python-net/other-options/).

**Вы также можете изучить бесплатное [веб-приложение для преобразования LaTeX в PDF](https://products.aspose.app/tex/conversion/latex-to-pdf), разработанное с использованием [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**