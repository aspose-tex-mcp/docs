---
translation: true
template: /templates/_template-python-net.md
title: Інші методи надання основного вхідного файлу TeX | Python
linktitle: Інші способи надання основного вхідного файлу TeX
weight: 14
url: /python-net/other-ways-of-main-input/
description: API-рішення Aspose.TeX для Python містить конструктор, який приймає потік як перший аргумент, забезпечуючи функцію перетворення.
lastmod: 2024-09-20
---

{{<section overview>}}

## Постачання основного вхідного файлу механізму TeX за допомогою потоку

Поки що ми навчилися лише надавати [основний вхідний файл](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) механізму TeX як ім’я файлу, чи то в його повній формі, чи то в скороченій формі, з розширенням або без нього. Однак у класі [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob) доступний [інший конструктор](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#io.RawIOBase-aspose.tex.presentation.Device-aspose.tex.TeXOptions), який приймає потік як перший аргумент. Це корисно, якщо з якоїсь причини основний вхідний файл не має форми файлу у файловій системі диска. Ось приклад того, як це можна реалізувати:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-InputStream.py" >}}

Зауважте, що всі вихідні файли матимуть назву `textput`. Це тому, що механізм не має доступу до жодного іншого імені. `textput` — назва завдання за замовчуванням. Ви можете знайти більш детальну інформацію про назви завдань [Вивід TeX](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) і [Як встановити назву завдання](/tex/{{lang.url-fragment}}net/other-options/#how-to-set-the-job-name).

## Введення основного вхідного файлу TeX через термінал

У класі [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob) доступний [ще один конструктор](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#aspose.tex.presentation.Device-aspose.tex.TeXOptions), який взагалі не дозволяє вказати вхідні дані. Вам може бути цікаво, що таке завдання TeX оброблятиме. У цьому випадку нам знадобиться використовувати вхідний термінал. Механізм TeX запропонує нам ввести назву файлу з терміналу.

Ось код:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-MainInputTerminal.py" >}}

Щойно він запуститься, движок призупиниться і чекатиме, поки ми введемо ім’я файлу (із шляхом чи без, із розширенням чи без):


![Вікно терміналу](/tex/images/python-net/.png)

І ось як це буде виглядати на вихідному терміналі (консолі):

```text
This is ObjectTeX, Version 3.1415926-1.0 (Aspose.TeX 21.8)
entering extended mode
**<path_to_the_file>/hello-world.ltx
(<path_to_the_file>/hello-world.ltx
LaTeX2e <2011/06/27>
(article.cls
Document Class: article 2007/10/19 v1.4h Standard LaTeX document class
(size10.clo))
No file hello-world.aux.
[1]
(<output_directory>\hello-world.aux) )
Output written on hello-world.xps (1 page).
Transcript written on hello-world.log.
```