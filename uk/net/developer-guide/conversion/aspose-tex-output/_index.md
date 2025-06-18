---
translation: true
template: /templates/_template-net.md
title: Інтерфейс виводу Aspose.TeX | .NET
linktitle: Інтерфейс виведення Aspose.TeX
weight: 16
url: /net/aspose-tex-output/
description: Функціональність перетворення рішення Aspose.TeX API для .NET із TeX як вихідний формат пояснюється тут із прикладами коду.
lastmod: "2025-06-13"
---

{{<section overview>}}

Будь ласка, зверніться до **Aspose.TeX для .NET** [посилання на API](https://reference.aspose.com/tex/net/aspose.tex.io/), щоб отримати формальні визначення реалізації вводу/виводу.

## Поняття вихідного каталогу

Оскільки примітиви вводу-виводу мови TeX можуть мати справу лише з іменами файлів, Aspose.TeX визначає каталог як відображення між іменами та масивами даних. Маси даних мають бути файлами, потоками, масивами або будь-яким іншим. API дозволяє нам окремо вказувати вхідні та вихідні робочі каталоги. Він надає загальний інтерфейс [IOutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputworkingdirectory/) для виведення, який користувач може реалізувати для власних цілей. Він також надає власні реалізації, які будуть розглянуті нижче. Інтерфейс розширює [IInputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/), оскільки механізм може спочатку створити та записати файл, а потім прочитати його назад. Власний метод інтерфейсу [GetOutputFile()](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputworkingdirectory/getoutputfile/) повертає потік для запису, на відміну від потоку для читання, який повертає [GetFile()](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/getfile/).

### Запис вихідного файлу у файлову систему диска

Як ми згадували [вище](/tex/{{lang.url-fragment}}net/latex-to-png/), найпоширенішим значенням для [OutputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) буде екземпляр класу [OutputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/).

Ось як ми це встановимо:

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-OutputFileSystemDirectory.cs" >}}

Цей варіант використання досить простий, тому більше не потрібно зосереджуватися на ньому.

### Запис вихідного файлу в ZIP-архів

Ми також можемо створити файл (або потік) і дозволити механізму TeX використовувати його як ZIP-архів для зберігання вихідних файлів. Ось воно:

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-OutputZipDirectory.cs" >}}

Спочатку ми створюємо вихідний потік для файлу ZIP. Потім, після створення параметрів перетворення, ми встановлюємо параметр [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) як екземпляр класу [OutputZipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/).

## Поняття про вихідний термінал

Є ще одна важлива частина виводу --- вихід терміналу. Що стосується цього, **Aspose.TeX для .NET** визначає загальний інтерфейс [IOutputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/), який має лише одну властивість, яка повертає екземпляр реалізації [TextWriter](https://docs.microsoft.com/en-us/dotnet/api/system.io.textwriter). Надані реалізації обговорюються нижче.

### Запис виводу терміналу на консоль

Для цього нам потрібно встановити параметр [TerminalOut](https://reference.aspose.com/tex/net/aspose.tex/texoptions/terminalout/) як екземпляр класу [OutputConsoleTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/).

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-OutputConsoleTerminal.cs" >}}

Знову ж таки, це значення параметра за замовчуванням, тому немає потреби вказувати його. Через це цей розділ служить лише для демонстраційних цілей.

### Запис вихідних даних терміналу у файл

На відміну від вхідного терміналу, **Aspose.TeX для .NET** забезпечує реалізацію [IOutputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/), яка дозволяє нам записувати вихідні дані терміналу у файл у деякому вихідному каталозі.

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-OutputFileTerminal.cs" >}} 

Тут ми просимо механізм TeX записати вихідні дані терміналу у файл із назвою [<назва_завдання>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trm, який зберігатиметься в тому самому каталозі виводу, який ми вказали для решти виводу. Але в цьому немає необхідності. Ми також можемо передати будь-який інший екземпляр будь-якої реалізації [IOutputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/) до конструктора.