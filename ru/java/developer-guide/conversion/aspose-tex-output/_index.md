---
translation: true
template: /templates/_template-java.md
title: Выходной интерфейс Aspose.TeX | Java
linktitle: Выходной интерфейс Aspose.TeX
weight: 16
url: /java/aspose-tex-output/
description: Функциональность преобразования решения Aspose.TeX API для Java с TeX в качестве выходного формата объясняется здесь с примерами кода.
lastmod: "2026-04-21"
---

{{<section overview>}}

Пожалуйста, обратитесь к **Aspose.TeX for Java** [ссылка на API](https://reference.aspose.com/tex/java/com.aspose.tex/) для формальных определений реализации ввода-вывода.

Примеры файловой системы, ZIP и терминалов выполняют набор `hello-world.tex` в XPS. Укажите в `inputDirectory` папку с файлом TeX, а в `outputDirectory` — существующую папку вывода. Для вывода в ZIP задайте `outputZip` как `java.nio.file.Path` в существующей папке. Импортируйте классы Aspose.TeX из выбранного примера, `com.aspose.tex.rendering.XpsDevice` и необходимые классы `java.io` и `java.nio.file`. Вызывающий метод должен обрабатывать или объявлять исключения. Примените лицензию согласно [руководству по лицензированию](/tex/{{lang.url-fragment}}java/licensing/), чтобы избежать ограничений ознакомительной версии.

## Концепция выходного каталога

Поскольку примитивы ввода-вывода языка TeX могут работать только с именами файлов, Aspose.TeX определяет каталог как сопоставление между именами и объемами данных. Предполагается, что основная часть данных представляет собой файлы, потоки, массивы или что-то еще. API позволяет нам отдельно указывать входные и выходные рабочие каталоги. Он предоставляет общий интерфейс [IOutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/) для вывода, который пользователь может реализовать в своих целях. Он также предоставляет свои собственные реализации, которые будут обсуждаться ниже. Интерфейс расширяет [IInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/), поскольку механизм может сначала создать и записать файл, а затем прочитать его обратно. Собственный метод интерфейса [getOuputFile()](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/#getOutputFile-java.lang.String-java.lang.String:A-) возвращает поток для записи, в отличие от потока для чтения, возвращаемого [getFile()](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-).

### Запись вывода файла в файловую систему диска

Как мы уже упоминали [выше](/tex/{{lang.url-fragment}}/java/conversion/), наиболее распространенным значением [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--), скорее всего, будет экземпляр класса [OutputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputfilesystemdirectory/).

Вот как мы это установим:

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputFileSystemDirectory.java" >}}

Этот вариант использования достаточно прост, поэтому мы не будем на нем долго останавливаться.

### Запись вывода файла в ZIP-архив

Мы также можем создать файл (или поток) и позволить движку TeX использовать его в качестве ZIP-архива для хранения выходных файлов. Вот:

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputZipDirectory.java" >}}

Сначала мы создаем выходной поток для ZIP-файла. Затем, после создания параметров преобразования, мы устанавливаем параметр [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--) как экземпляр класса [OutputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputzipdirectory/). Пример сохраняет `hello-world.xps` и `hello-world.log` в архиве. После задания вызовите `finish()` для папки вывода до закрытия потока ZIP-архива. Примеры держат потоки и рабочие папки открытыми до завершения задания, затем закрывают их.

## Концепция выходного терминала

Есть еще одна важная часть вывода — вывод терминала. Что касается этого, **Aspose.TeX для Java** определяет общий интерфейс [IOutputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputterminal/) как имеющий два метода. Один из них возвращает экземпляр [BufferedWriter](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedWriter.html). Другой возвращает экземпляр [OutputStream](https://docs.oracle.com/javase/6/docs/api/java/io/OutputStream.html) в качестве базового потока. Предоставленные реализации интерфейса обсуждаются ниже.

### Запись вывода терминала на консоль

Для этого нам нужно установить опцию [TerminalOut](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getTerminalOut--) как экземпляр класса [OutputConsoleTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/outputconsoleterminal/).

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputConsoleTerminal.java" >}}

`OutputConsoleTerminal` — значение этого параметра по умолчанию. Пример явно выбирает его и записывает вывод терминала в консоль во время преобразования. Все четыре примера выполняются без взаимодействия с пользователем; примеры файловой системы и ZIP сохраняют вывод терминала в памяти.

### Запись вывода терминала в файл

В отличие от терминала ввода, **Aspose.TeX for Java** предоставляет реализацию [IOutputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputterminal/), которая позволяет нам записывать вывод терминала в файл в некотором выходном каталоге.

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputFileTerminal.java" >}}

Задайте рабочую папку вывода до создания `OutputFileTerminal`. Он записывает вывод терминала в [<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trm, в этом примере — `hello-world.trm`, в указанной папке. Этот файл терминала отделён от журнала TeX `hello-world.log`. Для записи вывода терминала в другое место передайте конструктору другую реализацию [IOutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/).