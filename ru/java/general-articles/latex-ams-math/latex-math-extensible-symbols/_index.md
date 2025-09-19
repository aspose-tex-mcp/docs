---
translation: true
template: /templates/_template-java.md
linktitle: Расширяемые и настраиваемые символы
title: 5. Расширяемые и настраиваемые символы
weight: 50
url: /java/latex-math-extensible-symbols/
keywords: ams-latex, amsmath, amsxtra, латехные математические операторы, латехные математические разделители, латехные математические скобки, латехные математические скобки, латехные математические акценты
description: В этой статье рассматриваются возможности LaTeX, связанные с работой с расширяемыми и настраиваемыми математическими символами.
lastmod: "2024-09-24"
---

{{<section overview>}}

В LaTeX есть определенные возможности, позволяющие создавать структуры, которые могут расти до любого необходимого размера. Математическая верстка остро нуждается в такой вариативности. Некоторые аспекты этого процесса мы обсудим в этой статье. Все команды, описанные в этом разделе (если не указано иное), предоставляются стандартом LaTeX.


## 5.1. Многоточие...

Пакет amsmath заменяет (почти во всех случаях) все эти `\ldots`, `cdots` и т. д. из стандартного LaTeX одной командой `\dots`. И вертикальное положение многоточия, и пространство вокруг него выбираются автоматически в зависимости от типа символа, следующего за `\dots`. Если следующим символом является, скажем, знак плюса, точки будут располагаться по центру; если это запятая, они попадут на базовую линию. Это всегда три точки, но интервал варьируется.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
A series $H_1, H_2, \dots, H_n$, a sum
$H_1 + H_2 + \dots + H_n$, an orthogonal product
$H_1 \times H_2 \times \dots \times H_n$.
```

![Многоточие с автоматически определяемым интервалом](/tex/images/java/tutorial/latex-ams-math-5-1.png)

Однако, когда точки появляются в конце формулы, следующим объектом будет что-то вроде `\end` или `\)` или `$`, и это не дает LaTeX никакой информации о расположении точек. В таком случае вы должны помочь, используя `\dotsc` для точек, за которыми следуют запятые, `\dotsb` для точек, за которыми следует *Бинарный оператор* или *Символ отношения*, `\dotsm` для точек, за которыми следуют точки умножения, `\dotsm` для точек, за которыми следуют точки умножения, \dotsi` для точек, за которыми следуют целые числа, или `\dotso` в любом другом случае.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
A series $H_1, H_2, \dotsc\,$, a sum
$H_1 + H_2 + \dotsb\,$, an orthogonal product
$H_1 \times H_2 \times \dotsm\,$, and an infinite
integral: \[ \int_{H_1} \int_{H_2} \dotsi \;
{-\Gamma}\, d\Theta \]
```

![Многоточие в конце формулы](/tex/images/java/tutorial/latex-ams-math-5-2.png)

## 5.2. Символы, которые можно расширять по горизонтали

По сути, LaTeX позволяет настроить любую команду математического акцента для создания соответствующего глифа из диапазона ширины, когда они предусмотрены доступными шрифтами. Однако в стандартном LaTeX таких команд всего две: `\widehat` и `\widetilde`.

В следующем примере мы демонстрируем использование нескольких команд, которые создают конструкции, аналогичные вышеупомянутым расширяемым акцентам. Все они создают составные символы математического класса *Ordinary*.

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

![Расширяемые акценты](/tex/images/java/tutorial/latex-ams-math-5-3.png)

Здесь «изменить стиль» означает, что на используемый символ влияет используемый математический стиль, поэтому он будет выглядеть правильно при использовании, например, в дробях или нижнем/надстрочном индексе. Те, которые не меняют стиль, будут отображаться правильно только на верхнем уровне отображаемых формул.

## 5.3. Символы, которые можно расширять по вертикали

Вертикальная расширяемость гораздо шире. В следующей таблице перечислены все символы, которые можно расширять по вертикали.

*Вертикально расширяемые символы*

|||||||
|:---:|---|:---:|---|:---:|---|
| !["Скобки"](/tex/images/java/tutorial/latex-ams-math-delim-5-1.png) | `(` `)` | !["Открывающие фигурные скобки"](/tex/images/java/tutorial/latex-ams-math-delim-5-11.png) | `\{` `\}` | !["Двойные вертикальные черты"](/tex/images/java/tutorial/latex-ams-math-delim-5-18.png) | *`\lVert` `\rVert`* |
| !["Угловые скобки"](/tex/images/java/tutorial/latex-ams-math-delim-5-2.png) | `\langle` `\rangle` | !["Закрывающие фигурные скобки"](/tex/images/java/tutorial/latex-ams-math-delim-5-11.png) | `\lbrace` `\rbrace` | !["Одиночные вертикальные черты"](/tex/images/java/tutorial/latex-ams-math-delim-5-19.png) | *`\lvert` `\rvert`* |
| !["Lgroup и Rgroup"](/tex/images/java/tutorial/latex-ams-math-delim-5-3.png) | `\lgroup` `\rgroup` | !["Открывающие квадратные скобки"](/tex/images/java/tutorial/latex-ams-math-delim-5-12.png) | `[` `]` | !["Вертикальная черта"](/tex/images/java/tutorial/latex-ams-math-delim-5-20.png) | `|` |
| !["Усы"](/tex/images/java/tutorial/latex-ams-math-delim-5-4.png) | `\lmoustache` `\rmoustache` | !["Закрывающие квадратные скобки"](/tex/images/java/tutorial/latex-ams-math-delim-5-12.png) | `\lbrack` `\rbrack` | !["Вертикальная черта"](/tex/images/java/tutorial/latex-ams-math-delim-5-20.png) | `\vert` |
| !["Стрелка вниз"](/tex/images/java/tutorial/latex-ams-math-delim-5-5.png) | `\Downarrow` | !["Открытые потолочные кронштейны"](/tex/images/java/tutorial/latex-ams-math-delim-5-13.png) | `\lceil` `\rceil` | !["Вертикальная стрелка"](/tex/images/java/tutorial/latex-ams-math-delim-5-20.png) | `\arrowvert` |
| !["Стрелка вверх"](/tex/images/java/tutorial/latex-ams-math-delim-5-6.png) | `\Uparrow` | !["Закрытые напольные кронштейны"](/tex/images/java/tutorial/latex-ams-math-delim-5-14.png) | `\lfloor` `\rfloor` | !["Скобная вертикальная черта"](/tex/images/java/tutorial/latex-ams-math-delim-5-21.png) | `\bracevert` |
| !["Стрелка вверх-вниз"](/tex/images/java/tutorial/latex-ams-math-delim-5-7.png) | `\Updownarrow` | !["Двойные открывающие скобки"](/tex/images/java/tutorial/latex-ams-math-delim-5-15.png) | ***`\llbracket` `\rrbracket`*** | !["Двойная стрелка-вертикальная черта"](/tex/images/java/tutorial/latex-ams-math-delim-5-22.png) | `\Arrowvert` |
| !["Одиночная стрелка вниз"](/tex/images/java/tutorial/latex-ams-math-delim-5-8.png) | `\downarrow` | !["Косая черта"](/tex/images/java/tutorial/latex-ams-math-delim-5-16.png) | `/` | !["Двойная вертикальная линия"](/tex/images/java/tutorial/latex-ams-math-delim-5-22.png) | `\|` |
| !["Одиночная стрелка вверх"](/tex/images/java/tutorial/latex-ams-math-delim-5-9.png) | `\uparrow` | !["Обратная косая черта"](/tex/images/java/tutorial/latex-ams-math-delim-5-17.png) | `\backslash` | !["Двойная вертикальная линия"](/tex/images/java/tutorial/latex-ams-math-delim-5-22.png) | `\Vert` |
| !["Одиночная стрелка вверх-вниз"](/tex/images/java/tutorial/latex-ams-math-delim-5-10.png) | `\updownarrow` | | `.` | !["Знак квадратного корня"](/tex/images/java/tutorial/latex-ams-math-delim-5-23.png) | `\sqrtsign` |


> *Символы, выделенные курсивом, требуют либо пакета `amsmath`, либо, если они дополнительно набраны жирным шрифтом, пакета `stmaryrd`. Точка (.) сама по себе не является расширяемым символом, но ее можно использовать для создания «невидимого» разделителя. Символ `\sqrtsign` нельзя использовать с `\left`, `\right` или `\middle`.*

> *Синонимы: [ - `\lbrack`, `[`;	] - `\rbrack`, `]`;	{ - `\lbrace`, `\{`;	} - `\rbrace`, `\}`; | - `\vert`, `|`;	|| - `\Vert`, `\|`.*

Эти символы становятся расширяемыми только в определенных случаях. В их основе должна лежать следующая конструкция:

```tex
\left <ext-Open> <sub-formula> \right <ext-Close>
```

> Если LaTeX использует программу eTeX, то вы также можете использовать эти расширяемые символы с `\middle`.

Здесь `<ext-Open>` и `<ext-Close>` могут быть любыми символами (кроме `\sqrtsign`), перечисленными в таблице выше. Это должны быть символы, которые можно расширять, как описано в [fntguide](https://www.latex-project.org/help/documentation/fntguide.pdf). Таким образом, должен быть доступен символ, обозначающий отсутствие фактического глифа. Так получилось, что этот символ, также известный как *нулевой разделитель*, является точкой (.). Размеры реальных глифов для набора расширяемого символа выбираются так, чтобы они соответствовали высоте и глубине подформулы, лежащей между ними.

Радикальный символ `\sqrtsign` увеличивается как по вертикали, так и по горизонтали, чтобы соответствовать размеру своего аргумента. В LaTeX для получения этого символа лучше использовать команду `\sqrt`.


```tex
\[
  \sqrtsign{1 + \sqrtsign{1 + \sqrtsign{1 +
    \sqrtsign{1 + \sqrtsign{1 + \sqrtsign{1 + x}}}}}}
\]
```

![Расширяющиеся радикалы](/tex/images/java/tutorial/latex-ams-math-5-24.png)