---
translation: true
template: /templates/_template-python-net.md
title: LaTeX до зображення | Aspose.TeX для Python
linktitle: LaTeX до зображення
weight: 10
url: /python-net/latex-to-image/
aliases:
- /python-net/latex-to-png/
- /python-net/latex-to-svg/
keywords: латекс у png, латекс png, латекс у зображення, латексне зображення, латекс у jpg, латекс у jpg, латекс у jpeg, латекс у jpeg, латекс у tiff, латекс у tiff, латекс у bmp, латекс bmp
description: Щоб перетворити TeX у формати зображень за допомогою рішення Aspose.TeX API для Python, ознайомтеся з цією статтею, щоб побачити, як це зробити, і приклади коду.
lastmod: 2024-09-20
---

{{<section overview>}}

**Aspose.TeX для Python** надає нам можливість конвертувати файли LaTeX у різні формати растрових зображень.

## Перетворення LaTeX у PNG

Тепер давайте детально розглянемо код Python, який пропонує найпростіший підхід до перетворення LaTeX у формат PNG.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToPng-Simplest.py" >}}

Для початку нам потрібно створити екземпляр класу [TeXOptions](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/) за допомогою методу [console_app_options()](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/console_app_options/#aspose.tex.TeXConfig). Не турбуйтеся про назву, це лише статичний метод, який створює екземпляр. Цей метод використовує екземпляр [object_latex](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_latex/) класу [TeXConfig](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/), який ідеально підходить для перетворення [файлу LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Ця конфігурація налаштовує механізм Object TeX для завантаження формату Object LaTeX і готовності до обробки файлу LaTeX. Формат Object LaTeX по суті такий самий, як [формат LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), але він використовує специфічні примітиви [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) для визначення показників сторінки.

Першим із необхідних параметрів є [output_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/output_working_directory/), який визначає місце, де буде збережено вихід TeX. Якщо вам цікаво, ви можете дізнатися більше про концепцію [каталогу виводу в **Aspose.TeX для Python**](/tex/{{lang.url-fragment}}python-net/aspose-tex-output/). У цьому конкретному прикладі ми використовуємо клас [OutputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputfilesystemdirectory/) для запису результату в певний каталог або папку.

Друга опція є екземпляром класу [SaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/saveoptions/), який відповідає за керування перетворенням з [об’єктної моделі](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) у потрібний формат. У цьому випадку, оскільки ми перетворюємо LaTeX у PNG, ми використовуємо екземпляр класу [PngSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.image/pngsaveoptions/), який дозволяє нам вказати роздільну здатність вихідних зображень.

Далі ми створюємо екземпляр класу [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/). У цьому випадку, оскільки ми хочемо перетворити файл LaTeX, що зберігається у файловій системі, ми використовуємо [цю версію конструктора](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#str-aspose.tex.presentation.Device-aspose.tex.TeXOptions). Нам потрібно вказати повний шлях до файлу, інакше механізм шукатиме його в поточному каталозі (який є робочим каталогом сценарію) і може не знайти. Однак розширення `.tex` можна опустити, оскільки система автоматично додасть його. Другим аргументом конструктора є екземпляр класу [Device](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/device/). Оскільки ми перетворюємо LaTeX у PNG, це екземпляр класу [ImageDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.image/imagedevice/), який є спільним для всіх підтримуваних форматів зображень. Нарешті, ми передаємо підготовлені параметри перетворення як останній аргумент.

Тепер залишається лише [запустити](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/run/#) роботу.

Після виконання завдання, незалежно від його успіху чи невдачі, першим виходом, який ми зустрінемо, є вихід терміналу. У разі успішного запуску результат буде приблизно таким:


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
Output written on hello-world.png (1 page).
Transcript written on hello-world.log.
```

Результати роботи движка можна знайти в зазначеному нами вихідному каталозі. Це включатиме файл стенограми та, що найважливіше, основний вихідний файл(и) зображень PNG.

## Альтернативний спосіб запису основних вихідних файлів PNG

Існує альтернативний метод отримання даних зображення у вигляді масиву масивів байтів, де кожен масив у другому вимірі представляє дані зображення для окремої сторінки.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToPng-Alternative.py" >}}

Файл(и) "page-n.png" можна записати до будь-якого вказаного шляху. На відміну від [PDF output](/tex/{{lang.url-fragment}}python-net/latex-to-pdf/#an-alternative-way-to-write-the-main-output-pdf-file), ці PNG-файли дублюватимуть вихідні PNG-файли, які записуються у вихідний каталог.

## Щодо варіантів введення

Якщо наш основний вхідний файл потребує залежностей, наприклад пакетів, які не входять до базової системи LaTeX або підтримуваних пакунків, нам потрібно встановити параметр [required_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/) подібним чином до того, як ми встановлюємо параметр *output_working_directory* і розмістіть залежності в цьому каталозі. Залежності можна організовувати в підкаталоги за потреби. Якщо у нас є файли, які потрібно включити в процес верстки, наприклад зовнішні графічні файли, нам також потрібно встановити [input_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/input_working_directory/) на місце, де зберігаються ці файли. Ми також можемо розмістити головний вхідний файл у вхідному каталозі та вказати відносний шлях у методі `run()` або взагалі не вказати шлях, якщо основний вхідний файл знаходиться в кореневому каталозі. Також є більше деталей про [концепцію каталогу введення](/tex/{{lang.url-fragment}}python-net/aspose-tex-input/) в **Aspose.TeX** і описані надані реалізації.

Також ознайомтеся з [іншими варіантами роботи TeX тут](/tex/{{lang.url-fragment}}python-net/other-options/).

**Ви також можете дослідити безкоштовну [веб-програму](https://products.aspose.app/tex/conversion/latex-to-png) для перетворення LaTeX у PNG, яка розроблена за допомогою [Aspose.TeX для .NET API](https://products.aspose.com/tex/net/).**

Нижче ми коротко пояснимо перетворення LaTeX в інші підтримувані формати растрових зображень, не занурюючись у подробиці, оскільки суттєвих відмінностей немає. Єдина відмінність полягає в типі властивості [save_options](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/save_options/) у параметрах перетворення.

## Перетворення LaTeX у JPG

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToJpeg.py" >}}

**Ви також можете дослідити безкоштовну [веб-програму для перетворення LaTeX у JPG](https://products.aspose.app/tex/conversion/latex-to-jpg), яка розроблена за допомогою [Aspose.TeX для .NET API](https://products.aspose.com/tex/net/).**

## Перетворення LaTeX у TIFF

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToTiff.py" >}}

**Ви також можете дослідити безкоштовну [веб-програму для перетворення LaTeX у TIFF](https://products.aspose.app/tex/conversion/latex-to-tiff), яка розроблена за допомогою [Aspose.TeX для .NET API](https://products.aspose.com/tex/net/).**

## Перетворення LaTeX на BMP

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToBmp.py" >}}

**Ви також можете дослідити безкоштовну [веб-програму для перетворення LaTeX у BMP](https://products.aspose.app/tex/conversion/latex-to-bmp), яка розроблена за допомогою [Aspose.TeX для .NET API](https://products.aspose.com/tex/net/).**


## Перетворення LaTeX у SVG

Інший підтримуваний цільовий формат — [**SVG**](https://en.wikipedia.org/wiki/SVG). **Масштабована векторна графіка (SVG)** — це формат векторних зображень на основі XML, який використовується для визначення двовимірної графіки. Він підтримує інтерактивність і анімацію.

Зображення **SVG** зберігаються в текстових файлах XML і визначаються у форматі векторної графіки. Це означає, що зображення **SVG** можна масштабувати без втрати якості, а самі файли **SVG** можна шукати, індексувати, створювати сценарії та стискати. Текстові файли XML можна створювати та редагувати за допомогою текстових редакторів або редакторів векторної графіки, і вони можуть відтворюватися у веб-браузерах, які найчастіше використовуються.

API [**Aspose.SVG**](https://products.aspose.com/svg/) пропонує низку функцій для роботи з **SVG**, наприклад створення, завантаження, редагування та перетворення документів **SVG**.

Перетворення LaTeX у SVG так само просте, як [перетворення у формати растрових зображень](/tex/{{lang.url-fragment}}python-net/latex-to-image/), з тією лише різницею, що [save_options](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/save_options/) має бути встановлено на екземпляр класу [SvgSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.svg/svgsaveoptions/) і пристрій має бути змінено на екземпляр класу [SvgDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.svg/svgdevice/).

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToSvg-Simplest.py" >}}

**Ви також можете дослідити безкоштовну [веб-програму для перетворення LaTeX у SVG](https://products.aspose.app/tex/conversion/latex-to-svg), яка розроблена за допомогою [Aspose.TeX для .NET API](https://products.aspose.com/tex/net/).**