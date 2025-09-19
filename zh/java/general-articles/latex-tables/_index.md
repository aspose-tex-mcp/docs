---
translation: true
template: /templates/_template-java.md
linktitle: 乳胶表
title: 乳胶中的桌子
weight: 50
url: /java/latex-tables/
keywords: 乳胶桌，表格环境，乳胶桌设计，乳胶格式，乳胶中排版桌，乳胶桌布局，乳胶桌间距，自定义乳胶表，乳胶桌对齐，乳胶桌中的多餐和多餐
description: 本文是在乳胶中创建功能，读者友好，视觉上的专业表的快速指南。
lastmod: "2025-06-10"
---

{{<section overview>}}

## 1. 简介

桌子在增强学术和专业文档的清晰度，组织和视觉吸引力方面起着重要作用。它们是一种以结构化且易于消化的格式呈现复杂数据，比较和关系的有力方法。这是其重要性的简要概述：

1. **数据摘要**：表提供了信息的凝结表示，否则可能需要多个段落才能解释。它们允许作者简洁地展示大量数据，从而使读者更容易理解关键点。

2. **清晰的可视化**：可以使用表更有效地介绍复杂的数据，例如统计数据，调查结果和实验结果。表格格式可帮助读者更轻松地识别趋势，模式和离群值。

3. **比较分析**：表可以并排对不同数据集的比较。无论是比较产品规格，财务绩效还是研究变量，表都可以帮助读者一目了然地得出有意义的结论。

4. **逻辑组织**：表提供了将数据分离为行和列的逻辑结构。该组织促进了具有不同类别的数据的呈现，从而使读者可以轻松地导航和查找特定信息。

5. **数据完整性**：在学术和专业背景下，数据准确性至关重要。表使作者能够提供原始数据，从而消除了以叙事形式传达数据时可能出现的误解的风险。

6. **参考和引用**：当表格张贴良好并正确地引用表时，它们会成为文档中有价值的参考点。作者在讨论发现时可以参考特定表，从而使读者更容易遵循该论点。

7. **视觉参与**：精心设计的桌子分解了文本内容的单调，视觉上吸引了读者，并帮助他们保持感兴趣。他们为文档的整体美学和专业精神做出了贡献。

8. **沟通效率**：忙碌的专业人员和研究人员通常需要快速提取信息。表允许他们查看数据并查找特定详细信息，而不必阅读文本段落。

9. **标准化**：在学术研究中，经常使用标准化表来介绍实验方法，结果和统计分析。这确保了跨越出版物的一致性，并有助于研究的可重复性。

本质上，表充当信息中心，有效地展示了数据驱动的见解，同时保持结构化和读者友好的格式。它们在传达复杂细节的同时确保清晰度和可及性的作用使它们成为学术和专业沟通中必不可少的工具。

现在，让我们转向乳胶作为一个强大的排版系统，使作者可以将自己的想法转换为精美的文档。乳胶超越了传统文字处理器的局限性，在处理表格结构时，提供了精确，优雅和多功能性的领域。
从本质上讲，乳胶不仅仅是文档准备工具。这是一种将版式与技术结合在一起的艺术形式。无论您是创建学术论文，报告，演示文稿，甚至书籍，乳胶都在生产不仅在美学上令人愉悦的文档方面都擅长传达信息。它的掌握在于其复杂表格结构的无缝集成，这是各个领域中数据表示的骨干。

使用乳胶，表格中的信息排列超出了排行的简单网格。取而代之的是，这是一个精心策划的交响曲，对齐，间距和样式协调以提供精致的数据表示。乳胶中的表格结构成为视觉叙事，以优雅和精确的方式传达复杂的数据集，关系和比较。

通过提供大量针对表格设计的工具和包装，乳胶将数据转换为视觉讲故事。从控制列的宽度到调整单元边界和阴影，Latex的自定义水平可确保每个表与文档的目的完美对齐。对于那些从事数学，技术或科学内容的人来说，乳胶在表单元中无缝包含方程式和符号会提高复杂思想的交流。

然而，乳胶的力量超出了仅仅是美学的范围。它通过交叉引用机制引入了效率，在文档中制造了桌子的导航地标。此外，乳胶的软件包允许创建跨越多行或列的复杂布局，从而适应最苛刻的数据演示。

您越深入到乳胶的世界中，您探索的功能就越细微；使乳胶成为科学家，专业人士和研究人员的必不可少工具的功能。您深入研究设计表的艺术，这些表可以有说服力地引起人们的注意，呈现信息，并为文档的整体影响做出贡献。


## 2. 乳胶的基础知识

乳胶中表的基本概念围绕着“表格”环境，您在其中定义列，行及其内容以结构化且视觉上令人愉悦的格式组织和呈现数据。

乳胶中表的基本结构涉及以下组件：

1. **开始“表格环境”**：要创建表，您将表内容包装在``表格环境中''。此环境指定了表的布局和结构。

2. 列规范：在 `tabular` 环境中，您可以使用列说明符定义列数及其对齐方式。常用的说明符包括 `l`（左对齐）、`c`（居中）和 `r`（右对齐）。您还可以指定 LaTeX 应使用垂直线分隔哪些列，以及应绘制哪些垂直外边框。

3. **行内容**：表格的每一行都是通过指定行内每个单元格的内容来创建的。单元格之间用 `&` 符号分隔，每行以 `\\` 命令结尾。

4. **水平线**：您可以使用`\ hline`命令添加水平线和水平外边界。这增强了表的视觉结构。

### 简单的例子

这是乳胶表的基本示例：

```tex
\begin{tabular}{|c|c|c|}                             \hline
    Header 1 & Header 2 & Header 3 \\                \hline
    Row 1, Cell 1 & Row 1, Cell 2 & Row 1, Cell 3 \\ \hline
    Row 2, Cell 1 & Row 2, Cell 2 & Row 2, Cell 3 \\ \hline
\end{tabular}

```

在此示例中，“表格”环境用于创建一个带有三列的表，每个列中居中(`c`)。排版的结果如下：

<a href="/tex/images/java/tutorial/latex-tables-1.jpg" style="display:inline-block;width:100%;">![示例输出](/tex/images/java/tutorial/latex-tables-1.jpg)</a>

以下示例显示了如何使用左右对齐列创建表。

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

右外边框是双重的，标头也通过双线与桌子分开，没有垂直线将柱分开。

<a href="/tex/images/java/tutorial/latex-tables-2.jpg" style="display:inline-block;width:100%;">![示例输出](/tex/images/java/tutorial/latex-tables-2.jpg)</a>

您还可以绘制从左到右跨越整个桌子的水平线。

```tex
\begin{tabular}{|r|l|}         \hline
  9D5 & hexadecimal \\
  4725 & octal \\              \cline{2-2}
  1001 1101 0101 & binary \\   \hline \hline
  2517 & decimal \\            \hline
\end{tabular}
```

在这里，`\ cline {i-j}`命令告诉乳胶从i <sup> th </sup>列绘制一条线，到J <sup> th </sup>列。

<a href="/tex/java/latex-tables/latex-tables-3.jpg" style="display:inline-block;width:100%;">![示例输出](latex-tables-3.jpg)</a>

表中的列可能具有固定宽度，在这种情况下，它们被称为 *段落*列。要创建此类列，请使用`p`指示符，然后使用括号中的列宽度。考虑以下示例：

```tex
\begin{tabular}{|p{3cm}|p{2cm}|}            \hline
  A short text. & A very very long text. \\ \hline
  A very very long text. \newline And some more text in a new line. & A short text. \\ \hline
\end{tabular}
```

请注意使用“ \ newline”命令的使用。

<a href="/tex/java/latex-tables/latex-tables-4.jpg" style="display:inline-block;width:100%;">![示例输出](/tex/images/java/tutorial/latex-tables-4.jpg)</a>

包含“数组”软件包，还有两个选项可用于固定宽度列：`m {width}` - 与`p {width}`相同，但垂直将中间的单元格内容对齐；
`b {width}` - 与`p {width}`相同，但垂直将底部的单元格内容对齐。

在极少数需要在段落中包含表的情况下，您可以指定表相对于封闭文本行的基线的位置。为此，您使用`t'，`c`(默认)或`b`选项将基线对齐到表的顶部，中心或底部。例如，

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

在这里，我们告诉乳胶，基线应与桌子的底部保持一致。

<a href="/tex/java/latex-tables/latex-tables-5.jpg" style="display:inline-block;width:100%;">![示例输出](/tex/images/java/tutorial/latex-tables-5.jpg)</a>

### 定义多个列

当您的表包含相同对齐的列时，您可以使用`*{num} {format}`语法将它们全部定义在一个列。当您的表有许多列时，这特别有用。

```tex
\begin{tabular}{l*{7}{c}r}
  Employee   & Sun & Mon & Tue & Wed & Thu & Fri & Sat & Total \\ \hline
  John Doe   &     &  x  &     &     &     &  x  &     &   2   \\
  Dean Jones &  x  &     &  x  &     &  x  &     &     &   3   \\
  Chris Cross&     &     &     &  x  &     &     &     &   1   \\
  Pete Brad  &     &     &     &     &     &     &  x  &   1
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-6.jpg" style="display:inline-block;width:100%;">![示例输出](/tex/images/java/tutorial/latex-tables-6.jpg)</a>

### 使用`> {\ commmand}`and`<{\ command}`列规范

指定列的另一种方法是使用`> {\ command}`对于 *在 *每个列元素之前正确执行 *的命令，并且在 *每个列元素后正确执行 *执行的命令。当您在文档序言中包含“阵列”软件包时，可以使用。在下面的示例中，我们使用此语法将两个列中的每条中心中心，并以粗体面键入第一个。

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

<a href="/tex/java/latex-tables/latex-tables-7.jpg" style="display:inline-block;width:100%;">![示例输出](/tex/images/java/tutorial/latex-tables-7.jpg)</a>

## 3. 定制表布局

在乳胶表中，调整间距对于确保表看起来良好且视觉上吸引人至关重要。适当的间距可以增强可读性并防止内容拥挤。以下是乳胶表中间距调整的一些关键方面：

### 柱间间距

乳胶自动在列之间添加一些空间。要调整列间空间，您可以在表格环境之前使用`\ setLength {\ tabcolsep} {value}`命令。增加值会增加列之间的空间。默认值为“ 6pt”。

### 行间间距

为了增加行之间的空间，您可以使用`\ renewcommand {\ arrayStretch} {value} {value}`命令在`tagular`环境之前。增加价值会使行分开，从而增强了桌子的垂直间距。默认值为`1.0`。

您也可以在线路终止器后明确使用胶水明确指定跳线。

```tex
\begin{tabular}{cl} \hline
  Level & Complexity \\ [1cm]
  1 & Simple \\
  2 & Intermediate \\
  3 & Complex \\ \hline
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-8.jpg" style="display:inline-block;width:100%;">![示例输出](/tex/images/java/tutorial/latex-tables-8.jpg)</a>

### 使用`@'和`！'表达

在文档序言中包含“数组”软件包，您可以使用`@{...}`or`or`or`！{...}`构造指定列分隔符。

他们通常以一些文本为参数，当将其附加到列上时，他们会在该单元格之前和/或之后自动将其插入该列中的每个单元格中。 `@{...}`命令用指定为参数的内容代替了柱间空间。通过将参数留为空，您可以抑制柱间空间。

让我们以以下代码指定的基本表：

```tex
\begin{tabular}{|l|l|}
  \hline
  1.1 & 1.2 \\ \hline
  2.1 & 2.2 \\
  \hline
\end{tabular}
```

通过改变列描述，我们将获得以下结果：

<a href="/tex/java/latex-tables/latex-tables-9.jpg" style="display:inline-block;width:100%;">![示例输出](/tex/images/java/tutorial/latex-tables-9.jpg)</a>

为了保留初始间距，您可以使用`！{...}`。

<a href="/tex/java/latex-tables/latex-tables-10.jpg" style="display:inline-block;width:100%;">![示例输出](/tex/images/java/tutorial/latex-tables-10.jpg)</a>

这是与小数点对齐的浮点数列的示例：

```tex
\begin{tabular}{r@{.}l}
  3 & 14159 \\
  16 & 2 \\
  123 & 456 \\
\end{tabular}

```

<a href="/tex/java/latex-tables/latex-tables-11.jpg" style="display:inline-block;width:100%;">![示例输出](/tex/images/java/tutorial/latex-tables-11.jpg)</a>

### 使用“ dcolumn”包

可以使用“ DCOLUMN”软件包将小数分离器上的列集中在小数分离器上，该软件包为浮点数提供了一个新的列规范。在以下示例中说明了使用此软件包的简单方法：

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

<a href="/tex/java/latex-tables/latex-tables-12.jpg" style="display:inline-block;width:100%;">![示例输出](/tex/images/java/tutorial/latex-tables-12.jpg)</a>

请注意，小数点对齐的列是在数学模式下排版的，因此在上面的示例中，列标题使用了 `\mathrm`。此外，小数点对齐列中的文本（例如，表头）将在小数点分隔符前右对齐（假设文本中没有小数点分隔符）。虽然这对于非常短的文本或数字列标题来说可能没问题，但在上面的示例中，它看起来很麻烦。解决方案是使用下面描述的 `\multicolumn` 命令，指定单个列及其对齐方式。例如，要在上例中将表头 *Decimal* 居中放置在其列上，表格本身的第一行应该是 `Left&Right&Center&\multicolumn{1}{c}{Decimal}\\`。

## 4. 合并细胞

可以通过水平和/或垂直合并细胞来获得稍微复杂的表格。

### 跨越多列的单元

使单元格跨越多列的命令的一般形式为：`\multicolumn{num_cols}{alignment}{contents}`。其中，`num_cols` 表示要合并的列数；`alignment` 可以是 `l`、`c`、`r`，或者（如果要进行文本换行）`p{width}`。`contents` 表示要放入该单元格的数据。

这是一个简单的示例：

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

<a href="/tex/java/latex-tables/latex-tables-13.jpg" style="display:inline-block;width:100%;">![示例输出](/tex/images/java/tutorial/latex-tables-13.jpg)</a>

### 跨越多行的单元

要使单元跨越多行，您需要包括``Multirow``软件包。该软件包提供以下命令：`\ multirow {num_rows} {width} {contents}`。

在这里，`num_rows`是要合并的行数。 ``宽度``是单元格宽度(对于内容的自然宽度)，而``内容``是要在单元格中排除的实际数据。

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

<a href="/tex/java/latex-tables/latex-tables-14.jpg" style="display:inline-block;width:100%;">![示例输出](/tex/images/java/tutorial/latex-tables-14.jpg)</a>

您需要记住，当使用`\ Multirow`命令时，都必须在每个随后的行中插入每个适当单元格的空白条目，以要跨越。

### 在两个方向上跨越细胞

下面的示例演示了如何同时跨越两个方向并正确绘制边界：

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

命令`\多柱{1} {`用于绘制垂直左右边框。尽管它与`\ sultirow {2} {*} {...}`结合使用，但它仍然绘制仅跨第一行的垂直边界。为了弥补这一点，我们添加了`\多柱{1} {`在由`mutltirow`跨越以下行中添加。

<a href="/tex/java/latex-tables/latex-tables-15.jpg" style="display:inline-block;width:100%;">![示例输出](/tex/images/java/tutorial/latex-tables-15.jpg)</a>

## 5. 桌子大小

`graphICX`软件包提供了命令`\ resizebox {width} {height} {object} {object} {可以与``tagular`环境一起使用，以将表拉伸或缩小表至指定的宽度和高度。在下面的示例中，我们将表调整到12厘米的宽度，同时保持纵横比。

```tex
\resizebox{12cm}{!} {
  \begin{tabular}{|c|c|c|}                           \hline
    Header 1 & Header 2 & Header 3 \\                \hline
    Row 1, Cell 1 & Row 1, Cell 2 & Row 1, Cell 3 \\ \hline
    Row 2, Cell 1 & Row 2, Cell 2 & Row 2, Cell 3 \\ \hline
  \end{tabular}
}
```

<a href="/tex/java/latex-tables/latex-tables-16.jpg" style="display:inline-block;width:100%;">![示例输出](/tex/images/java/tutorial/latex-tables-16.jpg)</a>

您还可以以相同的方式使用`\ scalebox {ratio} {object} {object} {object}`，但使用比率而不是固定大小：

```tex
\scalebox{0.7}{
  \begin{tabular}...
  \end{tabular}
}
```

## 6. 定位表

如果将表放置在“表”环境中，则可以轻松地将表放在页面上。

```tex
\begin{table}[positioning_option]
  \centering
  \begin{tabular}{...}
    ...
  \end{tabular}
\end{table}
```

可用定位选项是：

`h`-将在此处 *放置桌子*。

`t`-将表位于页面的 *顶部*。

`b`-将表位于页面的 *底部*。

`p`-将表放入特殊页面(仅适用于表)。

`！` - 覆盖内部乳胶参数。

`h`-将桌子放在这个精确的位置(非常类似于``h``)。

为了水平居中，您可以在``表格环境''中使用``\ centering''命令之前的“表格”环境。

## 7. 字幕，标签和参考
您可以用一些文字标记表格。在输出中，文本将以 *表N。 *前缀为前缀，其中 *n*是乳胶自动跟踪的适当表号。为此，请使用`\ catchion`命令。也可以将标签分配给表格，以便可以从文档中的任何地方引用该表。相应的一对命令为`\ label`和`\ ref`。考虑以下示例：

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

在这里，第一行中的引用将自动替换为“ \ label”命令设置的数字。

<a href="/tex/java/latex-tables/latex-tables-17.jpg" style="display:inline-block;width:100%;">![示例输出](/tex/images/java/tutorial/latex-tables-17.jpg)</a>

## 8. 着色表

### 桌行中的变化颜色

`XColor`软件包提供了必要的命令，以产生带有其他行颜色的表。包装必须加上表选项：`\usepackage {table] {xcolor}`。
命令`\ rowcolors {starter_row} {odd_color} {even_color}`必须在`tagular`环境启动''之前发生。

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

由`XColor`软件包提供的命令`\ hiderOwColors`，从其出现到表末端的行开始。要重新激发突出显示，请使用“ \ showrowcolors”命令。

<a href="/tex/java/latex-tables/latex-tables-18.jpg" style="display:inline-block;width:100%;">![示例输出](/tex/images/java/tutorial/latex-tables-18.jpg)</a>

### 染色单个细胞

使用“ Xcolor”软件包，您还可以指定特定单元格的颜色。

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

<a href="/tex/java/latex-tables/latex-tables-19.jpg" style="display:inline-block;width:100%;">![示例输出](/tex/images/java/tutorial/latex-tables-19.jpg)</a>

### 使用“ colortbl”软件包

“ colortbl”软件包提供了`\ columnColor`命令，以在`> {...}`构造中指定列颜色。这意味着您还必须包含“数组”软件包。 (别忘了还包括“ Xcolor”软件包。)

```tex
\begin{tabular}{|>{\columncolor{green}}l|>{\color{white}\columncolor{red}}c|}
  one & two\\
  three & four
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-20.jpg" style="display:inline-block;width:100%;">![示例输出](/tex/images/java/tutorial/latex-tables-20.jpg)</a>

`\ rowcolor`命令可用于指定行颜色。必须在行开始时使用它。该命令具有与`\ columnColor`的语法相同的语法。

```tex
\begin{tabular}{l|c|}
  \rowcolor{green} one & two\\
  \rowcolor{red} three & four
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-21.jpg" style="display:inline-block;width:100%;">![示例输出](/tex/images/java/tutorial/latex-tables-21.jpg)</a>

您也可以为垂直规则着色。例如， 

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

会导致

<a href="/tex/java/latex-tables/latex-tables-22.jpg" style="display:inline-block;width:100%;">![示例输出](/tex/images/java/tutorial/latex-tables-22.jpg)</a>

注意`\ setLength {\ arrayRulewIdth} {2pt}`用于更改规则厚度的使用。

但是，颜色`\ hline`和`\ cline`有点棘手，并且可以带有额外的命令(然后也适用于垂直规则)。 `\ arrayrulecolor`命令可在全球或表中使用。在这两种情况下，它都会影响所有后续规则。因此，如果您想要垂直规则的其他颜色，则应在表序列中指定它。例如，

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

会导致

<a href="/tex/java/latex-tables/latex-tables-23.jpg" style="display:inline-block;width:100%;">![示例输出](/tex/images/java/tutorial/latex-tables-23.jpg)</a>

## 9. 建造长桌子

“表格”环境具有一个重要的缺点。它可以使用Tex的内置页面破坏算法在页面之间分配的表格。因此，如果您的桌子很长，它将仅在页面底部下方。

令人高兴的是，如今大多数发行版中提供了“ Longtable”软件包，该软件包定义了用于处理此类长桌子的“ Longtable”环境。在大多数方面，此环境的工作方式与“表格”环境相同。但是，有一些差异。

我们将在下面的示例中演示大多数“ longtable”功能，您还可以在其中找到使用“表明”和“表格”环境的差异。 (该示例还使用`verbatim`软件包用于某些文本格式，因此还必须包括在内。)

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
  \raggedleft This last column is a ``p`` column so this ``row`` of the table can take
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

这将导致两页：

<a href="/tex/java/latex-tables/latex-tables-24.jpg" style="display:inline-block;width:49%;">![示例输出](/tex/images/java/tutorial/latex-tables-24.jpg)</a>
<a href="/tex/java/latex-tables/latex-tables-25.jpg" style="display:inline-block;width:49%;">![示例输出](/tex/images/java/tutorial/latex-tables-25.jpg)</a>

如果您在Tex的第一次运行之后您没有得到相同的结果，请不要感到困惑。由于TEX的技术局限性，可能需要几次运行才能在图像中看到桌子。

## 10. 一个复杂的表示例

我们将提供一个更复杂的示例，以结合上述许多功能。

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

在“ longtable”环境之前，我们使用`dcolumn`软件包提供的`\ newColumnType`命令定义列类型。在参数中，我们使用`> {...}`符号来定义列格式。列定义依次使用命令指定颜色，对齐方式，字体和列宽度。 “ Longtable”环境本身是使用的另一个功能。在环境中，我们使用`\多列命令与先前定义的列类型一起水平合并单元格。

所有努力的结果如下：

<a href="/tex/java/latex-tables/latex-tables-26.jpg" style="display:inline-block;width:49%;">![示例输出](/tex/images/java/tutorial/latex-tables-26.jpg)</a>
<a href="/tex/java/latex-tables/latex-tables-27.jpg" style="display:inline-block;width:49%;">![示例输出](/tex/images/java/tutorial/latex-tables-27.jpg)</a>

## 11. 最佳实践和技巧

在乳胶中排版桌可能是一个细微的任务，但是遵循最佳实践和技巧可以帮助您创建清晰，美观和专业的桌子。以下是乳胶中排版表的一些宝贵的最佳实践和技巧：

1. **使用有意义的列标题：**
   - 为每一列提供清晰且描述性的标题，以引导读者理解内容。
   
2. **在小数点处对齐数值数据：**
   - 呈现数值数据时，请将小数点对齐以提高可读性。您可以使用 `dcolumn` 包来实现此目的。
   
3. **避免垂直藤蔓**：
   - 在专业出版物中，通常建议避免使用垂直线分隔列。为了清晰起见，请谨慎使用水平线。

4. **保持一致性：**
   - 在整个文档中保持一致的格式，包括字体、字体大小和表格内的对齐方式。
   
5. **最小化单元格内容：**
   - 避免在单元格中放入过多内容。如果单元格包含过多文本，请考虑将其拆分为多行或多列。
   
6. **添加标题和标签：**
   - 在表格上方或下方添加信息标题，并使用“\label”命令在文档中启用交叉引用。

7. **使用``multow``和`多列：**
    - 虽然“多行”和“多列”对于合并单元格很有用，但避免过度使用，因为它会使表格变得复杂且难以阅读。

8. **避免过度复杂的表格：**
    - 如果您的数据过于复杂，无法在单个表中显示，请考虑将其分成多个较小的表或使用其他视觉辅助工具，如图形或图表。
    
9. **若有所思地使用水平空间：**
    - 使用 `\setlength{\tabcolsep}{value}` 调整列之间的空间，使用 `\renewcommand{\arraystretch}{value}` 调整行之间的空间，以优化表格布局。

10. **校对表：**
    - 仔细校对并检查表格中的错误，包括数据准确性、格式和对齐。
    
通过实施这些最佳实践和技巧，您可以创建乳胶表不仅可以有效地传达您的数据，还可以增强文档的整体质量和专业精神。

## 12.结论

我们已经浏览了乳胶中复杂的餐桌结构世界，发现了这个排版系统提供的显着多功能性和精度。乳胶将表无缝集成到文档中的能力使用户能够与宽限和清晰度传达复杂的数据，比较以及关系。

从“表格”环境的基本概念到涉及``Multirow''longtable'软件包的先进技术，我们探索了使乳胶成为制作桌子的强大设备的工具和策略。我们已经了解了乳胶不仅如何美化我们的桌子，还可以简化数据显示，并有助于有效的沟通。 

我们强调了最佳实践的重要性：有意义的柱标头，对齐，适当的间距和一致性。这些实践使我们能够创建功能功能，而且具有视觉吸引力和专业的桌子。

当您继续探索乳胶时，请记住，掌握表结构是一门科学的艺术。这项技能可以大大增强您的学术论文，报告和演讲的影响。 

因此，凭借对乳胶的桌面功能的了解，将您的文档提升到一个新的水平。实验，完善和创新在桌子结构的领域中，让乳胶成为您在制作文档中可信赖的伴侣，这些文件有效，精美和专业传达信息。