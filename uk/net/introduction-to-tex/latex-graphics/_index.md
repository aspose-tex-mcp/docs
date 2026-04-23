---
translation: true
template: /templates/_template-net.md
title: Графіка LaTeX | \includegraphics команда
linktitle: Графіка LaTeX
weight: 18
url: /net/latex-graphics/
description: Про включення графіки в TeX варто згадати. Коли мова йде про це, перше, що спадає на думку, це команда `\includegraphics`.
lastmod: "2026-04-22"
---

{{<section overview>}}

Насправді є два аспекти графіки LaTeX, про які варто згадати:

 * векторна графіка, описана безпосередньо за допомогою команд LaTeX/TeX і,
 * включення зовнішньої графіки, описаної за допомогою зовнішніх форматів, наприклад EPS, PDF або растрових PNG і PDF.



Перший має обмежену підтримку в оригінальному LaTeX та його пакетах. Це реалізовано за допомогою вертикальних і горизонтальних правил TeX. Це тому, що оригінальний LaTeX базується на оригінальному движку TeX, який створює основний вихід у форматі *DVI*, який не підходить для опису ліній і кривих або даних бінарного растрового зображення. Але двигуни, які можуть виводити у формати, що підтримують графіку (наприклад, pdfTeX у PDF), також можуть працювати з графікою за допомогою залежних від формату пакетів або функцій пакетів. Остання графіка не підтримується в базовому LaTeX з тієї ж причини. Ми обговоримо функції включення графіки нижче.

## Пакет LaTeX `graphics` і команда `\includegraphics`

Коли мова йде про включення графіки LaTeX, перше, що спадає на думку, це команда `\includegraphics`. Він визначений у пакеті `graphics`, який слід згадати у преамбулі, щоб увімкнути його функції.
```tex
\usepackage{graphics}
```

Якщо ваша система верстки не налаштована на використання, скажімо, pdfTeX за замовчуванням, ви повинні вказати відповідний параметр, який змусить пакет використовувати необхідний файл `driver`:


```tex
\usepackage[pdftex]{graphics}
```
Файл `драйвера` є частиною пакета, який реалізує інтерфейс між командами пакета та залежними від формату примітивами розширення TeX низького рівня. Підтримка графіки LaTeX Aspose.TeX налаштована на використання власного драйвера, тому вам не потрібно вказувати параметр драйвера.

Тепер найпростіший спосіб включити, скажімо, зображення у форматі PNG, це ввести:


```tex
\includegraphics{sample-image.png}
```
де `sample-image.png` — це ім'я файлу, який ви хочете включити. Ви навіть можете пропустити розширення. Пакет `graphics` містить список визначень підтримуваних форматів. Під час пошуку файлу він проходить цей список і включає перший знайдений відповідний файл.

Ви також можете вказати повне ім’я файлу за допомогою абсолютного або відносного шляху:


```tex
\includegraphics{d:/sample-image.png} % absolute path
\includegraphics{./sample-image.png} % relative to the current directory
\includegraphics{../img/sample-image.png} % relative to the directory containing the current one
```

Інший спосіб вказати розташування графічних файлів — це визначити список альтернативних шляхів за допомогою команди `\graphicspath` перед викликом `\includegraphics`:


```tex
\graphicspath{{d:/img}{c:/img}{d:/work/img}}
```

### Масштабування графіки

Пакет LaTeX `graphics` надає команди для керування вмістом. Таким чином, ви можете масштабувати включену графіку (фактично, все, що описано кодом TeX/LaTeX) наступним чином:


```tex
\scalebox{.5}{\includegraphics{sample-image.png}} % scales both width and height by 0.5
\scalebox{.5}[1.5]{\includegraphics{sample-image.png}} % scales the width and height by 0.5 and 1.5 respectively
```

### Зміна розміру графіки

Це схоже на масштабування, але ви вказуєте необхідний розмір замість коефіцієнта масштабування:


```tex
\resizebox{10mm}{!}{\includegraphics{sample-image.png}} % changes the width to 10mm preserving the proprtions
\resizebox{20mm}{10mm}{\includegraphics{sample-image.png}} % changes both width and height independently
```

### Обертання графіки

```tex
\rotatebox{25}{\includegraphics{sample-image.png}} % rotates the image by 25 degrees counterclockwise
```

## Пакет LaTeX `graphicx`

Пакет LaTeX `graphicx` забезпечує інтерфейс `key=value` для перетворень вмісту. Щоб увімкнути його функції, вам слід згадати про це у преамбулі:


```tex
\usepackage{graphicx}
\usepackage[pdftex]{graphicx} % with the driver option
```

Ви можете комбінувати будь-який із наведених нижче варіантів, але майте на увазі, що порядок важливий.

### Вікно перегляду графіки

```tex
\includegraphics[viewport=10 10 280 220]{sample-image.png} % sets the viewport with the lower left corner
                                                           % at the point (10, 10) (coinsides with (0, 0)
                                                           % of the box) and dimensions 280x220pt
\includegraphics[viewport=10 10 250 220,clip]{sample-image.png} % the same, but the image is clipped by the viewport
```

### Масштабування графіки

```tex
\includegraphics[scale=.5]{sample-image.png} % scales both width and height by 0.5
```

### Зміна розміру графіки

```tex
\includegraphics[width=15mm]{sample-image.png} % changes the width to 15mm preserving the proprtions
\includegraphics[height=15mm,width=25mm]{sample-image.png} % changes both width and height independently
```

### Графіка, що обертається

```tex
\includegraphics[angle=10]{sample-image.png} % rotates the image by 10 degrees counterclockwise
```

Щоб дізнатися більше про функції пакета `graphics`, перегляньте документацію [тут](https://ctan.org/pkg/graphics) і
[тут](http://mirrors.ctan.org/macros/latex/required/graphics/graphics.pdf).

**Ви також можете ознайомитися з безкоштовним [веб-додатком](https://products.aspose.app/tex/conversion/latex/) перетворення, створеним на основі [Aspose.TeX для .NET API](https://products.aspose.com/tex/net/).**