---
translation: true
template: /templates/_template-java.md
title: Інтерфейс виводу Aspose.TeX | Java
linktitle: Інтерфейс виведення Aspose.TeX
weight: 16
url: /java/aspose-tex-output/
description: Функціональність перетворення рішення Aspose.TeX API для Java з TeX як формат виводу пояснюється тут із прикладами коду.
lastmod: "2026-04-21"
---

{{<section overview>}}

Будь ласка, зверніться до **Aspose.TeX для Java** [посилання на API](https://reference.aspose.com/tex/java/com.aspose.tex/), щоб отримати формальні визначення реалізації введення/виведення.

Приклади файлової системи, ZIP і терміналів набирають `hello-world.tex` у XPS. Укажіть у `inputDirectory` папку з файлом TeX, а в `outputDirectory` — наявну папку виведення. Для виведення в ZIP задайте `outputZip` як `java.nio.file.Path` у наявній папці. Імпортуйте класи Aspose.TeX із вибраного прикладу, `com.aspose.tex.rendering.XpsDevice` і потрібні класи `java.io` та `java.nio.file`. Метод виклику має обробляти або оголошувати винятки. Застосуйте ліцензію згідно з [посібником із ліцензування](/tex/{{lang.url-fragment}}java/licensing/), щоб уникнути обмежень ознайомлювальної версії.

## Поняття вихідного каталогу

Оскільки примітиви вводу-виводу мови TeX можуть мати справу лише з іменами файлів, Aspose.TeX визначає каталог як відображення між іменами та масивами даних. Маси даних мають бути файлами, потоками, масивами або будь-яким іншим. API дозволяє нам окремо вказувати вхідні та вихідні робочі каталоги. Він надає загальний інтерфейс [IOutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/) для виведення, який користувач може реалізувати для власних цілей. Він також надає власні реалізації, які будуть розглянуті нижче. Інтерфейс розширює [IInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/), оскільки механізм може спочатку створити та записати файл, а потім прочитати його назад. Власний метод інтерфейсу [getOuputFile()](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/#getOutputFile-java.lang.String-java.lang.String:A-) повертає потік для запису, на відміну від потоку для читання, який повертає [getFile()](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-).

### Запис вихідного файлу у файлову систему диска

Як ми згадували [вище](/tex/{{lang.url-fragment}}/java/conversion/), найпоширенішим значенням для [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--) буде екземпляр класу [OutputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputfilesystemdirectory/).

Ось як ми це встановимо:

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputFileSystemDirectory.java" >}}

Цей варіант використання досить простий, тому ми не будемо на ньому довго зупинятися.

### Запис вихідного файлу в ZIP-архів

Ми також можемо створити файл (або потік) і дозволити механізму TeX використовувати його як ZIP-архів для зберігання вихідних файлів. Ось воно:

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputZipDirectory.java" >}}

Спочатку ми створюємо вихідний потік для файлу ZIP. Потім, після створення параметрів перетворення, ми встановлюємо параметр [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--) як екземпляр класу [OutputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputzipdirectory/). Приклад зберігає `hello-world.xps` і `hello-world.log` в архіві. Після завдання викличте `finish()` для папки виведення до закриття базового потоку. Приклади тримають потоки й робочі папки відкритими до завершення завдання, потім закривають їх.

## Поняття про вихідний термінал

Є ще одна важлива частина виводу --- вихід терміналу. Що стосується цього, **Aspose.TeX для Java** визначає загальний інтерфейс [IOutputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputterminal/) як такий, що має два методи. Один із них повертає екземпляр [BufferedWriter](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedWriter.html). Інший повертає екземпляр [OutputStream](https://docs.oracle.com/javase/6/docs/api/java/io/OutputStream.html) як базовий потік. Надані реалізації інтерфейсу обговорюються нижче.

### Запис виводу терміналу на консоль

Для цього нам потрібно встановити параметр [TerminalOut](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getTerminalOut--) як екземпляр класу [OutputConsoleTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/outputconsoleterminal/).

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputConsoleTerminal.java" >}}

`OutputConsoleTerminal` — значення цього параметра за замовчуванням. Приклад явно вибирає його та записує виведення термінала в консоль під час перетворення. Усі чотири приклади виконуються без взаємодії з користувачем; приклади файлової системи та ZIP зберігають виведення термінала в пам’яті.

### Запис вихідних даних терміналу у файл

На відміну від вхідного терміналу, **Aspose.TeX для Java** забезпечує реалізацію [IOutputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputterminal/), яка дозволяє нам записувати вихідні дані терміналу у файл у деякому вихідному каталозі.

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputFileTerminal.java" >}}

Задайте робочу папку виведення до створення `OutputFileTerminal`. Він записує виведення термінала в [<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trm, у цьому прикладі — `hello-world.trm`, у вказаній папці. Цей файл термінала відокремлений від журналу TeX `hello-world.log`. Для запису виведення термінала в інше місце передайте конструктору іншу реалізацію [IOutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/).