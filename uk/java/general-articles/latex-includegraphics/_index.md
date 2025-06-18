---
translation: true
template: /templates/_template-java.md
linktitle: Пакет Includegraphics
title: ЛаТеХ includegraphics | Aspose.TeX для Java
weight: 10
url: /java/latex-includegraphics/
keywords: includegraphics latex, latex includegraphic, вставити зображення latex, latex graphicx, латексне вставити зображення, includegraphics latex package, draw io latex, latex includegraphics width, includegraphics width, figure scale latex
description: Дізнайтеся про макрос LaTeX includegraphics, а також про перетворення зображень, вікно перегляду, відсікання та різницю між пакетами graphics і graphicx.
lastmod: "2025-06-13"
---

{{<section overview>}}

## вступ

Працюючи над академічними та науковими документами, такими як дослідницькі статті, матеріали конференцій і наукові презентації, ви можете інколи захотіти включити графічні зображення.

З одного боку, це можуть бути малюнки, графіки, гістограми або щось інше, що зазвичай називають векторною графікою. Сучасні системи LaTeX (такі як `pdfTeX`) надають багато інструментів для створення такої графіки в документі. Наприклад, пакети `pict2e`, `PGF(TikZ)` і `PGFplots`. У більшості випадків самі малюнки генеруються механізмом TeX і включаються у вихідний файл як послідовності інструкцій векторної графіки, що відповідають певному формату виводу.

З іншого боку, у вас можуть бути растрові зображення, які ви також захочете включити у свою публікацію. Системи LaTeX наразі також здатні робити це, але вам потрібно вказати шлях до вашого файлу зображення у вашому файлі LaTeX як параметр до якогось макросу LaTeX.

У цій статті розглядається включення растрових зображень у файли LaTeX за допомогою макросу `\includegraphics` з пакета `graphics` (і супровідного `graphicx`).

## Який пакет вибрати, `graphics` чи `graphicx`?

Обидва Пакети, `graphics` і `graphicx`, дуже схожі. Основна відмінність полягає в синтаксисі. У той час як пакет `graphics` використовує набір окремих макросів для застосування трансформацій до зображення, пакет `graphicx` використовує нотацію `key=value` для параметрів макросу `\includegraphics` для визначення цих перетворень. Ми наведемо приклади кожного випадку використання для обох пакунків одночасно, щоб зробити різницю більш зрозумілою.

## Включаючи обраний пакет

Це робиться за допомогою команди `\usepackage` так само, як і для будь-якого іншого пакета LaTeX:


```tex
\usepackage{graphics} % to use the graphics package
\usepackage{graphicx} % to use the graphicx package
```

### Вказівка ​​драйвера

Якщо ваша система верстки не налаштована на використання, скажімо, `pdfTeX` за замовчуванням, ви повинні вказати відповідний параметр, який змусить пакунок використовувати необхідний `драйвер`:


```tex
\usepackage[pdftex]{graphics} % graphics
\usepackage[pdftex]{graphicx} % graphicx
```

`Драйвер` - це частина пакету, яка реалізує інтерфейс між командами пакету та залежними від формату примітивами розширення TeX низького рівня. Підтримка графіки LaTeX **Aspose.TeX** налаштована на використання власного драйвера, тому вам не потрібно вказувати параметр драйвера.

## Макрос LaTeX `\includegraphics`

Тепер перейдемо до найпростішого прикладу. Це, звичайно, випадок включення зображення без будь-якої трансформації взагалі. Очікувано, код LaTeX, що використовує обидва Пакети, однаковий:


```tex
\includegraphics{sample-image.png}
```

У цьому прикладі передбачається, що ваш файл зображення знаходиться в тому самому каталозі, що й файл LaTeX. Але є кілька способів вказати інше місце. Код LaTeX знову буде однаковим для обох пакунків:


```tex
\includegraphics{d:/sample-image.png} % absolute path
\includegraphics{./sample-image.png} % relative to the current directory
\includegraphics{../img/sample-image.png} % relative to the directory containing the current one
```

Інший спосіб вказати розташування графічних файлів — це визначити список альтернативних шляхів за допомогою команди `\graphicspath` перед викликом `\includegraphics`:


```tex
\graphicspath{{d:/img}{c:/img}{d:/work/img}}
```

## Перетворення графіки LaTeX

Пакети LaTeX `graphics` і `graphicx` надають кілька способів маніпулювання вмістом.

### Масштаб фігури LaTeX

Таким чином, ви можете масштабувати включену графіку (фактично, все, що описано кодом TeX/LaTeX) наступним чином:


```tex
% graphics examples
\scalebox{.5}{\includegraphics{sample-image.png}} % scales both width and height by 0.5
\scalebox{.5}[1.5]{\includegraphics{sample-image.png}} % scales the width and height by 0.5 and 1.5 respectively

% graphicx examples
\includegraphics[scale=.5]{sample-image.png} % scales both width and height by 0.5
% there's no analogue for the graphicx package to scale both dimensions independently
```

### Змінити розмір фігури LaTeX

Це схоже на масштабування, але ви вказуєте необхідний розмір замість коефіцієнта масштабування:


```tex
% graphics examples
\resizebox{10mm}{!}{\includegraphics{sample-image.png}} % changes the width to 10mm preserving the proprtions
\resizebox{20mm}{10mm}{\includegraphics{sample-image.png}} % changes both width and height independently

% graphicx examples
\includegraphics[width=15mm]{sample-image.png} % changes the width to 15mm preserving the proprtions
\includegraphics[height=15mm,width=25mm]{sample-image.png} % changes both width and height independently
```

### Повернути фігуру LaTeX

```tex
% graphics example
\rotatebox{25}{\includegraphics{sample-image.png}} % rotates the image by 25 degrees counterclockwise

% graphicx example
\includegraphics[angle=-10]{sample-image.png} % rotates the image by 10 degrees clockwise
```

### Налаштування вікна перегляду та вирізання

```tex
% This time there's no analogue for the graphics package

% graphicx example
\includegraphics[viewport=10 10 280 220]{sample-image.png} % sets the viewport with the lower left corner
                                                           % at the point (10, 10) (coinsides with (0, 0)
                                                           % of the box) and dimensions 280x220pt
\includegraphics[viewport=10 10 250 220,clip]{sample-image.png} % the same, but the image is clipped by the viewport
```

Що стосується пакета `graphicx`, трансформації можна комбінувати, але порядок важливий.
Щоб дізнатися більше про функції пакета `graphics`, перегляньте [сторінку пакета на CTAN](https://ctan.org/pkg/graphics) і
[документація пакета](http://mirrors.ctan.org/macros/latex/required/graphics/graphics.pdf).

### Безкоштовна веб-програма LaTeX Include Graphics

Якщо ви не бажаєте працювати з латексним пакетом includegraphics програмним шляхом, ви також можете скористатися безкоштовною веб-програмою [LaTeX Include Graphics](https://products.aspose.app/tex/includegraphics/), створеною на основі [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/). 

Додаток дозволяє вибирати кілька зображень і візуально коригувати трансформації для них. Він також генерує вихідний код LaTeX за допомогою пакета `graphicx` і рендерить його, відображаючи результат на сторінці.

### Функція LaTeX Figure Rendering у бібліотеці Aspose.TeX

Бібліотека **Aspose.TeX** забезпечує спосіб створення растрових і SVG-фігур, які можна використовувати у своїх публікаціях поза контекстом TeX/LaTeX. Наприклад, на веб-сторінці. Це називається **LaTeX Figure Rendering**. Коротко кажучи, ця частина API дозволяє відтворювати фрагмент вихідного коду LaTeX незалежно від макета сторінки. Щоб дізнатися більше, зверніться до цієї [статті](/tex/{{lang.url-fragment}}java/latex-figure-rendering/).

Стаття про [включаючи зовнішні пакети LaTeX](/tex/{{lang.url-fragment}}java/external-latex-packages/) також може дати вам підказку про те, як створити фігури з графіків LaTeX.