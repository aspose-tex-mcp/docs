---
translation: true
template: /templates/_template-python-net.md
title: LaTeX до XPS | Python через .NET
linktitle: LaTeX до XPS
weight: 12
url: /python-net/latex-to-xps/
description: Рішення Aspose.TeX API для Python забезпечує функцію перетворення для перетворення файлів LaTeX у формат XPS.
lastmod: "2025-06-13"
---

{{<section overview>}}

Іншим цільовим форматом є [**XPS**](https://docs.aspose.com/page/net/what-is-xps-file/). Файл [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification) — це, по суті, пакет ZIP, який містить розбитий на сторінки вміст документа, а також необхідні метадані для належного відображення певними засобами перегляду (наприклад, Windows XPS Viewer) і друку. Пакет складається з різних файлів, деякі з яких двійкові та містять такі ресурси, як зображення, шрифти та профілі ICC. Інші — це файли XML у певних схемах, включаючи файли, які містять самі дані документа. Дані документа поділено на кілька файлів, кожен з яких представляє окрему сторінку документа. Ці файли складаються з одного елемента сторінки та дерева дочірніх елементів, включаючи *Canvas*, *Path* і *Glyphs*. Елемент *Canvas* — це груповий елемент, який може містити інші *Canvases*, *Paths* і *Glyphs*, і він контролює вигляд усіх дочірніх елементів як групи. Елементи *Path* використовуються для визначення контурів векторної графіки, тоді як елементи *Glyphs* використовуються для визначення текстового вмісту. Всі три елементи мають властивості, які визначають різні аспекти зовнішнього вигляду.

Існує бібліотека [**Aspose.Page**](https://products.aspose.com/page/), яка пропонує API для роботи з документами XPS, а також дозволяє конвертувати ці документи у формати PDF і растрових зображень.

## Перетворення LaTeX на XPS

Процес перетворення LaTeX на XPS настільки ж простий, подібний до [перетворення у формати растрових зображень](/tex/{{lang.url-fragment}}python-net/latex-to-image/). Однак для цього потрібно встановити [save_options](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/save_options/) на екземпляр класу [XpsSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.xps/xpssaveoptions/) (за замовчуванням або явно) і змінити пристрій на екземпляр класу [XpsDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.xps/xpsdevice/).

Укажіть шлях до файлу LaTeX у `ASPOSE_TEX_INPUT_FILE`, а вихідний каталог — у `ASPOSE_TEX_OUTPUT_DIR`, або змініть шляхи в прикладі. Типові значення — `hello-world.ltx` і `output`. Спочатку застосуйте ліцензію. Додаткові вхідні файли шукаються поруч з основним документом; обробка виконується без інтерактивного введення. [Ліцензування](/tex/uk/python-net/licensing/)

{{< gist "aspose-com-gists" "3616f5e300517031e6a4ae4158e24776" "Aspose.TeX.Examples-Conversion-LaTeXToXps-Simplest.py" >}}

### Альтернативний спосіб запису основного вихідного файлу XPS

Для класу *XpsDevice* доступний альтернативний конструктор, який дозволяє отримати кінцевий файл XPS іншим способом.

{{< gist "aspose-com-gists" "3616f5e300517031e6a4ae4158e24776" "Aspose.TeX.Examples-Conversion-LaTeXToXps-Alternative.py" >}}

Двійковий потік записує `any-name.xps` у налаштований вихідний каталог. Додатковий файл XPS із типовим ім’ям не створюється; допоміжні файли та журнал і надалі зберігаються в `output_working_directory`.

**Ви також можете дослідити безкоштовну [веб-програму для перетворення LaTeX у XPS](https://products.aspose.app/tex/conversion/latex-to-xps), яка розроблена за допомогою [Aspose.TeX для .NET API](https://products.aspose.com/tex/net/).**