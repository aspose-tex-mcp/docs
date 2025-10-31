---
translation: true
template: /templates/_template-net.md
title: Выходной интерфейс Aspose.TeX | .NET 
linktitle: Выходной интерфейс Aspose.TeX
weight: 16
url: /net/aspose-tex-output/
description: Функциональность преобразования решения Aspose.TeX API для .NET с TeX в качестве выходного формата объясняется здесь с примерами кода.
keywords: вывод aspose tex, .net tex, выходной каталог, выходной zip, выходная консоль, выходной терминал, параметры tex, выходной каталог_файла, выходной каталог_zip, преобразование tex
lastmod: "2024-09-24"
---

{{<section overview>}}

Пожалуйста, обратитесь к **Aspose.TeX for .NET** [ссылка на API](https://reference.aspose.com/tex/net/aspose.tex.io/) для формальных определений реализации ввода-вывода.

## Концепция выходного каталога

Поскольку примитивы ввода-вывода языка TeX могут работать только с именами файлов, Aspose.TeX определяет каталог как сопоставление между именами и объемами данных. Предполагается, что основная часть данных представляет собой файлы, потоки, массивы или что-то еще. API позволяет нам отдельно указывать входные и выходные рабочие каталоги. Он предоставляет общий интерфейс [IOutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputworkingdirectory/) для вывода, который пользователь может реализовать в своих целях. Он также предоставляет свои собственные реализации, которые будут обсуждаться ниже. Интерфейс расширяет [IInputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/), поскольку механизм может сначала создать и записать файл, а затем прочитать его обратно. Собственный метод интерфейса [GetOutputFile()](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputworkingdirectory/getoutputfile/) возвращает поток для записи, в отличие от потока для чтения, возвращаемого функцией [GetFile()](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/getfile/).

### Запись вывода файла в файловую систему диска

Как мы уже упоминали [выше](/tex/{{lang.url-fragment}}net/latex-to-image/), наиболее распространенным значением для [OutputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/), скорее всего, будет экземпляр класса [OutputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/).

Вот как мы это установим:

{{< gist "aspose-com-gists""0fbd18cd8c28d5ed12e19cd52634ebd4""Example-OutputFileSystemDirectory.cs" >}}

Этот вариант использования довольно прост, поэтому больше нет необходимости на нем зацикливаться.

### Запись вывода файла в ZIP-архив

Мы также можем создать файл (или поток) и позволить движку TeX использовать его в качестве ZIP-архива для хранения выходных файлов. Вот:

{{< gist "aspose-com-gists""0fbd18cd8c28d5ed12e19cd52634ebd4""Example-OutputZipDirectory.cs" >}}

Сначала мы создаем выходной поток для ZIP-файла. Затем, после создания параметров преобразования, мы устанавливаем параметр [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) как экземпляр класса [OutputZipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/).

## Концепция выходного терминала

Есть еще одна важная часть вывода — вывод терминала. Что касается этого, **Aspose.TeX для .NET** определяет общий интерфейс [IOutputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/), имеющий только одно свойство, которое возвращает экземпляр реализации [TextWriter](https://docs.microsoft.com/en-us/dotnet/api/system.io.textwriter). Предоставленные реализации обсуждаются ниже.

### Запись вывода терминала на консоль

Для этого нам нужно установить опцию [TerminalOut](https://reference.aspose.com/tex/net/aspose.tex/texoptions/terminalout/) как экземпляр класса [OutputConsoleTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/).

{{< gist "aspose-com-gists""0fbd18cd8c28d5ed12e19cd52634ebd4""Example-OutputConsoleTerminal.cs" >}}

Опять же, это значение параметра по умолчанию, поэтому нет необходимости его указывать. В связи с этим данный раздел служит только демонстрационным целям.

### Запись вывода терминала в файл

В отличие от терминала ввода, **Aspose.TeX for .NET** предоставляет реализацию [IOutputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/), которая позволяет нам записывать вывод терминала в файл в некотором выходном каталоге.

{{< gist "aspose-com-gists""0fbd18cd8c28d5ed12e19cd52634ebd4""Example-OutputFileTerminal.cs" >}} 

Здесь мы просим движок TeX записать вывод терминала в файл с именем [<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trm, который будет храниться в том же выходном каталоге, который мы указали для остальной части вывода. Но это не обязательно. С таким же успехом мы могли бы передать в конструктор любой другой экземпляр любой реализации [IOutputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/).