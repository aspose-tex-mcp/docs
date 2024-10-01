---
translation: true
template: /templates/_template-net.md
title: Интерфейс ввода Aspose.TeX | .СЕТЬ
linktitle: Входной интерфейс Aspose.TeX
weight: 15
url: /net/aspose-tex-input/
description: Функциональность преобразования решения Aspose.TeX API для .NET с TeX в качестве входного формата объясняется здесь с примерами кода.
lastmod: "2024-09-24"
---

{{<section overview>}}

Пожалуйста, обратитесь к **Aspose.TeX for .NET** [ссылка на API](https://reference.aspose.com/tex/net/aspose.tex.io/) для формальных определений реализации ввода-вывода.

## Концепция входного каталога

Поскольку примитивы ввода-вывода языка TeX могут работать только с именами файлов, **Aspose.TeX для .NET** определяет каталог как сопоставление между именами и объемами данных. Предполагается, что основная часть данных представляет собой файлы, потоки, массивы или что-то еще. API позволяет нам отдельно указывать входные и выходные рабочие каталоги. Он предоставляет общий интерфейс [IInputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/), который пользователь может реализовать в своих целях. Он также предоставляет свои собственные реализации, которые будут обсуждаться ниже. В интерфейсе определен метод [GetFile()](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/getfile/), который возвращает поток данных и определяет полное имя файла, при этом в качестве первого аргумента принимает какое-то, гипотетически другое, имя, которое, по сути, и является ключом сопоставления. .

### Получение входных файлов из файловой системы диска

Вот как мы это сделаем:

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-InputFileSystemDirectory.cs" >}}

Этот вариант использования довольно прост, поэтому больше нет необходимости на нем зацикливаться.

### Получение ввода файла из ZIP-архива

Мы также можем поместить входные файлы в ZIP-архив и считать его входным каталогом. В этом случае нам следует поступить следующим образом:

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-InputZipDirectory.cs" >}}

Сначала мы создаем поток, содержащий ZIP-файл. Затем, после создания параметров преобразования, мы устанавливаем параметр [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/inputworkingdirectory/) как экземпляр класса [InputZipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/). Второй аргумент конструктора — базовый путь внутри архива. Если мы хотим, чтобы весь архив был входным каталогом, нам следует передать пустую строку. 

## Концепция входного терминала

Теперь пора вспомнить, что есть еще и терминальный вход. Что касается этого, **Aspose.TeX для .NET** определяет общий интерфейс [IInputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/iinputterminal/), имеющий только одно свойство, которое возвращает экземпляр реализации [TextReader](https://docs.microsoft.com/en-us/dotnet/api/system.io.textreader). Предоставленные реализации обсуждаются ниже.

### Получение терминального ввода с консоли

Для этого нам нужно установить опцию [TerminalIn](https://reference.aspose.com/tex/net/aspose.tex/texoptions/terminalin/) как экземпляр класса [InputConsoleTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/inputconsoleterminal/).

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-InputConsoleTerminal.cs" >}}

Но, по правде говоря, это значение параметра по умолчанию, поэтому указывать его нет особой необходимости. В связи с этим и до тех пор, пока нет других реализаций, данный раздел служит только демонстрационным целям.

Теоретически, если у нас есть интерактивный файл (или скрипт) TeX с предсказуемым поведением, мы можем захотеть реализовать версию входного терминала, которая будет содержать дополнительный скрипт для ответа на запросы движка TeX. Попробуйте свои силы, когда у вас есть время!