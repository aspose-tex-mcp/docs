---
translation: true
template: /templates/_template-python-net.md
title: Інтерфейс введення Aspose.TeX | Python через .NET
linktitle: Інтерфейс введення Aspose.TeX
weight: 15
url: /python-net/aspose-tex-input/
description: Функціональність перетворення рішення Aspose.TeX API для Python з TeX як формат введення пояснюється тут із прикладами коду.
lastmod: "2025-06-13"
---

{{<section overview>}}

> Щоб отримати офіційні визначення реалізації вводу-виводу в **Aspose.TeX для Python**, зверніться до [посилання на API](https://reference.aspose.com/tex/python-net/aspose.tex.io /).

## Ідея вхідного каталогу

Враховуючи, що примітиви вводу-виводу мови TeX можуть обробляти лише імена файлів, **Aspose.TeX для Python** визначає каталог як відображення між іменами та колекціями даних. Ці колекції даних можуть бути файлами, потоками, масивами або будь-яким іншим типом. API дозволяє окремо вказувати вхідні та вихідні робочі каталоги. Він надає загальний клас [InputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputworkingdirectory/), який користувачі можуть реалізувати для своїх конкретних потреб. Крім того, API забезпечує вбудовані реалізації, які будуть обговорюватися пізніше. Інтерфейс містить метод [get_file()](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/get_file/#str-bool), який отримує потік даних і визначає повне ім’я файлу на основі заданого імені, яке служить ключем відображення.

### Отримання вхідних файлів із файлової системи диска

Ось наш підхід:

Укажіть вихідний каталог у `ASPOSE_TEX_OUTPUT_DIR` (типово `output`). Спочатку застосуйте ліцензію. [Licensing](/tex/uk/python-net/licensing/).

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputFileSystemDirectory.py" >}}

Укажіть у `ASPOSE_TEX_INPUT_DIR` папку з `hello-world.tex` (типово `input`). Приклад використовує plain TeX із `TeXConfig.object_tex()` і створює `hello-world.xps` та `hello-world.log`. Вхідний файл:

```tex
Hello, World!
\end
```

### Отримання введених файлів із ZIP-архіву

Інший варіант — зберігати вхідні файли в архіві ZIP і розглядати його як вхідний каталог. У такому сценарії слід виконати такі дії:

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputZipDirectory.py" >}}

`ASPOSE_TEX_INPUT_ZIP` задає архів із `in/hello-world.tex` (типово `zip-in.zip`). Відкрийте його у двійковому режимі `rb` і тримайте потік відкритим до завершення завдання.

Для початку ми створюємо потік, який містить ZIP-файл. Згодом, після створення параметрів перетворення, ми призначаємо екземпляр класу [InputZipDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputzipdirectory/) властивості [input_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/input_working_directory/). Другий параметр конструктора представляє базовий шлях в архіві. Якщо ми хочемо, щоб весь архів функціонував як вхідний каталог, ми повинні надати порожній рядок як аргумент.

## Ідея вхідного терміналу

Тепер давайте розглянемо концепцію термінального введення. **Aspose.TeX для Python** визначає загальний інтерфейс [IInputTerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputterminal/) спеціально для цієї мети, який включає одну властивість, яка повертає екземпляр реалізації [TerminalReader](https://reference.aspose.com/tex/python-net/aspose.tex.io/terminalreader/). Доступні реалізації будуть обговорені пізніше.

### Отримання введення терміналу з консолі

Щоб досягти цього, нам потрібно призначити екземпляр класу [InputConsoleTerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputconsoleterminal/) опції [terminal_in](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/terminal_in/).

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputConsoleTerminal.py" >}}

Приклад читає рядок командою `\read` і записує його в `texput.xps`. Уведіть у терміналі, наприклад, `Terminal input works!` або передайте рядок через стандартне введення. `SCROLL_MODE` дозволяє такий запит введення.
