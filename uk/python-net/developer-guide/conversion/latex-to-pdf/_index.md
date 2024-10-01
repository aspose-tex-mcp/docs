---
translation: true
template: /templates/_template-python-net.md
title: LaTeX у PDF | Aspose.TeX для Python
linktitle: LaTeX у PDF
weight: 11
url: /python-net/latex-to-pdf/
keywords: latex у pdf, latex pdf, конвертація latex у pdf
description: Дізнайтеся, як конвертувати TeX у PDF за допомогою рішення Aspose.TeX API для Python із цією статтею, яка містить детальне пояснення та приклади коду.
lastmod: 2024-09-20
---

{{<section overview>}}

## Перетворення LaTeX у PDF

Тепер давайте детально розглянемо код Python, який пропонує найпростіший підхід до перетворення LaTeX у формат PDF.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToPdf-Simplest.py" >}}

Для початку нам потрібно створити екземпляр класу [TeXOptions](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/). Метод [console_app_options()](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/console_app_options/#aspose.tex.TeXConfig) є єдиним статичним методом, який виконує це, тому не турбуйтеся про його назву. Цей метод використовує екземпляр [object_latex](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_latex/) класу [TeXConfig](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/), який ідеально підходить для перетворення [файлу LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Ця конфігурація наказує механізму Object TeX завантажити формат Object LaTeX і підготуватися до обробки файлу LaTeX. Формат Object LaTeX по суті такий же, як і формат [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), але він використовує специфічні примітиви [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) для визначення показників сторінки.

Перший параметр, який потрібно вказати, це [output_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/output_working_directory/), який визначає місце, де буде збережено вихід TeX. Якщо потрібно, ви можете знайти більше інформації про [концепцію вихідного каталогу в **Aspose.TeX**](/tex/{{lang.url-fragment}}net/aspose-tex-output/). У цьому конкретному випадку ми використовуємо клас [OutputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputfilesystemdirectory/), який дозволяє нам записувати вихідні дані у визначений каталог або папку.

Для другого варіанту потрібен екземпляр класу [SaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/saveoptions/), який визначає, як [об’єктна модель](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) перетворюється на потрібний формат. У нашому випадку, коли ми перетворюємо LaTeX у PDF, це посилається на екземпляр класу [PdfSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfsaveoptions/).

Щоб перетворити файл LaTeX, який зберігається у файловій системі, нам потрібно створити екземпляр класу [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/) за допомогою [constructor](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#str-aspose.tex.presentation.Device-aspose.tex.TeXOptions), який приймає повний шлях до файлу як параметр. Якщо ми не вкажемо повний шлях, механізм шукатиме файл у поточному каталозі (який є робочим каталогом сценарію) і може не знайти його. Однак ми можемо опустити розширення, якщо наш файл має розширення `.tex`, оскільки система автоматично додасть його. Другим аргументом конструктора є екземпляр класу [Device](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/device/). У нашому випадку, оскільки ми перетворюємо LaTeX у PDF, це екземпляр класу [PdfDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfdevice/). Нарешті, ми передаємо нещодавно підготовлені параметри перетворення як останній аргумент.

Тепер залишається лише [запустити](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/run/#) роботу.

Після виконання, незалежно від того, було воно успішним чи ні, перше, що ми побачимо, це вихід терміналу. Якщо виконання виконано успішно, результат виглядатиме приблизно так:

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

У папці, яку ми вказали як вихідний каталог, серед інших результатів роботи движка ми знайдемо файл стенограми і, **ось він!**, основний вихідний PDF-файл.

## Альтернативний спосіб запису основного вихідного файлу PDF

Клас *PdfDevice* має ще один [конструктор](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfdevice/__init__/#io.RawIOBase), який дозволяє нам отримувати кінцевий PDF-файл інакше.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToPdf-Alternative.py" >}}

Основний вихідний файл PDF матиме назву `any-name.pdf` і буде розміщено у вказаному каталозі. Однак, на відміну від [виведення зображення](/tex/{{lang.url-fragment}}python-net/latex-to-image/#an-alternative-way-to-write-the-main-output-png-files), у вихідному каталозі, визначеному параметрами перетворення, не буде інших PDF-файлів. Винятком є ​​випадки, коли `any-name.pdf` знаходиться в тому самому каталозі файлової системи, призначеному параметру *output_working_directory* за допомогою *OutputFileSystemDirectory*.

## Про параметри введення

Якщо наш основний вхідний файл потребує залежностей, таких як Пакети, які не входять до базової системи LaTeX, і підтримувані Пакети, необхідно встановити опцію [required_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/) подібним чином, як ми встановлюємо опцію *output_working_directory* і розмістіть залежності в цьому каталозі. Залежності можна організовувати у підкаталоги за бажанням. Крім того, якщо у нас є власні файли для включення в процес верстки, наприклад зовнішні графічні файли, ми також повинні встановити [input_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/input_working_directory/), використовуючи шлях до місця, де зберігаються ці файли. Ми також можемо розмістити головний вхідний файл у вхідному каталозі та вказати відносний шлях у методі `run()` або взагалі не вказати шлях, якщо основний вхідний файл знаходиться в корені. Щоб отримати докладніші відомості про концепцію каталогу введення в **Aspose.TeX для Python** і надані реалізації, зверніться до [тут](/tex/{{lang.url-fragment}}python-net/aspose-tex-input/).

Також обговорюються [інші варіанти завдань TeX](/tex/{{lang.url-fragment}}python-net/other-options/).

**Ви також можете дослідити безкоштовну [веб-програму для перетворення LaTeX у PDF](https://products.aspose.app/tex/conversion/latex-to-pdf), яка розроблена за допомогою [Aspose.TeX для .NET API](https://products.aspose.com/tex/net/).**