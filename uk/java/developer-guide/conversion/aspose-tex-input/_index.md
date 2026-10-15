---
translation: true
template: /templates/_template-java.md
title: Інтерфейс введення Aspose.TeX | Java
linktitle: Інтерфейс введення Aspose.TeX
weight: 15
url: /java/aspose-tex-input/
description: Функціональність перетворення рішення Aspose.TeX API для Java з TeX як форматом введення пояснюється тут із прикладами коду.
lastmod: "2026-04-21"
---

{{<section overview>}}

Будь ласка, зверніться до **Aspose.TeX для Java** [посилання на API](https://reference.aspose.com/tex/java/com.aspose.tex/), щоб отримати формальні визначення реалізації введення/виведення.

Приклади файлової системи та ZIP набирають `hello-world.tex` у `hello-world.xps`. Укажіть у `inputDirectory` папку з файлом TeX, а в `outputDirectory` — наявну папку виведення. Для введення із ZIP задайте `inputZip` як `java.nio.file.Path` до архіву з `in/hello-world.tex`. Імпортуйте класи Aspose.TeX із вибраного прикладу, `com.aspose.tex.rendering.XpsDevice` і потрібні класи `java.io` та `java.nio.file`. Метод виклику має обробляти або оголошувати винятки. Застосуйте ліцензію згідно з [посібником із ліцензування](/tex/{{lang.url-fragment}}java/licensing/), щоб уникнути обмежень ознайомлювальної версії.

## Поняття вхідного каталогу

Оскільки примітиви вводу-виводу мови TeX можуть працювати лише з іменами файлів, **Aspose.TeX для Java** визначає каталог як відображення між іменами та масивами даних. Маси даних мають бути файлами, потоками, масивами або будь-яким іншим. API дозволяє нам окремо вказувати вхідні та вихідні робочі каталоги. Він забезпечує загальний інтерфейс [IInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/), який користувач може реалізувати для власних цілей. Він також надає власні реалізації, які будуть розглянуті нижче. Інтерфейс визначає метод [getFile()](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-), який повертає потік даних і визначає повне ім'я файлу, при цьому в якості першого аргументу бере якесь, гіпотетично інше ім'я, яке, по суті, є ключем відображення .

### Отримання вхідних файлів із файлової системи диска

Ось як би ми це зробили:

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-InputFileSystemDirectory.java" >}}

Цей варіант використання досить простий, тому ми не будемо на ньому довго зупинятися.

### Отримання вхідних файлів із ZIP-архіву

Ми також можемо помістити вхідні файли в архів ZIP і вважати його вхідним каталогом. У цьому випадку ми повинні діяти наступним чином:

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-InputZipDirectory.java" >}}

Спочатку ми створюємо потік, що містить ZIP-файл. Потім, після створення параметрів перетворення, ми встановлюємо параметр [InputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getInputWorkingDirectory--) як екземпляр класу [InputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputzipdirectory/). Другим аргументом конструктора є базовий шлях всередині архіву. Якщо ми хочемо, щоб весь архів був вхідним каталогом, ми повинні передати порожній рядок. Приклад тримає ZIP-потік і папку введення відкритими до завершення завдання TeX, потім закриває їх. Він виконується без взаємодії з користувачем і зберігає виведення термінала в пам’яті.

## Поняття про вхідний термінал

Тепер давайте згадаємо, що є також термінальний вхід. Що стосується цього, **Aspose.TeX для Java** визначає загальний інтерфейс [IInputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/iinputterminal/) як такий, що має два методи. Один із них повертає екземпляр [BufferedReader](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedReader.html). Інший метод повертає [InputStream](https://docs.oracle.com/javase/6/docs/api/java/io/InputStream.html) як базовий потік. Надані реалізації інтерфейсу обговорюються нижче.

### Отримання введення терміналу з консолі

Для цього нам потрібно встановити опцію [TerminalIn](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getTerminalIn--) як екземпляр класу [InputConsoleTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/inputconsoleterminal/).

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-InputConsoleTerminal.java" >}}

`InputConsoleTerminal` — значення цього параметра за замовчуванням. Цей приклад показує лише налаштування термінала та не запускає завдання. Завданню, що запитує введення з термінала, потрібні дані користувача або власна реалізація термінала. Приклади файлової системи та ZIP вище виконуються без взаємодії з користувачем із повними вхідними файлами.

Теоретично, якщо у нас є інтерактивний файл TeX (або сценарій) з передбачуваною поведінкою, ми можемо захотіти реалізувати версію терміналу введення, яка б містила додатковий сценарій для відповіді на запити механізму TeX. Спробуйте свої сили, коли матимете час!