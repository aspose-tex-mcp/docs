---
translation: true
template: /templates/_template-cpp.md
title: Інтерфейс виводу Aspose.TeX | C++
linktitle: Інтерфейс виведення Aspose.TeX
weight: 16
url: /cpp/aspose-tex-output/
description: Функціональність перетворення рішення Aspose.TeX API для C++ із TeX як вихідний формат пояснюється тут із прикладами коду.
lastmod: "2026-04-20"
---

{{<section overview>}}

Будь ласка, зверніться до **Aspose.TeX для C++** [посилання на API](https://reference.aspose.com/tex/cpp/namespace/aspose.te_x.i_o), щоб отримати формальні визначення реалізації введення/виведення.

## Поняття вихідного каталогу

Оскільки примітиви вводу-виводу мови TeX можуть мати справу лише з іменами файлів, Aspose.TeX визначає каталог як відображення між іменами та масивами даних. Маси даних мають бути файлами, потоками, масивами або будь-яким іншим. API дозволяє нам окремо вказувати вхідні та вихідні робочі каталоги. Він надає загальний інтерфейс [IOutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputworkingdirectory) для виведення, який користувач може реалізувати для власних цілей. Він також надає власні реалізації, які будуть розглянуті нижче. Інтерфейс розширює [IInputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputworkingdirectory), оскільки механізм може спочатку створити та записати файл, а потім прочитати його назад. Власний метод інтерфейсу [GetOutputFile()](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputworkingdirectory/getoutputfile) повертає потік для запису, на відміну від потоку для читання, який повертає [GetFile()](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputworkingdirectory#adc0d6f35f9a0c426ba010779d90b5cd6).

### Запис вихідного файлу у файлову систему диска

Як ми згадували [вище](/tex/{{lang.url-fragment}}cpp/latex-to-image/), найпоширенішим значенням для [OutputDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory) буде екземпляр класу [OutputFileSystemDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputfilesystemdirectory).

Ось як ми це встановимо:

```C++
// Create conversion options instance.
...
// Specify a file system working directory for the output.
options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));

```
Цей варіант використання досить простий, тому більше не потрібно зосереджуватися на ньому.

### Запис вихідного файлу в ZIP-архів

Ми також можемо створити файл (або потік) і дозволити механізму TeX використовувати його як ZIP-архів для зберігання вихідних файлів. Ось воно:

```C++
    // Open the stream for the ZIP archive that will serve as the output working directory.
    System::SharedPtr<System::IO::Stream> outZipStream = System::IO::File::Open(System::IO::Path::Combine(RunExamples::OutputDirectory, u"zip-pdf-out.zip"), System::IO::FileMode::Create);

    // Create conversion options instance.
    ...
    // Specify a ZIP archive working directory for the output.
    options->set_OutputWorkingDirectory(System::MakeObject<OutputZipDirectory>(outZipStream));
```

Спочатку ми створюємо вихідний потік для файлу ZIP. Потім, після створення параметрів перетворення, ми встановлюємо параметр [OutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory) як екземпляр класу [OutputZipDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputzipdirectory).

## Поняття про вихідний термінал

Є ще одна важлива частина виводу --- вихід терміналу. Що стосується цього, **Aspose.TeX для C++** визначає загальний інтерфейс [IOutputTerminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputterminal), який має лише одну властивість, яка повертає екземпляр реалізації [TextWriter](https://reference.aspose.com/tex/cpp/system.io/textwriter). Надані реалізації обговорюються нижче.

### Запис виводу терміналу на консоль

Для цього нам потрібно встановити параметр [TerminalOut](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_terminalout) як екземпляр класу [OutputConsoleTerminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputconsoleterminal).

```C++
// Create conversion options instance.
...
// Specify the console as the output terminal.
options->set_TerminalOut(System::MakeObject<OutputConsoleTerminal>()); // Default. No need to specify.

```

Знову ж таки, це значення параметра за замовчуванням, тому немає потреби вказувати його. Через це цей розділ служить лише для демонстраційних цілей.

### Запис вихідних даних терміналу у файл

На відміну від вхідного терміналу, **Aspose.TeX для C++** забезпечує реалізацію [IOutputTerminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputterminal), яка дозволяє нам записувати вихідні дані терміналу у файл у деякому вихідному каталозі.

```C++
// Create conversion options instance.
...
// Specify that the terminal output must be written to a file in the output working directory.
// The file name is <job_name>.trm.
options->set_TerminalOut(System::MakeObject<OutputFileTerminal>(options->get_OutputWorkingDirectory()));

```

Тут ми просимо механізм TeX записати вихідні дані терміналу у файл із назвою [<назва_завдання>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trm, який зберігатиметься в тому самому каталозі виводу, який ми вказали для решти виводу. Але в цьому немає необхідності. Ми також можемо передати будь-який інший екземпляр будь-якої реалізації [IOutputTerminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputterminal) до конструктора.