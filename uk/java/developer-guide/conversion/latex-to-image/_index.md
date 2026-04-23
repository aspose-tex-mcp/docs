---
translation: true
template: /templates/_template-java.md
title: LaTeX до зображення | Java
linktitle: LaTeX до зображення
weight: 10
url: /java/latex-to-image/
keywords: латекс у png, латекс png, латекс у зображення, латексне зображення, латекс у jpg, латекс у jpg, латекс у jpeg, латекс у jpeg, латекс у tiff, латекс у tiff, латекс у bmp, латекс bmp
description: Щоб перетворити TeX у формати зображень за допомогою Aspose.TeX API для Java, ознайомтеся з цією статтею, яка описує, як це зробити, і прикладами коду.
lastmod: "2026-04-21"
---

{{<section overview>}}

**Aspose.TeX for Java** provides features for converting LaTeX files to a number of raster image formats.

## Як конвертувати LaTeX у PNG

Давайте ближче розглянемо код Java, що забезпечує найпростіший спосіб перетворення LaTeX у формат PNG.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-LaTeXToPng-Simplest.java" >}}

Отже, перше, що нам потрібно зробити (іноді не перше, як ми дізнаємося пізніше), це створити екземпляр класу [TeXOptions](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions). Єдиним статичним методом, який це робить, є [consoleAppOptions()](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#consoleAppOptions-com.aspose.tex.TeXConfig-), тому не будемо турбуватися про значення його назви. Метод використовує [примірник objectLaTeX()](https://reference.aspose.com/tex/java/com.aspose.tex/TeXConfig#objectLaTeX--) класу [TeXConfig](https://reference.aspose.com/tex/java/com.aspose.tex/TeXConfig), який точно підходить для перетворення [файлу LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Ця конфігурація вказує механізму Object TeX завантажити формат Object LaTeX і бути готовим прийняти файл LaTeX. Формат Object LaTeX насправді є лише форматом [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), за винятком того, що він використовує специфічні примітиви [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) для налаштування показників сторінки.

Першим із необхідних параметрів є [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--), який визначає простір або область, куди буде записаний вихід TeX. [Тут](/tex/{{lang.url-fragment}}java/aspose-tex-output/) наведено деталі про концепцію вихідного каталогу в **Aspose.TeX для Java**. У цьому прикладі ми використовуємо клас [OutputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/OutputFileSystemDirectory), який дозволяє записувати вихідні дані у вказаний каталог або папку.

Другий варіант — екземпляр класу [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/SaveOptions), який керуватиме перетворенням [об’єктної моделі](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) у цільовий формат. Оскільки ми перетворюємо LaTeX у PNG, це екземпляр класу [PngSaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PngSaveOptions), який дозволяє нам вказати роздільну здатність вихідних зображень.

Далі нам потрібно створити екземпляр класу [TeXJob](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob). Бажаючи перетворити файл LaTeX, що зберігається у файловій системі, ми використовуємо [this](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob#TeXJob-java.lang.String-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-) версію конструктора. Потрібно вказати повний шлях до файлу. В іншому випадку механізм шукатиме його в поточному каталозі (який визначено [тут](https://docs.oracle.com/javase/7/docs/api/java/io/File.html)) і, швидше за все, не знайде. Тим не менш, ми можемо опустити розширення, якщо наш файл має *.tex*. Механізм додасть його автоматично. Другим аргументом конструктора є екземпляр класу [Device](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/Device). Оскільки ми перетворюємо LaTeX у PNG, це екземпляр класу [ImageDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/ImageDevice) (який є спільним для всіх підтримуваних форматів зображень). В якості останнього аргументу ми передаємо нещодавно підготовлені параметри конвертації.

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
Output written on hello-world.png (1 page).
Transcript written on hello-world.log.
```

Ми знайдемо інші продукти роботи двигуна в папці, яку ми вказали як каталог виведення. Це буде файл стенограми (.log) і, **Вуаля!**, основний вихідний(і) файл(и) зображень PNG.

## Альтернативний спосіб запису основних вихідних файлів PNG

Існує інший спосіб отримати дані зображення у вигляді масиву байтів, кожен масив у другому вимірі представляє дані зображення для окремої сторінки.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-LaTeXToPng-Alternative.java" >}}

Файл(и) *"page-n.png"* буде записаний у будь-який шлях, який ми вкажемо. На відміну від [PDF output](/tex/{{lang.url-fragment}}java/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file), вони дублюватимуть вихідні файли PNG, записані у вихідний каталог.

## Про параметри введення

Якщо наш головний вхідний файл потребує залежностей, наприклад, пакетів, які не входять до базової системи LaTeX і підтримуваних пакетів, ми ПОВИННІ встановити опцію [RequiredInputDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getRequiredInputDirectory--) так само, як ми встановлюємо [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--) і помістіть залежності в цей каталог. Залежності можуть бути довільно організовані в підкаталоги. Якщо у нас є власні файли для включення в процес верстки, скажімо, зовнішні графічні файли, ми ПОВИННІ також встановити [InputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getInputWorkingDirectory--), використовуючи шлях до розташування, де ці файли зібрано. Ми також можемо розмістити головний вхідний файл десь усередині вхідного каталогу та вказати відносний шлях у методі `run()` (або взагалі не вказати шлях, якщо головний вхідний файл знаходиться в корені). [Тут](/tex/{{lang.url-fragment}}java/aspose-tex-input/) наведено деталі про концепцію каталогу вводу в **Aspose.TeX для Java** та надані реалізації.

Інші варіанти завдань TeX обговорюються [тут](/tex/{{lang.url-fragment}}java/other-options/).

**Ви також можете ознайомитися з безкоштовною [веб-програмою](https://products.aspose.app/tex/conversion/latex-to-png) для перетворення LaTeX у PNG, створеною на основі API [Aspose.TeX для .NET](https://products.aspose.com/tex/net/). [Тут](https://products.aspose.com/tex/java/) – сторінка версії Java.**

Нижче ми обговорюємо перетворення LaTeX в інші підтримувані формати растрових зображень. Ми не будемо вдаватися в подробиці лише тому, що їх насправді немає. Єдина відмінність полягає в типі властивості [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getSaveOptions--) у параметрах перетворення.

## Як конвертувати LaTeX у JPG

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToJpeg.cs" >}}

**Ви також можете ознайомитися з безкоштовною [веб-програмою](https://products.aspose.app/tex/conversion/latex-to-jpg) для перетворення LaTeX у JPG, створеною на основі API [Aspose.TeX для .NET](https://products.aspose.com/tex/net/). [Тут](https://products.aspose.com/tex/java/) – сторінка версії Java.**

## Як конвертувати LaTeX у TIFF

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToTiff.cs" >}}

**Ви також можете скористатися безкоштовною [веб-програмою](https://products.aspose.app/tex/conversion/latex-to-tiff) для перетворення LaTeX у TIFF, створеною на основі API [Aspose.TeX для .NET](https://products.aspose.com/tex/net/). [Тут](https://products.aspose.com/tex/java/) – сторінка версії Java.**

## Як конвертувати LaTeX у BMP

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToBmp.cs" >}}

**Ви також можете ознайомитися з безкоштовною [веб-програмою](https://products.aspose.app/tex/conversion/latex-to-bmp) для перетворення LaTeX у BMP, створеною на основі API [Aspose.TeX для .NET](https://products.aspose.com/tex/net/). [Тут](https://products.aspose.com/tex/java/) – сторінка версії Java.**


## Як конвертувати LaTeX у SVG

І ще одним підтримуваним цільовим форматом є [**SVG**](https://en.wikipedia.org/wiki/SVG). **Масштабована векторна графіка (SVG)** — це формат векторних зображень на основі XML для визначення двовимірної графіки з підтримкою інтерактивності та анімації.

Зображення **SVG** визначаються у форматі векторної графіки та зберігаються в текстових файлах XML. Це означає, що зображення **SVG** можна масштабувати без втрати якості, а файли **SVG** можна шукати, індексувати, створювати сценарії та стискати. Текстові файли XML можна створювати та редагувати за допомогою текстових редакторів або редакторів векторної графіки. Вони відображаються веб-браузерами, які найчастіше використовуються.

Крім того, існує бібліотека [**Aspose.SVG**](https://products.aspose.com/svg/), яка має різні функції на основі формату **SVG**. Це включає створення, завантаження, редагування та конвертацію документів **SVG**.

Перетворення у SVG таке ж просте, як і [перетворення у формати растрових зображень](/tex/{{lang.url-fragment}}java/latex-to-image/), за винятком того, що на додаток до [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getSaveOptions--), ми маємо змінити пристрій на екземпляр [SvgDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/SvgDevice). ) клас.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-LaTeXToSvg-Simplest.java" >}}

**Ви також можете перевірити безкоштовну [веб-програму](https://products.aspose.app/tex/conversion/latex-to-svg) для перетворення LaTeX у SVG, створену на основі [Aspose.TeX для .NET ](https://products.aspose.com/tex/net/). [Тут](https://products.aspose.com/tex/java/) – сторінка версії Java.**