---
translation: true
template: /templates/_template-java.md
title: LaTeX Рендеринг фигур | Java
linktitle: Отрисовка фигур LaTeX
weight: 20
url: /java/latex-figure-rendering/
description: Aspose.TeX API для рендеринга фрагментов (рисунков) Java LaTeX описано в этой статье. Изучите примеры кода о том, как использовать эту функциональность.
lastmod: "2024-09-24"
---

{{<section overview>}}

Может случиться так, что вы захотите извлечь некоторый контент (рисунок, надпись, сюжет и т. д.) из файла LaTeX как отдельно визуализируемый фрагмент или *"рисунок"*, независимо от его места на странице выходного документа. . Например, иллюстрация для вашей публикации в Интернете. Наш API может помочь вам с этой задачей. Доступны два целевых формата — PNG и SVG. Точно так же, как при рендеринге математических формул LaTeX. Мы также должны отметить, что **рендеринг фигур LaTeX** является обобщением [рендеринга математических формул LaTeX](/tex/{{lang.url-fragment}}java/latex-math-formula-rendering/).

## Как преобразовать фигуру LaTeX в PNG

Как и в случае с рендерингом формул, мы начнем с примера. Вот:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.java" >}}

Прежде всего, мы создаем экземпляр [параметры рендеринга](https://reference.aspose.com/tex/java/com.aspose.tex/PngFigureRendererOptions). Мы делаем это здесь вместе с указанием разрешения выходного изображения.

Далее уточняем преамбулу. Для рендеринга фигур LaTeX нет преамбулы по умолчанию, поэтому, если вы хотите, например, визуализировать некоторую графику, построенную с использованием пакета LaTeX `pict2e`, вам необходимо указать ее в преамбуле:

```tex
\usepackage{pict2e}
```

Затем мы указываем рендереру масштабировать результат на 300%.

Следующая опция определяет цвет фона. В отличие от рендеринга математических формул, мы не указываем цвет переднего плана, поскольку предполагаем, что цвета полностью находятся под контролем кода LaTeX. Собственно, как и цвет фона, так что это просто опция для удобства.

Следующая строка примера не имеет особого смысла. Это просто демонстрирует, что вы можете направить вывод журнала в какой-то поток.

И последняя опция «ShowTerminal» позволяет вам переключать запись вывода терминала на консоль.

Метод, который фактически выполняет рендеринг, — [FigureRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/figurerenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.FigureRendererOptions-). Возвращает размер фигуры в пунктах.

Поток, в который должно быть записано изображение, принимается методом в качестве второго аргумента. Далее мы создаем поток.

И, наконец, мы вызываем сам метод «FigureRenderer.render()», передавая параметры в качестве третьего аргумента. Код LaTeX рисунка передается в качестве первого аргумента.

В последних строках примера выводятся два артефакта отрисовки фигуры — размер фигуры и краткий отчет об ошибке (в случае возникновения ошибок).

Вот результат рендеринга.

![Рендеринг рисунков LaTeX в PNG](/tex/images/java/text-and-formula.png)

Это наиболее общий вариант использования функции **рендеринга фигур LaTeX**.

## Как преобразовать фигуру LaTeX в SVG

Примерно таким же образом мы можем преобразовать фигуру LaTeX в формат SVG.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.java" >}}

Отличия заключаются в следующем:

 * Мы используем класс [SvgFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/SvgFigureRendererOptions) вместо [PngFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/PngFigureRendererOptions).
 * Разрешение не указываем.
 * Мы используем класс [SvgFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/SvgFigureRenderer) вместо [PngFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/PngFigureRenderer).

 
Вот результат:

<a href="/tex/images/java/text-and-formula.svg">![Рендеринг рисунков LaTeX в SVG](/tex/images/java/text-and-formula.svg)</a>