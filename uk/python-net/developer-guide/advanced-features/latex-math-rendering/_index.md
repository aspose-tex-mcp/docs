---
translation: true
template: /templates/_template-python-net.md
title: Відтворення математичних формул LaTeX | Python через .NET
linktitle: Відтворення математичних формул LaTeX
weight: 10
url: /python-net/latex-math-formula-rendering/
description: У статті подано огляд рішення Aspose.TeX API для Python та його функціональних можливостей для відтворення математичних формул LaTeX. Вивчіть приклади коду
lastmod: "2026-04-03"
---

{{<section overview>}}

## Відтворення математичної формули LaTeX у форматі PNG

За потреби перегляньте [довідковий розділ API для цієї теми](https://reference.aspose.com/tex/python-net/aspose.tex.features/). Насправді, найкращий спосіб продемонструвати функцію відтворення **математичної формули LaTeX** — почати з прикладу. Ось воно:

Укажіть вихідний каталог у `ASPOSE_TEX_OUTPUT_DIR` або використайте типову папку `output`. Увесь код LaTeX включено до прикладів; зовнішні вхідні файли не потрібні. Спочатку застосуйте ліцензію. [Ліцензування](/tex/uk/python-net/licensing/).

{{< gist "aspose-com-gists" "cbf380b84d7f2067481756d42da32b08" "Aspose.TeX.Examples-Features-PngLaTeXMathRendering.py" >}}

Перейдемо до деталей. По-перше, ми ініціюємо об’єкт [параметри візуалізації](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrendereroptions/), подібний до набору тексту TeX/LaTeX, який містить специфікацію для бажаної роздільної здатності вихідного зображення.

Далі уточнюємо преамбулу. Типова преамбула:


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

який пропонує розширену підтримку математичних формул порівняно зі стандартним LaTeX. Наприклад, ви можете включити пакет `color`, щоб налаштувати підсвічування у формулі, як показано в наданому прикладі коду.

Задаємо `scale = 3000` для масштабу 300% і `margin = 5`, щоб залишити поля навколо фрагмента. Приклад PNG використовує `resolution = 150` DPI.

Наступні два параметри визначають кольори переднього плану та фону. Будь-які частини формули, на які не впливає спеціальне виділення, відображатимуться кольором `text_color`.

Приклад присвоює двійковий файловий потік властивості `log_stream` і зберігає журнал у `math-formula.png.log` поруч із `math-formula.png`. Конструкція `with` автоматично закриває обидва потоки.

Параметр `show_terminal` керує виведенням термінала в консоль. У прикладах він дорівнює `False`; журнал і надалі записується у файл.

Фактичний процес візуалізації виконується методом [MathRenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrenderer/render/), який повертає розмір формули в балах.

Другий аргумент — двійковий вихідний потік, відкритий для зображення. Третій аргумент містить параметри рендерингу.

І, нарешті, викликається метод `MathRenderer.render()` з параметрами, які передаються як третій аргумент. Код LaTeX формули надається як перший аргумент.

Останні рядки виводять звіт про помилки або `No rendering errors.`, якщо звіт порожній, а потім ширину та висоту в пунктах.

Ось результат візуалізації.

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.png">![Відтворення математичної формули LaTeX у форматі PNG](/tex/images/python-net/math-formula.png)</a>

Це найбільш поширене та широке застосування функції **відтворення математичних формул LaTeX**.

**Ви також можете дослідити безкоштовну [веб-програму](https://products.aspose.app/tex/equation-editor/png), яка використовує реалізовану функцію [Aspose.TeX для .NET API](https://products.aspose.com/tex/net/).**

## Відтворення математичної формули LaTeX у SVG

Так само ми можемо перетворити математичну формулу LaTeX у формат SVG, використовуючи той самий підхід.

{{< gist "aspose-com-gists" "cbf380b84d7f2067481756d42da32b08" "Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.py" >}}

Цей приклад створює `math-formula.svg` і журнал `math-formula.svg.log` у тому самому вихідному каталозі.

Відмінності:

* Замість використання класу [PngMathRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrendereroptions/) ми використовуємо клас [SvgMathRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrendereroptions/).
* Ми не вказуємо роздільну здатність.
* Замість використання класу [PngMathRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrenderer/) ми використовуємо клас [SvgMathRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrenderer/).


Ось результат:

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.svg">![Відтворення математичної формули LaTeX у SVG](/tex/images/python-net/math-formula.svg)</a>

**Ви також можете дослідити безкоштовну [веб-програму](https://products.aspose.app/tex/equation-editor/svg), яка використовує реалізовану функцію [Aspose.TeX для .NET API](https://products.aspose.com/tex/net/).**