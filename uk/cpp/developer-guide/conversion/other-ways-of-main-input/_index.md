---
translation: true
template: /templates/_template-cpp.md
title: Інші способи надання основного вхідного файлу TeX | C++
linktitle: Інші способи надання основного вхідного файлу TeX
weight: 14
url: /cpp/other-ways-of-main-input/
description: Функція перетворення рішення Aspose.TeX API для C++ має конструктор, який приймає потік як перший аргумент. Ось кілька прикладів коду.
lastmod: 2024-09-20
---

{{<section overview>}}

## Надання основного вхідного файлу механізму TeX у вигляді потоку

До цього моменту ми лише знали, як передати [основний вхідний файл](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) механізму TeX як ім’я файлу, повністю вказане чи у короткій формі, з розширенням чи без нього. Але є інший [конструктор](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/) класу `TeXJob`, який приймає потік як перший аргумент. Це зручно, якщо з якоїсь причини ми маємо основний вхідний файл у формі, відмінній від файлу у файловій системі диска. Ось як це можна реалізувати:

```C++
// Create conversion options instance.
...
// Create some device.
...
// Run LaTeX to XPS conversion.
System::MakeObject<Aspose::TeX::TeXJob>(System::MakeObject<System::IO::MemoryStream>(System::Text::Encoding::get_ASCII()->GetBytes(
    u"\\documentclass{article} \\begin{document} Hello, World! \\end{document}")), device, options)->Run();
```

Зауважте, що всі вихідні файли матимуть назву *textput*. Це тому, що двигун ніде не може отримати іншу назву. *textput* — назва завдання за умовчанням. [Тут](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) і [тут](/tex/{{lang.url-fragment}}cpp/other-options/#how-to-set-the-job-name) наведено відомості про назви посад.

## Введення основного вхідного файлу TeX з терміналу

Існує ще один [конструктор](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_job/main) класу `TeXJob`, який взагалі не дозволяє вказати вхідні дані. Ви можете запитати, що таке завдання TeX буде обробляти? Цього разу нам знадобиться термінал введення. Механізм TeX попросить нас ввести назву файлу з терміналу.

Ось код:

```C++
// Create conversion options instance.
...
// Run LaTeX to XPS conversion.
System::MakeObject<Aspose::TeX::TeXJob>(System::MakeObject<XpsDevice>(), options)->Run();
```

Як тільки він запускається, движок зависає, чекаючи, поки ми введемо ім’я файлу (із шляхом чи без, із розширенням чи без):


![Вікно терміналу](/tex/images/cpp/Conversion-MainInputTerminal.png)

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