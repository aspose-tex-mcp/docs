---
translation: true
template: /templates/_template-java.md
linktitle: LaTeX 文本字体
title:	3. 在文本中使用 LaTeX 字体的方法
weight: 30
url: /java/latex-text-fonts/
keywords: latex、latexフォント、latexテキストフォントコマンド、latex大、latexフォントサイズ
description: 本文介绍了 LaTeX 字体命令，这些命令可以独立改变不同的字体属性，以用于普通文本。
lastmod: "2026-02-28"
---

{{<section overview>}}

当您编写 LaTeX 文档时，用于组织文档的标记标签会自动选择合适的字体。例如，对于章节标题，诸如大号大小和粗体重量等字体属性由文档类定义，并在使用 `\section` 命令时应用。因此，您通常不需要直接指定字体属性。

但有时这是必要的。例如，您可能想为主文本选择不同的字体族（或其他整体字体属性）。这种更改通常只需要指定相应的宏包即可实现。

另一种情况是，当您希望将文档中的某些片段标记为特殊——例如，用于表示缩略词、示例或公司名称。如果您选择为这些片段使用无衬线字体，可以通过在公司名称周围使用 `\textsf{...}` 来实现。但更好的做法是为此定义一个新命令（比如 `\Company`）。为逻辑上不同的内容定义单独的命令，可在后续更改格式时保持一致性，操作更方便。

您可能还希望以更小的字号排版表格，以使其适应页面。由于文档类只能在一定程度上自动格式化文档，这种需求是合理的。因此，手动格式化，如插入分页符，往往是创建最终版本所必需的。遗憾的是，显式的格式化会使后续使用文档变得困难且易出错。因此，应该尽量减少在文档中直接使用改变字体的命令。这同样适用于所有视觉格式化命令。

## 3.1. 在标准 LaTeX 中如何使用字体命令

文档主体文本使用的字体称为 *主字体*、*正文字体* 或 *普通字体*。它会在文档开始时自动选择，并在某些结构中（如脚注和图形）使用。章节标题和其他逻辑标记标签会自动切换到不同的字体或字号，这取决于文档类。因此，引入正确的逻辑标记是作者唯一需要做的操作。不过，有时可能希望通过选择合适的字体手动突出显示文本的某些部分。下面讨论的命令即可实现此目的。

大多数改变字体的命令有两种形式：一种是带一个参数的命令，例如 `\textbf{...}`；另一种是声明形式，如 `\bfseries`。声明形式不带参数，而是指示 LaTeX 从此以后（直到当前的大括号组或环境结束）以特殊方式呈现。这意味着您不应该写 `\bfseries{...}`，因为这会导致从此点起到当前环境结束的所有内容都为粗体。

最好使用带一个参数的字体命令来改变文档中单个单词或短语的字体。对于更长的片段，您应该使用声明的环境形式，如下例所示：

```tex
Some words in this sentence are \begin{bfseries}typeset in bold letters.
The bold typeface\end{bfseries} continues here. 
```

![\bfseries 的环境形式](/tex/images/java/tutorial/latex-font-selection-3-1.png)

声明形式本身在定义新环境或新命令时通常更好。

> 还需要注意，带一个参数的字体命令在其参数中不允许出现段落换行。

### 文档主字体

使用 `\textnormal` 命令或 `\normalfont` 声明，可以切换回文档主字体。它们通常只出现在命令或环境的定义中，以确保无论周围环境如何，始终使用相同的字体排版。例如，排版 LaTeX 命令名称的命令如下所示：

```tex
\newcommand\Lcs[1]{{\normalfont\ttfamily\textbackslash#1}%}
```

使用 `\normalfont` 可防止即使在斜体文本中，命令名称也以斜体显示。

### 标准字体族

默认情况下，LaTeX 保持三种字体族：衬线字体族（使用 `\textrm` 调用）、无衬线字体族（使用 `\textsf` 调用）以及打字机（等宽）字体族（使用 `\texttt` 调用）。这些命令的声明形式分别是 `\rmfamily`、`\sffamily` 和 `\ttfamily`。

这些命令访问的外部字体族的具体名称取决于文档类，但可以在导言区或通过宏包进行更改。作为安装默认，衬线字体族是 **Computer Modern Roman**，无衬线族是 **Computer Modern Sans**，打字机族是 **Computer Modern Typewriter**。如果您使用不同的设置，应确保定义这些默认字体族，以便在视觉上不会冲突。还需要确保外部字体在目标输出设备的分辨率下可用。

大多数文档类将 `\textrm` 访问的衬线字体设为文档的主字体，因此 `\textrm` 并不常用。但如果文档设计者选择无衬线字体作为主字体，则 `\textrm` 将成为可选的衬线字体族。

### 标准字族系列

在 LaTeX 中，*系列*是宽度和粗细（重量）的组合。LaTeX 提供两个命令来改变系列：`\textmd` 和 `\textbf`。对应的声明分别是 `\mdseries` 和 `\bfseries`。第一个命令选择宽度和粗细均为中等的字体，而后者切换到更粗的系列。同样，实际值取决于文档类及其选项或后续宏包。在默认设置下，`\textbf` 切换到当前字体的粗体扩展版本，而 `\textmd` 返回到当前字体的中等宽度和中等粗细版本。

### 标准字形

当前字形是可以独立于其他属性更改的第三个字体属性。大多数文档的默认字形是正体（upright），可以使用 `\textup` 命令或必要时的 `\upshape` 声明来访问。

最常用的命令似乎是 `\textit` 和 `\textsc`，它们分别切换到斜体或小型大写字形。对应的声明是 `\itshape` 和 `\scshape`。

`\textsl` 命令（其声明形式为 `\slshape`）切换到倾斜字形。一个字体族通常只包含斜体或倾斜字形，尽管 Computer Modern Roman 两者都有。

在从倾斜切换回正体时，字符通常会靠得太近，特别是当最后一个倾斜字符有上升部时。应在此边界添加的额外空间称为 **斜体校正**。此空间的确切宽度取决于具体字符，存储在 `.tfm` 文件中。带参数的字体命令会自动添加斜体校正，但使用声明时必须手动使用 `\/` 插入。对于正体字体，字符的斜体校正通常为零或非常小，尽管有例外。下例展示了如何正确使用切换到倾斜字形的声明。

```tex
\raggedright
When switching back from {\itshape italic\/} or {\slshape slanted\/} shapes to an upright font one
should add the {\itshape italic correction}, except when a small punctuation character follows.
```

![斜体校正](/tex/images/java/tutorial/latex-font-selection-3-2.png)

小型大写有时用于标题或格式化姓名。对于后者，您可以例如定义命令 `\name` 如下：

```tex
\newcommand\name[1]{\textsc{#1}}
```

或者使用两条声明：

```tex
\newcommand\name[1]{{\normalfont\scshape #1}}
```

第一个命令仅切换到小型大写字形，而第二种形式首先将所有字体属性重置为默认。选择哪种方式取决于可用字体和文档类型。使用 Computer Modern 时，只有 Roman 和 Typewriter 字体族包含小型大写字形，因此在某些应用中可能更倾向于使用第二种定义，因为它会在 `\sffamily` 环境中仍使用小型大写（虽然是衬线的）。第一个命令会请求在 Computer Modern Sans 家族中使用中等系列、小型大写、已成形的字体。这种字体不存在，LaTeX 会先将字形属性改为默认，从而找不到小型大写。因此，您将得不到小型大写效果。

另一个 LaTeX 的特殊字形命令是 `\emph`，用于在普通文本中强调片段。其声明形式是 `\em`。传统上，文本中的强调词会使用斜体；但如果在已经斜体的文本片段中需要强调，通常会切换回正体。`\emph` 命令通过在当前字体为正体时切换到 `\itshape`，而在当前字体已为倾斜（即 `\itshape` 或 `\slshape`）时切换到 `\upshape`，从而实现此约定。因此，用户无需关心使用 `\emph` 或 `\em` 时文本的当前状态。

```tex
{\em Nevertheless, one has to be careful about the\/ {\em proper\/} use of italic corrections
on both ends of the emphasized text}. It is therefore better to use the \verb=\emph= command,
which \emph{automatically} takes care of the italic correction on both sides.
```

![强调文本片段](/tex/images/java/tutorial/latex-font-selection-3-3.png)

### 标准字号

LaTeX 中有 10 种改变字号的命令。这些命令没有对应的带参数形式，因为字号变化通常只在命令定义中使用。

![标准字号](/tex/images/java/tutorial/latex-font-selection-3-4.png)

这些命令选择的字号取决于文档类的设置，可能还受选项（例如 `11pt`）的影响。一般来说，`\normalsize` 对应文档的主字号，字号改变命令形成有序序列，以 `\tiny` 为最小，向上到 `\Huge` 为最大。可能出现多个命令对应同一字号的情况。例如，当选择较大的 `\normalsize` 时，`\Huge` 可能与 `\huge` 相同。但顺序始终被遵守。

用于主文本的字号改变命令（即 `\normalsize`、`\small` 和 `\footnotesize`）通常会影响列表和公式的间距。因此，若要更改它们的行为，不应仅通过调用 `\fontsize` 来替换其定义，而应从原始定义出发，正如 `classes.dtx` 中所记录的那样。

## 3.2. 如何组合标准字体命令

正如前面所示，标准的改变字体的命令和声明可以组合使用，从而选取符合组合后属性的字体。见下例：

```tex
One can typeset a text {\sffamily\bfseries\large in a large sans serif
bold typeface} but note the unchanged leading! \LaTeX{} uses the value
in force at the \emph{end} of the paragraph!
```

![LaTeX 字体命令组合](/tex/images/java/tutorial/latex-font-selection-3-5.png)

内部工作原理是：`\sffamily` 切换到无衬线默认族，然后 `\bfseries` 在该族中切换到默认的粗体系列，最后 `\large` 选择大号字号但保持其他属性不变。因为 `\large` 的作用范围在段落结束前结束，所以行距（leading）保持不变。即使这些中间字体从未实际使用，仍会加载相应的字体度量文件。在上述示例中，它们分别是 “无衬线中等 10pt” 在 `\sffamily` 后，“无衬线粗体扩展 10pt” 在 `\bfseries` 后，最后是 “无衬线粗体扩展 14pt”，即实际使用的字体。因此，此类高级命令可能会强制 LaTeX 加载其实并未使用的字体。首次使用给定组合时仅会有少量的处理速度损失。但如果您有许多此类不同组合，最好考虑使用[原始字体改变声明](/tex/{{lang.url-fragment}}java/latex-fonts-low-level/)来定义它们。

## 3.3. 字体命令与声明的比较

带参数的字体改变命令全部以 `\text...` 开头（`\emph` 除外），以示它们用于普通文本。使用这些命令而非声明形式的优势在于能够保持与其他 LaTeX 构造的一致性。它们旨在在特定的族、系列或字形中排版短块文本。下表展示了这些命令的效果。

![命令与声明](/tex/images/java/tutorial/latex-font-selection-3-6.png)

这些命令的另一优势是会自动在参数两侧插入必要的斜体校正。因此，您无需担心在更改字体时遗漏斜体校正。

自动插入的斜体校正在极少数情况下会不适用。通常建议在字体变化后直接跟随小标点（逗号或句号）时省略斜体校正。您可以定义在何种情况下应抑制斜体校正。这通过在 `\nocorrlist` 列表中指定应取消前置斜体校正的字符来实现。该命令的默认定义为

```tex
\newcommand{\nocorrlist}{,.}
```

也可以在单独实例中抑制斜体校正。为此提供了 `\nocorr` 命令。请将 `\nocorr` 放在 `\text...` 命令参数的左端或右端，视需要抑制哪一侧的斜体校正而定。

```tex
\emph{When using the \LaTeX{} high-level font commands, the \emph{proper} use of
italic corrections is automatically taken care of}. Only \emph{sometimes} one has
to help \LaTeX{} by adding a \verb=\nocorr= command.
```

![斜体校正](/tex/images/java/tutorial/latex-font-selection-3-7.png)

相反，声明形式往往更适合用于定义您自己的命令或环境。

```tex
% Part of the preamble
\newenvironment{bfitemize}{\begin{itemize}%
  \normalfont\bfseries\raggedright}{\end{itemize}}
-----------------------------------------------
\begin{bfitemize}
\item This environment produces boldface items.
\item It is defined in terms of \LaTeX's
\texttt{itemize} environment and NFSS declarations.
\end{bfitemize}
```

![带粗体项目的列表](/tex/images/java/tutorial/latex-font-selection-3-8.png)

## 3.4. 如何访问字体的所有字符

即使某字符在字体中存在，有时也无法直接从键盘输入。许多有用的字符可通过类似 `\ss` 或 `\AE` 的命令访问。某些字符可以通过字母序列隐式生成，如 `ffi` 产生 “ffi” 连字，`---` 产生标准 TeX 字体中的长破折号。

此外，`\symbol` 命令允许通过在当前编码方案中给出字符的编号（十进制、八进制（前缀 `'`）或十六进制（前缀 `"`））来访问任意字符。

```tex
\fontencoding{T1}\selectfont
-----------------------------------------------
In the font encoding (\texttt{T1}), characters like \symbol{"DE},
symbol{'237}, and \symbol{32} are included and can be accessed with
the \verb=\symbol= command.
```

![`\symbol` 命令](/tex/images/java/tutorial/latex-font-selection-3-9.png)

## 3.5. 如何更改默认文本字体

如果您想轻松修改文档的整体外观，可以使用 LaTeX 内置的钩子来修改前面讨论的高级字体改变命令的行为。这些钩子的值可以在宏包文件或文档的导言区通过 `\renewcommand` 设置。以下是这些钩子的列表：

![高级字体改变的钩子](/tex/images/java/tutorial/latex-font-selection-3-10.png)

例如，在导言区写下

```tex
\renewcommand\familydefault{cmss}
```

整个文档将使用 Computer Modern Sans，因为此重新定义更改了 LaTeX 用于主字体的字体族。详细来说，文档主字体由 `\encodingdefault`、`\familydefault`、`\seriesdefault` 和 `\shapedefault` 的值决定。这意味着您必须确保这些命令的定义能够组合成 LaTeX 内部表格中存在的字体字形。

`\encodingdefault`（默认 `OT1`）的默认值实际上是出于兼容性考虑。这意味着 LaTeX 假设大多数字体使用原始编码。在大多数情况下，使用 `T1` 编码更好，因为它包含许多 OT1 不具备的附加字形，并且能够正确断字带有重音字符的单词。如今，一些字体根本不支持 `OT1`，因为它们是为使用 `T1` 设计的。

重要的是要记住，并非每种字体都可以作为文档编码的默认。前提是编码必须在其标准位置包含大多数可见的 ASCII 字母。可以通过加载 `fontenc` 宏包并提供一个或多个选项来更改 `\encodingdefault`。

`\familydefault` 的初始设置意味着更改 `\rmdefault` 会隐式地将 `\familydefault` 改为新的值，只要没有为 `\familydefault` 定义特殊设置。但如果改变了 `\familydefault`，`\rmdefault` 则不受影响。
