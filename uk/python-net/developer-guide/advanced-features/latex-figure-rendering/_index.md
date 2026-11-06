---
translation: true
template: /templates/_template-python-net.md
title: Візуалізація фігур LaTeX | Python через .NET
linktitle: LaTeX містить малюнок
weight: 20
url: /python-net/latex-figure-rendering/
description: У статті наведено огляд рішення Aspose.TeX API для Python та його функціональні можливості для відтворення фрагментів LaTeX (фігур). Вивчіть приклади коду.
keywords: латексна фігура, розмір фігури латекс, латексна картинка, латексне зображення, латексна фігура, латексне зображення, параметри латексної фігурки
lastmod: "2026-04-03"
---

{{<section overview>}}

У певних ситуаціях вам може знадобитися витягти певний вміст із файлу LaTeX як окрему відтворену частину, яку зазвичай називають *фігурою*, без будь-якого зв’язку з макетом сторінки. Це може стати в нагоді, наприклад, при створенні ілюстрацій для інтернет-видання. Наш API дозволяє вам це зробити. Цільовими форматами для візуалізації фігур є PNG і SVG, як і у функції рендеринга математичних формул LaTeX. Варто зазначити, що **Відтворення фігур LaTeX** є більш загальною функцією порівняно з [Відтворенням математичних формул LaTeX](/tex/{{lang.url-fragment}}python-net/latex-math-formula-rendering/).

## Відтворення фігури LaTeX у форматі PNG

Якщо потрібно, спочатку подивіться [довідковий розділ API для цієї теми](https://reference.aspose.com/tex/python-net/aspose.tex.features/). Подібно до відтворення формули, ми почнемо з прикладу. Ось воно:

Укажіть вихідний каталог у `ASPOSE_TEX_OUTPUT_DIR` або використайте типову папку `output`. Увесь код LaTeX включено до прикладів; зовнішні вхідні файли не потрібні. Спочатку застосуйте ліцензію. [Ліцензування](/tex/uk/python-net/licensing/).

{{< gist "aspose-com-gists" "cbf380b84d7f2067481756d42da32b08" "Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.py" >}}

Для початку ми створюємо екземпляр класу [LaTeX figure renderer options](https://reference.aspose.com/tex/python-net/aspose.tex.features/figurerendereroptions/), де ми одночасно вказуємо роздільну здатність вихідного зображення.

Далі нам потрібно вказати преамбулу. На відміну від відтворення математичних формул LaTeX, для відтворення фігур у LaTeX немає преамбули за замовчуванням. Тому, якщо ви плануєте рендерити графіку, створену за допомогою, наприклад, пакета `pict2e` LaTeX, вам потрібно буде вказати це у преамбулі:

```tex
\usepackage{pict2e}
```

Задаємо `scale = 3000` для масштабу 300% і `margin = 5`, щоб залишити поля навколо фрагмента. Приклад PNG використовує `resolution = 150` DPI.

Наступний параметр визначає колір фону. На відміну від відтворення математичних формул, нам не потрібно вказувати колір переднього плану, оскільки ми припускаємо, що кольори повністю контролюються кодом LaTeX. Подібним чином колір фону також контролюється кодом LaTeX, тому цей параметр надається просто для зручності.

Приклад присвоює двійковий файловий потік властивості `log_stream` і зберігає журнал у `text-and-formula.png.log` поруч із `text-and-formula.png`. Конструкція `with` автоматично закриває обидва потоки.

Параметр `show_terminal` керує виведенням термінала в консоль. У прикладах він дорівнює `False`; журнал і надалі записується у файл.

Метод, відповідальний за рендеринг фігури, це [FigureRenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/figurerenderer/render/#str-io.RawIOBase-aspose.tex.features.FigureRendererOptions) . Він повертає розмір фігури в пунктах.

Другий аргумент — двійковий вихідний потік, відкритий для зображення. Третій аргумент містить параметри рендерингу.

Нарешті, ми викликаємо сам метод `FigureRenderer.render()`, передаючи параметри як третій аргумент. Код LaTeX малюнка надається як перший аргумент.

Останні рядки виводять звіт про помилки або `No rendering errors.`, якщо звіт порожній, а потім ширину та висоту в пунктах.

Ось результат візуалізації.

<a href="/tex/python-net/latex-figure-rendering/text-and-formula.png">![Рендеринг LaTeX Figure у PNG](/tex/images/python-net/text-and-formula.png)</a>

Це найбільш загальний варіант використання функції **Відтворення фігурок LaTeX**.

## Відтворення фігури LaTeX у SVG

Так само ми можемо відобразити фігуру LaTeX у форматі SVG.

{{< gist "aspose-com-gists" "cbf380b84d7f2067481756d42da32b08" "Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.py" >}}

Цей приклад створює `text-and-formula.svg` і журнал `text-and-formula.svg.log` у тому самому вихідному каталозі.

Відмінності:

* Замість використання класу [PngFigureRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerendereroptions/) ми використовуємо клас [SvgFigureRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerendereroptions/).
* Нам не потрібно вказувати роздільну здатність.
* Замість використання класу [PngFigureRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerenderer/) ми використовуємо клас [SvgFigureRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerenderer/).

 
Ось результат:

<a href="/tex/python-net/latex-figure-rendering/text-and-formula.svg">![Рендеринг LaTeX Figure у SVG](/tex/images/python-net/text-and-formula.svg)</a>