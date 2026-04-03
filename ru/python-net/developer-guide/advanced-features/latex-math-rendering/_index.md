---
translation: true
template: /templates/_template-python-net.md
title: Рендеринг математических формул LaTeX | Python через .NET
linktitle: Отрисовка математических формул LaTeX
weight: 10
url: /python-net/latex-math-formula-rendering/
description: В статье представлен обзор API-Aspose.TeX для Python и его функциональных возможностей для рендеринга математических формул LaTeX. Изучите примеры кода.
lastmod: "2026-04-03"
---

{{<section overview>}}

## Преобразование математической формулы LaTeX в PNG

При необходимости ознакомьтесь с [разделом ссылок на API для этой темы](https://reference.aspose.com/tex/python-net/aspose.tex.features/). Фактически, лучший способ продемонстрировать функцию рендеринга **математической формулы LaTeX** — начать с примера. Вот:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Features-PngLaTeXMathRendering.py" >}}

Давайте перейдем к деталям. Во-первых, мы инициируем объект [параметры рендеринга](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrendereroptions/), аналогичный набору текста TeX/LaTeX, который включает в себя спецификацию желаемого разрешения выходного изображения.

Далее уточняем преамбулу. Преамбула по умолчанию:

```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

который предлагает расширенную поддержку математических формул по сравнению со стандартным LaTeX. Например, вы можете включить пакет «color», чтобы настроить выделение в формуле, как показано в приведенном примере кода.

Затем мы указываем рендереру масштабировать результат на 300%.

Следующие два параметра определяют цвета переднего плана и фона. Любые части формулы, на которые не влияет пользовательское выделение, будут отображаться цветом TextColor.

Следующая строка в примере служит иллюстрацией того, что у вас есть возможность перенаправить вывод журнала в определенный поток.

И, наконец, опция ShowTerminal позволяет вам контролировать, должен ли вывод терминала отображаться в консоли.

Сам процесс рендеринга осуществляется методом [MathRenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrenderer/render/), который возвращает размер формулы в пунктах.

В качестве второго аргумента метод принимает поток, в который будет записано изображение. Далее приступаем к созданию потока.

И, наконец, вызывается метод MathRenderer.render(), параметры которого передаются в качестве третьего аргумента. Код формулы LaTeX предоставляется в качестве первого аргумента.

В последних строках примера отображаются два результата процесса отрисовки математической формулы — размер формулы и краткий отчет об ошибках в случае возникновения каких-либо ошибок.

Вот результат рендеринга.

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.png">![Рендеринг математической формулы LaTeX в PNG](/tex/images/python-net/math-formula.png)</a>

Это наиболее распространенное и широкое применение функции **рендеринга математических формул LaTeX**.

**Вы также можете изучить бесплатное [веб-приложение](https://products.aspose.app/tex/equation-editor/png), в котором используется реализованная функция [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**

## Преобразование математической формулы LaTeX в SVG

Точно так же мы можем преобразовать математическую формулу LaTeX в формат SVG, используя тот же подход.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.py" >}}

Отличия заключаются в следующем:

* Вместо использования класса [PngMathRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrendereroptions/) мы используем класс [SvgMathRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrendereroptions/).
* Мы не указываем разрешение.
* Вместо использования класса [PngMathRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrenderer/) мы используем класс [SvgMathRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrenderer/).

 
Вот результат:

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.svg">![Рендеринг математических формул LaTeX в SVG](/tex/images/python-net/math-formula.svg)</a>

**Вы также можете изучить бесплатное [веб-приложение](https://products.aspose.app/tex/equation-editor/svg), в котором используется реализованная функция [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**