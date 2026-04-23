---
translation: true
template: /templates/_template-java.md
title: Рендеринг математических формул LaTeX | Java
linktitle: Отрисовка математических формул LaTeX
weight: 10
url: /java/latex-math-formula-rendering/
description: В статье описан рендеринг формул LaTeX с помощью API Aspose.TeX для Java. Изучите примеры кода, показывающие, как использовать эту функциональность.
lastmod: "2026-04-21"
---

{{<section overview>}}

## Как преобразовать математическую формулу LaTeX в PNG

Фактически, самый простой способ продемонстрировать функцию рендеринга **математической формулы LaTeX** — начать с примера. Вот:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-PngLaTeXMathRendering.java" >}}

Давайте перейдем к деталям. Прежде всего, мы создаем экземпляр [параметры рендеринга](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRendererOptions), аналогичный набору текста TeX/LaTeX. Мы делаем это здесь, одновременно указывая разрешение выходного изображения.

Далее уточняем преамбулу. Преамбула по умолчанию:


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

который обеспечивает немного более продвинутую поддержку математических формул, чем базовый LaTeX. Например, вы можете добавить пакет `color`, если хотите использовать в формуле собственную подсветку, как мы показали в примере кода.

Затем мы указываем рендереру масштабировать результат на 300%.

Следующие два параметра определяют цвета переднего плана и фона. Те части формулы, которые не покрыты («окрашены») пользовательской подсветкой, будут отображаться цветом TextColor.

Следующая строка примера не имеет особого смысла. Это просто демонстрирует, что вы можете направить вывод журнала в какой-то поток.

И последняя опция `ShowTerminal` позволяет вам переключать запись вывода терминала на консоль.

Метод, который фактически выполняет рендеринг, — это [MathRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/mathrenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.MathRendererOptions-). Возвращает размер формулы в пунктах.

Поток, в который должно быть записано изображение, принимается методом в качестве второго аргумента. Далее мы создаем поток.

И, наконец, мы вызываем сам метод MathRenderer.render(), передавая параметры в качестве третьего аргумента. Код LaTeX формулы передается в качестве первого аргумента.

В последних строках примера выводятся два артефакта отрисовки математической формулы — размер формулы и краткий отчет об ошибке (на случай, если были ошибки).

Вот результат рендеринга.

<a href="/tex/images/java/math-formula.png">![Рендеринг рисунков LaTeX в PNG](/tex/images/java/math-formula.png)</a>

Это наиболее общий вариант использования рендеринга **математической формулы LaTeX**.

**Вы также можете ознакомиться с бесплатным [веб-приложением](https://products.aspose.app/tex/equation-editor/png), созданным на основе функции, реализованной в API [Aspose.TeX for .NET](https://products.aspose.com/tex/net/). [Здесь](https://products.aspose.com/tex/java/) — страница версии Java.**

## Как преобразовать математическую формулу LaTeX в SVG

Практически таким же образом мы можем преобразовать математическую формулу LaTeX в формат SVG.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.java" >}}

Отличия заключаются в следующем:

* Мы используем класс [SvgMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/SvgMathRendererOptions) вместо [PngMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRendererOptions).
* Мы не указываем разрешение.
* Мы используем класс [SvgMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/SvgMathRenderer) вместо [PngMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRenderer).

Вот результат:

<a href="/tex/images/java/math-formula.svg">![Рендеринг математических формул LaTeX в SVG](/tex/images/java/math-formula.svg)</a>

**Вы также можете ознакомиться с бесплатным [веб-приложением](https://products.aspose.app/tex/equation-editor/svg), созданным на основе функции, реализованной в [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**