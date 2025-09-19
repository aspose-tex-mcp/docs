---
translation: true
template: /templates/_template-python-net.md
title: Відтворення математичних формул LaTeX | Python через .NET
linktitle: Відтворення математичних формул LaTeX
weight: 10
url: /python-net/latex-math-formula-rendering/
description: У статті подано огляд рішення Aspose.TeX API для Python та його функціональних можливостей для відтворення математичних формул LaTeX. Вивчіть приклади коду
lastmod: "2025-06-13"
---

{{<section overview>}}

## Відтворення математичної формули LaTeX у форматі PNG

За потреби перегляньте [довідковий розділ API для цієї теми](https://reference.aspose.com/tex/python-net/aspose.tex.features/). Насправді, найкращий спосіб продемонструвати функцію відтворення **математичної формули LaTeX** — почати з прикладу. Ось воно:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Features-PngLaTeXMathRendering.py" >}}

Перейдемо до деталей. По-перше, ми ініціюємо об’єкт [параметри візуалізації](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrendereroptions/), подібний до набору тексту TeX/LaTeX, який містить специфікацію для бажаної роздільної здатності вихідного зображення.

Далі уточнюємо преамбулу. Типова преамбула:


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

який пропонує розширену підтримку математичних формул порівняно зі стандартним LaTeX. Наприклад, ви можете включити пакет `color`, щоб налаштувати підсвічування у формулі, як показано в наданому прикладі коду.

Потім ми наказуємо рендереру масштабувати вихід на 300%.

Наступні два параметри визначають кольори переднього плану та фону. Будь-які частини формули, на які не впливає спеціальне виділення, відображатимуться кольором `TextColor`.

Наступний рядок у прикладі служить ілюстрацією того, що у вас є можливість перенаправити вихід журналу до певного потоку.

І, нарешті, параметр `ShowTerminal` дозволяє контролювати, чи слід відображати вихід терміналу на консолі.

Фактичний процес візуалізації виконується методом [MathRenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrenderer/render/), який повертає розмір формули в балах.

Метод приймає потік, куди буде записано зображення, як другий аргумент. Далі переходимо до створення потоку.

І, нарешті, викликається метод `MathRenderer.render()` з параметрами, які передаються як третій аргумент. Код LaTeX формули надається як перший аргумент.

У останніх рядках прикладу відображаються два результати процесу відтворення математичної формули — розмір формули та стислий звіт про помилку, якщо виникнуть помилки.

Ось результат візуалізації.

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.png">![Відтворення математичної формули LaTeX у форматі PNG](/tex/images/python-net/math-formula.png)</a>

Це найбільш поширене та широке застосування функції **відтворення математичних формул LaTeX**.

**Ви також можете дослідити безкоштовну [веб-програму](https://products.aspose.app/tex/equation-editor/png), яка використовує реалізовану функцію [Aspose.TeX для .NET API](https://products.aspose.com/tex/net/).**

## Відтворення математичної формули LaTeX у SVG

Так само ми можемо перетворити математичну формулу LaTeX у формат SVG, використовуючи той самий підхід.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.py" >}}

Відмінності:

* Замість використання класу [PngMathRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrendereroptions/) ми використовуємо клас [SvgMathRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrendereroptions/).
* Ми не вказуємо роздільну здатність.
* Замість використання класу [PngMathRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrenderer/) ми використовуємо клас [SvgMathRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrenderer/).


Ось результат:

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.svg">![Відтворення математичної формули LaTeX у SVG](/tex/images/python-net/math-formula.svg)</a>

**Ви також можете дослідити безкоштовну [веб-програму](https://products.aspose.app/tex/equation-editor/svg), яка використовує реалізовану функцію [Aspose.TeX для .NET API](https://products.aspose.com/tex/net/).**