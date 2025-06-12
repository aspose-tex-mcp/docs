---
translation: true
template: /templates/_template-java.md
linktitle: 字符编码的模型
title: 7. 乳胶的字符编码模型
weight: 70
url: /java/latex-encodings-model/
keywords: 乳胶，乳胶字体，乳胶字体编码，乳胶输入编码，乳胶输出编码，LICR对象，乳胶内部字符表示
description: 本文涵盖了乳胶中的输入和输出编码的内部和乳胶内部字符表示。
lastmod: "2025-06-10"
---

{{<section overview>}}


本文详细介绍了乳胶编码。首先讨论乳胶系统中的字符数据流。接下来，我们仔细研究乳胶中字符数据的内部表示模型，然后讨论通过输入编码映射传入数据的机制，以介绍该内部表示。最后，我们解释了如何通过输出编码将内部表示形式转换为排版所需的形式。

## 7.1. 乳胶中的字符数据流

使用乳胶处理文档开始，开始解释一个或多个源文件中存在的数据。代表文档内容的数据存储在源文件中，作为代表字符的八位字节序列。要正确解释这些八位位，用于处理文件的任何程序(包括乳胶)都必须知道抽象字符和代表它们的八位位置之间的映射。换句话说，它必须知道文件编写时使用的编码。

通过不正确的映射，除非文件仅包含在正确和不正确的编码中的子集的字符，否则所有进一步的处理都会或多或少是错误的。
乳胶在这一点上做出了一个基本的假设：几乎所有可见的ASCII字符(十进制32-126)由它们在ASCII代码表中的数字表示。

![可见的ASCII字符](/tex/images/java/tutorial/latex-font-selection-7-1.png)

此假设的原因之一是，当今使用中的大多数8位编码共享一个共同的7位平面。另一个原因是，要有效地使用TEX，ASCII的可见部分需要作为类别 *字母 *的字符处理，因为只有此类别的字符才能在Tex中的多字符命令名称中使用，或类别 *其他 *  - 因为Tex不会将其视为该类别代码的数字的一部分，因此不会将其视为数字的一部分。

当一个字符(或更确切地说是8位编号)被宣布为类别 *字母 *或 *其他 *的其他 *，则此8位编号将通过Tex透明地传递。这意味着Tex将在该数字所解决的位置处的字体中排序任何符号。

由于上述假设的结果，要用于一般文本的字体要求(大多数)可见的ASCII字符在字体中存在并根据ASCII编码进行编码。

输入文件中可能存在的所有其他8位编号(外部可见ASCII)均分配了 *Active*的类别代码，这会导致它们像Tex内部的命令一样行动。因此，乳胶可以通过输入编码转换为我们称为 *乳胶内部字符表示(LICR) *的形式。

至于Unicode的UTF8编码，它的处理方式类似。 ASCII字符代表自己，而多字节表示的起始八位字节是扫描其余八位位的输入的活动字符。如果映射映射，则结果将变成licr中的对象，或者如果给定的Unicode字符未映射，则乳胶会丢弃错误。

LICR中的对象最重要的是，7位ASCII字符的表示对于任何编码更改都是不变的，因为所有输入编码都应该相对于可见的ASCII透明。
然后，输出(或字体)编码用于将内部字符表示形式映射到用于排版的当前字体中的字形位置，或者在某些情况下启动更复杂的动作。例如，它可以在某些符号(在当前字体中的不同位置)上放置一个重音(在当前字体中的一个位置)，以获取内部字符编码中命令表示的抽象字符的打印图像。

LICR编码可在乳胶中寻址的所有可能的字符。因此，它比单个Tex字体(最多可以包含256个字形)可以表示的字符数量要大得多。在某些情况下，内部编码中的字符可以通过将字形(例如重音字符)组合使用字体来呈现。但是，当内部字符需要特殊形状时，如果字形不存在该字形，就无法伪造它。

然而，字符编码的乳胶模型支持从不同字体获取字形的自动机制，因此当前字体中缺少的字符将获得排版，只要提供合适的额外字体包含它们即可。

## 7.2. 乳胶的内部角色表示(LICR)

文本字符在内部由乳胶以三种方式之一表示。

### 表示为字符

少数字符用“自身”表示。例如，拉丁字母 A 表示为字符“A”。此类字符如上表所示。它们构成可见 ASCII 的一个子集，在 TeX 内部，所有这些字符都被分配了“字母”或“其他”的类别代码。可见 ASCII 范围内的某些字符不以这种方式表示，要么是因为它们是 TeX 语法的一部分，要么是因为它们并非存在于所有字体中。例如，如果在文本中使用“<”，则当前字体编码决定了打印输出中显示的是“<”（“T1”）还是倒置的感叹号（“OT1”）。

### 表示为字符序列

TeX 的内部连字机制可以从输入字符序列生成新字符。这实际上是字体的属性，尽管某些此类序列被明确设计为输入大多数键盘难以输入的字符的快捷方式。只有少数以这种方式生成的字符被认为属于 LaTeX 的内部表示。这些字符包括由连字 `--` 和 `---` 生成的短划线和长划线，以及由 ``` `` ``` 和 `''` 生成的左右双引号（后者通常也可以用单个 `"` 表示）。虽然大多数字体也实现了 ``` !``` 和 ``` ?``` 来生成倒置的感叹号和问号，但这并非在所有字体中都通用。这就是为什么**所有**此类字符都有一个替代的内部表示作为命令（例如，`\textendash` 或 `\textexclamdown`）。

### 表示为“字体编码特定”命令

覆盖大部分字符的乳胶内部表示字符的第三种方法是特殊的乳胶命令(或命令序列)，这些命令(或命令序列)在写入文件或放入移动参数中时仍保持不足。我们将此类特殊命令称为 *字体编码特定的命令 *，因为它们的含义取决于乳胶准备排放它们时当前使用的字体编码。正如我们将在下面讨论的那样，使用特殊声明声明此类命令，通常需要每个字体编码的单个定义。如果当前编码不存在定义，则使用默认值(如果可用)或向用户提供错误消息。
当字体编码在文档的某个时刻更改时，编码特定命令的定义不会立即更改，因为这意味着现场更改大量命令。取而代之的是，这些命令以这样的方式实现，一旦使用它们，他们会注意到它们当前的定义是否不再适用于有效编码的字体。在这种情况下，他们将当前字体编码的同行称为实际工作。

字体编码特定命令的集合未固定，而是隐式定义为为单个字体编码定义的所有命令的结合。因此，当将新的字体编码添加到乳胶中时，可能需要新的字体编码特定命令。

## 7.3. 输入编码

一旦加载了`inputenc`软件包，``\declareInputText`和'\ ecledInputmath“'\ declareInputText`和'\ declareInputmath`将8位输入字符映射到LICR对象。它们应仅用于编码文件(见下文)，软件包，或者在必要时在文档序言中使用。

这些命令将8位数字作为其第一个参数，可以作为小数号，八分音数字或十六进制符号表示。建议使用十进制符号，因为字符`''和/或``可能在语言支持软件包中获得特殊含义，例如重音的快捷方式，因此如果包装以错误的顺序加载，则可以使八分和/或十六进制符号无效。

```tex
\DeclareInputText{number}{LICR-object}
```

`\declareInputText`命令声明字符映射用于文本。它的第二个参数包含编码特定命令(或命令序列)，即应映射字符编号的LICR对象。例如，

```tex
\DeclareInputText{239}{\"\i}
```

将数字`239`映射到`i-umlaut`的编码特定表示，即`\ i-i`。输入字符以这种方式声明的输入字符都无法在数学公式中使用。

```tex
\DeclareInputMath{number}{math-object}
```

如果数字代表在数学公式中使用的字符，则必须使用声明`\declareInputmath`。例如，在编码`cp437de`(德语MS-DOS键盘)的输入中，

```tex
\DeclareInputMath{224}{\alpha}
```

将数字`224`映射到命令`\ alpha`。重要的是要注意，此声明将使仅在数学模式下可用的密钥生成此数字，因为`\ alpha`在其他任何地方都不允许。

```tex
\DeclareUnicodeCharacter{hex-number}{LICR-object}
```

仅当使用“ UTF8”选项时，此声明才可用。它将Unicode编号映射到LICR对象(即，在文本中可用)。例如， 

```tex
\DeclareUnicodeCharacter{00A3}{\textsterling}
\DeclareUnicodeCharacter{011A}{\v E}
\DeclareUnicodeCharacter{2031}{\textpertenthousand}
```

从理论上讲，两个空间之间只能有一个唯一的双向映射，因此当选择“ UTF8”选项时，所有这些声明都可以自动做出。实际上，事情要复杂一些。首先，自动提供整个桌子将需要大量Tex的内存。此外，有许多Unicode字符不存在LICR对象，相反，许多LICR对象在Unicode中没有等效。通过仅加载与特定文档中使用的编码相对应的那些Unicode映射(据他们所知)，并响应具有合适错误消息的Unicode字符的任何其他请求，就可以在“ Inputenc”软件包中解决此问题。然后，提供正确的映射信息，或者在必要时加载额外的字体编码成为用户的任务。

如上所述，可以在软件包或文档序言中使用输入编码声明。为了使所有内容以这种方式工作，首先加载`inputenc'软件包很重要，从而选择合适的编码。随后的输入编码声明将充当替代(或添加)由当前输入编码定义的声明。
使用`inputenc`软件包时，您可能会看到命令`\@tabacckludge`，该命令代表“ tabbing coctent kludge”。之所以需要，是因为乳胶的当前版本继承了命令的过载。这就是为什么涉及任何这些口音的映射需要以特殊的方式进行编码。例如，如果您想将`232`映射到`e-grave`字符(具有内部表示````

```tex
\DeclareInputText{232}{\@tabacckludge`e}
```

而不是 

```tex
\DeclareInputText{232}{\`e}
```

### 映射到文本和/或数学

出于技术和概念原因，Tex在文本和数学中可以使用的字符之间做出了非常有力的区别。除了可见的ASCII字符外，产生字符的命令通常可以在文本或数学模式下使用，但在两种模式下都不能使用。

### 输入编码8位编码的文件

输入编码存储在带有扩展名的文件中，其中基本名称是输入编码的名称(例如，`latin1.def`)。此类文件应仅包含当前部分中讨论的命令。
该文件应以一个包含`\ supportfile`命令的标识行开始，描述了文件的性质。例如：

```tex
\ProvidesFile{latin1.def}[2000/07/01 v0.996 Input encoding file]
```

如果有映射以编码特定的命令，除非加载其他软件包，否则可能无法使用``\ provideTextCommandDefault''声明默认值。例如：

```tex
\ProvideTextCommandDefault{\textonehalf}{\ensurement{\frac12}}
\ProvideTextCommandDefault{\textcent}{\TextSymbolUnavailable\textcent}
```

命令`\ textsymbolunavailable`发出警告，表明当前使用的字体无法获得某个字符。仅当加载特殊字体并且没有合适的方式以现有字符伪造字符时，这可以作为默认值有用(如`\ textOnehalf''的默认值)。

文件的其余部分应仅包括输入编码声明`\declareInputText`和`\declareInputmath`。如上所述，不建议使用后一个命令，但允许使用。在输入编码文件中不应使用其他命令，特别是没有命令可以防止多次读取文件(例如`\ newCommand`)，因为编码文件通常在单个文档中多次加载。

### UTF8的输入映射文件

如前所述，从Unicode到LICR对象的映射是通过使Latex仅加载与当前文档中使用的字体编码相关的那些映射的方式来组织的。这是通过尝试为每个编码<*name*>加载文件<*name*> fenc.dfu'的每个编码来完成的。除了许多“ \ ecledunicodecharacter”声明之外，此类文件还应仅包括`\ supportfile'行。

由于不同的字体编码通常会提供或多或少提供相同的字符，因此同一Unicode字符的声明非常常见，以不同的`dfu`文件出现。因此，重要的是，不同文件中的这些声明是相同的。否则，上次加载的声明将生存，这可能与文档到文档不同。

因此，任何想为某些编码提供新的编码的新文件的人都应仔细检查.dfu'文件中的现有定义中的相关编码。保证带有“输入”的标准文件具有统一的定义。实际上，它们都是从适当拆分的单个列表中生成的。当前现有映射的完整列表可以在文件“ `utf8enc.dfu`”中找到。

## 7.4. 输出编码
我们已经提到，输出编码定义了用于排版的字体中可用的字体中可用的从licr到glyphs的映射(或构造的构造)。这些映射在乳胶中以两个字母的名称(例如ot1`和`t3`)引用。我们说，如果映射对应于字体中字形的位置，则某个字体在某个编码中。现在让我们看一下这样的映射的确切组成部分。

由ASCII字符内部代表的字符简单地传递到字体。换句话说，Tex使用ASCII代码从当前字体中选择字形。例如，带有ASCII代码65的字符“ A”将导致在当前字体中的位置65中排版字形。这就是为什么乳胶需要字体才能在其ASCII代码位置中包含所有此类ASCII字母的原因，因为无法与此基本TEX机制进行交互。因此，对于可见的ASCII，在所有输出编码中隐含了一对一的映射。

内部表示为ASCII字符的序列(例如，“`` - `”)的字符如下：当前字体首次加载时，Tex被告知该字体包含许多所谓的连字程程序。这些程序定义了某些不应直接排版的字符序列，而是要用字体中的其他字形替换。例如，当Tex在输入中遇到“``` - `”(即ASCII代码45两次)时，结扎程序可以将其引导到第123位的字形(然后将其握住En Dash Glyph)。同样，没有办法与这种机制进行互动。

然而，内部字符表示的最大部分是由字体编码特定的命令组成，这些命令使用以下所述的声明进行映射。所有声明在其前两个参数中都具有相同的结构：字体编码特定的命令(或它的第一个组件，如果是命令序列)，然后是编码的名称。剩下的任何参数将取决于声明类型。

因此，编码`xyz`的编码是由一堆声明定义的，所有这些都以`xyz`的名字作为第二个论点。然后，当然，必须在该编码中编码某些字体。实际上，字体编码的开发通常是相反的 - 某人从现有字体开始，然后提供适当的使用声明。然后将此声明集合给出一个合适的名称，例如“ OT1”。在下面，我们将采用字体`ecrm1000`(请参见字形图)，其字体编码在乳胶中称为`t1`，并构建适当的声明以从以这种方式编码的字体访问字形。字形图中的蓝色字符是在每个编码中都应存在相同位置的蓝色字符，因为它们透明地通过了乳胶。

![ECRM1000字体的字形图表](/tex/images/java/tutorial/latex-font-selection-7-2.png)

### 输出编码文件

输出编码文件通过与输入编码文件相同的“ .def”扩展名来标识。但是，该文件的基本名称结构化一些。它由小写字母中的编码名称组成，然后是`eNC`(例如，`t1enc.def` t1`t1`编码了)。

这些文件应仅包括当前部分中描述的声明。由于编码文件的输出可以通过乳胶多次读取，因此遵循此规则并避免使用，例如`\ newCommand“，它可以防止读取此类文件不止一次！

同样，一个输出编码文件以描述文件性质的标识行开始。例如：

```tex
\ProvidesFile{t1enc.def}[2001/06/05 v1.94 Standard LaTeX file]
```

在向特定编码声明任何特定的编码命令之前，我们首先必须将此编码为乳胶已知。这是通过`\declareFontenCoding`命令完成的。在这一点上，声明编码的默认替换规则也很有用。我们可以通过使用命令`\declarefontsubstitution`这样做。在[如何设置新字体](/tex/{{lang.url-fragment}}java/latex-fonts-setup/)中详细讨论了这两种声明。

```tex
\DeclareFontEncoding{T1}{}{}
\DeclareFontSubstitution{T1}{cmr}{m}{n}
```

现在，我们已经以这种方式将“ T1”编码介绍给乳胶，我们可以继续宣布在该编码中如何表现为字体编码特定的命令。

```tex
\DeclareTextSymbol{LICR-Object}{encoding}{slot}
```

文本符号的声明似乎是最简单的。在这里，可以将内部表示形式直接映射到目标字体中的单个字形。这是通过使用`\declareTextSymbol`声明来实现的，该声明的第三个论点-Glyph位置可以作为小数，八分或十六进制的数字给出。例如，

```tex
\DeclareTextSymbol{\ss}{T1}{255}
\DeclareTextSymbol{\AE}{T1}{'306} %font position as octal number
\DeclareTextSymbol{\ae}{T1}{"E6} %...as hexadecimal number
```

宣布字体编码特定的命令`\ ss'，`\ ae'，并且应分别以“ T1”编码的字体映射到字体(十进制)位置255、198和230. 如上所述，在此类声明中使用小数表示法是最安全的。无论如何，像上一个示例一样混合符号当然是不好的样式。

```tex
\DeclareTextAccent{LICR-accent}{encoding}{slot}
```

字体通常包含音量标记作为单个字形，以通过将这种音量标记与其他一些字形结合使用来构建重音字符。使用`\declareTextAccent`命令(只要将其放在其他字形的顶部放置在其他字形的顶部)即可。第三个论点 *插槽 *是字体中的变音符号的位置。例如，

```tex
\DeclareTextAccent{\"}{T1}{4}
```

定义了“变音符号”的重音符号。从此时起，诸如“\"a”之类的内部表示在“T1”编码中具有以下含义：通过将位置 4 的重音符号置于位置 97（字符“a”的 ASCII 码）的字形上，排版出“带变音符号的 a”。事实上，这样的声明隐式地定义了大量的内部字符表示，即任何类型为“\"*<base-glyph>* 的字符，其中 *<base-glyph>* 是通过“\DeclareTextSymbol”定义的字符，或者任何属于 LICR 的 ASCII 字符，例如“a”。

即使那些没有多大意义的组合，例如“\"\P”（即带有变音符号的段落符号），从概念上来说，也以这种方式成为特定于字体编码的命令集的成员。
```tex
\DeclareTextComposite
     {LICR-accent}{encoding}{simple-LICR-object}{slot}
```

上面的字形图包含大量重音字符作为单个字形 - 例如，“ a with umlaut'在位`240`八进式。因此，在“ T1”中，编码特定命令`\'a a不应导致对字符'a'的重音，而应直接在字体的位置上访问字形。这是通过声明实现的

```tex
\DeclareTextComposite{\"}{T1}{a}{228}
```

它表明特定于编码的命令“\"a”会导致排版字形 228，从而禁用上面的重音符声明。对于所有其他以“\"”开头的特定于编码的命令，重音符声明保持不变。例如，“\"b”将通过在基本字形“b”上放置重音符来生成“带变音符号的 b”。

第三个参数 *simple-LICR-object* 应该是单个字母，例如“a”，或者单个命令，例如“\j”或“\oe”。。

```tex
\DeclareTextCompositeCommand
     {LICR-object}{encoding}{simple-LICR-object}{code}
```

虽然它不用于“T1”编码，但也有一个更通用的“\DeclareTextComposite”版本，允许任意代码代替插槽位置。例如，在“OT1”编码中，它用于降低“A”上的环形重音符，使其与使用 TeX 的“\accent”原语排版的方式相比更低。“i”上的重音符也使用以下声明形式实现：

```tex
\DeclareTextCompositeCommand{\'}{OT1}{i}{\@tabacckludge'\i}
\DeclareTextCompositeCommand{\^}{OT1}{i}{\^\i}
```

许多音符标记没有放在其他字符的顶部，而是放置在其下方的某个位置。此类商标没有特殊的声明表格，因为口音的实际定位涉及低级Tex代码。取而代之的是，可以将通用的`\declareTextCommand`用于此​​目的。

```tex
\DeclareTextCommand{LICR-object}{encoding}[num][default]{code}
```

例如，用以下代码定义了`t1`编码`\b`的“ Underbar'acpent`\b`：

```tex
\DeclareTextCommand{\b}{T1}[1]
     {\hmode$bgroup\o$lign{\relax#1\crcr\hidewidth\sh$ft{29}%
           \vbox to.2ex{\hbox{\char9}\vss}\hidewidth}\egroup}
```

在本次讨论中，代码的具体含义并不重要，但我们可以看出 `\DeclareTextCommand` 在某种程度上与 `\newcommand` 类似。它有一个可选的 *num* 参数，表示参数的数量（此处为一个），第二个可选的 *default* 参数（此处未提供），以及最后一个强制参数，其中包含可以使用 `#1`、`#2` 等引用参数的代码。

`\DeclareTextCommand` 也可用于构建由单个控制序列组成的字体编码专用命令。在本例中，它不使用可选参数，从而定义了一个不带参数的命令。例如，在 `T1` 中没有“千分”符号的字形，但在 `'30` 位置有一个小“o”，如果将其直接放在 `%` 后面，就会产生相应的字形。因此，我们可以提供以下声明：：

```tex
\DeclareTextCommand{\textperthousand} {T1}{\%\char 24}
\DeclareTextCommand{\textpertenthousand}{T1}{\%\char 24\char 24 }
```

现在，我们介​​绍了为新编码声明字体编码特定的命令所需的所有命令。正如我们已经说过的，在编码定义文件中只有这些命令应存在。

### 输出编码默认值

现在，让我们看看如果使用当前字体编码中没有声明的编码特定命令会发生什么。在这种情况下，可能会发生两件事之一：要么LATEX对LICR对象具有默认定义，在这种情况下，使用此默认值，或者发出错误消息，指出当前编码中不可用所请求的LICR对象。有多种方法可以为LICR对象设置默认值。

```tex
\DeclareTextCommandDefault{LICR-object}[num][default]{code}
```

`\DeclareTextCommandDefault` 命令为 *LICR-object* 提供默认定义，当当前编码中没有为某个对象指定设置时，将使用该默认定义。例如，此类定义可以伪造某个字符。例如，`\textregistered` 有一个默认定义，其中的字符由另外两个字符构成，如下所示：

```tex
\DeclareTextCommandDefault{\textregistered}{\textcircled{\scshape r}}
```

从技术上讲，默认定义被存储为使用名称``？'的编码。尽管您不应该依靠这一事实，因为实现将来可能会发生变化，但这意味着您不能声明使用此名称的编码。

```tex
\DeclareTextSymbolDefault{LICR-object}{encoding}
```

在大多数情况下，默认的定义不需要编码，而只是指示乳胶从已知存在的某些编码中获取字符。例如，` TextComp`软件包都包含大量默认声明，这些声明都指向“ TS1”编码。例如：

```tex
\DeclareTextSymbolDefault{\texteuro}{TS1}
```

`\declareTextSymboldefault`命令可用于在没有参数的情况下定义任何LICR对象的默认值，而不仅仅是在其他编码中使用`\declareTextSymbol`命令声明的默认值。

```tex
\DeclareTextAccentDefault{LICR-accent}{encoding}
```

LICR对象也有类似的声明，该对象采用一个论点，例如口音。同样，此形式可用于任何一个参数的LICR对象。例如，乳胶内核包含许多类型的声明：

```tex
\DeclareTextAccentDefault{\"}{OT1}
\DeclareTextAccentDefault{\t}{OML}
```

这意味着，如果未在当前编码中定义`\`，则使用`ot1`编码的字体中的一个。同样，要获得扎带的口音，请从`oml`中挑选它，如果没有什么更好的可用。

```tex
\ProvideTextCommandDefault{LICR-object}[num][default]{code}
```

`\ providetextCommandDefault`声明允许“提供”另一种默认值。它可以执行与`\ ecledeTextCommandDefault`声明的工作相同的作业，只是仅在没有定义默认值之前提供默认值。这主要用于输入编码文件，以为不寻常的LICR对象提供某种琐碎的默认值。例如：

```tex
\ProvideTextCommandDefault{\textonequarter}{\ensuremath{\frac14}}
\ProvideTextCommandDefault{\textcent}{\TextSymbolUnavailable\textcent}
```

然后，诸如textcomp”之类的软件包可以用指向真实字形的声明替换此类定义。使用`\提供...`而不是`\ neclare ...`确保如果读取输入编码文件，则不会意外地覆盖更好的默认值。

```tex
\UndeclareTextCommand{LICR-object}{encoding}
```

在某些情况下，需要删除现有声明，以确保使用默认声明。这可以通过使用`\ undeclareTextComman`来完成。例如，` TextComp`软件包”删除了从编码`\ textdollar`和`\ textsterling`的定义''编码的定义，因为并非每个ot1编码的字体实际上都有这些符号。

```tex
\UndeclareTextCommand{\textsterling}{OT1}
\UndeclareTextCommand{\textdollar} {OT1}
```

没有此删除，从``ts1'''ot o ot1'编码的字体不使用新的默认声明。

```tex
\UseTextSymbol{encoding}{LICR-object}
\UseTextAccent{encoding}{LICR-object}{simple-LICR-object}
```

也可以直接使用声明`\declareTextSymboldefault`和`\ expareTextAccentDefault`也可以直接使用声明后面的动作。例如，让我们假设当前的编码为“ u”。在这种情况下，

```tex
\UseTextSymbol{OT1}{\ss}
\UseTextAccent{OT1}{\'}{a}
```

与输入下面的代码相同。特别注意，“ A”是编码`u'的排版 - 只有重音是从其他编码中获取的。

```tex
{\fontencoding{OT1}\selectfont\ss}
{\fontencoding{OT1}\selectfont\'{\fontendcoding{U}\selectfont a}}
```

### 标准LICR对象的列表

本小节中的表提供了有关拉丁语言的三个主要编码可用的乳胶内部表示形式：`ot1`(原始的TEX编码)，`t1 t1`(乳胶标准编码)和`Ly1`(由y＆y提出了替代的8位编码)。此外，它显示了通过加载`textComp`软件包提供的“ TS1”(乳胶标准文本符号编码)声明的所有LICR对象。

表的第一列按字母顺序显示LICR对象名称，表明哪些LICR对象的作用为重音。第二列显示对象的字形表示。

第三列描述对象是否具有默认声明。如果列出了编码，则意味着默认情况下，从该编码中的合适字体中获取字形； “约束。”表示默认值是从低级TEX代码产生的；如果列为空，则意味着该LICR对象没有定义默认值。在最后一个情况下，当您在没有明确定义的编码中使用它时，将返回“符号不可用”错误。如果该对象是其他LICR对象的别名，则该列中列出了替代名称。

第四至第七列显示在给定编码中是否可用的对象。在这里，“ x”意味着该对象在用该编码的字体上本地可用(作为字形)，“ o”意味着它可以通过默认值可用于所有编码，并且“约束”意味着它是从几个字形，口音标记或其他元素中生成的。如果默认值是从`ts1`获取的，则仅在加载`textComp`软件包时才可用LICR对象。

#### LICR对象。第1部分

![LICR对象列表。第1部分](/tex/images/java/tutorial/latex-font-selection-7-3.png)

#### LICR对象。第2部分

![LICR对象列表。第2部分](/tex/images/java/tutorial/latex-font-selection-7-4.png)

#### LICR对象。第3部分

![LICR对象列表。第3部分](/tex/images/java/tutorial/latex-font-selection-7-5.png)

#### LICR对象。第4部分

![LICR对象列表。第4部分](/tex/images/java/tutorial/latex-font-selection-7-6.png)

#### LICR对象。第5部分

![LICR对象列表。第5部分](/tex/images/java/tutorial/latex-font-selection-7-7.png)

#### LICR对象。第6部分

![LICR对象列表。第6部分](/tex/images/java/tutorial/latex-font-selection-7-8.png)

#### LICR对象。第7部分

![LICR对象列表。第7部分](/tex/images/java/tutorial/latex-font-selection-7-9.png)

#### LICR对象。第8部分

![LICR对象列表。第8部分](/tex/images/java/tutorial/latex-font-selection-7-10.png)