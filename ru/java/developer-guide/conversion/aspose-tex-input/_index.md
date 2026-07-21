---
translation: true
template: /templates/_template-java.md
title: Интерфейс ввода Aspose.TeX | Java
linktitle: Входной интерфейс Aspose.TeX
weight: 15
url: /java/aspose-tex-input/
description: Функциональность преобразования решения Aspose.TeX API для Java с TeX в качестве входного формата объясняется здесь с примерами кода.
lastmod: "2026-04-21"
---

{{<section overview>}}

Пожалуйста, обратитесь к **Aspose.TeX for Java** [ссылка на API](https://reference.aspose.com/tex/java/com.aspose.tex/) для формальных определений реализации ввода-вывода.

## Концепция входного каталога

Поскольку примитивы ввода-вывода языка TeX могут работать только с именами файлов, **Aspose.TeX для Java** определяет каталог как сопоставление имен и объемов данных. Предполагается, что основная часть данных представляет собой файлы, потоки, массивы или что-то еще. API позволяет нам отдельно указывать входные и выходные рабочие каталоги. Он предоставляет общий интерфейс [IInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/), который пользователь может реализовать в своих целях. Он также предоставляет свои собственные реализации, которые будут обсуждаться ниже. В интерфейсе определен метод [getFile()](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-), который возвращает поток данных и определяет полное имя файла, при этом в качестве первого аргумента принимает какое-то, гипотетически другое, имя, которое, по сути, и является ключом сопоставления.

### Получение входных файлов из файловой системы диска

Вот как мы это сделаем:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-InputFileSystemDirectory.java" >}}

Этот вариант использования достаточно прост, поэтому мы не будем на нем долго останавливаться.

### Получение ввода файла из ZIP-архива

Мы также можем поместить входные файлы в ZIP-архив и считать его входным каталогом. В этом случае нам следует поступить следующим образом:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-InputZipDirectory.java" >}}

Сначала мы создаем поток, содержащий ZIP-файл. Затем, после создания параметров преобразования, мы устанавливаем параметр [InputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getInputWorkingDirectory--) как экземпляр класса [InputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputzipdirectory/). Второй аргумент конструктора — базовый путь внутри архива. Если мы хотим, чтобы весь архив был входным каталогом, нам следует передать пустую строку. 

## Концепция входного терминала

Теперь вспомним, что есть еще и терминальный вход. Что касается этого, **Aspose.TeX для Java** определяет общий интерфейс [IInputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/iinputterminal/) как имеющий два метода. Один из них возвращает экземпляр [BufferedReader](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedReader.html). Другой метод возвращает [InputStream](https://docs.oracle.com/javase/6/docs/api/java/io/InputStream.html) в качестве базового потока. Предоставленные реализации интерфейса обсуждаются ниже.

### Получение терминального ввода с консоли

Для этого нам нужно установить опцию [TerminalIn](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getTerminalIn--) как экземпляр класса [InputConsoleTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/inputconsoleterminal/).

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-InputConsoleTerminal.java" >}}

Но, по правде говоря, это значение параметра по умолчанию, поэтому указывать его нет особой необходимости. В связи с этим и до тех пор, пока нет других реализаций, данный раздел служит только демонстрационным целям.

Теоретически, если у нас есть интерактивный файл (или скрипт) TeX с предсказуемым поведением, мы можем захотеть реализовать версию входного терминала, которая будет содержать дополнительный скрипт для ответа на запросы движка TeX. Попробуйте свои силы, когда у вас есть время!