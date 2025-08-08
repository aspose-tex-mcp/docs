---
translation: true
template: /templates/_template-python-net.md
title: Інтерфейс виводу Aspose.TeX | Python
linktitle: Інтерфейс виведення Aspose.TeX
weight: 16
url: /python-net/aspose-tex-output/
description: Ось пояснення функції перетворення рішення Aspose.TeX API для Python, з TeX як вихідним форматом, із прикладами коду.
lastmod: "2025-06-13"
---

{{<section overview>}}


> Щоб отримати офіційні визначення реалізації вводу/виводу, зверніться до [посилання на API](https://reference.aspose.com/tex/python-net/aspose.tex.io/) **Aspose.TeX для Python **.

## Ідея вихідного каталогу

Aspose.TeX визначає каталог як відображення між іменами та масивами даних, де масиви даних можуть бути файлами, потоками, масивами або іншими типами даних. API дозволяє специфікувати окремі вхідні та вихідні робочі каталоги. Для виведення API надає загальний інтерфейс [IOutputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/ioutputworkingdirectory/), який користувач може реалізувати для своїх конкретних потреб. Крім того, API надає готові до використання реалізації, які будуть розглянуті нижче. Інтерфейс *IOutputWorkingDirectory* розширює [IInputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/), оскільки механізм може спочатку створити та записати файл, а потім прочитати його назад. Інтерфейс містить метод [get_output_file()](https://reference.aspose.com/tex/python-net/aspose.tex.io/ioutputworkingdirectory/get_output_file/#str), який повертає потік для запису, на відміну від методу [get_file()](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/get_file/#str-bool), який повертає потік для читання.

### Збереження результату як файл у файловій системі диска

Як згадувалося [вище](/tex/{{lang.url-fragment}}net/latex-to-image/), [output_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/output_working_directory/) зазвичай встановлюється як екземпляр класу [OutputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputfilesystemdirectory/).

Ось як ми це встановимо:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-OutputFileSystemDirectory.py" >}}

Цей конкретний випадок використання простий, тому немає потреби заглиблюватися в нього далі.

### Збереження результату як архівний файл ZIP.

Інший варіант — створити файл або потік і використовувати його як ZIP-архів для зберігання вихідних файлів. Ось приклад:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-OutputZipDirectory.py" >}}

Для початку ми створюємо вихідний потік для файлу ZIP. Потім, після створення параметрів перетворення, ми встановлюємо параметр *output_working_directory* як екземпляр класу [OutputZipDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputzipdirectory/).

## Ідея вихідного терміналу

Вивід терміналу є ще одним важливим аспектом виводу. Для цього **Aspose.TeX для Python** визначає загальний інтерфейс [IOutputTerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/ioutputterminal/), який має єдину властивість, яка повертає екземпляр реалізації [TerminalWriter](https://reference.aspose.com/tex/python-net/aspose.tex.io/terminalwriter/). Доступні реалізації будуть розглянуті нижче.

### Запис виведення терміналу на консоль

Щоб досягти цього, нам потрібно встановити параметр [terminal_out](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/terminal_out/) як екземпляр класу [OutputConsoleTerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputconsoleterminal/).

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-OutputConsoleTerminal.py" >}}

Знову ж таки, це значення параметра за замовчуванням, тому немає справжньої потреби вказувати його. Тому цей розділ надається виключно для демонстрації.

### Запис вихідних даних терміналу у файл

На відміну від вхідного терміналу, **Aspose.TeX для Python** містить реалізацію інтерфейсу *IOutputTerminal*, який дозволяє нам записувати вихідні дані терміналу у файл у вказаному каталозі виведення.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-OutputFileTerminal.py" >}} 

У цьому випадку ми наказуємо механізму TeX записати вихідні дані терміналу до файлу з іменем [<назва_завдання>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trm, який буде розташований у тому самому каталозі виведення, що й решта виведення. Однак це не є обов'язковим. Ми також можемо надати будь-який інший екземпляр реалізації *IOutputTerminal* для конструктора.