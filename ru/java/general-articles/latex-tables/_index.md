---
translation: true
template: /templates/_template-java.md
linktitle: LaTeX Таблицы
title: Таблицы LaTeX 
weight: 50
url: /java/latex-tables/
keywords: Таблицы латех, табличная среда, дизайн таблиц LaTeX, форматирование таблиц в LaTeX, верстка таблиц в LaTeX, макет таблицы LaTeX, интервал между таблицами LaTeX, настройка таблиц LaTeX, выравнивание таблиц LaTeX, многострочная и многостолбцовая структура в таблицах LaTeX
description: Статья представляет собой краткое руководство по созданию функциональных, удобных для чтения, визуально привлекательных и профессиональных таблиц в LaTeX.
lastmod: "2024-09-24"
---

{{<section overview>}}

## 1. Введение

Таблицы играют важную роль в повышении ясности, организации и визуальной привлекательности академических и профессиональных документов. Они служат мощным способом представления сложных данных, сравнений и взаимосвязей в структурированном и легко усваиваемом формате. Вот краткий обзор их важности:

1. **Обобщение данных**. Таблицы обеспечивают сжатое представление информации, для объяснения которой в противном случае потребовалось бы несколько абзацев. Они позволяют авторам кратко представлять большие объемы данных, облегчая читателям понимание ключевых моментов.

2. **Четкая визуализация**. Сложные данные, такие как статистические данные, результаты опросов и экспериментальные данные, можно более эффективно представить с помощью таблиц. Табличный формат помогает читателям гораздо легче выявлять тенденции, закономерности и выбросы.

3. **Сравнительный анализ**. Таблицы позволяют параллельно сравнивать различные наборы данных. Будь то сравнение характеристик продукта, финансовых показателей или переменных исследования, таблицы помогают читателям с первого взгляда сделать значимые выводы.

4. **Логическая организация**. Таблицы представляют собой логическую структуру, которая разделяет данные на строки и столбцы. Такая организация облегчает представление данных, разделенных на отдельные категории, что позволяет читателям легко ориентироваться и находить конкретную информацию.

5. **Целостность данных**. В академическом и профессиональном контексте точность данных имеет первостепенное значение. Таблицы позволяют авторам представлять необработанные данные, устраняя риск неправильного толкования, который может возникнуть, когда данные передаются в описательной форме.

6. **Ссылки и цитаты**. Когда таблицы хорошо маркированы и правильно снабжены ссылками, они становятся ценными ориентирами в документе. Авторы могут ссылаться на конкретные таблицы при обсуждении результатов, что облегчает читателям понимание аргументации.

7. **Визуальное взаимодействие**. Хорошо продуманные таблицы разрушают монотонность текстового контента, визуально привлекают читателей и помогают поддерживать их интерес. Они способствуют общей эстетике и профессионализму документа.

8. **Эффективность общения**. Занятым специалистам и исследователям часто необходимо быстро извлекать информацию. Таблицы позволяют им просматривать данные и находить конкретные детали без необходимости читать абзацы текста.

9. **Стандартизация**. В академических исследованиях стандартизированные таблицы часто используются для представления экспериментальных методологий, результатов и статистического анализа. Это обеспечивает согласованность публикаций и способствует воспроизводимости исследований.

По сути, таблицы служат информационными центрами, эффективно предоставляя основанную на данных информацию, сохраняя при этом структурированный и удобный для чтения формат. Их роль в передаче сложных деталей при обеспечении ясности и доступности делает их незаменимым инструментом как в академическом, так и в профессиональном общении.

Давайте теперь обратимся к LaTeX как к мощной системе набора текста, которая позволяет авторам превращать свои идеи в красиво оформленные документы. LaTeX выходит за рамки ограничений традиционных текстовых процессоров, предлагая точность, элегантность и универсальность, которые очень заметны при обработке табличных структур.
По своей сути LaTeX — это больше, чем просто инструмент для подготовки документов; это форма искусства, сочетающая типографику с технологиями. Независимо от того, создаете ли вы научные статьи, отчеты, презентации или даже книги, LaTeX превосходно создает документы, которые не только эстетически приятны, но и передают информацию с предельной ясностью. Его мастерство заключается, среди прочего, в плавной интеграции сложных табличных структур, которые являются основой представления данных в различных областях.

Благодаря LaTeX расположение информации в таблицах выходит за рамки простой сетки строк и столбцов. Напротив, это тщательно срежиссированная симфония, в которой выравнивание, интервалы и стили гармонируют, обеспечивая изысканное представление данных. Табличные структуры в LaTeX становятся визуальными повествованиями, элегантно и точно передающими сложные наборы данных, отношения и сравнения.

Предлагая множество инструментов и пакетов, адаптированных для табличного дизайна, LaTeX преобразует данные в визуальное повествование. От управления шириной столбцов до настройки границ ячеек и заливки — уровень настройки LaTeX гарантирует, что каждая таблица идеально соответствует назначению вашего документа. Для тех, кто работает с математическим, техническим или научным контентом, бесшовное включение LaTeX уравнений и символов в ячейки таблицы повышает качество передачи сложных идей.

Тем не менее, возможности LaTeX выходят за рамки простой эстетики. Он повышает эффективность за счет механизмов перекрестных ссылок, делая таблицы навигационными ориентирами в вашем документе. Более того, пакеты LaTeX позволяют создавать сложные макеты, охватывающие несколько строк или столбцов, обеспечивая наиболее требовательное представление данных.

Чем глубже вы погружаетесь в мир LaTeX, тем больше нюансов вы изучаете; функции, которые делают LaTeX незаменимым инструментом для ученых, профессионалов и исследователей. Вы погрузитесь в искусство создания таблиц, которые привлекают внимание, убедительно представляют информацию и способствуют общему воздействию вашего документа.


## 2. Основы таблиц в LaTeX

Фундаментальная концепция таблиц в LaTeX вращается вокруг «табличной» среды, в которой вы определяете столбцы, строки и их содержимое для организации и представления данных в структурированном и визуально приятном формате.

Базовая структура таблицы в LaTeX включает следующие компоненты:

1. **Начать «табличную» среду**: Чтобы создать таблицу, вы помещаете ее содержимое в «табличную» среду. Эта среда определяет макет и структуру таблицы.

2. Спецификация столбцов. В «табличной» среде вы определяете количество столбцов и их выравнивание с помощью спецификаторов столбцов. Общие спецификаторы включают `l` для столбцов с выравниванием по левому краю, `c` для центрированных и `r` для столбцов с выравниванием по правому краю. Вы также можете указать, какие столбцы LaTeX должны быть разделены вертикальными линиями и какие вертикальные внешние границы должны быть нарисованы.

3. **Содержимое строки**: каждая строка таблицы создается путем указания содержимого каждой ячейки внутри строки. Ячейки разделяются символом `&`, а каждая строка завершается командой `\\`.



4. **Горизонтальные линии**. Вы можете добавлять горизонтальные линии для разделения строк, а также горизонтальные внешние границы, используя команду `\hline`. Это улучшает визуальную структуру таблицы.

### Простые примеры

Вот базовый пример таблицы LaTeX:

```tex
\begin{tabular}{|c|c|c|}                             \hline
    Header 1 & Header 2 & Header 3 \\                \hline
    Row 1, Cell 1 & Row 1, Cell 2 & Row 1, Cell 3 \\ \hline
    Row 2, Cell 1 & Row 2, Cell 2 & Row 2, Cell 3 \\ \hline
\end{tabular}

```

В этом примере среда «tabular» используется для создания таблицы с тремя столбцами, каждый из которых центрирован («c»). Результат верстки показан ниже:

<a href="/tex/images/java/tutorial/latex-tables-1.jpg" style="display:inline-block;width:100%;">![Пример вывода](/tex/images/java/tutorial/latex-tables-1.jpg)</a>

В следующем примере показано, как создать таблицу со столбцами, выровненными по левому и правому краю.

```tex
\begin{tabular}{|l r||}
  \hline
  Company & Income \\            \hline \hline
  Pinapple Computer & \$150M \\
  Megasoft & \$210M \\
  General Waters Ltd. & \$98M \\
  Alphamet & \$2117M \\           \hline
\end{tabular}
```

Правая внешняя граница сделана двойной, заголовок также отделен от таблицы двойной линией, вертикальная линия, разделяющая столбцы, отсутствует.

<a href="/tex/images/java/tutorial/latex-tables-2.jpg" style="display:inline-block;width:100%;">![Пример вывода](/tex/images/java/tutorial/latex-tables-2.jpg)</a>

Вы также можете рисовать горизонтальные линии, которые не охватывают всю таблицу слева направо.

```tex
\begin{tabular}{|r|l|}         \hline
  9D5 & hexadecimal \\
  4725 & octal \\              \cline{2-2}
  1001 1101 0101 & binary \\   \hline \hline
  2517 & decimal \\            \hline
\end{tabular}
```

Здесь команда `\cline{i-j}` сообщает LaTeX нарисовать линию от i<sup>th</sup> столбца до j<sup>th</sup> столбца.

<a href="/tex/java/latex-tables/latex-tables-3.jpg" style="display:inline-block;width:100%;">![Пример вывода](latex-tables-3.jpg)</a>

Столбцы в таблице могут иметь фиксированную ширину, и в этом случае они называются столбцами *абзаца*. Чтобы создать такие столбцы, вы используете спецификатор `p`, за которым следует ширина столбца в фигурных скобках. Рассмотрим следующий пример:

```tex
\begin{tabular}{|p{3cm}|p{2cm}|}            \hline
  A short text. & A very very long text. \\ \hline
  A very very long text. \newline And some more text in a new line. & A short text. \\ \hline
\end{tabular}
```

Обратите внимание на использование команды `\newline`.

<a href="/tex/java/latex-tables/latex-tables-4.jpg" style="display:inline-block;width:100%;">![Пример вывода](/tex/images/java/tutorial/latex-tables-4.jpg)</a>

При включении пакета `array` для столбцов фиксированной ширины доступны еще две опции: `m{width}` — то же, что `p{width}`, но выравнивает содержимое ячейки по вертикали посередине;
`b{width}` — то же, что `p{width}`, но выравнивает содержимое ячейки по вертикали внизу.

В том редком случае, когда таблицу необходимо включить в текст абзаца, вы можете указать положение таблицы относительно базовой линии охватывающей текстовой строки. Для этой цели вы используете параметр «t», «c» (по умолчанию) или «b», чтобы выровнять базовую линию по верху, центру или низу таблицы. Например,

```tex
This is the text of the paragraph
\begin{tabular}[t]{|r|l|}     \hline
  9D5 & hexadecimal \\
  4725 & octal \\             \cline{2-2}
  1001 1101 0101 & binary \\  \hline \hline
  2517 & decimal \\           \hline
\end{tabular}
that include a table.
```

Здесь мы сообщаем LaTeX, что базовая линия должна выравниваться по нижней части таблицы.

<a href="/tex/java/latex-tables/latex-tables-5.jpg" style="display:inline-block;width:100%;">![Пример вывода](/tex/images/java/tutorial/latex-tables-5.jpg)</a>

### Определение нескольких столбцов

Если ваша таблица содержит одинаково выровненные столбцы, вы можете определить их все по одному, используя синтаксис `*{num}{format}`. Это особенно полезно, когда в вашей таблице много столбцов.

```tex
\begin{tabular}{l*{7}{c}r}
  Employee   & Sun & Mon & Tue & Wed & Thu & Fri & Sat & Total \\ \hline
  John Doe   &     &  x  &     &     &     &  x  &     &   2   \\
  Dean Jones &  x  &     &  x  &     &  x  &     &     &   3   \\
  Chris Cross&     &     &     &  x  &     &     &     &   1   \\
  Pete Brad  &     &     &     &     &     &     &  x  &   1
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-6.jpg" style="display:inline-block;width:100%;">![Пример вывода](/tex/images/java/tutorial/latex-tables-6.jpg)</a>

### Спецификация столбца с использованием `>{\command}` и `<{\command}`

Другой способ указать столбцы — использовать `>{\command}` для команд, выполняемых непосредственно *перед* каждым элементом столбца, и `<{\command}` для команд, выполняемых сразу *после* каждого элемента столбца. Это доступно, если в преамбулу документа включен пакет array. В следующем примере мы используем этот синтаксис для центрирования каждого из двух столбцов и выделения первого из них жирным шрифтом.

```tex
\begin{tabular}{>{\centering\textbf\bgroup}p{3.5cm}<{\egroup}>|{\centering}p{3.5cm} }
  History & Geometry
  \tabularnewline \hline
  Ancient & Elementary
  \tabularnewline
  Medieval & Affine 
  \tabularnewline
  Modern & Analytic
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-7.jpg" style="display:inline-block;width:100%;">![Пример вывода](/tex/images/java/tutorial/latex-tables-7.jpg)</a>

## 3. Настройка макета таблицы

В таблицах LaTeX регулировка интервалов имеет решающее значение для того, чтобы таблица выглядела хорошо структурированной и визуально привлекательной. Правильный интервал улучшает читаемость и предотвращает скопление контента. Вот некоторые ключевые аспекты настройки интервалов в таблицах LaTeX:

### Межколонное расстояние

LaTeX автоматически добавляет пространство между столбцами. Чтобы настроить пространство между столбцами, вы можете использовать команду `\setlength{\tabcolsep}{value}` перед табличной средой. Увеличение значения увеличивает пространство между столбцами. Значение по умолчанию — `6pt`.

### Междурядье

Чтобы увеличить пространство между строками, вы можете использовать команду `\renewcommand{\arraystretch}{value}` перед средой `tabular`. Увеличение значения растягивает строки, увеличивая вертикальный интервал таблицы. Значение по умолчанию — «1.0».

Вы также можете явно указать пропуск после строки, используя клей после признака конца строки.

```tex
\begin{tabular}{cl} \hline
  Level & Complexity \\ [1cm]
  1 & Simple \\
  2 & Intermediate \\
  3 & Complex \\ \hline
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-8.jpg" style="display:inline-block;width:100%;">![Пример вывода](/tex/images/java/tutorial/latex-tables-8.jpg)</a>

### Использование выражений `@` и `!`

Включив пакет `array` в преамбулу документа, вы можете указать разделители столбцов с помощью конструкций `@{...}` или `!{...}`.

Обычно они принимают некоторый текст в качестве аргумента и при добавлении в столбец автоматически вставляют этот текст в каждую ячейку этого столбца до и/или после фактических данных для этой ячейки. Команда `@{...}` заменяет пространство между столбцами содержимым, указанным в качестве аргумента. Оставив аргумент пустым, вы можете подавить пробелы между столбцами.

Давайте возьмем базовую таблицу, заданную следующим кодом:

```tex
\begin{tabular}{|l|l|}
  \hline
  1.1 & 1.2 \\ \hline
  2.1 & 2.2 \\
  \hline
\end{tabular}
```

Варьируя описание столбца, получаем следующие результаты:

<a href="/tex/java/latex-tables/latex-tables-9.jpg" style="display:inline-block;width:100%;">![Пример вывода](/tex/images/java/tutorial/latex-tables-9.jpg)</a>

Чтобы сохранить начальный интервал, вы можете использовать `!{...}`.

<a href="/tex/java/latex-tables/latex-tables-10.jpg" style="display:inline-block;width:100%;">![Пример вывода](/tex/images/java/tutorial/latex-tables-10.jpg)</a>

А вот пример столбца чисел с плавающей запятой, выровненный по десятичной запятой:

```tex
\begin{tabular}{r@{.}l}
  3 & 14159 \\
  16 & 2 \\
  123 & 456 \\
\end{tabular}

```

<a href="/tex/java/latex-tables/latex-tables-11.jpg" style="display:inline-block;width:100%;">![Пример вывода](/tex/images/java/tutorial/latex-tables-11.jpg)</a>

### Использование пакета dcolumn

Центрировать столбец по десятичному разделителю можно с помощью пакета dcolumn, который предоставляет новый спецификатор столбца для чисел с плавающей запятой. Простой способ использования этого пакета продемонстрирован в следующем примере:

```tex
\usepackage{dcolumn}
................................................
\newcolumntype{d}[1]{D{.}{\cdot}{#1} } %the argument for d specifies the maximum number of decimal places
\begin{tabular}{l r c d{1} }
  Left&Right&Center&\mathrm{Decimal}\\
  1&2&3&4\\
  11&22&33&44\\
  1.1&2.2&3.3&4.4\\
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-12.jpg" style="display:inline-block;width:100%;">![Пример вывода](/tex/images/java/tutorial/latex-tables-12.jpg)</a>

Обратите внимание, что столбец с десятичной запятой набирается в математическом режиме, поэтому в приведенном выше примере для заголовка столбца используется `\mathrm`. Кроме того, текст в столбце с десятичной запятой (например, в заголовке) будет выровнен по правому краю перед десятичным разделителем (при условии, что в тексте нет десятичного разделителя). Хотя это может подойти для очень короткого текста или числовых заголовков столбцов, в приведенном выше примере это выглядит громоздко. Решением этой проблемы является использование описанной ниже команды `\multicolumn`, определяющей один столбец и его выравнивание. Например, чтобы центрировать заголовок *Decimal* по столбцу в приведенном выше примере, первая строка самой таблицы должна быть `Left&Right&Center&\multicolumn{1}{c}{Decimal}\\`.

## 4. Объединение ячеек

Немного более сложную таблицу можно получить, объединив ячейки по горизонтали и/или по вертикали.

### Ячейки, охватывающие несколько столбцов

Общая форма команды, которая распределяет ячейку по нескольким столбцам, следующая: `\multicolumn{num_cols}{alignment}{contents}`. Здесь `num_cols` — это количество столбцов, которые нужно объединить; `alignment` — это `l`, `c`, `r` или, для переноса текста, `p{width}`. А «содержимое» — это данные, которые вы хотите поместить в эту ячейку.

Вот простой пример:

```tex
\begin{tabular}{|l|l|}
  \hline
  \multicolumn{2}{|c|}{Available currencies} \\
  \hline
  CNY & Chinese Yuan \\
  JPY & Japanese Yen \\
  GBP & Great Britain Pound \\
  USD & US Dollar \\
  CAD & Canadian Dollar \\
  EUR & Euro \\
  \hline
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-13.jpg" style="display:inline-block;width:100%;">![Пример вывода](/tex/images/java/tutorial/latex-tables-13.jpg)</a>

### Ячейки, охватывающие несколько строк

Чтобы ячейка занимала несколько строк, вам необходимо подключить пакет multirow. Пакет предоставляет следующую команду: `\multirow{num_rows}{width}{contents}`.

Здесь `num_rows` — это количество строк, которые необходимо объединить; `width` — это ширина ячейки (`*` для естественной ширины содержимого), а `contents` — это фактические данные, которые будут напечатаны в ячейке.

```tex
\begin{tabular}{|l|l|l|}
  \hline
  \multicolumn{3}{ |c| }{Available currencies} \\
  \hline
  South America & BRL & Brazilian Real \\ \hline
  \multirow{3}{*}{Asia} & CNY & Chinese Yuan \\
   & JPY & Japanese Yen \\
   & HKD & Hong Kong Dollar \\ \hline
  \multirow{3}{*}{Europe} & EUR & Euro \\
   & GBP & Great Britain Pound \\
   & CHF & Swiss Franc \\ \hline
  Oceania & AUD & Australian Dollar \\ \hline
  \multirow{2}{*}{North America} & USD & US Dollar \\
   & CAD & Canadian Dollar \\
  \hline
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-14.jpg" style="display:inline-block;width:100%;">![Пример вывода](/tex/images/java/tutorial/latex-tables-14.jpg)</a>

Вам необходимо помнить, что при использовании команды `\multirow` вы должны вставить пустую запись для каждой соответствующей ячейки в каждой последующей строке, которую нужно объединить.

### Охват ячеек в обоих направлениях

В следующем примере показано, как одновременно охватывать ячейки в обоих направлениях и правильно рисовать границы:

```tex
\begin{tabular}{cc|c|c|c|c|l}
  \cline{3-6}
  & & \multicolumn{4}{ c| }{Primes} \\ \cline{3-6}
  & & 2 & 3 & 5 & 7 \\ \cline{1-6}
  \multicolumn{1}{ |c }{\multirow{2}{*}{Powers} } &
    \multicolumn{1}{ |c| }{504} & 3 & 2 & 0 & 1 & \\ \cline{2-6}
  \multicolumn{1}{ |c }{} &
    \multicolumn{1}{ |c| }{540} & 2 & 3 & 1 & 0 & \\ \cline{1-6}
  \multicolumn{1}{ |c }{\multirow{2}{*}{Powers} } &
    \multicolumn{1}{ |c| }{gcd} & 2 & 2 & 0 & 0 & min \\ \cline{2-6}
  \multicolumn{1}{ |c }{} &
    \multicolumn{1}{ |c| }{lcm} & 3 & 3 & 1 & 1 & max \\ \cline{1-6}
\end{tabular}
```

Команда `\multicolumn{1}{` используется для рисования как вертикальной левой, так и правой границы. Несмотря на то, что он комбинируется с `\multirow{2}{*}{...}`, он по-прежнему рисует вертикальные границы, охватывающие только первую строку. Чтобы компенсировать это, мы добавляем `\multicolumn{1}{` в следующие строки, охватываемые `mutltirow`.

<a href="/tex/java/latex-tables/latex-tables-15.jpg" style="display:inline-block;width:100%;">![Пример вывода](/tex/images/java/tutorial/latex-tables-15.jpg)</a>

## 5. Размер стола

Пакет `graphicx` предоставляет команду `\resizebox{width}{height}{object}`, которую можно использовать со средой `tabular` для растягивания или сжатия таблицы до заданной ширины и высоты. В следующем примере мы изменяем размер таблицы до ширины 12 см, сохраняя при этом соотношение сторон.

```tex
\resizebox{12cm}{!} {
  \begin{tabular}{|c|c|c|}                           \hline
    Header 1 & Header 2 & Header 3 \\                \hline
    Row 1, Cell 1 & Row 1, Cell 2 & Row 1, Cell 3 \\ \hline
    Row 2, Cell 1 & Row 2, Cell 2 & Row 2, Cell 3 \\ \hline
  \end{tabular}
}
```

<a href="/tex/java/latex-tables/latex-tables-16.jpg" style="display:inline-block;width:100%;">![Пример вывода](/tex/images/java/tutorial/latex-tables-16.jpg)</a>

Вы также можете использовать `\scalebox{ratio}{object}` таким же образом, но с соотношениями вместо фиксированного размера:

```tex
\scalebox{0.7}{
  \begin{tabular}...
  \end{tabular}
}
```

## 6. Таблицы позиционирования

Вы можете легко разместить таблицу на странице, если поместите ее в среду «таблица».

```tex
\begin{table}[positioning_option]
  \centering
  \begin{tabular}{...}
    ...
  \end{tabular}
\end{table}
```

Доступные варианты позиционирования:

`h` - разместит таблицу примерно *здесь*.

`t` — размещает таблицу вверху страницы.

`b` — позиционирует таблицу *внизу* страницы.

`p` - поместить таблицу на специальную страницу (только для таблиц).

`!` - переопределить внутренние параметры LaTeX.

`H` - поместите стол именно в это место (очень похоже на `h!`).

Чтобы центрировать таблицу по горизонтали, вы можете предварить среду `tabular` командой `\centering` в среде `table`.

## 7. Подписи, метки и ссылки

Вы можете подписать таблицу текстом. В выводе текст будет иметь префикс *Table N.*, где *N* — соответствующий номер таблицы, автоматически отслеживаемый LaTeX. Для этого используйте команду `\caption`. Также можно присвоить таблице метку, чтобы на нее можно было ссылаться из любого места документа. Соответствующая пара команд — `\label` и `\ref`. Рассмотрим следующий пример:

```tex
Table \ref{table:1} is an example of a referenced \LaTeX{} element.

\begin{table}[h!]
  \centering
  \begin{tabular}{|c|c|c|} \hline
    Header 1 & Header 2 & Header 3 \\                \hline
    Row 1, Cell 1 & Row 1, Cell 2 & Row 1, Cell 3 \\ \hline
    Row 2, Cell 1 & Row 2, Cell 2 & Row 2, Cell 3 \\ \hline
  \end{tabular}
  \caption{A caption for the table.}
  \label{table:1}
\end{table}
```

Здесь ссылка в первой строке будет автоматически заменена номером, заданным командой `\label`.

<a href="/tex/java/latex-tables/latex-tables-17.jpg" style="display:inline-block;width:100%;">![Пример вывода](/tex/images/java/tutorial/latex-tables-17.jpg)</a>

## 8. Таблицы раскрасок

### Изменение цветов в строках таблицы

Пакет xcolor предоставляет необходимые команды для создания таблиц с альтернативными цветами строк. Пакет должен быть загружен с опцией таблицы: `\usepackage{table]{xcolor}`.
Команда `\rowcolors{starting_row}{odd_color}{even_color}` должна выполняться до запуска `tabular` среды.

```tex
\begin{center}
  \rowcolors{2}{green}{pink}

  \begin{tabular}{lll}
    \multicolumn{3}{c}{The header} \\
    odd & odd & odd \\
    even & even & even\\
    \hiderowcolors odd & odd & odd \\
    \showrowcolors even & even & even\\
     even & even & even\\
  \end{tabular}
\end{center}
```

Команда `\hiderowcolors`, предоставляемая пакетом `xcolor`, отключает подсветку, начиная со строки, в которой она встречается, и до конца таблицы. Чтобы повторно активировать подсветку, используйте команду `\showrowcolors`.

<a href="/tex/java/latex-tables/latex-tables-18.jpg" style="display:inline-block;width:100%;">![Пример вывода](/tex/images/java/tutorial/latex-tables-18.jpg)</a>

### Раскрашивание отдельных ячеек

С помощью пакета xcolor вы также можете указать цвет конкретной ячейки.

```tex
\begin{tabular}{|l|l|l|}
  \multicolumn{3}{c}{The header} \\
  \hline
  \cellcolor{red} odd & odd & odd \\
  \hline
  even & \cellcolor{red} even & even\\
  \hline
  odd & odd & \cellcolor{red} odd \\
  \hline
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-19.jpg" style="display:inline-block;width:100%;">![Пример вывода](/tex/images/java/tutorial/latex-tables-19.jpg)</a>

### Использование пакета colortbl

Пакет `colortbl` предоставляет команду `\columncolor` для указания цвета столбца в преамбуле табличной среды внутри конструкции `>{...}`. Это означает, что у вас также должен быть включен пакет array. (Не забудьте также включить пакет xcolor.)

```tex
\begin{tabular}{|>{\columncolor{green}}l|>{\color{white}\columncolor{red}}c|}
  one & two\\
  three & four
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-20.jpg" style="display:inline-block;width:100%;">![Пример вывода](/tex/images/java/tutorial/latex-tables-20.jpg)</a>
Команда `\rowcolor` может использоваться для указания цвета строк. Его необходимо использовать в начале строки. Команда имеет тот же синтаксис, что и `\columncolor`.

```tex
\begin{tabular}{l|c|}
  \rowcolor{green} one & two\\
  \rowcolor{red} three & four
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-21.jpg" style="display:inline-block;width:100%;">![Пример вывода](/tex/images/java/tutorial/latex-tables-21.jpg)</a>

Вы также можете раскрасить вертикальные линейки. Например, 

```tex
\setlength{\arrayrulewidth}{2pt}
\begin{tabular}{!{\color{blue}\vline} l !{\color{blue}\vline} l !{\color{blue}\vline}
    l !{\color{blue}\vline}}
  \multicolumn{3}{c}{The header} \\
  odd & odd & odd \\
  even & even & even\\
  odd & odd & odd \\
\end{tabular}
```

приведет к

<a href="/tex/java/latex-tables/latex-tables-22.jpg" style="display:inline-block;width:100%;">![Пример вывода](/tex/images/java/tutorial/latex-tables-22.jpg)</a>

Обратите внимание на использование `\setlength{\arrayrulewidth}{2pt}` для изменения толщины линейки.

Однако раскрашивание `\hline` и `\cline` немного сложнее и доступно с помощью дополнительных команд (которые затем применяются и к вертикальным правилам). Команду `\arrayrulecolor` можно использовать глобально или внутри таблицы. В обоих случаях это влияет на все последующие правила. Поэтому, если вы хотите использовать другой цвет для вертикальных правил, вам следует указать его в преамбуле таблицы. Например,

```tex
\setlength\arrayrulewidth{2pt}
%\arrayrulecolor{blue} % to set the color for all rules
\begin{tabular}{|l!{\color{green}\vline}l|l|}
  \multicolumn{3}{c}{The header} \\
  \hline
  odd & odd & odd \\
  \arrayrulecolor{blue} \hline
  even & even & even\\
  \hline
  odd & odd & odd \\ \arrayrulecolor{red}
  \hline
\end{tabular}
```

приведет к

<a href="/tex/java/latex-tables/latex-tables-23.jpg" style="display:inline-block;width:100%;">![Пример вывода](/tex/images/java/tutorial/latex-tables-23.jpg)</a>

## 9. Создание длинных таблиц

У «табличной» среды есть один существенный недостаток. Он создает таблицы, которые невозможно разделить между страницами с помощью встроенного в TeX алгоритма разбивки страниц. Таким образом, если ваша таблица длинная, она просто разместится ниже низа страницы.

К счастью, в настоящее время в большинстве дистрибутивов имеется пакет longtable, который определяет среду longtable для обработки таких длинных таблиц. Во многих отношениях эта среда работает так же, как и «табличная» среда. Однако есть некоторые различия.

Мы продемонстрируем большинство функций longtable в следующем примере, где вы также можете найти примечания по использованию и отличия от среды table. (В этом примере также используется пакет `verbatim` для форматирования текста, поэтому его также необходимо включить.)

```tex
\begin{longtable}{|r||p{1in}|}
  \caption[An optional table caption ...]{A long table\label{long}}\\
  \hline\hline
  \multicolumn{2}{|c|}{This part appears at the top of the table}\\
  \textsc{First}&\textsc{Second}\\
  \hline\hline
  \endfirsthead % Everything above this command will appear at the beginning of the table, in the first page.

  \caption[]{(continued)}\\
  \hline\hline
  \multicolumn{2}{|c|}{This part appears at the top of every other page}\\
  \textbf{First}&\textbf{Second}\\
  \hline\hline
  \endhead % Whatever you put before this command and below \endfirsthead will be displayed at the top of the table in every page except the first one.

  \hline
  This goes at the&bottom.\\
  \hline
  \endfoot % What you put after \endhead and before this command will appear at the bottom of the table in every page except the last one.

  \hline
  These lines will&appear\\
  in place of the & usual foot\\
  at the end& of the table\\
  \hline
  \endlastfoot % The elements after \endfoot and before this command will be displayed at the bottom of the table but only in the last page where the table appears.

  \texttt{longtable} columns are specified& in the \\
  same way as in the \texttt{tabular}& environment.\\
  \verb!|r||p{1in}|! & inthis case. \\
  Each row ends with a & \verb|\\| command. \\
  The \verb|\\| command has an & optional \\
  argument, just as in & the \\
  \texttt{tabular} & environment. \\ [10pt]
  See the effect of \verb|\\[10pt]| & ? \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Also \verb|\hline| may be used, & as in \texttt{tabular}. \\
  \hline
  That was a \verb|\hline| & . \\
  \hline\hline
  That was a \verb|\hline\hline| & . \\
  \multicolumn{2}{||c||}
    {This is a \texttt{\textbackslash multicolumn\{2\}\{||c||\}}} \\
  If a page break occurs at a \verb|\hline| then & a line is drawn \\
  at the bottom of one page and at the & top of the next. \\
  \hline
  The \texttt{[t] [b] [c]} argument of \texttt{tabular} & cannot be used. \\
  The optional argument may be one of & \texttt{[l] [r] [c]} \\
  to specify whether the table should be & adjusted \\
  to the left, right, & or centrally. \\
  \hline\hline
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Some lines may take up a lot of space, like this: &
  \raggedleft This last column is a ``p'' column so this ``row'' of the table can take
  up several lines. Note however that \TeX will never break a page within such a row.
  Page breaks only occur between rows of the table or at \verb|\hline| commands.
  \tabularnewline
  Lots of lines & like this.\\
  Lots of lines & like this.\\
  Lots of lines & like this.\\
  Lots of lines & like this.\\
  Lots of lines & like this.\\
  Lots of lines & like this.\\
  \hline
  Lots of lines& like this.\\
  Lots of lines& like this.\\
\end{longtable}
```

В результате появятся две страницы:

<a href="/tex/java/latex-tables/latex-tables-24.jpg" style="display:inline-block;width:49%;">![Пример вывода](/tex/images/java/tutorial/latex-tables-24.jpg)</a>
<a href="/tex/java/latex-tables/latex-tables-25.jpg" style="display:inline-block;width:49%;">![Пример вывода](/tex/images/java/tutorial/latex-tables-25.jpg)</a>

Не смущайтесь, если вы не получите тот же результат после первого запуска TeX. Из-за технических ограничений TeX для получения таблицы, которую вы видите на изображениях, может потребоваться несколько запусков.

## 10. Пример сложной таблицы

Приведем еще один довольно сложный пример таблицы, сочетающей в себе многие из вышеперечисленных функций.

```tex
\documentclass{article}
  \usepackage{dcolumn}
  \usepackage{verbatim}
  \usepackage{colortbl}
  \usepackage[table]{xcolor}
  \usepackage{longtable}
\begin{document}
  \hbox{}\vspace{100pt} % To make the table break between pages

  \newcolumntype{A}{>{\color{white}\columncolor{red}[.5\tabcolsep]\raggedright}
    p{2cm}}
  \newcolumntype{B}{>{\columncolor{blue}[.5\tabcolsep]\color{yellow}\raggedright}
    p{3cm}}
  \newcolumntype{C}{>{\columncolor{yellow}[.5\tabcolsep]}D{.}{\cdot}{-1}}
  \newcolumntype{E}{>{\large\bfseries \columncolor{cyan}[.5\tabcolsep]}c}
  \newcolumntype{F}{>{\color{white} \columncolor{magenta}[.5\tabcolsep]}c}
  \newcolumntype{G}{>{\columncolor[gray]{0.8}[.5\tabcolsep][\tabcolsep]}l}
  \newcolumntype{H}{>{\columncolor[gray]{0.8}}l}
  \newcolumntype{I}{>{\columncolor[gray]{0.8}[\tabcolsep][.5\tabcolsep]}D{.}{\cdot}
    {-1}}
  \setlength\minrowclearance{2pt} %Before starting give a little space

  \begin{longtable}{ABC}
    \multicolumn{3}{E}{A long table example} \\
    \multicolumn{2}{F}{First two columns} & \multicolumn{1}{F}{Third column} \\
    \multicolumn{2}{F}{p-type} & \multicolumn{1}{F}{D-type (\textsf{dcolumn})}
    \endfirsthead

    \multicolumn{3}{E}{A long table example (continued)} \\
    \multicolumn{2}{F}{First two columns} & \multicolumn{1}{F}{Third column} \\
    \multicolumn{2}{F}{p-type} & \multicolumn{1}{F}{D-type (\textsf{dcolumn})}
    \endhead

    \multicolumn{3}{E}{Continued\ldots}
    \endfoot

    \multicolumn{3}{E}{The End}
    \endlastfoot

    P-column & and another one & 12.34 \\
    \multicolumn{1}{G}{Total} & \multicolumn{1}{H}{(wrong)} &
      \multicolumn{1}{I}{100.6}\\
    Some long text in the first column & bbb & 1.2 \\
    aaa & and some long text in the second column & 1.345 \\
    \multicolumn{1}{G}{Total} & \multicolumn{1}{H}{(wrong)} &
      \multicolumn{1}{I}{100.6} \\
    aaa&bbb & 1.345 \\
    Note that the colored rules in all columns stretch to accommodate large entries
      In one column. & bbb & 1.345 \\
    aaa & bbb & 100 \\
    aaa & Depending on your driver you may get unsightly gaps or lines
      where the `screens' used to produce different shapes interact
      badly. You may want to cause adjacent panels of the same color by
      specifying a larger overhang or by adding some negative space (in a
      \verb|\noalign| between rows. & 12.4 \\
    aaa & bbb & 45.3 \\
  \end{longtable}
\end{document}
```

Перед средой `longtable` мы определяем типы столбцов с помощью команды `\newcolumntype`, предоставляемой пакетом `dcolumn`. Внутри аргументов мы используем обозначение `>{...}` для определения форматов столбцов. В определениях столбцов, в свою очередь, используются команды, определяющие цвета, выравнивание, шрифты и ширину столбцов. Еще одной используемой функцией является сама среда «longtable». В среде мы используем команду `\multicolumn` для горизонтального объединения ячеек вместе с ранее определенными типами столбцов.

Результат всех усилий ниже:

<a href="/tex/java/latex-tables/latex-tables-26.jpg" style="display:inline-block;width:49%;">![Пример вывода](/tex/images/java/tutorial/latex-tables-26.jpg)</a>
<a href="/tex/java/latex-tables/latex-tables-27.jpg" style="display:inline-block;width:49%;">![Пример вывода](/tex/images/java/tutorial/latex-tables-27.jpg)</a>

## 11. Лучшие практики и советы

Набор таблиц в LaTeX может оказаться сложной задачей, но следование передовым практикам и советам поможет вам создавать четкие, эстетически приятные и профессионально выглядящие таблицы. Вот несколько ценных рекомендаций и советов по верстке таблиц в LaTeX:1. **Используйте осмысленные заголовки столбцов:**
   - Обеспечьте четкие и описательные заголовки для каждого столбца, чтобы помочь читателям понять содержание.
   
2. **Выровняйте числовые данные по десятичной запятой:**
   - При представлении числовых данных выравнивайте числа по десятичной запятой для улучшения читаемости. Для этой цели вы можете использовать пакет dcolumn.
   
3. **Избегайте вертикальных лоз**:
   - В профессиональных публикациях часто рекомендуется избегать использования вертикальных линий для разделения столбцов. Используйте горизонтальные линии умеренно для ясности.

4. **Сохраняйте последовательность:**
   - Сохраняйте единообразное форматирование во всем документе, включая шрифты, размеры шрифтов и выравнивание в таблицах.
   
5. **Свернуть содержимое ячейки:**
   - Избегайте перегрузки ячеек чрезмерным содержимым. Если ячейка содержит слишком много текста, рассмотрите возможность разделения ее на несколько строк или столбцов.
   
6. **Добавьте подписи и метки:**
   - Включите информативные подписи над или под таблицами и используйте команду `\label`, чтобы включить перекрестные ссылки в вашем документе.

7. **Осторожно используйте multirow и multicolumn:**
    - Хотя `multirow` и `multicolumn` полезны для объединения ячеек, избегайте чрезмерного использования, поскольку это может сделать таблицы сложными и трудными для чтения.

8. **Избегайте слишком сложных таблиц:**
    – Если ваши данные слишком сложны для одной таблицы, рассмотрите возможность разбить их на несколько таблиц меньшего размера или использовать другие наглядные пособия, такие как графики или диаграммы.
    
9. **Вдумчиво используйте горизонтальное пространство:**
    - Отрегулируйте расстояние между столбцами с помощью `\setlength{\tabcolsep}{value}` и пространство между строками с помощью `\renewcommand{\arraystretch}{value}` для оптимизации макета таблицы.

10. **Проверьте таблицы:**
    - Тщательно вычитайте и проверьте таблицы на наличие ошибок, включая точность данных, форматирование и выравнивание.


    
Применяя эти рекомендации и советы, вы сможете создавать таблицы LaTeX, которые не только эффективно передадут ваши данные, но и повысят общее качество и профессионализм ваших документов.

## 12. Заключение

Мы путешествовали по сложному миру табличных структур в LaTeX и обнаружили удивительную универсальность и точность, которые предлагает эта система набора текста. Способность LaTeX легко интегрировать таблицы в документы позволяет пользователям передавать сложные данные, сравнения и взаимосвязи с изяществом и ясностью.

От фундаментальных концепций «табличной» среды до продвинутых методов, включающих пакеты «multirow» и «longtable», мы изучили инструменты и стратегии, которые делают LaTeX мощным инструментом для создания таблиц. Мы узнали, как LaTeX не только украшает наши таблицы, но и оптимизирует представление данных, способствуя эффективному общению. 

Мы подчеркнули важность лучших практик: содержательных заголовков столбцов, выравнивания, правильного интервала и единообразия. Эти методы позволяют нам создавать таблицы, которые не только функциональны, но и визуально привлекательны и профессиональны.

Продолжая изучать LaTeX, помните, что освоение табличных структур — это не только наука, но и искусство. Это навык, который может значительно повысить эффективность ваших научных статей, отчетов и презентаций. 

Итак, вооружившись знаниями о возможностях таблиц LaTeX, поднимите свои документы на новый уровень. Экспериментируйте, совершенствуйте и внедряйте инновации в области табличных структур, и пусть LaTeX станет вашим надежным помощником в создании документов, которые передают информацию эффективно, красиво и профессионально.