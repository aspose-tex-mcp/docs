---
translation: true
template: /templates/_template-net.md
title: Відтворення математичних формул LaTeX | .NET
linktitle: Відтворення математичних формул LaTeX
weight: 10
url: /net/latex-math-formula-rendering/
description: У цій статті описано рішення Aspose.TeX API для відтворення математичних формул .NET LaTeX. Ознайомтеся з прикладами коду, як використовувати цю функцію.
lastmod: "2026-04-22"
---

{{<section overview>}}


## Як відобразити математичну формулу LaTeX у форматі PNG

Довідковий розділ API, пов’язаний із цією темою, знаходиться [тут](https://reference.aspose.com/tex/net/aspose.tex.features/). Насправді, найпростіший спосіб продемонструвати функцію **відтворення математичних формул LaTeX** — це почати з прикладу. Ось воно:

{{< gist "aspose-com-gists" "cd0acc55d1634f17dcf42e02075ca005" "Example-RenderMathToPNG.cs" >}}

Перейдемо до деталей. Перш за все, ми створюємо екземпляр [параметри візуалізації](https://reference.aspose.com/tex/net/aspose.tex.features/mathrendereroptions/), подібний до набору TeX/LaTeX. Ми робимо це тут, одночасно вказуючи роздільну здатність вихідного зображення.

Далі уточнюємо преамбулу. Типова преамбула:


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

який забезпечує трохи розширенішу підтримку математичних формул, ніж базовий LaTeX. Ви можете, наприклад, додати пакет `color`, якщо хочете використовувати власне виділення у формулі, як ми показали у прикладі коду.

Потім ми наказуємо рендереру масштабувати вихід на 300%.

Наступні два параметри визначають кольори переднього плану та фону. Ті частини формули, які не охоплені («забарвлені») спеціальним виділенням, відображатимуться кольором «Колір тексту».

Наступний рядок прикладу не має особливого сенсу. Це просто демонструє, що ви можете спрямувати вихід журналу в якийсь потік.

І остання опція `ShowTerminal` дозволяє вам перемикати запис виводу терміналу на консоль.

Метод, який фактично виконує візуалізацію, це [MathRenderer.Render()](https://reference.aspose.com/tex/net/aspose.tex.features/mathrenderer/render/). Він повертає розмір формули в пунктах.

Потік, у який буде записано зображення, приймається методом як другий аргумент. Далі створюємо потік.

І, нарешті, ми викликаємо сам метод `MathRenderer.Render()`, передаючи параметри як третій аргумент. Код LaTeX формули передається як перший аргумент.

Останні рядки прикладу друкують два артефакти відтворення математичної формули - розмір формули та короткий звіт про помилку (якщо помилки є).

Ось результат візуалізації.

<a href="/tex/net/latex-math-formula-rendering/math-formula.png">![Відтворення математичної формули LaTeX у форматі PNG](/tex/images/net/math-formula.png)</a>

Це найзагальніший варіант використання функції **відтворення математичних формул LaTeX**.

**Ви також можете переглянути безкоштовну [веб-програму](https://products.aspose.app/tex/equation-editor/png), створену на основі функції, реалізованої в [Aspose.TeX для .NET API](https://products.aspose.com/tex/net/).**

## Як відобразити математичну формулу LaTeX у SVG

Приблизно так само ми можемо відобразити математичну формулу LaTeX у форматі SVG.

{{< gist "aspose-com-gists" "cd0acc55d1634f17dcf42e02075ca005" "Example-RenderMathToSVG.cs" >}}

Відмінності:

* Ми використовуємо клас [SvgMathRendererOptions](https://reference.aspose.com/tex/net/aspose.tex.features/svgmathrendereroptions/) замість [PngMathRendererOptions](https://reference.aspose.com/tex/net/aspose.tex.features/pngmathrendereroptions/).
* Ми не вказуємо роздільну здатність.
* Ми використовуємо клас [SvgMathRenderer](https://reference.aspose.com/tex/net/aspose.tex.features/svgmathrenderer/) замість [PngMathRenderer](https://reference.aspose.com/tex/net/aspose.tex.features/pngmathrenderer/).

 
Ось результат:

<a href="/tex/net/latex-math-formula-rendering/math-formula.svg">![Відтворення математичної формули LaTeX у SVG](/tex/images/net/math-formula.svg)</a>

**Ви також можете переглянути безкоштовну [веб-програму](https://products.aspose.app/tex/equation-editor/svg), створену на основі функції, реалізованої в [Aspose.TeX для .NET API](https://products.aspose.com/tex/net/).**