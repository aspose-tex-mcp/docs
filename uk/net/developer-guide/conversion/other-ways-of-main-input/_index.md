---
translation: true
template: /templates/_template-net.md
title: Інші способи надання основного вхідного файлу TeX | .NET
linktitle: Інші способи надання основного вхідного файлу TeX
weight: 14
url: /net/other-ways-of-main-input/
description: Функціональність перетворення рішення Aspose.TeX API для .NET має конструктор, який приймає потік як перший аргумент.
lastmod: "2025-06-13"
---

{{<section overview>}}

## Надання основного вхідного файлу механізму TeX у вигляді потоку

До цього моменту ми лише знали, як передати [основний вхідний файл](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) механізму TeX як ім’я файлу, повністю вказане чи у короткій формі, з розширенням чи без нього. Але є інший [конструктор](https://reference.aspose.com/tex/net/aspose.tex/texjob/texjob/) класу `TeXJob`, який приймає потік як перший аргумент. Це зручно, якщо з якоїсь причини ми маємо основний вхідний файл у формі, відмінній від файлу у файловій системі диска. Ось як це можна реалізувати:

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-InputStream.cs" >}}

Зауважте, що всі вихідні файли матимуть назву *textput*. Це тому, що двигун ніде не може отримати іншу назву. *textput* — назва завдання за умовчанням. [Тут](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) і [тут](/tex/{{lang.url-fragment}}net/other-options/#how-to-set-the-job-name) наведено відомості про назви посад.

## Введення основного вхідного файлу TeX з терміналу

Існує ще один [конструктор](https://reference.aspose.com/tex/net/aspose.tex/texjob/texjob/) класу `TeXJob`, який взагалі не дозволяє вказати вхідні дані. Ви можете запитати, що таке завдання TeX буде обробляти? Цього разу нам знадобиться термінал введення. Механізм TeX попросить нас ввести назву файлу з терміналу.

Ось код:

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-MainInputTerminal.cs" >}}

Як тільки він запускається, движок зависає, чекаючи, поки ми введемо ім’я файлу (із шляхом чи без, із розширенням чи без):


![Вікно терміналу](/tex/images/net/Conversion-MainInputTerminal.png)

І ось як це виглядатиме на вихідному терміналі, який є консоллю:

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