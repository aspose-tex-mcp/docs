---
translation: true
template: /templates/_template-net.md
title: LaTeX Рендеринг фигур | Aspose.TeX для .NET
linktitle: LaTeX включает рисунок
weight: 20
url: /net/latex-figure-rendering/
description: Решение Aspose.TeX API для рендеринга фрагментов (рисунков) .NET LaTeX описано в этой статье. Изучите примеры кода о том, как использовать эту функциональность.
keywords: латехные фигурки, размеры фигурок из латеха, латехные картинки, латехные изображения, латехные фигурки, латехные картинки, варианты латехных фигурок
lastmod: "2024-09-24"
---

{{<section overview>}}


Иногда вам может потребоваться извлечь некоторый контент из файла LaTeX в виде отдельно визуализируемого фрагмента или *"фигуры"* без какой-либо связи с макетом страницы. Это может быть, например, иллюстрация к вашей публикации в Интернете. Вы можете сделать это с помощью нашего API. Что касается целевых форматов, то здесь есть два варианта — PNG и SVG. Как и в случае с функцией рендеринга математических формул LaTeX. Также стоит отметить, что **рендеринг фигур LaTeX** является обобщением [рендеринга математических формул LaTeX](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/).

## Как преобразовать фигуру LaTeX в PNG

Справочный раздел API, связанный с этой темой, находится [здесь](https://reference.aspose.com/tex/net/aspose.tex.features/). Как и в случае с рендерингом формул, мы начнем с примера. Вот:

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.cs" >}}

Прежде всего, мы создаем экземпляр [Параметры фигуры LaTeX](https://reference.aspose.com/tex/net/aspose.tex.features/figurerendereroptions/). Мы делаем это здесь, одновременно указывая разрешение выходного изображения.

Далее уточняем преамбулу. Для рендеринга фигур LaTeX нет преамбулы по умолчанию, поэтому, если вы, например, собираетесь визуализировать некоторую графику, построенную с использованием пакета LaTeX `pict2e`, вам необходимо указать ее в преамбуле:


```tex
\usepackage{pict2e}
```

Затем мы указываем рендереру масштабировать результат на 300%.

Следующая опция определяет цвет фона. В отличие от рендеринга математических формул, мы не указываем цвет переднего плана, поскольку предполагаем, что цвета полностью находятся под контролем кода LaTeX. Собственно, как и цвет фона, так что это просто опция для удобства.

Следующая строка примера не имеет особого смысла. Это просто демонстрирует, что вы можете направить вывод журнала в какой-то поток.

И последняя опция «ShowTerminal» позволяет вам переключать запись вывода терминала на консоль.

Метод, который фактически выполняет рендеринг, — это [FigureRenderer.Render()](https://reference.aspose.com/tex/net/aspose.tex.features/figurerenderer/render/). Возвращает размер фигуры в пунктах.

Поток, в который должно быть записано изображение, принимается методом в качестве второго аргумента. Далее мы создаем поток.

И, наконец, мы вызываем сам метод «FigureRenderer.Render()», передавая параметры в качестве третьего аргумента. Код LaTeX рисунка передается в качестве первого аргумента.

В последних строках примера выводятся два артефакта отрисовки фигуры — размер фигуры и краткий отчет об ошибке (в случае возникновения ошибок).

Вот результат рендеринга.

<a href="/tex/net/latex-figure-rendering/text-and-formula.png">![Рендеринг рисунков LaTeX в PNG](/tex/images/net/text-and-formula.png)</a>

Это наиболее общий вариант использования функции **рендеринга фигур LaTeX**.

## Как преобразовать фигуру LaTeX в SVG

Примерно таким же образом мы можем визуализировать фигуру LaTeX в формате SVG.

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.cs" >}}

Отличия заключаются в следующем:

* Мы используем класс [SvgFigureRendererOptions](https://reference.aspose.com/tex/net/aspose.tex.features/svgfigurerendereroptions/) вместо [PngFigureRendererOptions](https://reference.aspose.com/tex/net/aspose.tex.features/pngfigurerendereroptions/).
* Разрешение не указываем.
* Мы используем класс [SvgFigureRenderer](https://reference.aspose.com/tex/net/aspose.tex.features/svgfigurerenderer/) вместо [PngFigureRenderer](https://reference.aspose.com/tex/net/aspose.tex.features/pngfigurerenderer/).
 
Вот результат:

<a href="/tex/net/latex-figure-rendering/text-and-formula.svg">![Рендеринг рисунков LaTeX в SVG](/tex/images/net/text-and-formula.svg)</a>