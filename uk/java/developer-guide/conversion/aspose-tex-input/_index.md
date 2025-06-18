---
translation: true
template: /templates/_template-java.md
title: Інтерфейс введення Aspose.TeX | Java
linktitle: Інтерфейс введення Aspose.TeX
weight: 15
url: /java/aspose-tex-input/
description: Функціональність перетворення рішення Aspose.TeX API для Java з TeX як форматом введення пояснюється тут із прикладами коду.
lastmod: "2025-06-13"
---

{{<section overview>}}

Будь ласка, зверніться до **Aspose.TeX для Java** [посилання на API](https://reference.aspose.com/tex/java/com.aspose.tex/package-frame), щоб отримати формальні визначення реалізації введення/виведення.

## Поняття вхідного каталогу

Оскільки примітиви вводу-виводу мови TeX можуть працювати лише з іменами файлів, **Aspose.TeX для Java** визначає каталог як відображення між іменами та масивами даних. Маси даних мають бути файлами, потоками, масивами або будь-яким іншим. API дозволяє нам окремо вказувати вхідні та вихідні робочі каталоги. Він забезпечує загальний інтерфейс [IInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory), який користувач може реалізувати для власних цілей. Він також надає власні реалізації, які будуть розглянуті нижче. Інтерфейс визначає метод [getFile()](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-), який повертає потік даних і визначає повне ім'я файлу, при цьому в якості першого аргументу бере якесь, гіпотетично інше ім'я, яке, по суті, є ключем відображення .

### Отримання вхідних файлів із файлової системи диска

Ось як би ми це зробили:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-InputFileSystemDirectory.java" >}}

Цей варіант використання досить простий, тому ми не будемо на ньому довго зупинятися.

### Отримання вхідних файлів із ZIP-архіву

Ми також можемо помістити вхідні файли в архів ZIP і вважати його вхідним каталогом. У цьому випадку ми повинні діяти наступним чином:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-InputZipDirectory.java" >}}

Спочатку ми створюємо потік, що містить ZIP-файл. Потім, після створення параметрів перетворення, ми встановлюємо параметр [InputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getInputWorkingDirectory--) як екземпляр класу [InputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/InputZipDirectory). Другим аргументом конструктора є базовий шлях всередині архіву. Якщо ми хочемо, щоб весь архів був вхідним каталогом, ми повинні передати порожній рядок. 

## Поняття про вхідний термінал

Тепер давайте згадаємо, що є також термінальний вхід. Що стосується цього, **Aspose.TeX для Java** визначає загальний інтерфейс [IInputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/IInputTerminal) як такий, що має два методи. Один із них повертає екземпляр [BufferedReader](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedReader.html). Інший метод повертає [InputStream](https://docs.oracle.com/javase/6/docs/api/java/io/InputStream.html) як базовий потік. Надані реалізації інтерфейсу обговорюються нижче.

### Отримання введення терміналу з консолі

Для цього нам потрібно встановити опцію [TerminalIn](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getTerminalIn--) як екземпляр класу [InputConsoleTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/InputConsoleTerminal).

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-InputConsoleTerminal.java" >}}

Але, чесно кажучи, це значення параметра за замовчуванням, тому немає потреби вказувати його. Через цей факт і доки немає інших реалізацій, цей розділ служить лише для демонстраційних цілей.

Теоретично, якщо у нас є інтерактивний файл TeX (або сценарій) з передбачуваною поведінкою, ми можемо захотіти реалізувати версію терміналу введення, яка б містила додатковий сценарій для відповіді на запити механізму TeX. Спробуйте свої сили, коли матимете час!