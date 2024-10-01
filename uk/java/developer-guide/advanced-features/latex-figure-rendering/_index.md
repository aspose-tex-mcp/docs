---
translation: true
template: /templates/_template-java.md
title: Візуалізація фігур LaTeX | Aspose.TeX для Java
linktitle: Рендеринг фігур LaTeX
weight: 20
url: /java/latex-figure-rendering/
description: У цій статті описано рішення Aspose.TeX API для відтворення фрагментів (фігур) Java LaTeX. Ознайомтеся з прикладами коду, як використовувати цю функцію.
lastmod: 2024-09-20
---

{{<section overview>}}

Може статися так, що ви захочете витягти певний вміст (малюнок, напис, сюжет тощо) із файлу LaTeX як окремо відтворену частину або *"фігуру"*, незалежно від її місця на сторінці вихідного документа . Ілюстрація до вашої публікації в Інтернеті, наприклад, кейс. Наш API може допомогти вам із завданням. Є два доступних цільових формату - PNG і SVG. Так само, як у рендерингу математичних формул LaTeX. Ми також маємо зауважити, що **Відтворення фігур LaTeX** є узагальненням [Відтворення математичних формул LaTeX](/tex/{{lang.url-fragment}}java/latex-math-formula-rendering/).

## Як відобразити фігуру LaTeX у форматі PNG

Як і у випадку з відтворенням формул, ми почнемо з прикладу. Ось воно:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.java" >}}

Перш за все, ми створюємо екземпляр [параметри візуалізації](https://reference.aspose.com/tex/java/com.aspose.tex/PngFigureRendererOptions). Ми робимо це тут разом із визначенням роздільної здатності вихідного зображення.

Далі уточнюємо преамбулу. Немає преамбули за замовчуванням для візуалізації фігур LaTeX, тому, якщо ви хочете, наприклад, відобразити деяку графіку, намальовану за допомогою пакета `pict2e` LaTeX, вам потрібно вказати це у преамбулі:

```tex
\usepackage{pict2e}
```

Потім ми наказуємо рендереру масштабувати вихід на 300%.

Наступний параметр визначає колір фону. На відміну від відтворення математичних формул, ми не вказуємо колір переднього плану, оскільки припускаємо, що кольори повністю контролюються кодом LaTeX. Власне, фоновий колір також, тому це лише зручний варіант.

Наступний рядок прикладу не має особливого сенсу. Це просто демонструє, що ви можете спрямувати вихід журналу в якийсь потік.

І остання опція `ShowTerminal` дозволяє вам перемикати запис виводу терміналу на консоль.

Метод, який фактично виконує візуалізацію, це [FigureRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/figurerenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.FigureRendererOptions-). Він повертає розмір фігури в пунктах.

Потік, у який буде записано зображення, приймається методом як другий аргумент. Далі створюємо потік.

І, нарешті, ми викликаємо сам метод `FigureRenderer.render()`, передаючи параметри як третій аргумент. Код LaTeX фігури передається як перший аргумент.

Останні рядки прикладу друкують два артефакти відтворення фігури - розмір фігури та короткий звіт про помилку (якщо помилки є).

Ось результат візуалізації.

![LaTeX Figure rendering to PNG](/tex/images/java/text-and-formula.png)

Це найзагальніший випадок використання функції **LaTeX rendering figure**.

## Як відобразити фігуру LaTeX у SVG

Приблизно так само ми можемо відобразити фігуру LaTeX у форматі SVG.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.java" >}}

Відмінності:

 * Ми використовуємо клас [SvgFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/SvgFigureRendererOptions) замість [PngFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/PngFigureRendererOptions).
 * Ми не вказуємо роздільну здатність.
 * Ми використовуємо клас [SvgFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/SvgFigureRenderer) замість [PngFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/PngFigureRenderer).
 
Ось результат:

<a href="/tex/images/java/text-and-formula.svg">![Рендеринг малюнка LaTeX у SVG](/tex/images/java/text-and-formula.svg)</a>