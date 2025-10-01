---
translation: true
template: /templates/_template-java.md
linktitle: 乳胶文本字体
title: 3. 如何在文本中使用乳胶字体
weight: 30
url: /java/latex-text-fonts/
keywords: 乳胶，乳胶字体，乳胶文本字体命令，乳胶大，乳胶字体大小
description: 本文涵盖了乳胶字体命令，该命令独立更改不同的字体属性，以在正常文本中使用。
lastmod: "2025-06-10"
---

{{<section overview>}}

当您编写乳胶文档时，用于构建文档的标记标签会自动选择合适的字体。例如，对于截面标题，诸如大尺寸和粗体重量之类的字体属性是由文档类定义的，并在使用`\section`命令时应用。因此，您很少需要直接指定字体属性。

但是有时是必要的。例如，您可能需要为主文本选择其他字体系列(或其他整体字体属性)。这种更改通常可以像指定适当的软件包一样简单地完成。

另一种情况是，当您想将文档的某些片段标记为特殊片段时，例如表示首字母缩写，示例或公司名称。如果您选择使用这些片段的sans serif字体，则可以通过用`\ textsf {...}`围绕公司名称来做到这一点。但是，更好的做法是为此目的定义一个新命令(例如，`\ company`)。定义逻辑上不同事物的单个命令使以后以一致的方式更改格式化变得更加容易。

您可能还想以较小尺寸的表排放桌子，以使其适合页面。由于文档类只能在一定程度上自动格式化文档，因此这种愿望是合法的。因此，像插入页面断开一样，手工制作的格式通常是创建最终版本所必需的。不幸的是，显式格式可以进一步使用该文档困难且容易出错。因此，应将文档中字体改变命令的直接使用最小化。所有视觉格式命令也是如此。


## 3.1. 如何在标准乳胶中使用字体命令

用于文档的主文本的字体称为 *主字体*， *Body Font*或 *普通字体*。它是在文档开头和某些构造(例如脚注和图形)中自动选择的。截面标题和其他逻辑标记标签自动切换到其他字体或大小，具体取决于文档类。因此，引入正确的逻辑标记是作者唯一需要的操作。但是，有时可能希望通过选择合适的字体手动突出文本的某​​些部分。这是通过下面讨论的命令来完成的。

大多数字体改变命令有两种形式：一个带有一个参数的命令，例如`\ textbf {...}`，以及声明，例如`\bfseries`。声明的形式没有任何论点，而是指示乳胶，从现在开始(直到当前的牙套或环境组的尽头)，它应该以一种特殊的方式行事。这意味着您不应该写出类似`\ bfseries {...}`的东西，因为这将使所有内容从这一点开始直至当前环境的尽头。

最好使用一个参数使用字体命令来更改文档中单个单词或简短短语的字体。对于更长的片段，您应该使用声明的环境形式，如下所示：

```tex
Some words in this sentence are \begin{bfseries}typeset in bold letters.
The bold typeface\end{bfseries} continues here. 
```

![\ bfseries的环境形式](/tex/images/java/tutorial/latex-font-selection-3-1.png)

在新环境或命令的定义中，声明形式本身通常更好。

> 同样重要的是，带有一个参数的字体命令不允许在其参数中出现段落中断。

### 主文档字体

使用命令`\ textnormal`或声明`\ stranderfont`，可以切换到主文档字体。它们通常仅在命令或环境的定义中出现在定义在同一字体中始终排版的方法时，无论周围的条件如何。例如，toxeet latex命令名称的命令看起来如下：

```tex
\newcommand\Lcs[1]{{\normalfont\ttfamily\textbackslash#1}%}
```

使用`\ normalFont`即使在斜体字体中也可以防止命令名称以斜体形式出现。

### 标准字体家庭

默认情况下，乳胶维护了三个字体系列：带有命令`\ textrm`访问的串行文本字体; sans serif文本字体，由`\ textsf`访问;以及由`\ texttt`访问的打字机(单词)字体。这些命令的声明形式分别为 `\ rmfamily`， `\sffamily`”和``\ ttfamily``。

这些命令访问的外部字体家族的确切名称取决于文档类，但可以在序言或软件包中更改。作为安装默认，Serifed Font家族是**计算机Modern Roman**，Sans Serif家族是**计算机Modern Sans**，打字机家族是**计算机现代打字机**。如果使用其他设置，则应注意定义这些默认字体系列，以便可以将字体混合而不视觉冲突。同样重要的是要确保在正确分辨率的目标输出设备的正确分辨率中可用外部字体。

大多数文档类都设置了由`\ textrm`访问的衬线字体，作为文档的主要字体，因此命令`\ textrm`不经常使用。但是，如果文档设计师选择了Sans Serif字体作为主字体，则`\ textrm`将是替代的衬线字体系列。

### 标准字体系列

在乳胶中， *系列*是两个属性的组合：宽度和重量(粗体)。乳胶允许使用两个命令更改系列：`\ textmd`和`\ textbf`。相应的声明分别为`\ mdseries`和`\bfseries`。第一个命令选择具有宽度和重量中等值的字体，而后者则切换到大胆的系列。同样，实际值取决于文档类及其选项或后续软件包。在默认设置中，`\ textbf`切换到当前字体的粗体扩展版本，而`\ textmd`返回到当前字体的中等宽度和中等重量版本。

### 标准字体形状

当前字体的 *形状*是可能独立于其他字体更改的第三个字体属性。大多数文档的默认形状是直立形状，可以使用`\ textup`命令或`\ upshape`声明访问。

最常用的命令似乎是 `\ texti`t和 `\ textsc`，分别切换到斜体或小盖字体形状。相应的声明为 `\ ishape`和 `\ scshape`。

`\ textsl`命令(其声明形式为`\ slshape`)切换到倾斜的形状。字体系列通常只包含斜体或倾斜形状，尽管计算机现代罗马都包含两者。

在一个人从倾斜到直立的地方切换，这些角色通常会太近，尤其是如果最后一个倾斜的角色具有升华。应在此边界上添加的适当额外空间称为**斜体校正**。该空间的确切宽度取决于单个字符，并存储在`.tfm`文件中。带有参数的字体命令会自动添加斜体校正，但是当使用声明时，必须使用`\/'手动插入它。对于直立字体，尽管有一些例外，但字符的斜体校正通常为零或很小。下一个示例显示了如何正确使用切换到倾斜形状的变化声明。

```tex
\raggedright
When switching back from {\itshape italic\/} or {\slshape slanted\/} shapes to an upright font one
should add the {\itshape italic correction}, except when a small punctuation character follows.
```

![斜体校正](/tex/images/java/tutorial/latex-font-selection-3-2.png)

小帽子有时用于标题或格式名称。对于后一种情况，例如，您可以定义命令`\ name`，如下：

```tex
\newcommand\name[1]{\textsc{#1}}
```

另外，您可以使用两个声明：

```tex
\newcommand\name[1]{{\normalfont\scshape #1}}
```

第一个命令只需切换到小盖的形状，而第二个形式最初将所有字体归属于其默认值。选择哪种选项取决于可用字体和文档的类型。使用计算机现代，只有罗马和打字机系列包含小盖形状，因此在某些应用中可能会首选第二个定义，因为它即使在“ \ sffamily”上下文中也会使用小帽子(尽管是衬裙)。第一个命令将在计算机现代sans家族中要求一个中型系列，小帽子，形状的字体。该字体不可用，因此乳胶会尝试通过首先将形状属性更改为默认值来找到替代品。结果，您不会得到小帽子。

另一个乳胶特殊形状命令是`\emph`命令，它强调了普通文本中的片段。它的声明形式为`\ em`。作为一种传统，文本中强调的单词是斜体的。但是，如果在本文的斜体片段中需要重点，则通常会切换回直立字体。如果当前字体是直立的，则`\ emph”命令通过切换到` `\ ithape`形状来支持此惯例，如果当前字体已经倾斜，则`\ upshape`形状的形状(即，如果形状为`\ ithape``\ Itshape`或`\ ithape`or或`\ slshape`)。因此，使用`\ emph命令或`\ em'声明时，用户不必担心文本的当前状态。

```tex
{\em 尽管如此，仍需谨慎使用\/ {\em\/}斜体校正
在强调文本的两端}。因此，最好使用 \verb=\emph= 命令，
该命令会自动处理两端的斜体校正。
```

![强调文字片段](/tex/images/java/tutorial/latex-font-selection-3-3.png)

### 标准字体尺寸

乳胶中有10个改变尺寸的命令。这些命令没有一个参数的相应命令表格，因为字体大小更改通常仅在命令的定义中使用。

![标准字体尺寸](/tex/images/java/tutorial/latex-font-selection-3-4.png)

这些命令选择的大小取决于文档类中的设置，可能取决于所指定的选项(例如，`11pt`)。通常，`\ normalalsize`对应于文档的主要尺寸，而变化的命令则形成一个有序的序列，以`\ tiny`为最小的序列，并以最大的尺寸为`\ gualt`。可能会发生多个命令是指相同的大小。例如，当选择一个大的` \ normalalSize`时，`\ gume`可能与`\ gume`相同。但是命令总是很荣幸。

主要文本大小的尺寸变化命令(即`\ normalSize`，`\small`和`\ footnotesize`)通常会影响列表和显示周围的间距。因此，要改变其行为，不应简单地通过呼叫 `\ fontsize`来替换其定义，而应从其原始定义开始，如`class.dtx`的原始定义。

## 3.2. 如何组合标准字体命令

如前所述，可以组合标准字体改变的命令和声明，从而选择与字体属性组合匹配的字体。请参阅下面的示例：

```tex
可以将文本 {\sffamily\bfseries\large 排版为大型无衬线粗体字体}，但请注意行距不变！\LaTeX{} 使用段落 \emph{end} 处的有效值！
```

![乳胶字体命令组合](/tex/images/java/tutorial/latex-font-selection-3-5.png)

在内部，`\sffamily`命令切换到sans serif默认族，然后`\bfseries`切换到该家族中的默认粗体系列，最后选择一个大尺寸，但使所有其他属性保持不变。领导似乎没有变化，因为`\ligal`的范围在段落结束之前。即使从未使用过这些字体，也为所有中间字体的字体文件加载。在上面的示例中，它们将是`\sffamily`之后的“ sans serif Mediud 10pt”，然后是“ sans serif Bold扩展10pt”之后的`\bfseries`之后，最后是“ sans sans serif Bold扩展14pt”，这是实际使用的字体。因此，这样的高级命令可以迫使乳胶的字体选择不必要地加载从未使用的字体。首次使用给定组合时，处理速度只有很小的损失。但是，如果您对这种类型的组合有许多不同的组合，则最好考虑根据[原始字体改变声明](/tex/{{lang.url-fragment}}java/latex-fonts-low-level/)定义它们。

## 3.3. 字体命令和声明比较

使用参数更换字体的命令均以`\text ...`(除`\emph`)开始，以强调它们旨在在正常文本中使用。使用此类命令代替声明形式具有与其他乳胶结构保持一致性的优势。它们旨在在特定的家庭，系列或形状中排版短篇文本。下表显示了这些命令的效果。

![命令和声明](/tex/images/java/tutorial/latex-font-selection-3-6.png)

这些命令的另一个优点是，它们会自动在论证的两侧插入任何必要的斜体校正。因此，您不必担心更改字体时会丢失斜体校正。

在很少的情况下，自动插入的斜体校正会自动插入。通常，如果直接遵循字体更改，通常建议省略斜体校正。您可以定义应抑制斜体校正的情况。这是通过指定应取消列表`\nocorrist`中前面斜体校正的字符来完成的。此命令的默认定义是

```tex
\newcommand{\nocorrlist}{,.}
```

在各个实例中也可以抑制斜体校正。为此，提供了命令`\nocorr`。请注意，您必须在``\text ...`命令的左侧或右端放置`\nocorr`，具体取决于片段的哪一侧需要抑制斜体校正。

```tex
\emph{When using the \LaTeX{} high-level font commands, the \emph{proper} use of
italic corrections is automatically taken care of}. Only \emph{sometimes} one has
to help \LaTeX{} by adding a \verb=\nocorr= command.
```

![斜体校正](/tex/images/java/tutorial/latex-font-selection-3-7.png)

相比之下，声明表通常更适合定义自己的命令或环境。

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

![带有黑色项目的列表](/tex/images/java/tutorial/latex-font-selection-3-8.png)

## 3.4. 如何访问字体的所有字符

即使字符中存在字体，有时也无法从键盘输入它。许多有用的字符可通过'\ ss”或“ \ ae”等命令访问。某些字符可以被隐式地从字母序列中产生，例如``ffi''，该字母会产生“ FFI”绑扎和``---'，它在标准Tex字体中产生了长时间的破折号。

此外，`\symbol`命令允许您通过在当前编码方案中给出数字为十进制，八分(之前``'')或十六进制之前之前命令。

```tex
\fontencoding{T1}\selectfont
-----------------------------------------------
字体编码 (\texttt{T1}) 中包含 \symbol{"DE}、
symbol{'237} 和 \symbol{32} 等字符，可以使用 \verb=\symbol= 命令访问。
```

![\符号命令](/tex/images/java/tutorial/latex-font-selection-3-9.png)

## 3.5. 如何更改默认文本字体

如果您想轻松修改文档的整体外观，则可以使用乳胶的内置挂钩，以修改前面讨论的高级字体改变命令的行为。这些挂钩的值可以在包装文件中或在文档的序言中设置，并使用`\renewcommand`设置。这是钩子的列表：

![高级字体更换的钩子](/tex/images/java/tutorial/latex-font-selection-3-10.png)

例如，如果您在序言中写信
```tex
\renewcommand\familydefault{cmss}
```

整个文档将在计算机Modern Sans中发布，因为此重新定义会改变乳胶使用的主字体的字体系列。详细说明，主文档字体由 `\encodingDefault`， `\ familyDefault` `\ seriperdefault`和`\ sheapedefault`的值确定。这意味着您必须确保以这样的方式定义这些命令，以使它们的组合指向乳胶内部表中的现有字体形状。

`\encodingDefault`(ot1')的默认值实际上具有兼容性。这意味着乳胶假设大多数字体都使用原始编码。在大多数情况下，最好使用`t1`编码了，因为它包含了许多其他带有`ot1`的额外的字形，并且允许具有重音字符的单词的正确连字符。如今，有些字体根本不支持`ot1`，因为它们旨在与`t1`一起使用。

重要的是要记住，并非所有字体都可以用作文档编码默认值。先决条件是编码必须在其标准位置中包括大多数可见的ASCII字母。可以通过使用一个或多个选项加载`fontenc`软件包来更改 `\encodingDefault`。

`\familyDefault`的初始设置意味着更改`\rmdefault`将隐式将`\familyDefault`更改为新值，只要没有定义`\familyDefault`的特殊设置。但是，如果更改`\familyDefault`，则不会受到影响。