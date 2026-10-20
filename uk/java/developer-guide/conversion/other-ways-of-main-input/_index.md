---
translation: true
template: /templates/_template-java.md
title: Інші способи надання основного вхідного файлу TeX | Java
linktitle: Інші способи надання основного вхідного файлу TeX
weight: 14
url: /java/other-ways-of-main-input/
description: Функція перетворення рішення Aspose.TeX API для Java має конструктор, який приймає потік як перший аргумент.
lastmod: "2026-04-21"
---

{{<section overview>}}

## Надання основного вхідного файлу механізму TeX у вигляді потоку

До цього моменту ми лише знали, як передати [основний вхідний файл](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) механізму TeX як ім’я файлу, повністю вказане чи у короткій формі, з розширенням чи без нього. Але є інший [конструктор](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#TeXJob-java.io.InputStream-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-) класу `TeXJob`, який приймає потік як перший аргумент. Це зручно, якщо з якоїсь причини ми маємо основний вхідний файл у формі, відмінній від файлу у файловій системі диска. Ось як ми можемо з цим впоратися:

Укажіть у `outputDirectory` наявну папку виведення. Імпортуйте класи Aspose.TeX із прикладів, `com.aspose.tex.rendering.XpsDevice`, `com.aspose.tex.rendering.XpsSaveOptions`, а для введення з потоку — `java.io.ByteArrayInputStream` і `java.nio.charset.StandardCharsets`. Метод виклику має обробляти або оголошувати винятки. Застосуйте ліцензію згідно з [посібником із ліцензування](/tex/{{lang.url-fragment}}java/licensing/), щоб уникнути обмежень ознайомлювальної версії. Приклад потоку містить повний документ LaTeX, тому робоча папка введення не потрібна. Потоки й пристрої залишаються відкритими до завершення завдання, потім закриваються або звільняються.

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-StreamInput-LaTeX.java" >}}

Якщо для введення з потоку ім’я завдання не задано явно, механізм використовує ім’я за замовчуванням *texput*. Цей приклад створює `texput.xps` і `texput.log`. Для вибору іншого імені завдання використайте `options.setJobName(...)`. Докладніше про імена завдань див. [тут](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) і [тут](/tex/{{lang.url-fragment}}java/other-options/#how-to-set-the-job-name).

## Введення основного вхідного файлу TeX з терміналу

Існує ще один [конструктор](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#TeXJob-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-)  класу `TeXJob`, який взагалі не дозволяє нам вказати вхідні дані. Ви можете запитати, що таке завдання TeX буде обробляти? Цього разу нам знадобиться термінал введення. Механізм TeX попросить нас ввести назву файлу з терміналу.

Укажіть у `inputDirectory` папку з повним документом LaTeX під назвою `hello-world.ltx`, а в `outputDirectory` — наявну папку виведення. Запустіть приклад у консолі, введіть `hello-world.ltx` у відповідь на запрошення `**` і натисніть Enter. Він створює `hello-world.xps` і записує виведення термінала в консоль. Обидва приклади використовують `NonstopMode` для обробки, але термінальному конструктору все одно потрібне початкове ім’я файлу. Для запуску без участі користувача надайте реалізацію `IInputTerminal` або використайте введення з файлу чи потоку.

Ось код:

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-MainInputTerminal.java" >}}

Як тільки він запускається, движок зависає, чекаючи, поки ми введемо ім’я файлу (зі шляхом чи без, із розширенням чи без):


![Вікно терміналу](/tex/images/java/Conversion-MainInputTerminal.png)

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