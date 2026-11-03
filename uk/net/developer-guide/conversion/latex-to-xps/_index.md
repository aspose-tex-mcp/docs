---
translation: true
template: /templates/_template-net.md
title: LaTeX до XPS | .NET
linktitle: LaTeX до XPS
weight: 12
url: /net/latex-to-xps/
description: Функція перетворення рішення Aspose.TeX API для .NET дозволяє конвертувати файли LaTeX у формат XPS.
lastmod: "2026-11-02"
---

{{<section overview>}}


Іншим цільовим форматом є [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). Файл **XPS** фізично є ZIP-пакетом, який містить розбитий на сторінки вміст документа разом із метаданими, необхідними для належного відображення певними засобами перегляду (наприклад, Windows XPS Viewer) і друку. Усі дані в пакеті представлені файлами. Деякі з них є двійковими та містять такі ресурси, як зображення, шрифти та профілі ICC. Інші — це XML-файли в різних конкретних схемах. До останніх відносяться файли, що містять самі дані документа. Дані документа складаються з набору файлів - кожен файл містить дані для окремої сторінки документа. Такі файли складаються з одного елемента сторінки та дерева дочірніх елементів - *Canvas*, *Path* і *Glyphs*. *Canvas* — це груповий елемент, який може містити інші *Canvases*, *Paths* і *Glyphs*. Він служить для керування зовнішнім виглядом усіх дочірніх елементів як групи. Елементи *Path* використовуються для визначення шляхів векторної графіки. А елементи *Glyphs* використовуються для визначення текстового вмісту. Усі три елементи мають властивості визначати різні аспекти зовнішнього вигляду.

Існує бібліотека [**Aspose.Page**](https://products.aspose.com/page/), яка надає API для роботи з документами XPS, а також для їх перетворення у формати PDF і растрових зображень.

## Як конвертувати LaTeX у XPS

Перетворення LaTeX у XPS таке ж просте, як і [конвертація у формати растрових зображень](/tex/{{lang.url-fragment}}net/latex-to-image/), за винятком того, що для [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) ПОВИННО бути встановлено екземпляр класу [XpsSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpssaveoptions/) (за замовчуванням або явно) , і пристрій ПОВИНЕН бути змінений на екземпляр класу [XpsDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/).

**Приклад найпростішої конвертації перетворення**

Наведений нижче приклад показує, як конвертувати файл LaTeX у XPS за кілька кроків:
1. Створіть `TeXOptions` для формату ObjectLaTeX за допомогою `TeXOptions.ConsoleAppOptions(TeXConfig.ObjectLaTeX)`.
2. Вкажіть вихідний робочий каталог, наприклад `OutputFileSystemDirectory`.
3. Присвойте `SaveOptions` екземпляр `XpsSaveOptions`.
4. Запустіть `TeXJob` для вихідного файлу `.tex` з `XpsDevice`. Файл XPS записується у вихідний робочий каталог.

Цей код демонструє найпряміший спосіб створення файлу XPS з LaTeX.

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToXPS-Simplest.cs" >}}

### Альтернативний спосіб запису основного вихідного файлу XPS

Є ще один конструктор класу [XpsDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/xpsdevice/), який дозволяє нам отримати кінцевий файл XPS альтернативним способом.

**Приклад альтернативної конвертації**

Цей фрагмент демонструє використання конструктора `XpsDevice`, який приймає `Stream`. Кроки такі:
1. Відкрийте потік, у який буде записано документ XPS (тут — файловий потік; `MemoryStream` працює так само).
2. Створіть `TeXOptions`, вкажіть вихідний робочий каталог і присвойте `SaveOptions` екземпляр `XpsSaveOptions`, як у попередньому прикладі.
3. Запустіть `TeXJob` з `XpsDevice`, створеним із цим потоком. Документ XPS записується в потік; інші вихідні файли, наприклад протокол, і далі записуються у вихідний робочий каталог.

Цей підхід корисний, коли документ XPS потрібно записати у вибраний вами потік, наприклад щоб зберігати його в пам'яті або надіслати мережею.

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToXPS-Alternative.cs" >}}

Ефект такий самий, як ми отримуємо [тут](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-the-main-output-pdf-file).

**Ви також можете ознайомитися з безкоштовною [веб-програмою](https://products.aspose.app/tex/conversion/latex-to-xps) для перетворення LaTeX на XPS, створеною на основі [Aspose.TeX для .NET API](https://products.aspose.com/tex/net/).**