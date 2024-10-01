---
translation: true
template: /templates/_template-java.md
title: Графика LaTeX | команда \includegraphics
linktitle: Графика LaTeX 
weight: 18
url: /net/latex-graphics/
description: Стоит упомянуть включение графики в TeX. Говоря об этом, первое, что приходит на ум, — это команда `\includegraphics`.
lastmod: "2024-09-24"
---

{{<section overview>}}

На самом деле стоит упомянуть два аспекта графики LaTeX:

 * векторная графика, описываемая непосредственно с помощью команд LaTeX/TeX и,
 * включение внешней графики, описанной посредством внешних форматов, таких как EPS, PDF или растровые PNG и PDF.


Первый имеет ограниченную поддержку в исходном LaTeX и его пакетах. Это реализовано с помощью вертикальных и горизонтальных правил TeX. Это связано с тем, что исходный LaTeX основан на исходном движке TeX, который выдает основной вывод в формате *DVI*, который не подходит для описания линий и кривых или данных двоичного растрового изображения. Но механизмы, которые могут выводить в форматы, поддерживающие графику (например, pdfTeX в PDF), также могут работать с графикой, используя зависящие от формата пакеты или функции пакета. Последняя графика не поддерживается в базовом LaTeX по той же причине. Ниже мы обсудим возможности включения графики.

## Пакет LaTeX Graphics и команда \includegraphics.

Когда речь идет о включении графики LaTeX, первое, что приходит на ум, — это команда `\includegraphics`. Он определен в пакете «graphics», который следует упомянуть в преамбуле, чтобы включить его функции.
```tex
\usepackage{graphics}
```

Если ваша система набора текста не настроена на использование, скажем, pdfTeX по умолчанию, вам следует указать соответствующую опцию, которая заставит пакет использовать необходимый файл `драйвера`:


```tex
\usepackage[pdftex]{graphics}
```
Файл «драйвера» является частью пакета, который реализует интерфейс между командами пакета и зависящими от формата примитивами расширения TeX низкого уровня. Поддержка графики LaTeX в Aspose.TeX настроена на использование собственного драйвера, поэтому вам не нужно указывать опцию драйвера.

Теперь самый простой способ включить, скажем, изображение PNG — это набрать:


```tex
\includegraphics{sample-image.png}
```
где `sample-image.png` — это имя файла, который вы хотите включить. Вы можете даже опустить расширение. Пакет `graphics` содержит список определений поддерживаемых форматов. При поиске файла он проходит по этому списку и включает первый найденный соответствующий файл.

Вы также можете указать полное имя файла, используя абсолютный или относительный путь:


```tex
\includegraphics{d:/sample-image.png} % absolute path
\includegraphics{./sample-image.png} % relative to the current directory
\includegraphics{../img/sample-image.png} % relative to the directory containing the current one
```

Другой способ указать местоположение(я) графических файлов — определить список альтернативных путей с помощью команды `\graphicspath` перед вызовом `\includegraphics`:


```tex
\graphicspath{{d:/img}{c:/img}{d:/work/img}}
```

### Масштабирование графики

Пакет LaTeX Graphics предоставляет команды для управления содержимым. Таким образом, вы можете масштабировать включенную графику (фактически все, что описано кодом TeX/LaTeX) следующим образом:


```tex
\scalebox{.5}{\includegraphics{sample-image.png}} % scales both width and height by 0.5
\scalebox{.5}[1.5]{\includegraphics{sample-image.png}} % scales the width and height by 0.5 and 1.5 respectively
```

### Изменение размера графики

Это похоже на масштабирование, но вы указываете необходимый размер вместо коэффициента(ов) масштабирования:


```tex
\resizebox{10mm}{!}{\includegraphics{sample-image.png}} % changes the width to 10mm preserving the proprtions
\resizebox{20mm}{10mm}{\includegraphics{sample-image.png}} % changes both width and height independently
```

### Вращение графики

```tex
\rotatebox{25}{\includegraphics{sample-image.png}} % rotates the image by 25 degrees counterclockwise
```

## Пакет LaTeX «graphicx»

Пакет LaTeXgraphicx предоставляет интерфейс «ключ=значение» для преобразования контента. Чтобы включить его возможности, необходимо упомянуть об этом в преамбуле:


```tex
\usepackage{graphicx}
\usepackage[pdftex]{graphicx} % with the driver option
```

Вы можете комбинировать любые из следующих вариантов, но имейте в виду, что порядок важен.

### Графическое окно просмотра
```tex
\includegraphics[viewport=10 10 280 220]{sample-image.png} % sets the viewport with the lower left corner
                                                           % at the point (10, 10) (coinsides with (0, 0)
                                                           % of the box) and dimensions 280x220pt
\includegraphics[viewport=10 10 250 220,clip]{sample-image.png} % the same, but the image is clipped by the viewport
```

### Масштабирование графики

```tex
\includegraphics[scale=.5]{sample-image.png} % scales both width and height by 0.5
```

### Изменение размера графики

```tex
\includegraphics[width=15mm]{sample-image.png} % changes the width to 15mm preserving the proprtions
\includegraphics[height=15mm,width=25mm]{sample-image.png} % changes both width and height independently
```

### Вращающаяся графика

```tex
\includegraphics[angle=10]{sample-image.png} % rotates the image by 10 degrees counterclockwise
```

Чтобы узнать больше о функциях пакета `graphics`, см. документацию [здесь](https://ctan.org/pkg/graphics) и
[здесь](http://mirrors.ctan.org/macros/latex/required/graphics/graphics.pdf).

**Вы также можете ознакомиться с бесплатным преобразованием [веб-приложения](https://products.aspose.app/tex/conversion/latex/), созданным на основе [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**