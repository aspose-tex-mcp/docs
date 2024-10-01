---
translation: true
template: /templates/_template-java.md
title: LaTeX у PDF | Aspose.TeX для Java
linktitle: LaTeX у PDF
weight: 11
url: /java/latex-to-pdf/
keywords: latex у pdf, latex pdf, конвертація latex у pdf
description: Щоб конвертувати TeX у PDF за допомогою рішення Aspose.TeX API для Java, ознайомтеся з цією статтею, щоб побачити, як це зробити, і приклади коду.
lastmod: 2024-09-20
---

{{<section overview>}}


## Як конвертувати LaTeX у PDF

Давайте ближче розглянемо код Java, що забезпечує найпростіший спосіб перетворення LaTeX у формат PDF.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-LaTeXToPdf-Simplest.java" >}}

Отже, перше, що нам потрібно зробити (іноді не перше, як ми дізнаємося пізніше), це створити екземпляр класу [TeXOptions](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions). Єдиним статичним методом, який це робить, є [consoleAppOptions()](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#consoleAppOptions-com.aspose.tex.TeXConfig-), тому не будемо турбуватися про значення його назви. Метод приймає [примірник](https://reference.aspose.com/tex/java/com.aspose.tex/TeXConfig#objectLaTeX--) класу [TeXConfig](https://reference.aspose.com/tex/java/com.aspose.tex/TeXConfig), який точно підходить для перетворення [файлу LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Ця конфігурація вказує механізму Object TeX завантажити формат Object LaTeX і бути готовим прийняти файл LaTeX. Формат об’єкта LaTeX — це просто формат [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), за винятком того, що він використовує специфічні примітиви [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) для налаштування показників сторінки.

Першим із необхідних параметрів є [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--), який визначає простір або область, куди буде записаний вихід TeX. [Тут](/tex/{{lang.url-fragment}}java/aspose-tex-output/) наведено деталі про концепцію вихідного каталогу в **Aspose.TeX для Java**. У цьому прикладі ми використовуємо клас [OutputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/OutputFileSystemDirectory), який дозволяє записувати вихідні дані у вказаний каталог або папку.

Другий варіант — екземпляр класу [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/SaveOptions), який керуватиме перетворенням [об’єктної моделі](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) у цільовий формат. Оскільки ми перетворюємо LaTeX у PDF, це екземпляр класу [PdfSaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfSaveOptions).

Потім нам потрібно створити екземпляр класу [TeXJob](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob). Бажаючи перетворити файл LaTeX, що зберігається у файловій системі, ми використовуємо [this](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob#TeXJob-java.lang.String-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-) версію конструктора. Потрібно вказати повний шлях до файлу. В іншому випадку механізм шукатиме його в поточному каталозі (який визначено [тут](https://docs.oracle.com/javase/7/docs/api/java/io/File.html)) і, швидше за все, не знайде. Тим не менш, ми можемо опустити розширення, якщо наш файл має *.tex*. Механізм додасть його автоматично. Другим аргументом конструктора є екземпляр класу [Device](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/Device). Оскільки ми перетворюємо LaTeX у PDF, це екземпляр класу [PdfDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfDevice). В якості останнього аргументу ми передаємо нещодавно підготовлені параметри конвертації.

Все, що нам зараз потрібно зробити, це [запустити](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob#run--) роботу.

Незалежно від того, чи був запуск успішним чи ні, першим результатом, який ми побачимо, буде вихід терміналу. У разі успіху це виглядає приблизно так:

```text
This is ObjectTeX, Version 3.1415926-1.0 (Aspose.TeX 21.8)
entering extended mode

(<input_directory>\hello-world.ltx
LaTeX2e <2011/06/27>
(article.cls
Document Class: article 2007/10/19 v1.4h Standard LaTeX document class
(size10.clo))
No file hello-world.aux.
[1]
(<output_directory>\hello-world.aux) )
Output written on hello-world.pdf (1 page).
Transcript written on hello-world.log.
```

Ми знайдемо інші продукти роботи двигуна в папці, яку ми вказали як каталог виведення. Це буде файл стенограми (.log) і, **Вуаля!**, основний вихідний PDF-файл.

## Альтернативний спосіб запису основного вихідного файлу PDF

Є ще один конструктор класу [PdfDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfDevice#PdfDevice-java.io.OutputStream-), який дозволяє нам отримати кінцевий PDF-файл альтернативним способом.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-LaTeXToPdf-Alternative.java" >}}

Файл *any-name.pdf* у вказаному каталозі буде нашим основним вихідним PDF-файлом. У той же час, на відміну від [image output](/tex/{{lang.url-fragment}}java/latex-to-png/#an-alternative-way-to-write-main-output-png-files), ми не знайдемо PDF-файлів у вихідному каталозі, визначеному параметрами перетворення. Виняток: *any-name.pdf* знаходиться (за своїм шляхом) у тому самому каталозі файлової системи, який призначено параметру [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--) за допомогою [OutputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/OutputFileSystemDirectory).

## Про параметри введення

Якщо наш основний вхідний файл потребує залежностей, наприклад, пакетів, які не входять до базової системи LaTeX і підтримуваних пакетів, ми ПОВИННІ встановити опцію [RequiredInputDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getRequiredInputDirectory--) так само, як ми встановлюємо [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--) і помістіть залежності в цей каталог. Залежності можуть бути довільно організовані в підкаталоги. Якщо ми маємо власні файли для включення в процес верстки, скажімо, зовнішні графічні файли, ми ПОВИННІ також встановити [InputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getInputWorkingDirectory--), використовуючи шлях до розташування, де ці файли зібрано. Ми також можемо розмістити головний вхідний файл десь усередині вхідного каталогу та вказати відносний шлях у методі `run()` (або взагалі не вказати шлях, якщо головний вхідний файл знаходиться в корені). [Тут](/tex/{{lang.url-fragment}}java/aspose-tex-input/) наведено деталі про концепцію каталогу вводу в **Aspose.TeX для Java** та надані реалізації.

Інші варіанти завдань TeX обговорюються [тут](/tex/{{lang.url-fragment}}java/other-options/).

**Ви також можете ознайомитися з безкоштовною [веб-програмою] для перетворення LaTeX у PDF (29), створеною на основі API [Aspose.TeX для .NET](https://products.aspose.com/tex/net/). [Тут](https://products.aspose.com/tex/java/) – сторінка версії Java.**