---
translation: true
template: /templates/_template-java.md
linktitle: Розширювані та регульовані символи
title: 5. Розширювані та настроювані символи | Підручник з LaTeX
weight: 50
url: /java/latex-math-extensible-symbols/
keywords: ams-latex, amsmath, amsxtra, латексні математичні оператори, латексні математичні роздільники, латексні математичні дужки, латексні математичні дужки, латексні математичні акценти
description: У цій статті розглядаються функції LaTeX, пов’язані з роботою з розширюваними та регульованими математичними символами.
lastmod: "2025-06-13"
---

{{<section overview>}}

У LaTeX є певні функції, які дозволяють створювати структури, які можуть зростати до будь-якого необхідного розміру. Математичний набір гостро потребує такої варіативності. Ми обговоримо деякі його аспекти в цій статті. Усі команди, описані в цьому розділі (якщо не зазначено інше), надаються стандартним LaTeX.


## 5.1. Три крапки...

Пакет `amsmath` замінює (майже в усіх випадках) усі `\ldots`, `cdots` тощо зі стандартного LaTeX єдиною командою `\dots`. Як вертикальне положення еліпса, так і простір навколо нього вибираються автоматично залежно від типу символу після `\dots`. Якщо наступним символом є, скажімо, знак плюса, крапки розміщуватимуться по центру; якщо це кома, вони впадуть на базову лінію. Це завжди три крапки, але інтервал змінний.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
A series $H_1, H_2, \dots, H_n$, a sum
$H_1 + H_2 + \dots + H_n$, an orthogonal product
$H_1 \times H_2 \times \dots \times H_n$.
```

![Еліпс із автоматично визначеним інтервалом](/tex/images/java/tutorial/latex-ams-math-5-1.png)

Однак, коли крапки з’являються в кінці формули, наступним об’єктом буде щось на кшталт `\end` або `\)` або `$`, і це не дає LaTeX підказки про розташування крапок. У такому випадку ви повинні допомогти, використовуючи `\dotsc` для крапок, за якими йдуть коми, `\dotsb` для крапок, за якими йде *двійковий оператор* або *символ зв’язку*, `\dotsm` для крапок, за якими йдуть крапки множення, ` \dotsi` для крапок, за якими йдуть інтеграли, або `\dotso` в будь-якому іншому випадку.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
A series $H_1, H_2, \dotsc\,$, a sum
$H_1 + H_2 + \dotsb\,$, an orthogonal product
$H_1 \times H_2 \times \dotsm\,$, and an infinite
integral: \[ \int_{H_1} \int_{H_2} \dotsi \;
{-\Gamma}\, d\Theta \]
```

![Еліпсис у кінці формули](/tex/images/java/tutorial/latex-ams-math-5-2.png)

## 5.2. Символи, що розширюються по горизонталі

По суті, LaTeX дозволяє налаштувати будь-яку команду математичних акцентів для створення відповідного гліфа з діапазону ширини, якщо це передбачено доступними шрифтами. Однак у стандартному LaTeX є лише дві такі команди: `\widehat` і `\widetilde`.

У наступному прикладі ми демонструємо використання кількох команд, які створюють конструкції, подібні до вищезгаданих розширюваних наголосів. Усі вони створюють складені символи математичного класу *Ordinary*.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align*}
\widehat {\psi_\delta(t) E_t h}
&= \widetilde {\psi_\delta(t) E_t h} \\
\overline {\psi_\delta(t) E_t h}
&= \underline {\psi_\delta(t) E_t h} \\
\overbrace {\psi_\delta(t) E_t h}
&= \underbrace {\psi_\delta(t) E_t h}
& & \text{Do not change style} \\
\overrightarrow {\psi_\delta(t) E_t h} 
&= \overleftarrow {\psi_\delta(t) E_t h}
& & \text{Do not change style} \\[-3pt]
& & & \text{without \textsf{amsmath}} \\
\underrightarrow {\psi_\delta(t) E_t h}
&= \underleftarrow {\psi_\delta(t) E_t h}
& & \text{Do need \textsf{amsmath}} \\
\overleftrightarrow {\psi_\delta(t) E_t h}
&=\underleftrightarrow{\psi_\delta(t) E_t h}
& & \text{Do need \textsf{amsmath}}
\end{align*}
```

![Розтяжні наголоси](/tex/images/java/tutorial/latex-ams-math-5-3.png)

Тут «змінити стиль» означає, що використовуваний символ залежить від використовуваного математичного стилю, щоб він виглядав правильно, коли використовується, наприклад, у дробах або нижньому/верхньому індексі. Ті, які не змінюють стиль, вийдуть правильними лише на верхньому рівні показаних формул.

## 5.3. Символи, що розширюються по вертикалі

Вертикальна розтяжність значно ширша. У наведеній нижче таблиці перераховано всі символи, які можна розширювати вертикально.

*Вертикально розширювані символи*

|||||||
|:---:|---|:---:|---|:---:|---|
| !["Парентези"](/tex/images/java/tutorial/latex-ams-math-delim-5-1.png) | `(` `)` | !["Відкрити фігурні дужки"](/tex/images/java/tutorial/latex-ams-math-delim-5-11.png) | `\{` `\}` | !["Подвійні вертикальні смуги"](/tex/images/java/tutorial/latex-ams-math-delim-5-18.png) | *`\lВерт` `\rВерт`* |
| !["Кутові дужки"](/tex/images/java/tutorial/latex-ams-math-delim-5-2.png) | `\langle` `\rangle` | !["Закрити фігурні дужки"](/tex/images/java/tutorial/latex-ams-math-delim-5-11.png) | `\lbrace` `\rbrace` | !["Одиночні вертикальні смуги"](/tex/images/java/tutorial/latex-ams-math-delim-5-19.png) | *`\lvert` `\rvert`* |
| !["Lgroup і Rgroup"](/tex/images/java/tutorial/latex-ams-math-delim-5-3.png) | `\lgroup` `\rgroup` | !["Квадратні дужки відкриті"](/tex/images/java/tutorial/latex-ams-math-delim-5-12.png) | `[` `]` | !["Вертикальна смуга"](/tex/images/java/tutorial/latex-ams-math-delim-5-20.png) | `|` |
| !["Вуса"](/tex/images/java/tutorial/latex-ams-math-delim-5-4.png) | `\lmoustache` `\rmoustache` | !["Закрити квадратні дужки"](/tex/images/java/tutorial/latex-ams-math-delim-5-12.png) | `\lbrack` `\rbrack` | !["Вертикальна смуга"](/tex/images/java/tutorial/latex-ams-math-delim-5-20.png) | `\верт` |
| !["Стрілка вниз"](/tex/images/java/tutorial/latex-ams-math-delim-5-5.png) | `\Вниз` | !["Ceiling Brackets Open"](/tex/images/java/tutorial/latex-ams-math-delim-5-13.png) | `\lceil` `\rceil` | !["Вертикальна панель зі стрілкою"](/tex/images/java/tutorial/latex-ams-math-delim-5-20.png) | `\arrowvert` |
| !["Стрілка вгору"](/tex/images/java/tutorial/latex-ams-math-delim-5-6.png) | `\Uparrow` | !["Закрити квадратні дужки"](/tex/images/java/tutorial/latex-ams-math-delim-5-14.png) | `\lfloor` `\rfloor` | !["Вертикальна смуга в дужках"](/tex/images/java/tutorial/latex-ams-math-delim-5-21.png) | `\bracevert` |
| !["Стрілка вгору вниз"](/tex/images/java/tutorial/latex-ams-math-delim-5-7.png) | `\Стрілка вгору` | !["Подвійні дужки відкриті"](/tex/images/java/tutorial/latex-ams-math-delim-5-15.png) | ***`\llbracket` `\rrbracket`*** | !["Вертикальна панель з подвійною стрілкою"](/tex/images/java/tutorial/latex-ams-math-delim-5-22.png) | `\Arrowvert` |
| !["Одна стрілка вниз"](/tex/images/java/tutorial/latex-ams-math-delim-5-8.png) | `\стрілка вниз` | !["Слеш"](/tex/images/java/tutorial/latex-ams-math-delim-5-16.png) | `/` | !["Подвійна вертикальна лінія"](/tex/images/java/tutorial/latex-ams-math-delim-5-22.png) | `\|` |
| !["Одна стрілка вгору"](/tex/images/java/tutorial/latex-ams-math-delim-5-9.png) | `\uparrow` | !["Зворотний слеш"](/tex/images/java/tutorial/latex-ams-math-delim-5-17.png) | `\зворотна коса риска` | !["Подвійна вертикальна лінія"](/tex/images/java/tutorial/latex-ams-math-delim-5-22.png) | `\Верт` |
| !["Стрілка вгору вниз"](/tex/images/java/tutorial/latex-ams-math-delim-5-10.png) | `\updownarrow` | | `.` | !["Знак квадратного кореня"](/tex/images/java/tutorial/latex-ams-math-delim-5-23.png) | `\sqrtsign` |


> *Символи, виділені курсивом, вимагають пакета `amsmath` або, якщо додатково введено жирним шрифтом, пакет `stmaryrd`. Крапка (.) сама по собі не є розширюваним символом, але її можна використовувати для створення «невидимого» роздільника. Символ `\sqrtsign` не можна використовувати з `\left`, `\right` або `\middle`.*

> *Синоніми: [ - `\lbrack`, `[`;	] - `\rbrack`, `]`;	{ - `\lbrace`, `\{`;	} - `\rbrace`, `\}`; | - `\vert`, `|`;	|| - `\Vert`, `\|`.*

Ці символи стають розширюваними лише в певних випадках використання. Вони повинні базуватися на такій конструкції:

```tex
\left <ext-Open> <sub-formula> \right <ext-Close>
```

> Якщо LaTeX використовує програму eTeX, ви також можете використовувати ці розширювані символи з `\middle`.

Тут `<ext-Open>` і `<ext-Close>` можуть бути будь-яким із символів (окрім `\sqrtsign`), перелічених у таблиці вище. Це мають бути символи, налаштовані розширюваними, як описано в [fntguide](https://www.latex-project.org/help/documentation/fntguide.pdf). Таким чином, повинен бути доступний символ, що вказує на відсутність фактичного гліфа. Траплялося, що цей символ, також відомий як *нульовий роздільник*, є крапкою (.). Розміри фактичних гліфів для набору розширюваного символу вибираються так, щоб вони відповідали висоті та глибині підформули, яка лежить між ними.

Радикальний символ `\sqrtsign` збільшується як вертикально, так і горизонтально, щоб відповідати розміру свого аргументу. У LaTeX ви б краще використали команду `\sqrt`, щоб отримати цей символ.


```tex
\[
  \sqrtsign{1 + \sqrtsign{1 + \sqrtsign{1 +
    \sqrtsign{1 + \sqrtsign{1 + \sqrtsign{1 + x}}}}}}
\]
```

![Розширення радикалів](/tex/images/java/tutorial/latex-ams-math-5-24.png)