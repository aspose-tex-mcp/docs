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

Укажите выходной каталог в `ASPOSE_TEX_OUTPUT_DIR` либо используйте папку `output` по умолчанию. Весь код LaTeX включён в примеры; внешние входные файлы не требуются. Предварительно примените лицензию. [Лицензирование](/tex/ru/python-net/licensing/).

{{< gist "aspose-com-gists" "cbf380b84d7f2067481756d42da32b08" "Aspose.TeX.Examples-Features-PngLaTeXMathRendering.py" >}}

Давайте перейдем к деталям. Во-первых, мы инициируем объект [параметры рендеринга](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrendereroptions/), аналогичный набору текста TeX/LaTeX, который включает в себя спецификацию желаемого разрешения выходного изображения.

Далее уточняем преамбулу. Преамбула по умолчанию:

```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

который предлагает расширенную поддержку математических формул по сравнению со стандартным LaTeX. Например, вы можете включить пакет «color», чтобы настроить выделение в формуле, как показано в приведенном примере кода.

Задаём `scale = 3000` для масштаба 300% и `margin = 5`, чтобы оставить поля вокруг фрагмента. Пример PNG использует `resolution = 150` DPI.

Следующие два параметра определяют цвета переднего плана и фона. Любые части формулы, на которые не влияет пользовательское выделение, будут отображаться цветом text_color.

Пример присваивает двоичный файловый поток свойству `log_stream` и сохраняет журнал в `math-formula.png.log` рядом с `math-formula.png`. Конструкция `with` автоматически закрывает оба потока.

Параметр `show_terminal` управляет выводом терминала в консоль. В примерах он равен `False`; журнал при этом записывается в файл.

Сам процесс рендеринга осуществляется методом [MathRenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrenderer/render/), который возвращает размер формулы в пунктах.

Второй аргумент — двоичный выходной поток, открытый для изображения. Третий аргумент содержит параметры рендеринга.

И, наконец, вызывается метод MathRenderer.render(), параметры которого передаются в качестве третьего аргумента. Код формулы LaTeX предоставляется в качестве первого аргумента.

Последние строки выводят отчёт об ошибках либо `No rendering errors.`, если отчёт пуст, а затем ширину и высоту в пунктах.

Вот результат рендеринга.

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.png">![Рендеринг математической формулы LaTeX в PNG](/tex/images/python-net/math-formula.png)</a>

Это наиболее распространенное и широкое применение функции **рендеринга математических формул LaTeX**.

**Вы также можете изучить бесплатное [веб-приложение](https://products.aspose.app/tex/equation-editor/png), в котором используется реализованная функция [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**

## Преобразование математической формулы LaTeX в SVG

Точно так же мы можем преобразовать математическую формулу LaTeX в формат SVG, используя тот же подход.

{{< gist "aspose-com-gists" "cbf380b84d7f2067481756d42da32b08" "Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.py" >}}

Этот пример создаёт `math-formula.svg` и журнал `math-formula.svg.log` в том же выходном каталоге.

Отличия заключаются в следующем:

* Вместо использования класса [PngMathRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrendereroptions/) мы используем класс [SvgMathRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrendereroptions/).
* Мы не указываем разрешение.
* Вместо использования класса [PngMathRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrenderer/) мы используем класс [SvgMathRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrenderer/).

 
Вот результат:

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.svg">![Рендеринг математических формул LaTeX в SVG](/tex/images/python-net/math-formula.svg)</a>

**Вы также можете изучить бесплатное [веб-приложение](https://products.aspose.app/tex/equation-editor/svg), в котором используется реализованная функция [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**