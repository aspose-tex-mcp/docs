---
translation: true
template: /templates/_template-java.md
title: LaTeX в изображение | Aspose.TeX для Java
linktitle: LaTeX для изображения
weight: 10
url: /java/latex-to-image/
aliases:
- /java/latex-to-png/
- /java/latex-to-svg/
keywords: латех в png, латех png, латех в изображение, латехное изображение, латех в jpg, латех jpg, латех в jpeg, латех jpeg, латех в tiff, латех tiff, латех в bmp, латех bmp
description: Чтобы преобразовать TeX в форматы изображений с помощью решения Aspose.TeX API для Java, изучите эту статью, в которой описывается, как это сделать, и примеры кода.
lastmod: "2024-09-24"
---

{{<section overview>}}
**Aspose.TeX for Java** предоставляет функции для преобразования файлов LaTeX в ряд форматов растровых изображений.

## Как конвертировать LaTeX в PNG

Давайте подробнее рассмотрим код Java, обеспечивающий самый простой способ преобразования LaTeX в формат PNG.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-LaTeXToPng-Simplest.java" >}}

Итак, первое, что нам нужно сделать (иногда не самое первое, как мы узнаем позже) — это создать экземпляр класса [TeXOptions](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions). Единственный статический метод, который это делает, — [consoleAppOptions()](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#consoleAppOptions-com.aspose.tex.TeXConfig-), поэтому не будем заморачиваться над значением его имени. Метод принимает экземпляр [objectLaTeX()](https://reference.aspose.com/tex/java/com.aspose.tex/TeXConfig#objectLaTeX--) класса [TeXConfig](https://reference.aspose.com/tex/java/com.aspose.tex/TeXConfig), который точно подходит для преобразования [файла LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Эта конфигурация предписывает механизму Object TeX загрузить формат Object LaTeX и быть готовым принять файл LaTeX. Формат Object LaTeX на самом деле представляет собой формат [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), за исключением того, что он использует специальные примитивы [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) для настройки показателей страницы.

Первая из обязательных опций — [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--), которая определяет пространство или область, куда будет записываться вывод TeX. [Здесь](/tex/{{lang.url-fragment}}java/aspose-tex-output/) приведены подробные сведения о концепции выходного каталога в **Aspose.TeX для Java**. В этом примере мы используем класс [OutputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/OutputFileSystemDirectory), который позволяет нам записывать выходные данные в указанный каталог или папку.

Второй вариант — это экземпляр класса [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/SaveOptions), который будет управлять преобразованием [объектной модели](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) в целевой формат. Поскольку мы конвертируем LaTeX в PNG, именно экземпляр класса [PngSaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PngSaveOptions) позволяет нам указать разрешение выходных изображений.

Далее нам нужно создать экземпляр класса [TeXJob](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob). Желая преобразовать файл LaTeX, хранящийся в файловой системе, мы используем [эту](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob#TeXJob-java.lang.String-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-) версию конструктора. Нам следует указать полный путь к файлу. В противном случае движок будет искать его в текущем каталоге (который определен [здесь](https://docs.oracle.com/javase/7/docs/api/java/io/File.html)) и, скорее всего, не найдет. Тем не менее, мы можем опустить расширение, если наш файл имеет расширение *.tex*. Движок добавит его автоматически. Второй аргумент конструктора — это экземпляр класса [Device](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/Device). Поскольку мы конвертируем LaTeX в PNG, это экземпляр класса [ImageDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/ImageDevice) (который является общим для всех поддерживаемых форматов изображений). В качестве последнего аргумента мы передаем недавно подготовленные варианты конвертации.

Все, что нам нужно сделать сейчас, это [запустить](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob#run--) задание.

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
Output written on hello-world.png (1 page).
Transcript written on hello-world.log.
```

Остальные продукты запуска движка мы найдем в папке, которую мы указали в качестве выходного каталога. Это будет файл стенограммы (.log) и, **Вуаля!**, основные выходные файлы изображений PNG.

## Альтернативный способ записи основного выходного файла PNG.

Есть еще один способ получить данные изображения в виде массива байтовых массивов: каждый массив во втором измерении представляет данные изображения для отдельной страницы.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-LaTeXToPng-Alternative.java" >}}

Файл(ы) *"page-n.png"* будут записаны по любому указанному нами пути. В отличие от [Вывод PDF](/tex/{{lang.url-fragment}}java/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file), они будут дублировать выходные файлы PNG, записанные в выходной каталог.

## О параметрах ввода

Если наш основной входной файл требует зависимостей, например, пакетов, которые не включены в базовую систему LaTeX и поддерживаемых пакетов, мы ДОЛЖНЫ установить параметр [RequiredInputDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getRequiredInputDirectory--) аналогично тому, как мы устанавливаем параметр [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--). и поместите зависимости в этот каталог. Зависимости могут быть произвольно организованы в подкаталогах. Если у нас есть собственные файлы, которые нужно включить в процесс верстки, скажем, внешние графические файлы, мы ДОЛЖНЫ также установить [InputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getInputWorkingDirectory--), используя путь к месту, где собраны эти файлы. Мы также можем поместить основной входной файл где-нибудь внутри входного каталога и указать относительный путь в методе `run()` (или вообще не указывать путь, если основной входной файл находится в корне). [Здесь](/tex/{{lang.url-fragment}}java/aspose-tex-input/) приведены подробные сведения о концепции входного каталога в **Aspose.TeX для Java** и предоставленных реализациях.

Другие варианты работы в TeX обсуждаются [здесь](/tex/{{lang.url-fragment}}java/other-options/).

**Вы также можете ознакомиться с бесплатным преобразованием LaTeX в PNG [веб-приложение](https://products.aspose.app/tex/conversion/latex-to-png), созданным на основе API [Aspose.TeX for .NET](https://products.aspose.com/tex/net/). [Здесь](https://products.aspose.com/tex/java/) — страница версии Java.**

Ниже мы обсудим преобразование LaTeX в другие поддерживаемые форматы растровых изображений. Мы не будем вдаваться в подробности только потому, что на самом деле никаких подробностей нет. Единственная разница заключается в типе свойства [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getSaveOptions--) в параметрах преобразования.

## Как конвертировать LaTeX в JPG

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-LaTeXToJpeg.cs" >}}

**Вы также можете ознакомиться с бесплатным [веб-приложением](https://products.aspose.app/tex/conversion/latex-to-jpg) для преобразования LaTeX в JPG, созданным на основе API [Aspose.TeX for .NET](https://products.aspose.com/tex/net/). [Здесь](https://products.aspose.com/tex/java/) — страница версии Java.**

## Как конвертировать LaTeX в TIFF

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-LaTeXToTiff.cs" >}}

**Вы также можете ознакомиться с бесплатным преобразованием LaTeX в TIFF [веб-приложение](https://products.aspose.app/tex/conversion/latex-to-tiff), созданным на основе API [Aspose.TeX for .NET](https://products.aspose.com/tex/net/). [Здесь](https://products.aspose.com/tex/java/) — страница версии Java.**

## Как конвертировать LaTeX в BMP

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-LaTeXToBmp.cs" >}}

**Вы также можете ознакомиться с бесплатным [веб-приложением](https://products.aspose.app/tex/conversion/latex-to-bmp) для преобразования LaTeX в BMP, созданным на основе API [Aspose.TeX for .NET](https://products.aspose.com/tex/net/). [Здесь](https://products.aspose.com/tex/java/) — страница версии Java.**


## Как конвертировать LaTeX в SVG

И еще один поддерживаемый целевой формат — [**SVG**](https://en.wikipedia.org/wiki/SVG). **Масштабируемая векторная графика (SVG)** — это формат векторных изображений на основе XML для определения двумерной графики с поддержкой интерактивности и анимации.

Изображения **SVG** определяются в формате векторной графики и сохраняются в текстовых файлах XML. Это означает, что изображения **SVG** можно масштабировать без потери качества, а файлы **SVG** можно искать, индексировать, создавать сценарии и сжимать. Текстовые файлы XML можно создавать и редактировать с помощью текстовых редакторов или редакторов векторной графики. Они отображаются наиболее часто используемыми веб-браузерами.

Кроме того, существует библиотека [**Aspose.SVG**](https://products.aspose.com/svg/), которая имеет различные функции, основанные на формате **SVG**. К ним относятся создание, загрузка, редактирование и преобразование документов **SVG**.

Преобразование в SVG так же просто, как и [преобразование в форматы растровых изображений](/tex/{{lang.url-fragment}}java/latex-to-image/), за исключением того, что в дополнение к [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getSaveOptions--) нам нужно изменить устройство на экземпляр [SvgDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/SvgDevice).

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-LaTeXToSvg-Simplest.java" >}}

**Вы также можете ознакомиться с бесплатным преобразованием LaTeX в SVG [веб-приложение](https://products.aspose.app/tex/conversion/latex-to-svg), созданным на основе [Aspose.TeX for .NET](https://products.aspose.com/tex/net/). [Здесь](https://products.aspose.com/tex/java/) — страница версии Java.**