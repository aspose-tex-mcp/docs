---
translation: true
template: /templates/_template-net.md
title: LaTeX у PDF | .NET
linktitle: LaTeX у PDF
weight: 11
url: /net/latex-to-pdf/
keywords: latex у pdf, latex pdf, конвертація latex у pdf
description: Щоб конвертувати TeX у PDF за допомогою рішення API Aspose.TeX для .NET, ознайомтеся з цією статтею, щоб побачити, як це зробити, і приклади коду.
lastmod: "2025-06-13"
---

{{<section overview>}}


## Як конвертувати LaTeX у PDF

Давайте детально розглянемо код у C#, що забезпечує найпростіший спосіб конвертувати LaTeX у формат PDF.

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-LaTeXToPdf-Simplest.cs" >}}

Отже, перше, що нам потрібно зробити (ну, іноді не перше), це створити екземпляр класу [TeXOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/). Єдиним статичним методом, який це робить, є [ConsoleAppOptions()](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions/), тож давайте не будемо спантеличуватися значенням його назви. Метод приймає [примірник](https://reference.aspose.com/tex/net/aspose.tex/texconfig/objectlatex/) класу [TeXConfig](https://reference.aspose.com/tex/net/aspose.tex/texconfig/), який точно підходить для перетворення [файлу LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Ця конфігурація повідомляє механізму Object TeX завантажити формат Object LaTeX і бути готовим прийняти файл LaTeX. Формат Object LaTeX насправді є лише форматом [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), за винятком того, що він використовує специфічні примітиви [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) для налаштування показників сторінки.

Першим із необхідних параметрів є [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/), який визначає простір або область, куди буде записаний вихід TeX. [Тут](/tex/{{lang.url-fragment}}net/aspose-tex-output/) наведено подробиці про концепцію вихідного каталогу в **Aspose.TeX для .NET**. У цьому прикладі ми використовуємо клас [OutputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/), який дозволяє записувати вихідні дані у вказаний каталог або папку.

Другий варіант — екземпляр класу [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation/saveoptions/), який керуватиме перетворенням [об’єктної моделі](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) у цільовий формат. Оскільки ми перетворюємо LaTeX у PDF, це екземпляр класу [PdfSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/).

Потім нам потрібно створити екземпляр класу [TeXJob](https://reference.aspose.com/tex/net/aspose.tex/texjob/). Бажаючи перетворити файл LaTeX, що зберігається у файловій системі, ми використовуємо [this](https://reference.aspose.com/tex/net/aspose.tex/texjob/texjob/) версію конструктора. Потрібно вказати повний шлях до файлу. Інакше механізм шукатиме його в поточному каталозі (це [CurrentDirectory](https://docs.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory)) і, швидше за все, не знайде. Тим не менш, ми можемо опустити розширення, якщо наш файл має *.tex*. Механізм додасть його автоматично. Другим аргументом конструктора є екземпляр класу [Device](https://reference.aspose.com/tex/net/aspose.tex.presentation/device/). Оскільки ми перетворюємо LaTeX у PDF, це екземпляр класу [PdfDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/). В якості останнього аргументу ми передаємо нещодавно підготовлені параметри конвертації.

Все, що залишилося зробити зараз, це [запустити](https://reference.aspose.com/tex/net/aspose.tex/texjob/run/) роботу.

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

Інші «плоди» праці движка ми знайдемо в папці, яку ми вказали як вихідний каталог. Це буде файл стенограми та, **ось він!**, основний вихідний PDF-файл.

## Альтернативний спосіб запису основного вихідного файлу PDF

Є ще один конструктор класу [PdfDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/pdfdevice/), який дозволяє нам отримати кінцевий PDF-файл альтернативним способом.

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-LaTeXToPdf-Alternative.cs" >}}

Файл *any-name.pdf* у вказаному каталозі буде нашим основним вихідним PDF-файлом. У той же час, на відміну від [image output](/tex/{{lang.url-fragment}}net/latex-to-png/#an-alternative-way-to-write-main-output-png-files), ми не знайдемо PDF-файлів у вихідному каталозі, визначеному параметрами перетворення. Виняток: *any-name.pdf* знаходиться (за своїм шляхом) у тому самому каталозі файлової системи, який призначено параметру [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) за допомогою [OutputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/).

## Про параметри введення

Якщо наш основний вхідний файл потребує залежностей, наприклад, пакетів, які не входять до базової системи LaTeX і підтримуваних пакетів, ми ПОВИННІ встановити опцію [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) так само, як ми встановлюємо [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) і помістіть залежності в цей каталог. Залежності можуть бути довільно організовані в підкаталоги. Якщо ми маємо власні файли для включення в процес верстки, скажімо, зовнішні графічні файли, ми ПОВИННІ також встановити [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/inputworkingdirectory/), використовуючи шлях до розташування, де ці файли зібрано. Ми також можемо розмістити головний вхідний файл десь усередині вхідного каталогу та вказати відносний шлях у методі `run()` (або взагалі не вказати шлях, якщо головний вхідний файл знаходиться в корені). [Тут](/tex/{{lang.url-fragment}}net/aspose-tex-input/) наведено подробиці про концепцію каталогу введення в **Aspose.TeX для .NET** і надані реалізації.

Інші варіанти завдань TeX обговорюються [тут](/tex/{{lang.url-fragment}}net/other-options/).

**Ви також можете ознайомитися з безкоштовною [веб-програмою] для перетворення LaTeX у PDF (29), створеною на основі [Aspose.TeX для .NET API](https://products.aspose.com/tex/net/).**