---
translation: true
template: /templates/_template-python-net.md
title: LaTeX Рендеринг фигур | Aspose.TeX для Python
linktitle: LaTeX включает рисунок
weight: 20
url: /python-net/latex-figure-rendering/
description: В статье представлен обзор API-решения Aspose.TeX для Python и его функционала по рендерингу фрагментов LaTeX (рисунки). Изучите примеры кода.
keywords: латехные фигурки, размеры фигурок из латеха, латехные картинки, латехные изображения, латехные фигурки, латехные картинки, варианты латехных фигурок
lastmod: "2024-09-24"
---

{{<section overview>}}

В определенных ситуациях вам может потребоваться извлечь определенное содержимое из файла LaTeX в виде отдельной визуализированной части, обычно называемой *фигурой*, без какой-либо связи с макетом страницы. Это может быть полезно, например, при создании иллюстраций для интернет-издания. Наш API позволяет вам это сделать. Целевыми форматами для рендеринга фигур являются PNG и SVG, как и в случае с функцией рендеринга математических формул LaTeX. Стоит отметить, что **рендеринг фигур LaTeX** является более общей функцией по сравнению с [рендерингом математических формул LaTeX](/tex/{{lang.url-fragment}}python-net/latex-math-formula-rendering/).

## Рендеринг фигуры LaTeX в PNG

При необходимости сначала просмотрите [справочный раздел API для этой темы](https://reference.aspose.com/tex/python-net/aspose.tex.features/). Как и в случае с рендерингом формул, мы начнем с примера. Вот:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.py" >}}

Для начала мы создаем экземпляр класса [Параметры рендеринга фигур LaTeX](https://reference.aspose.com/tex/python-net/aspose.tex.features/figurerendereroptions/), где одновременно указываем разрешение выходного изображения.

Далее нам нужно указать преамбулу. В отличие от рендеринга математических формул LaTeX, для рендеринга фигур LaTeX нет преамбулы по умолчанию. Поэтому, если вы планируете визуализировать графику, созданную, например, с помощью пакета LaTeX `pict2e`, вам нужно будет указать это в преамбуле:

```tex
\usepackage{pict2e}
```

Затем мы указываем рендереру масштабировать результат на 300%.

Следующая опция определяет цвет фона. В отличие от рендеринга математических формул, нам не нужно указывать цвет переднего плана, поскольку мы предполагаем, что цвета полностью контролируются кодом LaTeX. Аналогичным образом, цвет фона также контролируется кодом LaTeX, поэтому эта опция предусмотрена просто для удобства.

Следующая строка в примере может не иметь особого смысла. Он просто предназначен для демонстрации того, что у вас есть возможность направить вывод журнала в определенный поток.

Последняя опция, ShowTerminal, позволяет вам контролировать, должен ли вывод терминала отображаться в консоли.

Метод, отвечающий за рендеринг фигуры, — [FigureRenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/figurerenderer/render/#str-io.RawIOBase-aspose.tex.features.FigureRendererOptions). Возвращает размер фигуры в пунктах.

В качестве второго аргумента метод принимает поток, который является потоком, в который будет записано изображение. Мы создаем поток в следующей строке.

Наконец, мы вызываем сам метод «FigureRenderer.render()», передавая параметры в качестве третьего аргумента. Код LaTeX рисунка предоставляется в качестве первого аргумента.

Последние несколько строк примера отображают две части информации, связанные с рендерингом фигуры: размер фигуры и краткий отчет об ошибке (если есть какие-либо ошибки).

Вот результат рендеринга.

<a href="/tex/python-net/latex-figure-rendering/text-and-formula.png">![Рендеринг рисунков LaTeX в PNG](/tex/images/python-net/text-and-formula.png)</a>

Это наиболее общий вариант использования функции **рендеринга фигур LaTeX**.

## Рендеринг фигуры LaTeX в SVG

Точно так же мы можем визуализировать фигуру LaTeX в формате SVG.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.py" >}}

Отличия заключаются в следующем:

* Вместо использования класса [PngFigureRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerendereroptions/) мы используем класс [SvgFigureRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerendereroptions/).
* Нам не нужно указывать разрешение.
* Вместо использования класса [PngFigureRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerenderer/) мы используем класс [SvgFigureRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerenderer/).


Вот результат:

<a href="/tex/python-net/latex-figure-rendering/text-and-formula.svg">![Рендеринг рисунков LaTeX в SVG](/tex/images/python-net/text-and-formula.svg)</a>