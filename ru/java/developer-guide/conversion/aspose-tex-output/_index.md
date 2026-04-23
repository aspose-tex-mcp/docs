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

Пожалуйста, обратитесь к **Aspose.TeX for Java** [ссылка на API](https://reference.aspose.com/tex/java/com.aspose.tex/package-frame) для формальных определений реализации ввода-вывода.

## Концепция выходного каталога

Поскольку примитивы ввода-вывода языка TeX могут работать только с именами файлов, Aspose.TeX определяет каталог как сопоставление между именами и объемами данных. Предполагается, что основная часть данных представляет собой файлы, потоки, массивы или что-то еще. API позволяет нам отдельно указывать входные и выходные рабочие каталоги. Он предоставляет общий интерфейс [IOutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputWorkingDirectory) для вывода, который пользователь может реализовать в своих целях. Он также предоставляет свои собственные реализации, которые будут обсуждаться ниже. Интерфейс расширяет [IInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory), поскольку механизм может сначала создать и записать файл, а затем прочитать его обратно. Собственный метод интерфейса [getOuputFile()](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputWorkingDirectory#getOutputFile-java.lang.String-java.lang.String:A-) возвращает поток для записи, в отличие от потока для чтения, возвращаемого [getFile()](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-).

### Запись вывода файла в файловую систему диска

Как мы уже упоминали [выше](/tex/{{lang.url-fragment}}/java/conversion/), наиболее распространенным значением [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--), скорее всего, будет экземпляр класса [OutputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/OutputFileSystemDirectory).

Вот как мы это установим:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-OutputFileSystemDirectory.java" >}}

Этот вариант использования достаточно прост, поэтому мы не будем на нем долго останавливаться.

### Запись вывода файла в ZIP-архив

Мы также можем создать файл (или поток) и позволить движку TeX использовать его в качестве ZIP-архива для хранения выходных файлов. Вот:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-OutputZipDirectory.java" >}}

Сначала мы создаем выходной поток для ZIP-файла. Затем, после создания параметров преобразования, мы устанавливаем параметр [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--) как экземпляр класса [OutputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/OutputZipDirectory).

## Концепция выходного терминала

Есть еще одна важная часть вывода — вывод терминала. Что касается этого, **Aspose.TeX для Java** определяет общий интерфейс [IOutputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputTerminal) как имеющий два метода. Один из них возвращает экземпляр [BufferedWriter](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedWriter.html). Другой возвращает экземпляр [OutputStream](https://docs.oracle.com/javase/6/docs/api/java/io/OutputStream.html) в качестве базового потока. Предоставленные реализации интерфейса обсуждаются ниже.

### Запись вывода терминала на консоль

Для этого нам нужно установить опцию [TerminalOut](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getTerminalOut--) как экземпляр класса [OutputConsoleTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/OutputConsoleTerminal).

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-OutputConsoleTerminal.java" >}}

Опять же, это значение параметра по умолчанию, поэтому нет необходимости его указывать. В связи с этим данный раздел служит только демонстрационным целям.

### Запись вывода терминала в файл

В отличие от терминала ввода, **Aspose.TeX for Java** предоставляет реализацию [IOutputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputTerminal), которая позволяет нам записывать вывод терминала в файл в некотором выходном каталоге.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-OutputFileTerminal.java" >}} 

Здесь мы просим движок TeX записать вывод терминала в файл с именем [<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trm, который будет храниться в том же выходном каталоге, который мы указали для остальной части вывода. Но это не обязательно. С таким же успехом мы могли бы передать в конструктор любой другой экземпляр любой реализации [IOutputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputTerminal).