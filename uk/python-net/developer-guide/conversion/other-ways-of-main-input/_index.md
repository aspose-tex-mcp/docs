---
translation: true
template: /templates/_template-python-net.md
title: Інші методи надання основного вхідного файлу TeX | Python через .NET
linktitle: Інші способи надання основного вхідного файлу TeX
weight: 14
url: /python-net/other-ways-of-main-input/
description: API-рішення Aspose.TeX для Python містить конструктор, який приймає потік як перший аргумент, забезпечуючи функцію перетворення.
lastmod: "2026-04-20"
---

{{<section overview>}}

## Постачання основного вхідного файлу механізму TeX за допомогою потоку

Поки що ми навчилися лише надавати [основний вхідний файл](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) механізму TeX як ім’я файлу, чи то в його повній формі, чи то в скороченій формі, з розширенням або без нього. Однак у класі [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/) доступний [інший конструктор](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#io.RawIOBase-aspose.tex.presentation.Device-aspose.tex.TeXOptions), який приймає потік як перший аргумент. Це корисно, якщо з якоїсь причини основний вхідний файл не має форми файлу у файловій системі диска. Ось приклад того, як це можна реалізувати:

Укажіть вихідний каталог у `ASPOSE_TEX_OUTPUT_DIR` (типово `output`). Спочатку застосуйте ліцензію. [Licensing](/tex/uk/python-net/licensing/).

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputStream.py" >}}

Закодуйте повний документ LaTeX у двійковий потік `BytesIO` і передайте його в `TeXJob` із `TeXConfig.object_latex`. Тримайте потік відкритим під час завдання. Результат: `texput.xps` і `texput.log`.

Зауважте, що всі вихідні файли матимуть назву `textput`. Це тому, що механізм не має доступу до жодного іншого імені. `textput` — назва завдання за замовчуванням. Ви можете знайти більш детальну інформацію про назви завдань [Вивід TeX](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) і [Як встановити назву завдання](/tex/{{lang.url-fragment}}net/other-options/#how-to-set-the-job-name).

## Введення основного вхідного файлу TeX через термінал

У класі [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/) доступний [ще один конструктор](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#aspose.tex.presentation.Device-aspose.tex.TeXOptions), який взагалі не дозволяє вказати вхідні дані. Вам може бути цікаво, що таке завдання TeX оброблятиме. У цьому випадку нам знадобиться використовувати вхідний термінал. Механізм TeX запропонує нам ввести назву файлу з терміналу.

Ось код:

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-MainInputTerminal.py" >}}

Збережіть наведений текст plain TeX як `hello-world.tex` у `ASPOSE_TEX_INPUT_DIR` (типово `input`). Приклад використовує `TeXConfig.object_tex()`. На запит уведіть `hello-world.tex` і натисніть Enter або передайте ім’я через стандартне введення. Результат: `hello-world.xps` і `hello-world.log`.

```tex
Hello, World!
\end
```
