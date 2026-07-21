---
translation: true
template: /templates/_template-cpp.md
title: Інтерфейс введення Aspose.TeX | C++
linktitle: Інтерфейс введення Aspose.TeX
weight: 15
url: /cpp/aspose-tex-input/
description: Функціональність перетворення рішення Aspose.TeX API для C++ із TeX як форматом введення пояснюється тут із прикладами коду.
lastmod: "2025-06-13"
---

{{<section overview>}}

Будь ласка, зверніться до **Aspose.TeX для C++** [посилання на API](https://reference.aspose.com/tex/cpp/aspose.tex.io/), щоб отримати формальні визначення реалізації введення/виведення.

## Поняття вхідного каталогу

Оскільки примітиви вводу-виводу мови TeX можуть мати справу лише з іменами файлів, **Aspose.TeX для C++** визначає каталог як відображення між іменами та масивами даних. Маси даних мають бути файлами, потоками, масивами або будь-яким іншим. API дозволяє нам окремо вказувати вхідні та вихідні робочі каталоги. Він забезпечує загальний інтерфейс [IInputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputworkingdirectory/), який користувач може реалізувати для власних цілей. Він також надає власні реалізації, які будуть розглянуті нижче. Інтерфейс визначає метод [GetFile()](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputworkingdirectory#adc0d6f35f9a0c426ba010779d90b5cd6), який повертає потік даних і визначає повне ім'я файлу, при цьому в якості першого аргументу бере якесь, гіпотетично інше ім'я, яке, по суті, є ключем відображення .

### Отримання вхідних файлів із файлової системи диска

Ось як би ми це зробили:

```C++
// Create conversion options instance.
...
// Specify a file system working directory for input.
options->set_InputWorkingDirectory(System::MakeObject<InputFileSystemDirectory>(RunExamples::InputDirectory));

```

Цей варіант використання досить простий, тому більше не потрібно зосереджуватися на ньому.

### Отримання вхідних файлів із ZIP-архіву

Ми також можемо помістити вхідні файли в архів ZIP і вважати його вхідним каталогом. У цьому випадку ми повинні діяти наступним чином:

```C++
    // Open a stream on a ZIP archive that will serve as the input working directory.
    System::SharedPtr<System::IO::Stream> inZipStream = System::IO::File::Open(System::IO::Path::Combine(RunExamples::InputDirectory, u"zip-in.zip"), System::IO::FileMode::Open);

    // Create conversion options instance.
    ...
    // Specify a ZIP archive working directory for input.
    options->set_InputWorkingDirectory(System::MakeObject<InputZipDirectory>(inZipStream, u"in"));
```

Спочатку ми створюємо потік, що містить ZIP-файл. Потім, після створення параметрів перетворення, ми встановлюємо параметр [InputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_inputworkingdirectory/) як екземпляр класу [InputZipDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/inputzipdirectory/). Другим аргументом конструктора є базовий шлях всередині архіву. Якщо ми хочемо, щоб весь архів був вхідним каталогом, ми повинні передати порожній рядок. 

## Поняття про вхідний термінал

Тепер настав час згадати, що є також термінальний вхід. Що стосується цього, **Aspose.TeX для C++** визначає загальний інтерфейс [IInputTerminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputterminal/), який має лише одну властивість, яка повертає екземпляр реалізації [TextReader](https://reference.aspose.com/tex/cpp/system.io/textreader/). Надані реалізації обговорюються нижче.

### Отримання введення терміналу з консолі

Для цього нам потрібно встановити параметр [TerminalIn](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_terminalin/) як екземпляр класу [InputConsoleTerminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/inputconsoleterminal/).

```C++
// Create conversion options instance.
...
// Specify the console as the input terminal.
options->set_TerminalIn(System::MakeObject<InputConsoleTerminal>()); // Default. Not necessary to specify.

```

Але, чесно кажучи, це значення параметра за замовчуванням, тому немає потреби вказувати його. :-) У зв’язку з цим і доки немає інших реалізацій, цей розділ служить лише для демонстраційних цілей.

Теоретично, якщо у нас є інтерактивний файл TeX (або сценарій) з передбачуваною поведінкою, ми можемо захотіти реалізувати версію терміналу введення, яка б містила додатковий сценарій для відповіді на запити механізму TeX. Спробуйте свої сили, коли матимете час!