---
translation: true
template: /templates/_template-java.md
title: LaTeX до XPS | Aspose.TeX для Java
linktitle: LaTeX до XPS
weight: 12
url: /java/latex-to-xps/
description: Функція перетворення рішення Aspose.TeX API для Java дозволяє конвертувати файли LaTeX у формат XPS. Вивчіть приклади коду.
lastmod: "2025-06-13"
---

{{<section overview>}}


Іншим цільовим форматом є [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). Файл **XPS** фізично є ZIP-пакетом, який містить розбитий на сторінки вміст документа, а також метадані, необхідні для належного відображення певними засобами перегляду (наприклад, Windows XPS Viewer) і друку. Усі дані в пакеті організовано як файли в каталогах. Деякі з них містять такі ресурси, як зображення, шрифти та профілі ICC. Інші — це XML-файли в різних конкретних схемах. До останніх відносяться файли, що містять самі дані документа. Дані документа — це набір файлів — кожен файл містить дані для окремої сторінки документа. Такі файли складаються з одного елемента сторінки та дерева дочірніх елементів - *Canvas*, *Path* і *Glyphs*. *Canvas* — це груповий елемент, який може містити інші *Canvases*, *Paths* і *Glyphs*. Його призначення — контролювати вигляд усіх дочірніх елементів як групи. Елементи *Path* використовуються для визначення шляхів векторної графіки. А елементи *Glyphs* використовуються для визначення текстового вмісту. Усі три елементи мають властивості для визначення різних аспектів зовнішнього вигляду.

Існує бібліотека [**Aspose.Page**](https://products.aspose.com/page/), яка надає API для роботи з документами XPS, а також для їх перетворення у формати PDF і растрових зображень.

## Як конвертувати LaTeX у XPS

Перетворення в XPS таке ж просте, як і [перетворення у формати растрових зображень](/tex/{{lang.url-fragment}}java/latex-to-image/), за винятком того, що на додаток до [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getSaveOptions--) ми маємо використовувати екземпляр класу [XpsDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/XpsDevice).

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-LaTeXToXps-Simplest.java" >}}

### Альтернативний спосіб запису основного вихідного файлу XPS

Є ще один конструктор класу [XpsDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/XpsDevice#XpsDevice-java.io.OutputStream-), який дозволяє нам отримати результуючий файл XPS альтернативним способом.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-LaTeXToXps-Alternative.java" >}}

Ефект такий самий, як ми отримуємо [тут](/tex/{{lang.url-fragment}}java/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file).

**Ви також можете ознайомитися з безкоштовною [веб-програмою] для перетворення LaTeX на XPS (8), створеною на основі API [Aspose.TeX для .NET](https://products.aspose.com/tex/net/). [Тут](https://products.aspose.com/tex/java/) – сторінка версії Java.**