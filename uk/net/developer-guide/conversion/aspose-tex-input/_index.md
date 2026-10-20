---
translation: true
template: /templates/_template-net.md
title: Інтерфейс введення Aspose.TeX | .NET
linktitle: Інтерфейс введення Aspose.TeX
weight: 15
url: /net/aspose-tex-input/
description: Функціональність перетворення рішення Aspose.TeX API для .NET із TeX як формат введення пояснюється тут із прикладами коду.
keywords: вхідні дані aspose tex, .net tex, каталог вхідних даних, zip-архів вхідних даних, консоль введення, параметри tex, iinputworkingdirectory, inputzipdirectory, inputterminal, перетворення tex
lastmod: "2025-06-13"
---

{{<section overview>}}

Будь ласка, зверніться до **Aspose.TeX для .NET** [посилання на API](https://reference.aspose.com/tex/net/aspose.tex.io/), щоб отримати формальні визначення реалізації вводу/виводу.

## Поняття вхідного каталогу

Оскільки примітиви вводу/виводу мови TeX можуть мати справу лише з іменами файлів, **Aspose.TeX для .NET** визначає каталог як відображення між іменами та масивами даних. Маси даних мають бути файлами, потоками, масивами або будь-яким іншим. API дозволяє нам окремо вказувати вхідні та вихідні робочі каталоги. Він забезпечує загальний інтерфейс [IInputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/), який користувач може реалізувати для власних цілей. Він також надає власні реалізації, які будуть розглянуті нижче. Інтерфейс визначає метод [GetFile()](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/getfile/), який повертає потік даних і визначає повне ім'я файлу, при цьому в якості першого аргументу бере якесь, гіпотетично інше ім'я, яке, по суті, є ключем відображення .

### Отримання вхідних файлів із файлової системи диска

Ось як би ми це зробили:

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-InputFileSystemDirectory.cs" >}}

Цей варіант використання досить простий, тому більше не потрібно зосереджуватися на ньому.

### Отримання вхідних файлів із ZIP-архіву

Ми також можемо помістити вхідні файли в архів ZIP і вважати його вхідним каталогом. У цьому випадку ми повинні діяти наступним чином:

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-InputZipDirectory.cs" >}}

Спочатку ми створюємо потік, що містить ZIP-файл. Потім, після створення параметрів перетворення, ми встановлюємо параметр [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/inputworkingdirectory/) як екземпляр класу [InputZipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/). Другим аргументом конструктора є базовий шлях всередині архіву. Якщо ми хочемо, щоб весь архів був вхідним каталогом, ми повинні передати порожній рядок. 

## Поняття про вхідний термінал

Тепер настав час згадати, що є також термінальний вхід. Що стосується цього, **Aspose.TeX для .NET** визначає загальний інтерфейс [IInputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/iinputterminal/), який має лише одну властивість, яка повертає екземпляр реалізації [TextReader](https://docs.microsoft.com/en-us/dotnet/api/system.io.textreader). Надані реалізації обговорюються нижче.

### Отримання введення терміналу з консолі

Для цього нам потрібно встановити параметр [TerminalIn](https://reference.aspose.com/tex/net/aspose.tex/texoptions/terminalin/) як екземпляр класу [InputConsoleTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/inputconsoleterminal/).

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-InputConsoleTerminal.cs" >}}

Але, чесно кажучи, це значення параметра за замовчуванням, тому немає потреби вказувати його. Через цей факт і доки немає інших реалізацій, цей розділ служить лише для демонстраційних цілей.

Теоретично, якщо у нас є інтерактивний файл TeX (або сценарій) з передбачуваною поведінкою, ми можемо захотіти реалізувати версію терміналу введення, яка б містила додатковий сценарій для відповіді на запити механізму TeX. Спробуйте свої сили, коли матимете час!