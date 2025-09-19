---
translation: true
template: /templates/_template-net.md
title: Візуалізація фігур LaTeX | .NET
linktitle: LaTeX містить малюнок
weight: 20
url: /net/latex-figure-rendering/
description: У цій статті описано рішення Aspose.TeX API для відтворення фрагментів (фігур) .NET LaTeX. Ознайомтеся з прикладами коду, як використовувати цю функцію.
keywords: латексна фігура, розмір фігури латекс, латексна картинка, латексне зображення, латексна фігура, латексне зображення, параметри латексної фігурки
lastmod: "2025-06-13"
---

{{<section overview>}}


Іноді вам може знадобитися витягнути деякий вміст із файлу LaTeX як окремо відтворену частину або *"фігуру"* без будь-якого зв’язку з макетом сторінки. Це може бути ілюстрація до вашої публікації в Інтернеті, наприклад. Ви можете зробити це за допомогою нашого API. Що стосується цільових форматів, то тут є два варіанти - PNG і SVG. Як і у випадку з функцією відтворення математичних формул LaTeX. Варто також зазначити, що **Відтворення фігур LaTeX** є узагальненням [відтворення математичних формул LaTeX](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/).

## Як відобразити фігуру LaTeX у форматі PNG

Довідковий розділ API, пов’язаний із цією темою, знаходиться [тут](https://reference.aspose.com/tex/net/aspose.tex.features/). Як і у випадку з відтворенням формул, ми почнемо з прикладу. Ось воно:

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.cs" >}}

Перш за все, ми створюємо екземпляр [LaTeX figure options](https://reference.aspose.com/tex/net/aspose.tex.features/figurerendereroptions/). Ми робимо це тут, одночасно вказуючи роздільну здатність вихідного зображення.

Далі уточнюємо преамбулу. Немає преамбули за замовчуванням для візуалізації фігур LaTeX, тому якщо ви, наприклад, збираєтеся відобразити деякі графічні зображення, намальовані за допомогою пакета `pict2e` LaTeX, вам потрібно вказати це у преамбулі:


```tex
\usepackage{pict2e}
```

Потім ми наказуємо рендереру масштабувати вихід на 300%.

Наступний параметр визначає колір фону. На відміну від відтворення математичних формул, ми не вказуємо колір переднього плану, оскільки припускаємо, що кольори повністю контролюються кодом LaTeX. Власне, фоновий колір також, тому це лише зручний варіант.

Наступний рядок прикладу не має особливого сенсу. Це просто демонструє, що ви можете спрямувати вихід журналу в якийсь потік.

І остання опція `ShowTerminal` дозволяє вам перемикати запис виводу терміналу на консоль.

Метод, який фактично виконує візуалізацію, це [FigureRenderer.Render()](https://reference.aspose.com/tex/net/aspose.tex.features/figurerenderer/render/). Він повертає розмір фігури в пунктах.

Потік, у який буде записано зображення, приймається методом як другий аргумент. Далі створюємо потік.

І, нарешті, ми викликаємо сам метод `FigureRenderer.Render()`, передаючи параметри як третій аргумент. Код LaTeX фігури передається як перший аргумент.

Останні рядки прикладу друкують два артефакти відтворення фігури - розмір фігури та короткий звіт про помилку (якщо помилки є).

Ось результат візуалізації.

<a href="/tex/net/latex-figure-rendering/text-and-formula.png">![Рендеринг LaTeX Figure у PNG](/tex/images/net/text-and-formula.png)</a>

Це найзагальніший випадок використання функції **LaTeX rendering figure**.

## Як відобразити фігуру LaTeX у SVG

Приблизно так само ми можемо відобразити фігуру LaTeX у форматі SVG.

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.cs" >}}

Відмінності:

* Ми використовуємо клас [SvgFigureRendererOptions](https://reference.aspose.com/tex/net/aspose.tex.features/svgfigurerendereroptions/) замість [PngFigureRendererOptions](https://reference.aspose.com/tex/net/aspose.tex.features/pngfigurerendereroptions/).
* Ми не вказуємо роздільну здатність.
* Ми використовуємо клас [SvgFigureRenderer](https://reference.aspose.com/tex/net/aspose.tex.features/svgfigurerenderer/) замість [PngFigureRenderer](https://reference.aspose.com/tex/net/aspose.tex.features/pngfigurerenderer/).

 
Ось результат:

<a href="/tex/net/latex-figure-rendering/text-and-formula.svg">![Рендеринг LaTeX Figure у SVG](/tex/images/net/text-and-formula.svg)</a>