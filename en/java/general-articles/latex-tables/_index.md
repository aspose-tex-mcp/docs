---
translation: true
template: /templates/_template-java.md
linktitle: LaTeX tables
title:  Creation and manipulation tables in LaTeX
weight: 50
url: /java/latex-tables/
keywords: LaTeX tables, tabular environment, LaTeX table design, table formatting in LaTeX, typesetting tables in LaTeX, LaTeX table layout, LaTeX table spacing, customizing LaTeX tables, LaTeX table alignment, multirow and multicolumn in LaTeX tables
description: This article is a quick guide to creating functional, reader-friendly, visually apealing and professional tables in LaTeX.
lastmod: "2024-09-20"
---

{{<section overview>}}

## 1. Introduction

Tables play an important role in enhancing the clarity, organization, and visual appeal of academic and professional documents. They serve as a powerful way to present complex data, comparisons, and relationships in a structured and easily digestible format. Here's a brief overview of their importance:

1. **Data Summarization**: Tables provide a condensed representation of information that might otherwise require multiple paragraphs to explain. They allow authors to present large amounts of data concisely, making it easier for readers to understand key points.

2. **Clear Visualization**: Complex data, such as statistical figures, survey results, and experimental findings, can be presented more effectively using tables. The tabular format helps readers identify trends, patterns, and outliers much easier.

3. **Comparative Analysis**: Tables enable side-by-side comparisons of different sets of data. Whether it's comparing product specifications, financial performance, or research variables, tables help readers draw meaningful conclusions at a glance.

4. **Logical Organization**: Tables provide a logical structure that segregates data into rows and columns. This organization facilitates the presentation of data that has distinct categories, allowing readers to easily navigate and find specific information.

5. **Data Integrity**: In academic and professional contexts, data accuracy is paramount. Tables allow authors to present raw data, eliminating the risk of misinterpretation that may arise when data is conveyed in narrative form.

6. **References and Citations**: When tables are well-labeled and properly referenced, they become valuable reference points within a document. Authors can refer to specific tables when discussing findings, making it easier for readers to follow the argument.

7. **Visual Engagement**: Well-designed tables break up the monotony of textual content, visually engage readers, and help keep them interested. They contribute to the overall aesthetics and professionalism of a document.

8. **Efficiency in Communication**: Busy professionals and researchers often need to extract information quickly. Tables allow them to view data and find specific details without having to read paragraphs of text.

9. **Standardization**: In academic research, standardized tables are frequently used to present experimental methodologies, results, and statistical analyses. This ensures consistency across publications and aids in the reproducibility of research.

In essence, tables serve as information hubs, efficiently presenting data-driven insights while maintaining a structured and reader-friendly format. Their role in conveying intricate details while ensuring clarity and accessibility makes them an indispensable tool in both academic and professional communication.

Let's now turn to LaTeX as a powerful typesetting system that allows authors to transform their ideas into beautifully crafted documents. LaTeX transcends the limitations of traditional word processors, offering a realm of precision, elegance, and versatility that is very noticeable when processing tabular structures.

At its core, LaTeX is more than just a document preparation tool; it's an art form that combines typography with technology. Whether you're creating academic papers, reports, presentations, or even books, LaTeX excels in producing documents that are not only aesthetically pleasing but also convey information with utmost clarity. Its mastery lies, among other things, in its seamless integration of intricate tabular structures, which are the backbone of data representation in various fields.

With LaTeX, the arrangement of information within tables goes beyond a simple grid of rows and columns. Instead, it's a carefully orchestrated symphony where alignment, spacing, and styling harmonize to provide a refined presentation of data. Tabular structures in LaTeX become visual narratives, conveying complex datasets, relationships, and comparisons with elegance and precision.

By offering plenty of tools and packages tailored to tabular design, LaTeX transforms data into visual storytelling. From controlling the width of columns to adjusting cell borders and shading, LaTeX's level of customization ensures that each table aligns perfectly with your document's purpose. For those working with mathematical, technical, or scientific content, LaTeX's seamless inclusion of equations and symbols within table cells elevates the communication of complex ideas.

Nevertheless, the power of LaTeX extends beyond mere aesthetics. It introduces efficiency through cross-referencing mechanisms, making tables navigational landmarks within your document. Furthermore, LaTeX's packages allow for the creation of complex layouts that span multiple rows or columns, accommodating the most demanding data presentations.

The deeper you delve into the world of LaTeX, the more nuanced features you explore; the features that make LaTeX an indispensable tool for scientists, professionals, and researchers alike. You dive into the art of designing tables that capture attention, present information persuasively, and contribute to the overall impact of your document.


## 2. Basics of Tables in LaTeX

The fundamental concept of tables in LaTeX revolves around the `tabular` environment, where you define columns, rows, and their content to organize and present data in a structured and visually pleasing format.

The basic structure of a table in LaTeX involves the following components:

1. **Begin the `tabular` Environment**: To create a table, you enclose the table content within a `tabular` environment. This environment specifies the layout and structure of the table.

2. Column Specification: Within the `tabular` environment, you define the number of columns and their alignment using column specifiers. Common specifiers include `l` for left-aligned, `c` for centered, and `r` for right-aligned columns. You can also specify which columns LaTeX should separate with vertical lines and which vertical outer borders should be drawn.

3. **Row Content**: Each row of the table is created by specifying the content for each cell within the row. Cells are separated by the `&` symbol, and each row is terminated with the `\\` command.

4.	**Horizontal Lines**: You can add horizontal lines to separate rows, as well as horizontal outer borders, using the `\hline` command. This enhances the visual structure of the table.

### Simple examples

Here's a basic example of a LaTeX table:

```tex
\begin{tabular}{|c|c|c|}                             \hline
    Header 1 & Header 2 & Header 3 \\                \hline
    Row 1, Cell 1 & Row 1, Cell 2 & Row 1, Cell 3 \\ \hline
    Row 2, Cell 1 & Row 2, Cell 2 & Row 2, Cell 3 \\ \hline
\end{tabular}

```

In this example, the `tabular` environment is used to create a table with three columns, each centered (`c`). The result of typesetting is shown below:

<a href="/tex/images/java/tutorial/latex-tables-1.jpg" style="display:inline-block;width:100%;">![Example output](/tex/images/java/tutorial/latex-tables-1.jpg)</a>

The following example shows how to create a table with left and right aligned columns.

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

The right outer border is made double, the header is also separated from the table by a double line, there is no vertical line separating the columns.

<a href="/tex/images/java/tutorial/latex-tables-2.jpg" style="display:inline-block;width:100%;">![Example output](/tex/images/java/tutorial/latex-tables-2.jpg)</a>

You can also draw horizontal lines that don't span the entire table from left to right.

```tex
\begin{tabular}{|r|l|}         \hline
  9D5 & hexadecimal \\
  4725 & octal \\              \cline{2-2}
  1001 1101 0101 & binary \\   \hline \hline
  2517 & decimal \\            \hline
\end{tabular}
```

Here, the `\cline{i-j}` command tells LaTeX to draw a line from the i<sup>th</sup> column to the j<sup>th</sup> column.

<a href="/tex/java/latex-tables/latex-tables-3.jpg" style="display:inline-block;width:100%;">![Example output](latex-tables-3.jpg)</a>

Columns in a table may have a fixed width, in which case they are called *paragraph* columns. To create such columns, you use the `p` specifier followed by the column width in braces. Consider the following example:

```tex
\begin{tabular}{|p{3cm}|p{2cm}|}            \hline
  A short text. & A very very long text. \\ \hline
  A very very long text. \newline And some more text in a new line. & A short text. \\ \hline
\end{tabular}
```

Note the use of the `\newline` command.

<a href="/tex/java/latex-tables/latex-tables-4.jpg" style="display:inline-block;width:100%;">![Example output](/tex/images/java/tutorial/latex-tables-4.jpg)</a>

With the `array` package included, two more options are available for fixed-width columns: `m{width}` - same as `p{width}`, but vertically aligns the cell content in the middle;
`b{width}` - same as `p{width}`, but vertically aligns the cell content at the bottom.

In the rare case that a table needs to be included in the text of a paragraph, you may specify the position of the table relative to the baseline of the enclosing text line. For this purpose, you use the `t`, `c` (default), or `b` option to align the baseline to the top, center, or bottom of the table. For example,

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

Here we tell LaTeX that the baseline should align to the bottom of the table.

<a href="/tex/java/latex-tables/latex-tables-5.jpg" style="display:inline-block;width:100%;">![Example output](/tex/images/java/tutorial/latex-tables-5.jpg)</a>

### Defining multiple columns

When your table contains identically aligned columns, you may define them all at ones using the `*{num}{format}` syntax. This is especially useful when your table has many columns.

```tex
\begin{tabular}{l*{7}{c}r}
  Employee   & Sun & Mon & Tue & Wed & Thu & Fri & Sat & Total \\ \hline
  John Doe   &     &  x  &     &     &     &  x  &     &   2   \\
  Dean Jones &  x  &     &  x  &     &  x  &     &     &   3   \\
  Chris Cross&     &     &     &  x  &     &     &     &   1   \\
  Pete Brad  &     &     &     &     &     &     &  x  &   1
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-6.jpg" style="display:inline-block;width:100%;">![Example output](/tex/images/java/tutorial/latex-tables-6.jpg)</a>

### Column specification using `>{\commmand}` and `<{\command}`

Another way to specify columns is to use `>{\command}` for commands executed right *before* each column element and `<{\command}` for commands executed right *after* each column element. This is available when you have the `array` package included in the document preamble. In the following example, we use this syntax to center each of two columns and to type the first one in bold face.

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

<a href="/tex/java/latex-tables/latex-tables-7.jpg" style="display:inline-block;width:100%;">![Example output](/tex/images/java/tutorial/latex-tables-7.jpg)</a>

## 3. Customizing Table Layout

In LaTeX tables, adjusting spacing is crucial to ensure that the table appears well-structured and visually appealing. Proper spacing enhances readability and prevents crowding of content. Here are some key aspects of spacing adjustment in LaTeX tables:

### Inter-column spacing

LaTeX automatically adds some space between columns. To adjust the inter-column space, you can use the `\setlength{\tabcolsep}{value}` command before the tabular environment. Increasing the value increases the space between columns. The default value is `6pt`.

### Inter-row spacing

To increase the space between rows, you can use the `\renewcommand{\arraystretch}{value}` command before the `tabular` environment. Increasing the value stretches the rows apart, enhancing the table's vertical spacing. The default value is `1.0`.

You may also specify the skip after a line explicitly using glue after the line terminator.

```tex
\begin{tabular}{cl} \hline
  Level & Complexity \\ [1cm]
  1 & Simple \\
  2 & Intermediate \\
  3 & Complex \\ \hline
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-8.jpg" style="display:inline-block;width:100%;">![Example output](/tex/images/java/tutorial/latex-tables-8.jpg)</a>

### Using `@` and `!` expressions

Having the `array` package included in the document preamble, you can specify column separators with the `@{...}` or `!{...}` constructs.

They typically take some text as its argument, and when appended to a column, they automatically insert that text into each cell in that column before and/or after the actual data for that cell. The `@{...}` command replaces the inter-column space with the content specified as the argument. By leaving the argument empty, you may suppress the inter-column spaces.

Let's take a basic table specified by the following code:

```tex
\begin{tabular}{|l|l|}
  \hline
  1.1 & 1.2 \\ \hline
  2.1 & 2.2 \\
  \hline
\end{tabular}
```

By varying the column description, we get the following results:

<a href="/tex/java/latex-tables/latex-tables-9.jpg" style="display:inline-block;width:100%;">![Example output](/tex/images/java/tutorial/latex-tables-9.jpg)</a>

To preserve the initial spacing, you may use `!{...}`.

<a href="/tex/java/latex-tables/latex-tables-10.jpg" style="display:inline-block;width:100%;">![Example output](/tex/images/java/tutorial/latex-tables-10.jpg)</a>

And here is an example of a column of floating point numbers aligned to the decimal point:

```tex
\begin{tabular}{r@{.}l}
  3 & 14159 \\
  16 & 2 \\
  123 & 456 \\
\end{tabular}

```

<a href="/tex/java/latex-tables/latex-tables-11.jpg" style="display:inline-block;width:100%;">![Example output](/tex/images/java/tutorial/latex-tables-11.jpg)</a>

### Using the `dcolumn` package

It is possible to center a column on the decimal separator using the `dcolumn` package, which provides a new column specifier for floating point numbers. The simple way to use this package is demonstrated in the following example:

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

<a href="/tex/java/latex-tables/latex-tables-12.jpg" style="display:inline-block;width:100%;">![Example output](/tex/images/java/tutorial/latex-tables-12.jpg)</a>

Note that a decimal-aligned column is typeset in math mode, hence the use of `\mathrm` for the column heading in the example above. Also, text in a decimal-aligned column (for example, the header) will be right-aligned before the decimal separator (assuming there's no decimal separator in the text). While this may be fine for very short text, or numeric column headings, it looks cumbersome in the example above. A solution to this is to use the `\multicolumn` command described below, specifying a single column and its alignment. For example, to center the header *Decimal* over its column in the above example, the first line of the table itself would be `Left&Right&Center&\multicolumn{1}{c}{Decimal}\\`.

## 4. Merging cells

A slightly more complex table can be obtained by merging cells horizontally and/or vertically.

### Cells spanning multiple columns

The general form of the command that makes a cell span over multiple columns is: `\multicolumn{num_cols}{alignment}{contents}`. Here, `num_cols` is the number of columns to merge; `alignment` is either `l`, `c`, `r`, or, to have text wrapping, `p{width}`. And `contents` is the data you want to put in that cell.

Here is the simple example:

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

<a href="/tex/java/latex-tables/latex-tables-13.jpg" style="display:inline-block;width:100%;">![Example output](/tex/images/java/tutorial/latex-tables-13.jpg)</a>

### Cells spanning multiple rows

To make a cell span multiple rows, you will need to include the `multirow` package. The package provides the following command: `\multirow{num_rows}{width}{contents}`.

Here, `num_rows` is the number of rows to merge; `width` is the cell width (`*` for the natural width of the content), and `contents` is the actual data to be typeset in the cell.

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

<a href="/tex/java/latex-tables/latex-tables-14.jpg" style="display:inline-block;width:100%;">![Example output](/tex/images/java/tutorial/latex-tables-14.jpg)</a>

You need to remember that when using the `\multirow` command, you must insert a blank entry for each appropriate cell in each subsequent row to be spanned.

### Spanning cells in both directions

The following example demonstrates how to span cells in both directions simultaneously and get borders drawn correctly:

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

The command `\multicolumn{1}{` is used to draw both vertical left and right borders. Although it is combined with `\multirow{2}{*}{...}`, it still draws vertical borders that only span the first row. To compensate for that, we add `\multicolumn{1}{` in the following rows spanned by the `mutltirow`.

<a href="/tex/java/latex-tables/latex-tables-15.jpg" style="display:inline-block;width:100%;">![Example output](/tex/images/java/tutorial/latex-tables-15.jpg)</a>

## 5. Table Size

The `graphicx` package provides the command `\resizebox{width}{height}{object}` that can be used with the `tabular` environment to stretch or shrink a table to a specified width and height. In the following example, we're resizing the table to 12cm width while maintaining the aspect ratio.

```tex
\resizebox{12cm}{!} {
  \begin{tabular}{|c|c|c|}                           \hline
    Header 1 & Header 2 & Header 3 \\                \hline
    Row 1, Cell 1 & Row 1, Cell 2 & Row 1, Cell 3 \\ \hline
    Row 2, Cell 1 & Row 2, Cell 2 & Row 2, Cell 3 \\ \hline
  \end{tabular}
}
```

<a href="/tex/java/latex-tables/latex-tables-16.jpg" style="display:inline-block;width:100%;">![Example output](/tex/images/java/tutorial/latex-tables-16.jpg)</a>

You can also use `\scalebox{ratio}{object}` in the same way, but with ratios instead of fixed size:

```tex
\scalebox{0.7}{
  \begin{tabular}...
  \end{tabular}
}
```

## 6. Positioning Tables

You can easily position a table on a page if you place it inside a `table` environment.

```tex
\begin{table}[positioning_option]
  \centering
  \begin{tabular}{...}
    ...
  \end{tabular}
\end{table}
```

Available positioning options are:

`h` - will place the table *here* approximately.

`t` - positions the table at the *top* of the page.

`b` - positions the table at the *bottom* of the page.

`p` - put the table in a special page (for tables only).

`!` - override internal LaTeX parameters.

`H` - place the table at this precise location (pretty much like `h!`).

To center a table horizontally, you can precede the `tabular` environment with the `\centering` command within a `table` environment.

## 7. Captions, Labels and References

You can caption a table with some text. In the output, the text will be prefixed with *Table N.*, where *N* is the appropriate table number automatically tracked by LaTeX. To do so, use the `\caption` command. It is also possible to assign a label to a table so that the table can be referenced from anywhere across the document. The corresponding pair of commands is `\label` and `\ref`. Consider the following example:

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

Here, the reference in the first line will be automatically replaced with the number set by the `\label` command.

<a href="/tex/java/latex-tables/latex-tables-17.jpg" style="display:inline-block;width:100%;">![Example output](/tex/images/java/tutorial/latex-tables-17.jpg)</a>

## 8. Coloring Tables

### Altering colors in table rows

The `xcolor` package provides the necessary commands to produce tables with alternate row colors. The package must be loaded with the table option: `\usepackage{table]{xcolor}`.
The command `\rowcolors{starting_row}{odd_color}{even_color}` must occur before the `tabular` environment starts.

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

The command `\hiderowcolors`, provided by the `xcolor` package, deactivates highlighting starting from the row it occurs on to the end of the table. To reactivate highlighting, use the `\showrowcolors` command.

<a href="/tex/java/latex-tables/latex-tables-18.jpg" style="display:inline-block;width:100%;">![Example output](/tex/images/java/tutorial/latex-tables-18.jpg)</a>

### Coloring individual cells

With `xcolor` package, you can also specify the color of a particular cell.

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

<a href="/tex/java/latex-tables/latex-tables-19.jpg" style="display:inline-block;width:100%;">![Example output](/tex/images/java/tutorial/latex-tables-19.jpg)</a>

### Using the `colortbl` package

The `colortbl` package provides the `\columncolor` command to specify the column color in the preamble of a tabular environment within the `>{...}` construct. This means that you must also have the `array` package included. (Don't forget to also include the `xcolor` package.)

```tex
\begin{tabular}{|>{\columncolor{green}}l|>{\color{white}\columncolor{red}}c|}
  one & two\\
  three & four
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-20.jpg" style="display:inline-block;width:100%;">![Example output](/tex/images/java/tutorial/latex-tables-20.jpg)</a>

The `\rowcolor` command can be used to specify the row colors. It must be used at the start of the row. The command has the same syntax as `\columncolor`.

```tex
\begin{tabular}{l|c|}
  \rowcolor{green} one & two\\
  \rowcolor{red} three & four
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-21.jpg" style="display:inline-block;width:100%;">![Example output](/tex/images/java/tutorial/latex-tables-21.jpg)</a>

You can also color vertical rules. For example, 

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

will result in

<a href="/tex/java/latex-tables/latex-tables-22.jpg" style="display:inline-block;width:100%;">![Example output](/tex/images/java/tutorial/latex-tables-22.jpg)</a>

Note the use of `\setlength{\arrayrulewidth}{2pt}` for changing the rule thickness.

However, coloring `\hline` and `\cline` is a bit trickier and is available with extra commands (which then apply to vertical rules as well). The `\arrayrulecolor` command may be used globally or within a table. In both cases, it affects all subsequent rules. Therefore, if you want a different color for vertical rules, you should specify it in the table preamble. For example,

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

will result in

<a href="/tex/java/latex-tables/latex-tables-23.jpg" style="display:inline-block;width:100%;">![Example output](/tex/images/java/tutorial/latex-tables-23.jpg)</a>

## 9. Building Long Tables

The `tabular` environment has one significant disadvantage. It produces tables that cannot be split between pages with the TeX's built-in page breaking algorithm. Thus, if your table is long, it will just spread below the page bottom.

Happily, there is the `longtable` package, nowadays provided in most distributions, which defines the `longtable` environment for handling such long tables. In most respects, this environment works in the same way as the `tabular` environment. There are some differences, though.

We will demonstrate most of the `longtable`'s features in the following example, where you can also find usage notes and differences from the `tabular` environment. (The example also uses the `verbatim` package for some text formatting, so it must also be included.)

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

This will result in two pages:

<a href="/tex/java/latex-tables/latex-tables-24.jpg" style="display:inline-block;width:49%;">![Example output](/tex/images/java/tutorial/latex-tables-24.jpg)</a>
<a href="/tex/java/latex-tables/latex-tables-25.jpg" style="display:inline-block;width:49%;">![Example output](/tex/images/java/tutorial/latex-tables-25.jpg)</a>

Don't be confused if you don't get the same result after the first run of TeX. Due to the technical limitations of TeX, it may take a few runs to get the table you see in the images.

## 10. A Complex Table Example

We will provide one more rather complex example of a table that combines many of the above features.

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

Before the `longtable` environment, we define column types with the `\newcolumntype` command provided by the `dcolumn` package. Within the arguments, we use the `>{...}` notation to define column formats. The column definitions, in turn, use commands specifying colors, alignment, fonts, and column widths. The `longtable` environment itself is another feature employed. Within the environment, we use the `\multicolumn` command to merge cells horizontally along with the previously defined column types.

The result of all efforts is below:

<a href="/tex/java/latex-tables/latex-tables-26.jpg" style="display:inline-block;width:49%;">![Example output](/tex/images/java/tutorial/latex-tables-26.jpg)</a>
<a href="/tex/java/latex-tables/latex-tables-27.jpg" style="display:inline-block;width:49%;">![Example output](/tex/images/java/tutorial/latex-tables-27.jpg)</a>

## 11. Best Practices and Tips

Typesetting tables in LaTeX can be a nuanced task, but following best practices and tips can help you create clear, aesthetically pleasing, and professional-looking tables. Here are some valuable best practices and tips for typesetting tables in LaTeX:

1. **Use meaningful column headers:**
   - Provide clear and descriptive headers for each column to guide readers in understanding the content.
   
2. **Align numerical data at the decimal point:**
   - When presenting numerical data, align numbers at the decimal point for improved readability. You can use the `dcolumn` package for this purpose.
   
3. **Avoid vertical vines**:
   - In professional publications, it's often recommended to avoid using vertical lines to separate columns. Use horizontal lines sparingly for clarity.

4. **Maintain consistency:**
   - Keep consistent formatting throughout your document, including fonts, font sizes, and alignment within tables.
   
5. **Minimize cell content:**
   - Avoid overloading cells with excessive content. If a cell contains too much text, consider splitting it into multiple rows or columns.
   
6. **Add captions and labels:**
   - Include informative captions above or below your tables and use the `\label` command to enable cross-referencing within your document.

7. **Employ `multirow` and `multicolumn` sparingly:**
    - While `multirow` and `multicolumn` are useful for merging cells, avoid excessive use as it can make tables complex and harder to read.

8. **Avoid overly complex tables:**
    - If your data is too complex for a single table, consider breaking it into multiple smaller tables or using other visual aids like graphs or charts.
    
9. **Use horizontal space thoughtfully:**
    - Adjust the space between columns using `\setlength{\tabcolsep}{value}` and the space between rows using `\renewcommand{\arraystretch}{value}` to optimize table layout.

10. **Proofread your tables:**
    - Carefully proofread and check for errors in your tables, including data accuracy, formatting, and alignment.
    
By implementing these best practices and tips, you can create LaTeX tables that not only effectively communicate your data but also enhance the overall quality and professionalism of your documents.

## 12. Conclusion

We've journeyed through the intricate world of table structures in LaTeX, discovering the remarkable versatility and precision this typesetting system offers. LaTeX's ability to seamlessly integrate tables into documents empowers users to communicate complex data, comparisons, and relationships with grace and clarity.

From the fundamental concepts of the `tabular` environment to advanced techniques involving `multirow` and `longtable` packages, we've explored the tools and strategies that make LaTeX a powerhouse for crafting tables. We've learned how LaTeX not only beautifies our tables but also streamlines data presentation, aiding in effective communication. 

We've emphasized the importance of best practices: meaningful column headers, alignment, proper spacing, and consistency. These practices allow us to create tables that are not just functional but visually appealing and professional.

As you continue to explore LaTeX, remember that mastering table structures is an art as much as it is a science. It's a skill that can significantly enhance the impact of your academic papers, reports, and presentations. 

So, armed with the knowledge of LaTeX's table capabilities, take your documents to the next level. Experiment, refine, and innovate in the realm of table structures, and let LaTeX be your trusted companion in crafting documents that convey information effectively, beautifully, and professionally.
