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

Задайте `outputFile` как `java.nio.file.Path` в существующей папке: например, `Paths.get(outputDirectory, "math-formula.png")` для PNG или `Paths.get(outputDirectory, "math-formula.svg")` для SVG. Импортируйте используемые классы рендереров, параметров и `Size2D` из Aspose.TeX, а также `java.awt.Color`, `java.io.ByteArrayOutputStream`, `java.io.OutputStream`, `java.nio.file.Files`, `java.nio.file.Path`, `java.nio.file.Paths`. Вызывающий метод должен обрабатывать или объявлять исключения. Примените лицензию согласно [руководству по лицензированию](/tex/{{lang.url-fragment}}java/licensing/), чтобы избежать ограничений ознакомительной версии.

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderMathToPNG.java" >}}

Давайте перейдем к деталям. Прежде всего, мы создаем экземпляр [параметры рендеринга](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrendereroptions/), аналогичный набору текста TeX/LaTeX. Мы делаем это здесь, одновременно указывая разрешение выходного изображения.

Далее уточняем преамбулу. Преамбула по умолчанию:


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

который обеспечивает немного более продвинутую поддержку математических формул, чем базовый LaTeX. Например, вы можете добавить пакет `color`, если хотите использовать в формуле собственную подсветку, как мы показали в примере кода.

Затем мы указываем рендереру масштабировать результат на 300%.

Два параметра задают цвета переднего плана и фона. Части формулы без пользовательской подсветки отображаются цветом, заданным через `setTextColor()`.

Пример направляет журнал рендеринга в `ByteArrayOutputStream` с помощью `setLogStream()`. Потоки журнала и изображения автоматически закрываются после рендеринга.

`showTerminal()` управляет выводом терминала в консоль. В примерах задано `false`; установите `true`, чтобы показывать вывод.

[MathRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/mathrenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.MathRendererOptions-) вызывается на экземпляре `PngMathRenderer` или `SvgMathRenderer` и возвращает размеры формулы в пунктах в виде `Size2D`.

Метод принимает поток вывода изображения вторым аргументом. Пример открывает его в блоке try-with-resources, который закрывает поток после рендеринга.

Затем вызывается `render()` на экземпляре рендерера: первый аргумент — формула LaTeX, второй — поток вывода изображения, третий — параметры рендеринга.

В последних строках примера выводятся два артефакта отрисовки математической формулы — размер формулы и краткий отчет об ошибке (на случай, если были ошибки).

Вот результат рендеринга.

<a href="/tex/images/java/math-formula.png">![Рендеринг рисунков LaTeX в PNG](/tex/images/java/math-formula.png)</a>

Это наиболее общий вариант использования рендеринга **математической формулы LaTeX**.

**Вы также можете ознакомиться с бесплатным [веб-приложением](https://products.aspose.app/tex/equation-editor/png), созданным на основе функции, реализованной в API [Aspose.TeX for .NET](https://products.aspose.com/tex/net/). [Здесь](https://products.aspose.com/tex/java/) — страница версии Java.**

## Как преобразовать математическую формулу LaTeX в SVG

Практически таким же образом мы можем преобразовать математическую формулу LaTeX в формат SVG.

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderMathToSVG.java" >}}

Отличия заключаются в следующем:

* Мы используем класс [SvgMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/svgmathrendereroptions/) вместо [PngMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrendereroptions/).
* Мы не указываем разрешение.
* Мы используем класс [SvgMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/svgmathrenderer/) вместо [PngMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrenderer/).

Вот результат:

<a href="/tex/images/java/math-formula.svg">![Рендеринг математических формул LaTeX в SVG](/tex/images/java/math-formula.svg)</a>

**Вы также можете ознакомиться с бесплатным [веб-приложением](https://products.aspose.app/tex/equation-editor/svg), созданным на основе функции, реализованной в [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**