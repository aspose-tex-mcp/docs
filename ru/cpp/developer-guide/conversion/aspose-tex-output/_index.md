---
translation: true
template: /templates/_template-cpp.md
title: Выходной интерфейс Aspose.TeX | С++
linktitle: Выходной интерфейс Aspose.TeX
weight: 16
url: /cpp/aspose-tex-output/
description: Функциональность преобразования решения Aspose.TeX API для C++ с TeX в качестве выходного формата объясняется здесь с примерами кода.
lastmod: "2024-09-24"
---

{{<section overview>}}

Пожалуйста, обратитесь к **Aspose.TeX for C++** [ссылка на API](https://reference.aspose.com/tex/cpp/namespace/aspose.te_x.i_o) для формальных определений реализации ввода-вывода.

## Концепция выходного каталога
Поскольку примитивы ввода-вывода языка TeX могут работать только с именами файлов, Aspose.TeX определяет каталог как сопоставление между именами и объемами данных. Предполагается, что основная часть данных представляет собой файлы, потоки, массивы или что-то еще. API позволяет нам отдельно указывать входные и выходные рабочие каталоги. Он предоставляет общий интерфейс [IOutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputworkingdirectory) для вывода, который пользователь может реализовать в своих целях. Он также предоставляет свои собственные реализации, которые будут обсуждаться ниже. Интерфейс расширяет [IInputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputworkingdirectory), поскольку механизм может сначала создать и записать файл, а затем прочитать его обратно. Собственный метод интерфейса [GetOutputFile()](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputworkingdirectory/getoutputfile) возвращает поток для записи, в отличие от потока для чтения, возвращаемого функцией [GetFile()](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputworkingdirectory#adc0d6f35f9a0c426ba010779d90b5cd6).

### Запись вывода файла в файловую систему диска

Как мы уже упоминали [выше](/tex/{{lang.url-fragment}}cpp/latex-to-png/), наиболее распространенным значением для [OutputDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory), скорее всего, будет экземпляр класса [OutputFileSystemDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputfilesystemdirectory).

Вот как мы это установим:

```C++
// Create conversion options instance.
...
// Specify a file system working directory for the output.
options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));

```

Этот вариант использования довольно прост, поэтому больше нет необходимости на нем зацикливаться.

### Запись вывода файла в ZIP-архив

Мы также можем создать файл (или поток) и позволить движку TeX использовать его в качестве ZIP-архива для хранения выходных файлов. Вот:

```C++
    // Open the stream for the ZIP archive that will serve as the output working directory.
    System::SharedPtr<System::IO::Stream> outZipStream = System::IO::File::Open(System::IO::Path::Combine(RunExamples::OutputDirectory, u"zip-pdf-out.zip"), System::IO::FileMode::Create);

    // Create conversion options instance.
    ...
    // Specify a ZIP archive working directory for the output.
    options->set_OutputWorkingDirectory(System::MakeObject<OutputZipDirectory>(outZipStream));
```

Сначала мы создаем выходной поток для ZIP-файла. Затем, после создания параметров преобразования, мы устанавливаем параметр [OutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory) как экземпляр класса [OutputZipDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputzipdirectory).

## Концепция выходного терминала

Есть еще одна важная часть вывода — вывод терминала. Что касается этого, **Aspose.TeX для C++** определяет общий интерфейс [IOutputTerminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputterminal), имеющий только одно свойство, которое возвращает экземпляр реализации [TextWriter](https://reference.aspose.com/tex/cpp/system.io/textwriter). Предоставленные реализации обсуждаются ниже.

### Запись вывода терминала на консоль

Для этого нам нужно установить опцию [TerminalOut](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_terminalout) как экземпляр класса [OutputConsoleTerminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputconsoleterminal).


```C++
// Create conversion options instance.
...
// Specify the console as the output terminal.
options->set_TerminalOut(System::MakeObject<OutputConsoleTerminal>()); // Default. No need to specify.

```

Опять же, это значение параметра по умолчанию, поэтому нет необходимости его указывать. В связи с этим данный раздел служит только демонстрационным целям.

### Запись вывода терминала в файл

В отличие от терминала ввода, **Aspose.TeX для C++** предоставляет реализацию [IOutputTerminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputterminal), которая позволяет нам записывать вывод терминала в файл в некотором выходном каталоге.


```C++
// Create conversion options instance.
...
// Specify that the terminal output must be written to a file in the output working directory.
// The file name is <job_name>.trm.
options->set_TerminalOut(System::MakeObject<OutputFileTerminal>(options->get_OutputWorkingDirectory()));

```

Здесь мы просим движок TeX записать вывод терминала в файл с именем [<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trm, который будет храниться в том же выходном каталоге, который мы указали для остальной части вывода. Но это не обязательно. С таким же успехом мы могли бы передать в конструктор любой другой экземпляр любой реализации [IOutputTerminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputterminal).