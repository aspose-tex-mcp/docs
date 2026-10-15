---
translation: true
template: /templates/_template-java.md
title: Відтворення математичних формул LaTeX | Aspose.TeX для Java
linktitle: Відтворення математичних формул LaTeX
weight: 10
url: /java/latex-math-formula-rendering/
description: Відтворення математичних формул LaTeX в Aspose.TeX API для Java описано в цій статті. Ознайомтеся з прикладами коду, як використовувати цю функцію.
lastmod: "2026-04-21"
---

{{<section overview>}}

## Як відобразити математичну формулу LaTeX у форматі PNG

Фактично, найпростіший спосіб продемонструвати функцію візуалізації **LaTeX math formula** — це почати з прикладу. Ось воно:

Задайте `outputFile` як `java.nio.file.Path` у наявній папці: наприклад, `Paths.get(outputDirectory, "math-formula.png")` для PNG або `Paths.get(outputDirectory, "math-formula.svg")` для SVG. Імпортуйте використані класи рендерерів, параметрів і `Size2D` з Aspose.TeX, а також `java.awt.Color`, `java.io.ByteArrayOutputStream`, `java.io.OutputStream`, `java.nio.file.Files`, `java.nio.file.Path`, `java.nio.file.Paths`. Метод, що викликає цей код, має обробляти або оголошувати винятки. Застосуйте ліцензію згідно з [посібником із ліцензування](/tex/{{lang.url-fragment}}java/licensing/), щоб уникнути обмежень ознайомлювальної версії.

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderMathToPNG.java" >}}

Перейдемо до деталей. Перш за все, ми створюємо екземпляр [параметри візуалізації](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrendereroptions/), подібний до набору тексту TeX/LaTeX. Ми робимо це тут, одночасно вказуючи роздільну здатність вихідного зображення.

Далі уточнюємо преамбулу. Типова преамбула:


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

який забезпечує трохи розширенішу підтримку математичних формул, ніж базовий LaTeX. Ви можете, наприклад, додати пакет `color`, якщо хочете використовувати власне виділення у формулі, як ми показали у прикладі коду.

Потім ми наказуємо рендереру масштабувати вихід на 300%.

Два параметри задають кольори переднього плану та фону. Частини формули без спеціального виділення відображаються кольором, заданим через `setTextColor()`.

Приклад спрямовує журнал рендерингу в `ByteArrayOutputStream` за допомогою `setLogStream()`. Потоки журналу й зображення автоматично закриваються після рендерингу.

`showTerminal()` керує виводом термінала в консоль. У прикладах задано `false`; установіть `true`, щоб показувати вивід.

[MathRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/mathrenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.MathRendererOptions-) викликається на екземплярі `PngMathRenderer` або `SvgMathRenderer` і повертає розміри формули в пунктах як `Size2D`.

Метод приймає потік виводу зображення другим аргументом. Приклад відкриває його в блоці try-with-resources, який закриває потік після рендерингу.

Далі викликається `render()` на екземплярі рендерера: перший аргумент — формула LaTeX, другий — потік виводу зображення, третій — параметри рендерингу.

Останні рядки прикладу друкують два артефакти відтворення математичної формули - розмір формули та короткий звіт про помилку (якщо помилки були).

Ось результат візуалізації.

<a href="/tex/images/java/math-formula.png">![Рендеринг малюнка LaTeX у PNG](/tex/images/java/math-formula.png)</a>

Це найзагальніший варіант використання відтворення **математичної формули LaTeX**.

**Ви також можете переглянути безкоштовну [веб-програму](https://products.aspose.app/tex/equation-editor/png), створену на основі функції, реалізованої в [Aspose.TeX для .NET](https://products.aspose.com/tex/net/) API. [Тут](https://products.aspose.com/tex/java/) – сторінка версії Java.**

## Як відобразити математичну формулу LaTeX у SVG

Приблизно так само ми можемо відобразити математичну формулу LaTeX у форматі SVG.

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderMathToSVG.java" >}}

Відмінності:

* Ми використовуємо клас [SvgMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/svgmathrendereroptions/) замість [PngMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrendereroptions/).
* Ми не вказуємо роздільну здатність.
* Ми використовуємо клас [SvgMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/svgmathrenderer/) замість [PngMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrenderer/).

Ось результат:

<a href="/tex/images/java/math-formula.svg">![Відтворення математичної формули LaTeX у SVG](/tex/images/java/math-formula.svg)</a>

**Ви також можете переглянути безкоштовну [веб-програму](https://products.aspose.app/tex/equation-editor/svg), створену на основі функції, реалізованої в [Aspose.TeX для .NET API](https://products.aspose.com/tex/net/).**