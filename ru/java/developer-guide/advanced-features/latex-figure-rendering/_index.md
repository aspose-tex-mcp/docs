---
translation: true
template: /templates/_template-java.md
title: LaTeX Рендеринг фигур | Java
linktitle: Отрисовка фигур LaTeX
weight: 20
url: /java/latex-figure-rendering/
description: Aspose.TeX API для рендеринга фрагментов (рисунков) Java LaTeX описано в этой статье. Изучите примеры кода о том, как использовать эту функциональность.
lastmod: "2026-04-21"
---

{{<section overview>}}

Может случиться так, что вы захотите извлечь некоторый контент (рисунок, надпись, сюжет и т. д.) из файла LaTeX как отдельно визуализируемый фрагмент или *"рисунок"*, независимо от его места на странице выходного документа. . Например, иллюстрация для вашей публикации в Интернете. Наш API может помочь вам с этой задачей. Доступны два целевых формата — PNG и SVG. Точно так же, как при рендеринге математических формул LaTeX. Мы также должны отметить, что **рендеринг фигур LaTeX** является обобщением [рендеринга математических формул LaTeX](/tex/{{lang.url-fragment}}java/latex-math-formula-rendering/).

## Как преобразовать фигуру LaTeX в PNG

Как и в случае с рендерингом формул, мы начнем с примера. Вот:

Задайте `outputFile` как `java.nio.file.Path` в существующей папке: например, `Paths.get(outputDirectory, "text-and-formula.png")` для PNG или `Paths.get(outputDirectory, "text-and-formula.svg")` для SVG. Импортируйте используемые классы рендереров, параметров и `Size2D` из Aspose.TeX, а также `java.awt.Color`, `java.io.ByteArrayOutputStream`, `java.io.OutputStream`, `java.nio.file.Files`, `java.nio.file.Path`, `java.nio.file.Paths`. Вызывающий метод должен обрабатывать или объявлять исключения. Примените лицензию согласно [руководству по лицензированию](/tex/{{lang.url-fragment}}java/licensing/), чтобы избежать ограничений ознакомительной версии.

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderFigureToPNG.java" >}}

Прежде всего, мы создаем экземпляр [параметры рендеринга](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerendereroptions/). Мы делаем это здесь вместе с указанием разрешения выходного изображения.

Далее уточняем преамбулу. Для рендеринга фигур LaTeX нет преамбулы по умолчанию, поэтому, если вы хотите, например, визуализировать некоторую графику, построенную с использованием пакета LaTeX `pict2e`, вам необходимо указать ее в преамбуле:

```tex
\usepackage{pict2e}
```

Затем мы указываем рендереру масштабировать результат на 300%. Примеры также задают отступ в 5 пунктов вокруг фигуры через `setMargin(5)`. В PNG-примере используется разрешение 150 DPI.

Следующая опция определяет цвет фона. В отличие от рендеринга математических формул, мы не указываем цвет переднего плана, поскольку предполагаем, что цвета полностью находятся под контролем кода LaTeX. Собственно, как и цвет фона, так что это просто опция для удобства.

Пример направляет журнал рендеринга в `ByteArrayOutputStream` с помощью `setLogStream()`. Потоки журнала и изображения автоматически закрываются после рендеринга.

`showTerminal()` управляет выводом терминала в консоль. В примерах задано `false`; установите `true`, чтобы показывать вывод.

[FigureRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/figurerenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.FigureRendererOptions-) вызывается на экземпляре `PngFigureRenderer` или `SvgFigureRenderer` и возвращает размеры фигуры в пунктах в виде `Size2D`.

Метод принимает поток вывода изображения вторым аргументом. Пример открывает его в блоке try-with-resources, который закрывает поток после рендеринга.

Затем вызывается `render()` на экземпляре рендерера: первый аргумент — фигура LaTeX, второй — поток вывода изображения, третий — параметры рендеринга.

В последних строках примера выводятся два артефакта отрисовки фигуры — размер фигуры и краткий отчет об ошибке (в случае возникновения ошибок).

Вот результат рендеринга.

![Рендеринг рисунков LaTeX в PNG](/tex/images/java/text-and-formula.png)

Это наиболее общий вариант использования функции **рендеринга фигур LaTeX**.

## Как преобразовать фигуру LaTeX в SVG

Примерно таким же образом мы можем преобразовать фигуру LaTeX в формат SVG.

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderFigureToSVG.java" >}}

Отличия заключаются в следующем:

 * Мы используем класс [SvgFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/svgfigurerendereroptions/) вместо [PngFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerendereroptions/).
 * Разрешение не указываем.
 * Мы используем класс [SvgFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/svgfigurerenderer/) вместо [PngFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerenderer/).

 
Вот результат:

<a href="/tex/images/java/text-and-formula.svg">![Рендеринг рисунков LaTeX в SVG](/tex/images/java/text-and-formula.svg)</a>