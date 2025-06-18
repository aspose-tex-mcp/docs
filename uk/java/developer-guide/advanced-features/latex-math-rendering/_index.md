---
translation: true
template: /templates/_template-java.md
title: Відтворення математичних формул LaTeX | Java
linktitle: Відтворення математичних формул LaTeX
weight: 10
url: /java/latex-math-formula-rendering/
description: Відтворення математичних формул LaTeX в Aspose.TeX API для Java описано в цій статті. Ознайомтеся з прикладами коду, як використовувати цю функцію.
lastmod: "2025-06-13"
---

{{<section overview>}}

## Як відобразити математичну формулу LaTeX у форматі PNG

Фактично, найпростіший спосіб продемонструвати функцію візуалізації **LaTeX math formula** — це почати з прикладу. Ось воно:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Features-PngLaTeXMathRendering.java" >}}

Перейдемо до деталей. Перш за все, ми створюємо екземпляр [параметри візуалізації](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRendererOptions), подібний до набору тексту TeX/LaTeX. Ми робимо це тут, одночасно вказуючи роздільну здатність вихідного зображення.

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

Метод, який фактично виконує візуалізацію, це [MathRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/mathrenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.MathRendererOptions-). Він повертає розмір формули в пунктах.

Потік, у який буде записано зображення, приймається методом як другий аргумент. Далі створюємо потік.

І, нарешті, ми викликаємо сам метод `MathRenderer.render()`, передаючи параметри як третій аргумент. Код LaTeX формули передається як перший аргумент.

Останні рядки прикладу друкують два артефакти відтворення математичної формули - розмір формули та короткий звіт про помилку (якщо помилки були).

Ось результат візуалізації.

<a href="/tex/images/java/math-formula.png">![Рендеринг малюнка LaTeX у PNG](/tex/images/java/math-formula.png)</a>

Це найзагальніший варіант використання відтворення **математичної формули LaTeX**.

**Ви також можете переглянути безкоштовну [веб-програму](https://products.aspose.app/tex/equation-editor/png), створену на основі функції, реалізованої в [Aspose.TeX для .NET](https://products.aspose.com/tex/net/) API. [Тут](https://products.aspose.com/tex/java/) – сторінка версії Java.**

## Як відобразити математичну формулу LaTeX у SVG

Приблизно так само ми можемо відобразити математичну формулу LaTeX у форматі SVG.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.java" >}}

Відмінності:

 * Ми використовуємо клас [SvgMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/SvgMathRendererOptions) замість [PngMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRendererOptions).
 * Ми не вказуємо роздільну здатність.
 * Ми використовуємо клас [SvgMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/SvgMathRenderer) замість [PngMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRenderer).


Ось результат:

<a href="/tex/images/java/math-formula.svg">![Відтворення математичної формули LaTeX у SVG](/tex/images/java/math-formula.svg)</a>

**Ви також можете переглянути безкоштовну [веб-програму](https://products.aspose.app/tex/equation-editor/svg), створену на основі функції, реалізованої в [Aspose.TeX для .NET API](https://products.aspose.com/tex/net/).**