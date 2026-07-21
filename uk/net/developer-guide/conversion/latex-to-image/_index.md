---
translation: true
template: /templates/_template-net.md
title: LaTeX до зображення | .NET
linktitle: LaTeX до зображення
weight: 10
url: /net/latex-to-image/
keywords: латекс у png, латекс png, латекс у зображення, латексне зображення, латекс у jpg, латекс у jpg, латекс у jpeg, латекс у jpeg, латекс у tiff, латекс у tiff, латекс у bmp, латекс bmp
description: Щоб перетворити TeX у формати зображень за допомогою Aspose.TeX API для .NET, ознайомтеся з цією статтею, щоб побачити, як це зробити, і приклади коду.
lastmod: "2026-04-22"
---

{{<section overview>}}

**Aspose.TeX для .NET** дозволяє нам конвертувати файли LaTeX у декілька форматів растрових зображень.

## Як конвертувати LaTeX у PNG

Давайте детально розглянемо код у C#, що забезпечує найпростіший спосіб конвертації LaTeX у формат PNG.

{{< gist "aspose-com-gists" "58d1c43acd187f1cde7917fa9a430281" "Example-ConvertLaTeXToPNG-Simplest.cs" >}}

Отже, перше, що нам потрібно зробити (ну, іноді не перше), це створити екземпляр класу [TeXOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/). Єдиним статичним методом, який це робить, є [ConsoleAppOptions()](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions/), тож давайте не будемо спантеличуватися значенням його назви. Метод використовує [екземпляр ObjectLaTeX](https://reference.aspose.com/tex/net/aspose.tex/texconfig/objectlatex/) класу [TeXConfig](https://reference.aspose.com/tex/net/aspose.tex/texconfig/), який точно підходить для перетворення [файлу LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Ця конфігурація повідомляє механізму Object TeX завантажити формат Object LaTeX і бути готовим прийняти файл LaTeX. Формат Object LaTeX насправді є лише форматом [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), за винятком того, що він використовує специфічні примітиви [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) для налаштування показників сторінки.

Першим із необхідних параметрів є [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/), який визначає простір або область, куди буде записаний вихід TeX. [Тут](/tex/{{lang.url-fragment}}net/aspose-tex-output/) наведено подробиці про концепцію вихідного каталогу в **Aspose.TeX для .NET**. У цьому прикладі ми використовуємо клас [OutputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/), який дозволяє записувати вихідні дані у вказаний каталог або папку.

Другий варіант — екземпляр класу [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation/saveoptions/), який керуватиме перетворенням [об’єктної моделі](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) у цільовий формат. Оскільки ми перетворюємо LaTeX у PNG, це екземпляр класу [PngSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.image/pngsaveoptions/), який дозволяє нам вказати роздільну здатність вихідних зображень.

Потім нам потрібно створити екземпляр класу [TeXJob](https://reference.aspose.com/tex/net/aspose.tex/texjob/). Бажаючи перетворити файл LaTeX, що зберігається у файловій системі, ми використовуємо [this](https://reference.aspose.com/tex/net/aspose.tex/texjob/texjob/) версію конструктора. Нам потрібно вказати повний шлях до файлу. Інакше механізм шукатиме його в поточному каталозі (це [CurrentDirectory](https://learn.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory?view=net-10.0)) і, швидше за все, не знайде. Проте розширення *.tex* можна опустити. Механізм додасть його автоматично. Другим аргументом конструктора є екземпляр класу [Device](https://reference.aspose.com/tex/net/aspose.tex.presentation/device/). Оскільки ми перетворюємо LaTeX у PNG, це екземпляр класу [ImageDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.image/imagedevice/), і це є спільним для всіх підтримуваних форматів зображень. В якості останнього аргументу ми передаємо нещодавно підготовлені параметри конвертації.

Все, що залишилося зробити зараз, це [запустити](https://reference.aspose.com/tex/net/aspose.tex/texjob/run/) роботу.

Незалежно від того, чи був запуск успішним чи ні, першим результатом, який ми побачимо, буде вихід терміналу. Якщо запуск пройшов успішно, це буде виглядати приблизно так:


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

Інші «плоди» праці движка ми знайдемо в папці, яку ми вказали як вихідний каталог. Це буде файл стенограми та, **ось він!**, основний вихідний(і) файл(и) зображень PNG.

## Альтернативний спосіб запису основних вихідних файлів PNG

Існує інший спосіб отримати дані зображення у вигляді масиву масивів байтів, кожен масив у другому вимірі представляє дані зображення для окремої сторінки.

**Приклад альтернативного перетворення**

Наведений нижче фрагмент коду C# демонструє інший спосіб отримання виводу PNG шляхом запису даних зображення в потік пам'яті, а не безпосередньо у файлову систему. Цей підхід корисний, коли вам потрібні згенеровані байти PNG у пам'яті для подальшої обробки, наприклад, для надсилання їх через мережу, зберігання в базі даних або виконання додаткових перетворень перед збереженням.

{{< gist "aspose-com-gists" "58d1c43acd187f1cde7917fa9a430281" "Example-ConvertLaTeXToPNG-Alternative.cs" >}}

Файл(и) *"page-n.png"* буде записаний у будь-який шлях, який ми вкажемо. На відміну від [PDF output](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file), вони дублюватимуть вихідні файли PNG, записані у вихідний каталог.

## Про параметри введення

Якщо наш головний вхідний файл потребує залежностей, наприклад, пакетів, які не входять до базової системи LaTeX і підтримуваних пакетів, ми ПОВИННІ встановити опцію [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) так само, як ми встановлюємо [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) і помістіть залежності в цей каталог. Залежності можуть бути довільно організовані в підкаталоги. Якщо у нас є власні файли для включення в процес верстки, скажімо, зовнішні графічні файли, ми ПОВИННІ також встановити [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/inputworkingdirectory/), використовуючи шлях до розташування, де ці файли зібрано. Ми також можемо розмістити основний вхідний файл десь усередині вхідного каталогу та вказати відносний шлях у методі `run()` (або не вказати шлях взагалі, якщо головний вхідний файл знаходиться в корені). [Тут](/tex/{{lang.url-fragment}}net/aspose-tex-input/) наведено деталі про концепцію каталогу введення в **Aspose.TeX для .NET** і надані реалізації.

Інші варіанти завдань TeX обговорюються [тут](/tex/{{lang.url-fragment}}net/other-options/).

**Ви також можете ознайомитися з безкоштовною [веб-програмою] для перетворення LaTeX у PNG (26), створеною на основі [Aspose.TeX для .NET API](https://products.aspose.com/tex/net/).**

Нижче ми обговорюємо перетворення LaTeX в інші підтримувані формати растрових зображень, не занурюючись у деталі, оскільки деталей насправді немає. Єдина відмінність полягає в типі властивості [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) у параметрах перетворення.

## Як конвертувати LaTeX у JPG

{{< gist "aspose-com-gists" "58d1c43acd187f1cde7917fa9a430281" "Example-ConvertLaTeXToJPEG.cs" >}}

**Ви також можете ознайомитися з безкоштовною [веб-програмою] для перетворення LaTeX на JPG (29), створеною на основі [Aspose.TeX для .NET API](https://products.aspose.com/tex/net/).**

## Як конвертувати LaTeX у TIFF

{{< gist "aspose-com-gists" "58d1c43acd187f1cde7917fa9a430281" "Example-ConvertLaTeXToTIFF.cs" >}}

**Ви також можете ознайомитися з безкоштовним [веб-програмою] для перетворення LaTeX у TIFF (31), створеним на основі [Aspose.TeX для .NET API](https://products.aspose.com/tex/net/).**

## Як конвертувати LaTeX у BMP

{{< gist "aspose-com-gists" "58d1c43acd187f1cde7917fa9a430281" "Example-ConvertLaTeXToBMP.cs" >}}

**Ви також можете ознайомитися з безкоштовною [веб-програмою] для перетворення LaTeX у BMP (33), створеною на основі [Aspose.TeX для .NET API](https://products.aspose.com/tex/net/).**

## Як конвертувати LaTeX у SVG

І ще одним підтримуваним цільовим форматом є [**SVG**](https://en.wikipedia.org/wiki/SVG). **Масштабована векторна графіка (SVG)** — це формат векторних зображень на основі XML для визначення двовимірної графіки з підтримкою інтерактивності та анімації.

Зображення **SVG** визначаються у форматі векторної графіки та зберігаються в текстових файлах XML. Таким чином зображення **SVG** можна масштабувати без втрати якості, а файли **SVG** можна шукати, індексувати, створювати сценарії та стискати. Текстові XML-файли можна створювати та редагувати за допомогою текстових редакторів або редакторів векторної графіки, і вони відображаються найбільш використовуваними веб-браузерами.

Існує бібліотека [**Aspose.SVG**](https://products.aspose.com/svg/), яка надає різні функції, пов’язані з **SVG**. Це включає створення, завантаження, редагування та конвертацію документів **SVG**.

Перетворення LaTeX у SVG також таке ж просте, як [перетворення у формати растрових зображень](/tex/{{lang.url-fragment}}net/latex-to-image/), за винятком того, що [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) ПОВИНЕН бути встановлений на екземпляр класу [SvgSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.svg/svgsaveoptions/), а пристрій ПОВИНЕН бути змінено на екземпляр класу [SvgDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.svg/svgdevice/).

{{< gist "aspose-com-gists" "58d1c43acd187f1cde7917fa9a430281" "Example-ConvertLaTeXToSVG-Simplest.cs" >}}

**Ви також можете ознайомитися з безкоштовною [веб-програмою] для перетворення LaTeX у SVG (41), створеною на основі [Aspose.TeX для .NET API](https://products.aspose.com/tex/net/).**