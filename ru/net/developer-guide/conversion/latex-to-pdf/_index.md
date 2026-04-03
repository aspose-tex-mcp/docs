---
translation: true
template: /templates/_template-net.md
title: LaTeX в PDF | .NET
linktitle: LaTeX в PDF
weight: 11
url: /net/latex-to-pdf/
keywords: латех в pdf, латех pdf, конвертировать латех в pdf
description: Чтобы преобразовать TeX в PDF с помощью решения Aspose.TeX API для .NET, изучите эту статью, чтобы увидеть, как это сделать, и примеры кода.
lastmod: "2026-04-03"
---

{{<section overview>}}


## Как конвертировать LaTeX в PDF

Давайте подробно рассмотрим код на C#, обеспечивающий самый простой способ преобразования LaTeX в формат PDF.

{{< gist "aspose-com-gists""507170b996a1d0c39bb4374e888b3205""Example-ConvertLaTeXToPDF-Simplest.cs" >}}

Итак, первое, что нам нужно сделать (ну, иногда не самое первое), — это создать экземпляр класса [TeXOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/). Единственный статический метод, который это делает, — [ConsoleAppOptions()](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions/), поэтому давайте не будем озадачиваться значением его имени. Метод принимает [экземпляр](https://reference.aspose.com/tex/net/aspose.tex/texconfig/objectlatex/) класса [TeXConfig](https://reference.aspose.com/tex/net/aspose.tex/texconfig/), который точно подходит для преобразования [файла LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Эта конфигурация сообщает механизму Object TeX загрузить формат Object LaTeX и быть готовым принять файл LaTeX. Формат Object LaTeX на самом деле представляет собой формат [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), за исключением того, что он использует специальные примитивы [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) для настройки показателей страницы.

Первая из обязательных опций — [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/), которая определяет пространство или область, куда будет записываться вывод TeX. [Здесь](/tex/{{lang.url-fragment}}net/aspose-tex-output/) приведены подробности концепции выходного каталога в **Aspose.TeX для .NET**. В этом примере мы используем класс [OutputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/), который позволяет нам записывать выходные данные в указанный каталог или папку.

Второй вариант — это экземпляр класса [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation/saveoptions/), который будет управлять преобразованием [объектной модели](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) в целевой формат. Поскольку мы конвертируем LaTeX в PDF, это экземпляр класса [PdfSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/).

Затем нам нужно создать экземпляр класса [TeXJob](https://reference.aspose.com/tex/net/aspose.tex/texjob/). Желая преобразовать файл LaTeX, хранящийся в файловой системе, мы используем [эту](https://reference.aspose.com/tex/net/aspose.tex/texjob/texjob/) версию конструктора. Мы должны указать полный путь к файлу. В противном случае движок будет искать его в текущем каталоге (то есть [CurrentDirectory](https://docs.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory)) и, скорее всего, не найдет. Тем не менее, мы можем опустить расширение, если наш файл имеет расширение *.tex*. Движок добавит его автоматически. Второй аргумент конструктора — это экземпляр класса [Device](https://reference.aspose.com/tex/net/aspose.tex.presentation/device/). Поскольку мы конвертируем LaTeX в PDF, это экземпляр класса [PdfDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/). В качестве последнего аргумента мы передаем недавно подготовленные варианты конвертации.

Все, что осталось сделать сейчас, это [запустить](https://reference.aspose.com/tex/net/aspose.tex/texjob/run/) задание.

Независимо от того, был ли запуск успешным или нет, первым результатом, который мы увидим, будет вывод терминала. В случае успеха это выглядит примерно так:


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

Остальные «плоды» труда движка мы найдем в папке, которую мы указали в качестве выходного каталога. Это будет файл стенограммы и, **вот он!**, основной выходной PDF-файл.

## Альтернативный способ записи основного выходного PDF-файла.

Есть еще один конструктор класса [PdfDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/pdfdevice/), который позволяет нам получить результирующий PDF-файл альтернативным способом.

{{< gist "aspose-com-gists""507170b996a1d0c39bb4374e888b3205""Example-ConvertLaTeXToPDF-Alternative.cs" >}}

Файл *any-name.pdf* в указанном каталоге будет нашим основным выходным PDF-файлом. В то же время, в отличие от [вывод изображения](/tex/{{lang.url-fragment}}net/latex-to-png/#an-alternative-way-to-write-main-output-png-files), мы не найдем никаких PDF-файлов в выходном каталоге, определенном параметрами преобразования. Исключение: *any-name.pdf* находится (по пути) в том же каталоге файловой системы, который назначен параметру [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) с помощью [OutputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/).

## О параметрах ввода

Если наш основной входной файл требует зависимостей, например, пакетов, которые не включены в базовую систему LaTeX и поддерживаемых пакетов, мы ДОЛЖНЫ установить параметр [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) аналогично тому, как мы устанавливаем параметр [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/). и поместите зависимости в этот каталог. Зависимости могут быть произвольно организованы в подкаталогах. Если у нас есть собственные файлы, которые нужно включить в процесс верстки, скажем, внешние графические файлы, мы ДОЛЖНЫ также установить [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/inputworkingdirectory/), используя путь к месту, где собраны эти файлы. Мы также можем поместить основной входной файл где-нибудь внутри входного каталога и указать относительный путь в методе `run()` (или вообще не указывать путь, если основной входной файл находится в корне). [Здесь](/tex/{{lang.url-fragment}}net/aspose-tex-input/) приведены подробные сведения о концепции входного каталога в **Aspose.TeX for .NET** и предоставленных реализациях.

Другие варианты работы в TeX обсуждаются [здесь](/tex/{{lang.url-fragment}}net/other-options/).

**Вы также можете ознакомиться с бесплатным преобразованием LaTeX в PDF [веб-приложение](https://products.aspose.app/tex/conversion/latex-to-pdf), созданным на основе [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**