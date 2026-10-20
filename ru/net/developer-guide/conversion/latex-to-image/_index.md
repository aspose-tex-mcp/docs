---
translation: true
template: /templates/_template-net.md
title: LaTeX в изображение | .NET
linktitle: LaTeX для изображения
weight: 10
url: /net/latex-to-image/
keywords: латех в png, латех png, латех в изображение, латехное изображение, латех в jpg, латех jpg, латех в jpeg, латех jpeg, латех в tiff, латех tiff, латех в bmp, латех bmp
description: Чтобы преобразовать TeX в форматы изображений с помощью решения Aspose.TeX для .NET, изучите эту статью, чтобы увидеть, как это сделать, и примеры кода.
lastmod: "2026-04-22"
---

{{<section overview>}}

**Aspose.TeX for .NET** позволяет нам конвертировать файлы LaTeX в ряд форматов растровых изображений.

## Как конвертировать LaTeX в PNG

Давайте подробно рассмотрим код на C#, обеспечивающий самый простой способ преобразования LaTeX в формат PNG.

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToPNG-Simplest.cs" >}}

Итак, первое, что нам нужно сделать (ну, иногда не самое первое), — это создать экземпляр класса [TeXOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/). Единственный статический метод, который это делает, — [ConsoleAppOptions()](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions/), поэтому давайте не будем озадачиваться значением его имени. Метод принимает [экземпляр ObjectLaTeX](https://reference.aspose.com/tex/net/aspose.tex/texconfig/objectlatex/) класса [TeXConfig](https://reference.aspose.com/tex/net/aspose.tex/texconfig/), который точно подходит для преобразования [файла LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Эта конфигурация сообщает механизму Object TeX загрузить формат Object LaTeX и быть готовым принять файл LaTeX. Формат Object LaTeX на самом деле представляет собой формат [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), за исключением того, что он использует специальные примитивы [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) для настройки показателей страницы.

Первая из обязательных опций — [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/), которая определяет пространство или область, куда будет записываться вывод TeX. [Здесь](/tex/{{lang.url-fragment}}net/aspose-tex-output/) приведены подробности концепции выходного каталога в **Aspose.TeX для .NET**. В этом примере мы используем класс [OutputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/), который позволяет нам записывать выходные данные в указанный каталог или папку.

Второй вариант — это экземпляр класса [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation/saveoptions/), который будет управлять преобразованием [объектной модели](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) в целевой формат. Поскольку мы конвертируем LaTeX в PNG, именно экземпляр класса [PngSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.image/pngsaveoptions/) позволяет нам указать разрешение выходных изображений.

Затем нам нужно создать экземпляр класса [TeXJob](https://reference.aspose.com/tex/net/aspose.tex/texjob/). Желая преобразовать файл LaTeX, хранящийся в файловой системе, мы используем [эту](https://reference.aspose.com/tex/net/aspose.tex/texjob/texjob/) версию конструктора. Нам нужно указать полный путь к файлу. В противном случае движок будет искать его в текущем каталоге (то есть [CurrentDirectory](https://learn.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory?view=net-10.0)) и, скорее всего, не найдет. Тем не менее, расширение *.tex* может быть опущено. Движок добавит его автоматически. Второй аргумент конструктора — это экземпляр класса [Device](https://reference.aspose.com/tex/net/aspose.tex.presentation/device/). Поскольку мы конвертируем LaTeX в PNG, это экземпляр класса [ImageDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.image/imagedevice/), и он является общим для всех поддерживаемых форматов изображений. В качестве последнего аргумента мы передаем недавно подготовленные варианты конвертации.

Все, что осталось сделать сейчас, это [запустить](https://reference.aspose.com/tex/net/aspose.tex/texjob/run/) задание.

Независимо от того, был ли запуск успешным или нет, первым результатом, который мы увидим, будет вывод терминала. Если запуск прошел успешно, это будет выглядеть примерно так:


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

Остальные «плоды» труда движка мы найдем в папке, которую мы указали в качестве выходного каталога. Это будет файл стенограммы и, **вот он!**, основной выходной файл(ы) изображений PNG.

## Альтернативный способ записи основного выходного файла PNG.

Есть еще один способ получить данные изображения в виде массива байтовых массивов: каждый массив во втором измерении представляет данные изображения для отдельной страницы.

**Альтернативный пример преобразования**

В следующем фрагменте кода C# показан другой способ получения PNG-файла путем записи данных изображения в поток памяти, а не напрямую в файловую систему. Этот подход полезен, когда вам нужно сохранить сгенерированные байты PNG в памяти для дальнейшей обработки, например, для отправки по сети, сохранения в базе данных или выполнения дополнительных преобразований перед сохранением.

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToPNG-Alternative.cs" >}}

Файл(ы) *"page-n.png"* будут записаны по любому указанному нами пути. В отличие от [Вывод PDF](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file), они будут дублировать выходные файлы PNG, записанные в выходной каталог.

## О параметрах ввода

Если наш основной входной файл требует зависимостей, например, пакетов, которые не включены в базовую систему LaTeX и поддерживаемых пакетов, мы ДОЛЖНЫ установить параметр [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) аналогично тому, как мы устанавливаем параметр [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/). и поместите зависимости в этот каталог. Зависимости могут быть произвольно организованы в подкаталогах. Если у нас есть собственные файлы, которые нужно включить в процесс верстки, скажем, внешние графические файлы, мы ДОЛЖНЫ также установить [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/inputworkingdirectory/), используя путь к месту, где собраны эти файлы. Мы также можем поместить основной входной файл где-нибудь внутри входного каталога и указать относительный путь в методе `run()` (или вообще не указывать путь, если основной входной файл находится в корне). [Здесь](/tex/{{lang.url-fragment}}net/aspose-tex-input/) приведены подробные сведения о концепции входного каталога в **Aspose.TeX for .NET** и предоставленных реализациях.

Другие варианты работы в TeX обсуждаются [здесь](/tex/{{lang.url-fragment}}net/other-options/).

**Вы также можете ознакомиться с бесплатным преобразованием LaTeX в PNG [веб-приложение](https://products.aspose.app/tex/conversion/latex-to-png), созданным на основе [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**

Ниже мы обсудим преобразование LaTeX в другие поддерживаемые форматы растровых изображений, не углубляясь в детали, поскольку подробностей на самом деле нет. Единственная разница заключается в типе свойства [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) в параметрах преобразования.

## Как конвертировать LaTeX в JPG

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToJPEG.cs" >}}

**Вы также можете ознакомиться с бесплатным преобразованием LaTeX в JPG [веб-приложение](https://products.aspose.app/tex/conversion/latex-to-jpg), созданным на основе [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**

## Как конвертировать LaTeX в TIFF

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToTIFF.cs" >}}

**Вы также можете ознакомиться с бесплатным преобразованием LaTeX в TIFF [веб-приложение](https://products.aspose.app/tex/conversion/latex-to-tiff), созданным на основе [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**

## Как конвертировать LaTeX в BMP

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToBMP.cs" >}}

**Вы также можете ознакомиться с бесплатным [веб-приложением](https://products.aspose.app/tex/conversion/latex-to-bmp) для преобразования LaTeX в BMP, созданным на основе [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**

## Как конвертировать LaTeX в SVG

И еще один поддерживаемый целевой формат — [**SVG**](https://en.wikipedia.org/wiki/SVG). **Масштабируемая векторная графика (SVG)** — это формат векторных изображений на основе XML для определения двумерной графики с поддержкой интерактивности и анимации.

Изображения **SVG** определяются в формате векторной графики и сохраняются в текстовых файлах XML. Таким образом, изображения **SVG** можно масштабировать без потери качества, а файлы **SVG** можно искать, индексировать, создавать сценарии и сжимать. Текстовые файлы XML можно создавать и редактировать с помощью текстовых редакторов или редакторов векторной графики, и они отображаются в наиболее часто используемых веб-браузерах.

Существует библиотека [**Aspose.SVG**](https://products.aspose.com/svg/), которая предоставляет различные функции, связанные с **SVG**. К ним относятся создание, загрузка, редактирование и преобразование документов **SVG**.

Преобразование LaTeX в SVG так же просто, как [преобразование в форматы растровых изображений](/tex/{{lang.url-fragment}}net/latex-to-image/), за исключением того, что для [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) ДОЛЖЕН быть установлен экземпляр класса [SvgSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.svg/svgsaveoptions/), а устройство ДОЛЖНО быть изменен на экземпляр класса [SvgDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.svg/svgdevice/).

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToSVG-Simplest.cs" >}}

**Вы также можете ознакомиться с бесплатным преобразованием LaTeX в SVG [веб-приложение](https://products.aspose.app/tex/conversion/latex-to-svg), созданным на основе [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**