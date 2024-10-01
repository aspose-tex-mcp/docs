---
translation: true
template: /templates/_template-cpp.md
title: Интерфейс ввода Aspose.TeX | С++
linktitle: Входной интерфейс Aspose.TeX
weight: 15
url: /cpp/aspose-tex-input/
description: Функциональность преобразования решения Aspose.TeX API для C++ с TeX в качестве входного формата объясняется здесь с примерами кода.
lastmod: "2024-09-24"
---

{{<section overview>}}

Пожалуйста, обратитесь к **Aspose.TeX for C++** [ссылка на API](https://reference.aspose.com/tex/cpp/namespace/aspose.te_x.i_o) для формальных определений реализации ввода-вывода.

## Концепция входного каталога
Поскольку примитивы ввода-вывода языка TeX могут работать только с именами файлов, **Aspose.TeX для C++** определяет каталог как сопоставление между именами и объемами данных. Предполагается, что основная часть данных представляет собой файлы, потоки, массивы или что-то еще. API позволяет нам отдельно указывать входные и выходные рабочие каталоги. Он предоставляет общий интерфейс [IInputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputworkingdirectory), который пользователь может реализовать в своих целях. Он также предоставляет свои собственные реализации, которые будут обсуждаться ниже. В интерфейсе определен метод [GetFile()](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputworkingdirectory#adc0d6f35f9a0c426ba010779d90b5cd6), который возвращает поток данных и определяет полное имя файла, при этом в качестве первого аргумента принимает какое-то, гипотетически другое, имя, которое, по сути, и является ключом сопоставления. .

### Получение входных файлов из файловой системы диска

Вот как мы это сделаем:

```C++
// Create conversion options instance.
...
// Specify a file system working directory for input.
options->set_InputWorkingDirectory(System::MakeObject<InputFileSystemDirectory>(RunExamples::InputDirectory));

```

Этот вариант использования довольно прост, поэтому больше нет необходимости на нем зацикливаться.

### Получение ввода файла из ZIP-архива

Мы также можем поместить входные файлы в ZIP-архив и считать его входным каталогом. В этом случае нам следует поступить следующим образом:

```C++
    // Open a stream on a ZIP archive that will serve as the input working directory.
    System::SharedPtr<System::IO::Stream> inZipStream = System::IO::File::Open(System::IO::Path::Combine(RunExamples::InputDirectory, u"zip-in.zip"), System::IO::FileMode::Open);

    // Create conversion options instance.
    ...
    // Specify a ZIP archive working directory for input.
    options->set_InputWorkingDirectory(System::MakeObject<InputZipDirectory>(inZipStream, u"in"));
```

Сначала мы создаем поток, содержащий ZIP-файл. Затем, после создания параметров преобразования, мы устанавливаем параметр [InputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_inputworkingdirectory) как экземпляр класса [InputZipDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/inputzipdirectory). Второй аргумент конструктора — базовый путь внутри архива. Если мы хотим, чтобы весь архив был входным каталогом, нам следует передать пустую строку. 

## Концепция входного терминала

Теперь пора вспомнить, что есть еще и терминальный вход. Что касается этого, **Aspose.TeX для C++** определяет общий интерфейс [IInputTerminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputterminal), имеющий только одно свойство, которое возвращает экземпляр реализации [TextReader](https://reference.aspose.com/tex/cpp/class/system.i_o.text_reader). Предоставленные реализации обсуждаются ниже.

### Получение терминального ввода с консоли

Для этого нам нужно установить опцию [TerminalIn](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_terminalin) как экземпляр класса [InputConsoleTerminal](https://reference.aspose.com/tex/cpp/class/aspose.te_x.i_o.input_console_terminal).

```C++
// Create conversion options instance.
...
// Specify the console as the input terminal.
options->set_TerminalIn(System::MakeObject<InputConsoleTerminal>()); // Default. Not necessary to specify.

```

Но, по правде говоря, это значение параметра по умолчанию, поэтому указывать его нет особой необходимости. :-) В связи с этим и пока нет других реализаций, данный раздел служит лишь демонстрационным целям.

Теоретически, если у нас есть интерактивный файл (или скрипт) TeX с предсказуемым поведением, мы можем захотеть реализовать версию входного терминала, которая будет содержать дополнительный скрипт для ответа на запросы движка TeX. Попробуйте свои силы, когда у вас есть время!