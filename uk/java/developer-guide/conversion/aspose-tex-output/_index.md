---
translation: true
template: /templates/_template-java.md
title: Інтерфейс виводу Aspose.TeX | Java
linktitle: Інтерфейс виведення Aspose.TeX
weight: 16
url: /java/aspose-tex-output/
description: Функціональність перетворення рішення Aspose.TeX API для Java з TeX як формат виводу пояснюється тут із прикладами коду.
lastmod: "2025-06-13"
---

{{<section overview>}}

Будь ласка, зверніться до **Aspose.TeX для Java** [посилання на API](https://reference.aspose.com/tex/java/com.aspose.tex/package-frame), щоб отримати формальні визначення реалізації введення/виведення.

## Поняття вихідного каталогу

Оскільки примітиви вводу-виводу мови TeX можуть мати справу лише з іменами файлів, Aspose.TeX визначає каталог як відображення між іменами та масивами даних. Маси даних мають бути файлами, потоками, масивами або будь-яким іншим. API дозволяє нам окремо вказувати вхідні та вихідні робочі каталоги. Він надає загальний інтерфейс [IOutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputWorkingDirectory) для виведення, який користувач може реалізувати для власних цілей. Він також надає власні реалізації, які будуть розглянуті нижче. Інтерфейс розширює [IInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory), оскільки механізм може спочатку створити та записати файл, а потім прочитати його назад. Власний метод інтерфейсу [getOuputFile()](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputWorkingDirectory#getOutputFile-java.lang.String-java.lang.String:A-) повертає потік для запису, на відміну від потоку для читання, який повертає [getFile()](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-).

### Запис вихідного файлу у файлову систему диска

Як ми згадували [вище](/tex/{{lang.url-fragment}}/java/conversion/), найпоширенішим значенням для [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--) буде екземпляр класу [OutputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/OutputFileSystemDirectory).

Ось як ми це встановимо:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-OutputFileSystemDirectory.java" >}}

Цей варіант використання досить простий, тому ми не будемо на ньому довго зупинятися.

### Запис вихідного файлу в ZIP-архів

Ми також можемо створити файл (або потік) і дозволити механізму TeX використовувати його як ZIP-архів для зберігання вихідних файлів. Ось воно:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-OutputZipDirectory.java" >}}

Спочатку ми створюємо вихідний потік для файлу ZIP. Потім, після створення параметрів перетворення, ми встановлюємо параметр [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--) як екземпляр класу [OutputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/OutputZipDirectory).

## Поняття про вихідний термінал

Є ще одна важлива частина виводу --- вихід терміналу. Що стосується цього, **Aspose.TeX для Java** визначає загальний інтерфейс [IOutputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputTerminal) як такий, що має два методи. Один із них повертає екземпляр [BufferedWriter](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedWriter.html). Інший повертає екземпляр [OutputStream](https://docs.oracle.com/javase/6/docs/api/java/io/OutputStream.html) як базовий потік. Надані реалізації інтерфейсу обговорюються нижче.

### Запис виводу терміналу на консоль

Для цього нам потрібно встановити параметр [TerminalOut](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getTerminalOut--) як екземпляр класу [OutputConsoleTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/OutputConsoleTerminal).

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-OutputConsoleTerminal.java" >}}

Знову ж таки, це значення параметра за замовчуванням, тому немає потреби вказувати його. Через це цей розділ служить лише для демонстраційних цілей.

### Запис вихідних даних терміналу у файл

На відміну від вхідного терміналу, **Aspose.TeX для Java** забезпечує реалізацію [IOutputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputTerminal), яка дозволяє нам записувати вихідні дані терміналу у файл у деякому вихідному каталозі.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-OutputFileTerminal.java" >}} 

Тут ми просимо механізм TeX записати вихідні дані терміналу у файл із назвою [<назва_завдання>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trm, який зберігатиметься в тому самому каталозі виводу, який ми вказали для решти виводу. Але в цьому немає необхідності. Ми також можемо передати будь-який інший екземпляр будь-якої реалізації [IOutputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputTerminal) до конструктора.