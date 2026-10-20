---
translation: true
template: /templates/_template-java.md
title: Візуалізація фігур LaTeX | Aspose.TeX для Java
linktitle: Рендеринг фігур LaTeX
weight: 20
url: /java/latex-figure-rendering/
description: У цій статті описано рішення Aspose.TeX API для відтворення фрагментів (фігур) Java LaTeX. Ознайомтеся з прикладами коду, як використовувати цю функцію.
lastmod: "2026-04-21"
---

{{<section overview>}}

Може статися так, що ви захочете витягти певний вміст (малюнок, напис, сюжет тощо) із файлу LaTeX як окремо відтворену частину або *"фігуру"*, незалежно від її місця на сторінці вихідного документа . Ілюстрація до вашої публікації в Інтернеті, наприклад, кейс. Наш API може допомогти вам із завданням. Є два доступних цільових формату - PNG і SVG. Так само, як у рендерингу математичних формул LaTeX. Ми також маємо зауважити, що **Відтворення фігур LaTeX** є узагальненням [Відтворення математичних формул LaTeX](/tex/{{lang.url-fragment}}java/latex-math-formula-rendering/).

## Як відобразити фігуру LaTeX у форматі PNG

Як і у випадку з відтворенням формул, ми почнемо з прикладу. Ось воно:

Задайте `outputFile` як `java.nio.file.Path` у наявній папці: наприклад, `Paths.get(outputDirectory, "text-and-formula.png")` для PNG або `Paths.get(outputDirectory, "text-and-formula.svg")` для SVG. Імпортуйте використані класи рендерерів, параметрів і `Size2D` з Aspose.TeX, а також `java.awt.Color`, `java.io.ByteArrayOutputStream`, `java.io.OutputStream`, `java.nio.file.Files`, `java.nio.file.Path`, `java.nio.file.Paths`. Метод, що викликає цей код, має обробляти або оголошувати винятки. Застосуйте ліцензію згідно з [посібником із ліцензування](/tex/{{lang.url-fragment}}java/licensing/), щоб уникнути обмежень ознайомлювальної версії.

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderFigureToPNG.java" >}}

Перш за все, ми створюємо екземпляр [параметри візуалізації](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerendereroptions/). Ми робимо це тут разом із визначенням роздільної здатності вихідного зображення.

Далі уточнюємо преамбулу. Немає преамбули за замовчуванням для візуалізації фігур LaTeX, тому, якщо ви хочете, наприклад, відобразити деяку графіку, намальовану за допомогою пакета `pict2e` LaTeX, вам потрібно вказати це у преамбулі:

```tex
\usepackage{pict2e}
```

Потім ми наказуємо рендереру масштабувати вихід на 300%. Приклади також задають відступ у 5 пунктів навколо фігури через `setMargin(5)`. У PNG-прикладі використовується роздільна здатність 150 DPI.

Наступний параметр визначає колір фону. На відміну від відтворення математичних формул, ми не вказуємо колір переднього плану, оскільки припускаємо, що кольори повністю контролюються кодом LaTeX. Власне, фоновий колір також, тому це лише зручний варіант.

Приклад спрямовує журнал рендерингу в `ByteArrayOutputStream` за допомогою `setLogStream()`. Потоки журналу й зображення автоматично закриваються після рендерингу.

`showTerminal()` керує виводом термінала в консоль. У прикладах задано `false`; установіть `true`, щоб показувати вивід.

[FigureRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/figurerenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.FigureRendererOptions-) викликається на екземплярі `PngFigureRenderer` або `SvgFigureRenderer` і повертає розміри фігури в пунктах як `Size2D`.

Метод приймає потік виводу зображення другим аргументом. Приклад відкриває його в блоці try-with-resources, який закриває потік після рендерингу.

Далі викликається `render()` на екземплярі рендерера: перший аргумент — фігура LaTeX, другий — потік виводу зображення, третій — параметри рендерингу.

Останні рядки прикладу друкують два артефакти відтворення фігури - розмір фігури та короткий звіт про помилку (якщо помилки є).

Ось результат візуалізації.

![LaTeX Figure rendering to PNG](/tex/images/java/text-and-formula.png)

Це найзагальніший випадок використання функції **LaTeX rendering figure**.

## Як відобразити фігуру LaTeX у SVG

Приблизно так само ми можемо відобразити фігуру LaTeX у форматі SVG.

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderFigureToSVG.java" >}}

Відмінності:

 * Ми використовуємо клас [SvgFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/svgfigurerendereroptions/) замість [PngFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerendereroptions/).
 * Ми не вказуємо роздільну здатність.
 * Ми використовуємо клас [SvgFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/svgfigurerenderer/) замість [PngFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerenderer/).
 
Ось результат:

<a href="/tex/images/java/text-and-formula.svg">![Рендеринг малюнка LaTeX у SVG](/tex/images/java/text-and-formula.svg)</a>