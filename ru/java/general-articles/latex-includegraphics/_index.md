---
translation: true
template: /templates/_template-java.md
linktitle: Включить графику
title: LaTeX включитьграфику | Aspose.TeX для Java
weight: 10
url: /java/latex-includegraphics/
keywords: includegraphics latex, latex includegraphic, вставка изображений latex, latexgraphicx, латехная вставка изображения, пакет includegraphics latex, draw io latex, латехная ширина includegraphics, ширина includegraphics, латех масштаба фигуры
description: Узнайте о макросе LaTeX includegraphics, а также о преобразованиях изображений, области просмотра, обрезке и о разнице между пакетами Graphics и GraphicsX.
lastmod: "2024-09-24"
---

{{<section overview>}}

## Введение

При работе над академическими и научными документами, такими как исследовательские работы, материалы конференций и академические презентации, иногда вам может понадобиться включать графические изображения.

С одной стороны, это могут быть рисунки, графики, гистограммы или что-то еще, что принято называть векторной графикой. Современные системы LaTeX (такие как «pdfTeX») предоставляют множество инструментов для создания такой графики в документе. Например, пакеты pict2e, PGF(TikZ) и PGFplots. В большинстве случаев сами рисунки генерируются движком TeX и включаются в выходной файл как последовательность инструкций векторной графики, подходящая для определенного выходного формата.

С другой стороны, у вас могут быть растровые изображения, которые вы также захотите включить в свою публикацию. Системы LaTeX в настоящее время также способны это делать, но вам необходимо указать путь к файлу изображения в файле LaTeX в качестве параметра некоторого макроса LaTeX.

В этой статье рассматривается включение растровых изображений в файлы LaTeX с помощью макроса `\includegraphics` из пакета `graphics` (и сопутствующего `graphicx`).

## Какой пакет выбрать: «graphics» или «graphicx»?

Оба пакета, Graphics и Graphicx, очень похожи. Основное отличие заключается в синтаксисе. В то время как пакет `graphics` использует набор отдельных макросов для применения преобразований к изображению, пакет `graphicx` использует нотацию `key=value` для параметров макроса `\includegraphics` для указания этих преобразований. Мы приведем примеры каждого варианта использования сразу для обоих пакетов, чтобы разница была более понятной.

## Включить выбранный пакет

Это делается с помощью команды `\usepackage` так же, как и для любого другого пакета LaTeX:


```tex
\usepackage{graphics} % to use the graphics package
\usepackage{graphicx} % to use the graphicx package
```

### Указание драйвера

Если ваша система набора текста не настроена на использование, скажем, «pdfTeX» по умолчанию, вам следует указать соответствующую опцию, которая заставит пакет использовать необходимый «драйвер»:


```tex
\usepackage[pdftex]{graphics} % graphics
\usepackage[pdftex]{graphicx} % graphicx
```

«Драйвер» — это часть пакета, которая реализует интерфейс между командами пакета и зависящими от формата низкоуровневыми примитивами расширения TeX. Поддержка графики LaTeX в **Aspose.TeX** настроена на использование собственного драйвера, поэтому вам не нужно указывать опцию драйвера.

## Макрос LaTeX `\includegraphics`

Теперь приступим к самому простому примеру. Это, конечно, случай включения изображения вообще без какого-либо преобразования. Ожидается, что код LaTeX, использующий оба пакета, один и тот же:


```tex
\includegraphics{sample-image.png}
```

В этом примере предполагается, что ваш файл изображения находится в том же каталоге, что и файл LaTeX. Но есть несколько способов указать другое местоположение. Код LaTeX снова будет одинаковым для обоих пакетов:


```tex
\includegraphics{d:/sample-image.png} % absolute path
\includegraphics{./sample-image.png} % relative to the current directory
\includegraphics{../img/sample-image.png} % relative to the directory containing the current one
```

Другой способ указать местоположение(я) графических файлов — определить список альтернативных путей с помощью команды `\graphicspath` перед вызовом `\includegraphics`:


```tex
\graphicspath{{d:/img}{c:/img}{d:/work/img}}
```

## Преобразования графики LaTeX

Пакеты LaTeX «graphics» и «graphicx» предоставляют несколько способов управления содержимым.

### Масштабная фигура LaTeX

Таким образом, вы можете масштабировать включенную графику (фактически все, что описано кодом TeX/LaTeX) следующим образом:


```tex
% graphics examples
\scalebox{.5}{\includegraphics{sample-image.png}} % scales both width and height by 0.5
\scalebox{.5}[1.5]{\includegraphics{sample-image.png}} % scales the width and height by 0.5 and 1.5 respectively

% graphicx examples
\includegraphics[scale=.5]{sample-image.png} % scales both width and height by 0.5
% there's no analogue for the graphicx package to scale both dimensions independently
```

### Изменение размера фигуры LaTeX

Это похоже на масштабирование, но вы указываете необходимый размер вместо коэффициента(ов) масштабирования:


```tex
% graphics examples
\resizebox{10mm}{!}{\includegraphics{sample-image.png}} % changes the width to 10mm preserving the proprtions
\resizebox{20mm}{10mm}{\includegraphics{sample-image.png}} % changes both width and height independently

% graphicx examples
\includegraphics[width=15mm]{sample-image.png} % changes the width to 15mm preserving the proprtions
\includegraphics[height=15mm,width=25mm]{sample-image.png} % changes both width and height independently
```

### Поворот фигуры LaTeX

```tex
% graphics example
\rotatebox{25}{\includegraphics{sample-image.png}} % rotates the image by 25 degrees counterclockwise

% graphicx example
\includegraphics[angle=-10]{sample-image.png} % rotates the image by 10 degrees clockwise
```

### Настройка области просмотра и обрезки

```tex
% This time there's no analogue for the graphics package

% graphicx example
\includegraphics[viewport=10 10 280 220]{sample-image.png} % sets the viewport with the lower left corner
                                                           % at the point (10, 10) (coinsides with (0, 0)
                                                           % of the box) and dimensions 280x220pt
\includegraphics[viewport=10 10 250 220,clip]{sample-image.png} % the same, but the image is clipped by the viewport
```

Что касается пакета «graphicx», то преобразования можно комбинировать, но порядок важен.
Чтобы узнать больше о функциях пакета `graphics`, посетите [страницу пакета на CTAN](https://ctan.org/pkg/graphics) и
[документация пакета](http://mirrors.ctan.org/macros/latex/required/graphics/graphics.pdf).

### Бесплатное веб-приложение LaTeX Include Graphics

Если вы не хотите программно работать с пакетом includegraphics latex, вы также можете воспользоваться бесплатным веб-приложением [LaTeX Include Graphics](https://products.aspose.app/tex/includegraphics/), созданным на основе [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/). 

Приложение позволяет выбирать несколько изображений и визуально настраивать для них трансформации. Он также генерирует исходный код LaTeX с использованием пакета «graphicx» и визуализирует его, отображая результат на странице.

### Функция рендеринга фигур LaTeX в библиотеке Aspose.TeX

Библиотека **Aspose.TeX** предоставляет возможность создавать растровые изображения и изображения SVG, которые вы можете использовать в своих публикациях вне контекста TeX/LaTeX. Например, на веб-странице. Это называется **Рендерингом фигур LaTeX**. Вкратце, эта часть API позволяет отображать фрагмент исходного кода LaTeX независимо от макета страницы. Для получения более подробной информации обратитесь к этой [статье](/tex/{{lang.url-fragment}}java/latex-figure-rendering/).

Статья о [включая внешние пакеты LaTeX](/tex/{{lang.url-fragment}}java/external-latex-packages/) также может дать вам представление о том, как создавать фигуры из графиков LaTeX.