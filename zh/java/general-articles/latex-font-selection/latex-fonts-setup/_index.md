---
translation: true
template: /templates/_template-java.md
title: 6. 如何设置新字体
linktitle: 如何设置新字体
weight: 60
url: /java/latex-fonts-setup/
keywords: LaTeX、LaTeX字体、LaTeX字体替换、LaTeX字体设置
description: 本文介绍了在 LaTeX 中设置新字体的方式，并提供了字体定义的示例。
lastmod: "2026-02-28"
---

{{<section overview>}}

要在 LaTeX 中使用新字体，基本上需要把内部字体选择表填满，以便以后在文档中将字体请求与外部 `.tfm` 文件（包含字符信息）关联。因此，这些表负责把外部文件 `cmdunh10.tfm` 与以下请求关联：

```tex
\fontencoding{OT1}\fontfamily{cmdh}\fontseries{m}\fontshape{n}%
\fontsize{10}{12pt}\selectfont
```

要添加新字体，需要反向操作。对于每一个新外部字体，你必须回答五个问题：

1. 字体编码是什么——即字符在什么位置？
2. 它的族名是什么？
3. 它的系列（粗细和宽度）是什么？
4. 它的形状是什么？
5. 它的尺寸是什么？

这些问题的答案提供了按照 LaTeX 约定对外部字体进行分类所需的信息。接下来的几个章节中，我们将讨论如何把新字体录入 NFSS 表，以便在正文中使用。如果你想创建一个简短的包文件来访问新字体族，通常需要这些信息。后面的章节会讨论更复杂的概念，例如在数学中使用特殊字体而非标准字体。

## 6.1. 外部字体的命名约定

TeX 世界中一种事实上的标准字体命名方案使用 **八个字母数字字符** 对所有字体文件名进行分类，大小写不敏感。这个八字符的限制保证了相同的文件名可以在所有计算机平台上使用。该方案的原理在下表中说明，方括号中的部分如果对应默认值可以省略。例如，只有在字体未线性缩放时才给出设计尺寸。

![The naming convention for external fonts](/tex/images/java/tutorial/latex-font-selection-6-1.png)

下面给出了 35 种“基本” PostScript 字体在 LaTeX 字体接口下的分类。对于每种字体，列出了完整的 Adobe 名称以及对应的短文件名（在本章节讨论的分类中）。对于 `OT1`、`T1` 或 `TS1`，需要分别在文件名前加 `7t`、`8t`、`8c` 以得到完整文件名。例如，`putr8t` 表示 T1 编码下的 Utopia Regular。这在后面的讨论中会用到。

![PostScript fonts classification](/tex/images/java/tutorial/latex-font-selection-6-2.png)

该命名约定涵盖了 **内部 TeX 名称**（即在下一节的 `\DeclareFontShape` 声明中使用的名称）、**虚拟字体及其组件的名称**（例如对物理字体的重新编码）以及 **物理字体的名称**。在 PostScript 字体的情况下，物理字体名称常常与 TeX 内部使用的名称不同。后者需要在 LaTeX 运行结果被查看或打印时映射到相应的外部字体。例如，PostScript 驱动 `dvips` 使用映射文件（默认扩展名 `.map`）其中包含类似下面的行：

```
putr8r Utopia-Regular "TeXBase1Encoding ReEncodeFont " <8r.enc <putr8a.pfb
```

这表明字体 `putr8r` 可以通过特殊编码向量 (`8r.enc`) 从外部字体 `putr8a.pfb` 重新编码得到。然而，你在 `t1put.fd` 文件中找不到 `putr8r` 的引用，该文件包含了 `T1` 编码下 Utopia 家族的 `\DeclareFontShape` 声明。原因是 `putr8t` 是一个虚拟字体（由 `fontinst` 实用程序生成），它引用了 `putr8r`。后者只能在虚拟字体的源文件中找到。

## 6.2. 如何声明新的字体族和字体形状组

每一个 family/encoding 组合必须通过 `\DeclareFontFamily` 命令引入 LaTeX，该命令接受三个参数。前两个分别是编码方案和族名。第三个通常为空，但可以包含字体加载的特殊选项，后文会进一步解释。因此，如果你想声明一个新的族——比如说使用旧 TeX 编码的 Computer Modern Dunhill——可以写成

```tex
\DeclareFontFamily{OT1}{cmdh}{}
```

通常，一个字体族中会有许多单独的字体。为减少声明数量，需要把仅在尺寸上不同的字体合并为一个组，而不是单独声明每个成员。

这样一个组通过 `\DeclareFontShape` 进入 LaTeX 的内部表格，该命令接受 **六个** 参数。前四个分别是编码方案、族名、系列名和形状名。第五个参数是尺寸列表和外部字体名的组合，使用一种特殊格式（后文会讨论）。第六个参数通常为空，其用途将在后面说明。

举例来说，下面的 NFSS 表条目为 **Computer Modern Dunhill** 在旧 TeX 编码下的 **中等直立** 形状：

```tex
\DeclareFontShape{OT1}{cmdh}{m}{n}{ <10> cmdunh10 }{}
```

这是假设只有 10pt 的外部字体可用。如果同样的字体在 12pt（从 10pt 缩放）也可用，则声明为

```tex
\DeclareFontShape{OT1}{cmdh}{m}{n}{ <10> <12>cmdunh10 }{}
```

如果外部文件在所有可能尺寸上都可用，声明会非常简单。这种情况出现在 Type 1 PostScript（轮廓）字体，或者驱动程序能够通过调用 METAFONT 按需生成字体时。

例如，**Times Roman** 粗体直立在 LaTeX 的 `T1` 编码下可以这样引入：

```tex
\DeclareFontShape{T1}{ptm}{b}{n}{ <-> ptm8t }{}
```

此示例声明了一个两端开放的尺寸范围。结果是同一个外部 `ptmb8t.tfm` 文件用于所有尺寸，并按所需尺寸缩放。如果同一种字体有多个 `.tfm` 文件——比如说 `emtt10` 用于正文尺寸，`emtt12` 用于展示尺寸（European Modern Typewriter），则可以写成

```tex
\DeclareFontShape{T1}{emtt}{m}{n}{<-12> emtt10 <12-> emtt12}{}
```

在此情况下，`emtt10.tfm` 用于小于 12pt 的尺寸，`emtt12.tfm` 用于大于或等于 12pt 的尺寸。

上面的示例说明 `\DeclareFontShape` 的 **第五个参数** 由 **尺寸说明**（用尖括号括起）和 **加载信息**（字体名）交替组成。尖括号内的部分称为 *size info*，其后的部分称为 *font info*。*font info* 进一步拆分为 *size function*（通常为空）及其参数。在 `\DeclareFontShape` 的参数中，空格会被忽略以提高可读性。如果必须输入真实空格，可使用 `\space` 命令。

### 简单尺寸和尺寸范围

尺寸信息可分为 **简单尺寸** 与 **尺寸范围**。简单尺寸是单个（十进制）数，例如 `<10>` 或 `<17.28>`，可以是任意正数。不过通常不会出现小于 4 或大于 120 的值，因为该数表示点（pt）单位的字体大小。尺寸范围由两个简单尺寸用连字符分隔，表示共享同一 *font info* 的一组字体尺寸。下边界包含在范围内，上边界不包含。例如 `<5-10>` 表示 **≥ 5pt 且 < 10pt** 的尺寸。可以省略连字符两侧的数字：`<->` 表示所有可能尺寸，`<-10>` 表示小于 10pt 的所有尺寸，`<12->` 表示大于或等于 12pt 的所有尺寸。

若多个简单尺寸共用同一 *font info*，可以使用简写，只保留最后一个信息：

```tex
\DeclareFontShape{OT1}{panr}{m}{n}{ <5> <6> <7> <8> <9> <10>
    <10.95> <12> <14.4> <17.28> <20.74> <24.88> pan10 }{}
```

这表明 **Pandora** 中等罗马体在多个尺寸上都通过从同一设计尺寸（`pan10`）缩放得到。

### 尺寸函数

如上所述，*font info* 进一步被结构化为 **size function** 与其参数。如果字体信息字符串中出现 `*`，左侧为函数名，右侧为参数；如果没有 `*`，则整个字符串视为参数，函数名为空。

尺寸函数负责生成 LaTeX 用来查找外部字体并在所需尺寸加载的规格。该过程依据用户请求的尺寸以及 `\DeclareFontShape` 中的资讯。尺寸函数还会向用户报告特殊事件，例如是否产生警告。以下列出标准尺寸函数。

**“空”函数**  
空函数在 **简单尺寸** 情况下直接以请求的尺寸加载字体；在 **尺寸范围** 情况下，如果请求尺寸落在该范围内，则同样以请求尺寸加载字体。例如，若用户请求 `14.4`，则

```tex
<-> panr10
```

会在 14.4pt 加载 `panr10.tfm`（该文件的所有值会按 1.44 的比例缩放，因为它是为 10pt 设计的）。

有时需要稍微调整加载尺寸，例如某族字体相对于其他族显得过大。空函数允许使用可选参数指定 **缩放因子**，乘以请求尺寸得到实际加载尺寸。例如：

```tex
<-> [0.95] phvr8t
```

始终以 95% 的请求尺寸加载 `phvr8t.tfm`（T1 编码下的 Helvetica）。若使用可选参数，空函数会发出警告，提示用户字体并未按原始尺寸加载。

**“s”函数**  
`s` 与空函数功能相同，但在终端不产生消息。信息仍会写入转录文件，便于在出现错误时查看实际使用的字体。

**“gen”函数**  
外部字体名常通过在字体系列字符串后附加尺寸来生成，例如 `cmtt8`、`cmtt9`、`cmtt10`。使用 `gen` 可以简写这些条目。`gen` 将 *font info* 与请求尺寸组合生成外部字体名。例如：

```tex
<8> <9> <10> gen * cmtt
```

等价于

```tex
<8> cmtt8 <9> cmtt9 <10> cmtt10
```

此函数在内部直接拼接两部分，因此不应用于十进制尺寸（如 `14.4`），并且必须确保外部字体名中的数字真实表示设计尺寸（例如 `cmr17` 实际是 17.28pt）。

在其他方面，`gen` 与空函数行为相同，可使用可选参数指定缩放因子并产生信息消息。

**“sgen”函数**  
`sgen` 是 `gen` 的静默版，只把信息写入转录文件。

**“genb”函数**  
`genb` 与 `gen` 类似，但用于尺寸以 **厘点**（centipoints）编码的字体，例如 EC 字体。示例：

```tex
<9> <10> <10.95> <12> genb * ecrm
```

等价于

```tex
<9> ecrm0900 <10> ecrm1000 <10.95> ecrm1095 <12> ecrm1200
```

可选参数的作用同空函数。

**“sgenb”函数**  
`sgenb` 是 `genb` 的静默版。

**“sub”函数**  
`sub` 用于在当前字体形状组没有外部字体时，替代为 **另一组**（不同的族、系列、形状）. 例如，Computer Modern Sans 没有斜体，只提供倾斜形状，可将倾斜形状声明为斜体的替代：

```tex
\DeclareFontShape{OT1}{cmss}{m}{it}{ <-> sub * cmss/m/sl }{}
```

若未声明此项，LaTeX 的自动替代机制会改用默认的直立形状。

`sub` 还有其他用途。例如：

```tex
\DeclareFontShape{OT1}{cmss}{m}{sl}{ <-8> sub * cmss/m/n
   <8> cmssi8 <9> cmssi9 <10><10.95> cmssi10 <12><14.4> cmssi12
   <17.28><20.74><24.88> cmssi17 }{}
```

此声明表示 **<8pt** 时查找 `OT1/cmss/m/n` 中的形状组。若此组再次没有合适字体，替代过程可以继续链式进行。

**“ssub”函数**  
`ssub` 与 `sub` 功能相同，但不产生屏幕警告（`s` 表示 *silent*）。

**“subf”函数**  
`subf` 与空函数相同，但会在因替代而加载外部字体时发出警告。可用于在不声明单独的 `sub` 组时进行替代：

```tex
\DeclareFontShape{OT1}{ptm}{bx}{n}{ <-> subf * ptmb7t }{}
```

此声明会警告用户所请求的组合不可用，因而加载了 `ptmb7t`。相较于 `sub`，信息更少，推荐使用 `sub`。

**“ssubf”函数**  
`ssubf` 为 `subf` 的静默版，仅把消息写入转录文件。

**“fixed”函数**  
`fixed` 忽略请求的尺寸，直接加载参数中指定的外部字体。可选参数若出现，则表示加载该字体时所使用的 **点大小**。这使得可以为特定尺寸范围统一使用同一固定大小的字体。

**“sfixed”函数**  
`sfixed` 为 `fixed` 的静默版，常用于只能以固定大小提供的大型数学符号字体。

### 字体加载选项

如前所述，每个字体族需要使用 `\DeclareFontFamily` 声明。该命令的第三个参数以及 `\DeclareFontShape` 的第六个参数可用于指定 **字体加载时的特殊操作**，从而改变与整个字体相关的参数。

每个外部字体在 TeX 中都有一组 **全局尺寸**（如连字符字符、空格宽度等）。例如，每个字体都有自己的 **连字符字符**（在断字时插入的字符）。另一个例子是单词之间的正常空格宽度以及其伸缩性——这些值随字体切换而变化。通过在加载时修改这些值，可以实现特殊效果。

通常，这些更改应用于整个族；例如，你可能想禁止在 **typewriter** 家族中进行断字。这时应使用 `\DeclareFontFamily` 的第三个参数。如果更改仅针对特定的 **字体形状组**，则使用 `\DeclareFontShape` 的第六个参数。换句话说，加载字体时，NFSS 首先应用 `\DeclareFontFamily` 的参数，然后再应用 `\DeclareFontShape` 的第六个参数，以在必要时覆盖族级别的选项。

使用 `\hyphenchar\font=<number>` 可指定用于断字的字符。`<number>` 表示该字符在当前编码中的位置。默认值为 `\defaulthyphenchar`（通常为 45，即 `-` 的位置）。若设为 `-1`，则抑制断字。例如：

```tex
\DeclareFontFamily{0T1}{cmtt}{\hyphenchar\font=-1}
```

会在 `OT1` 编码的 `cmtt` 家族中禁止断字。`T1` 编码的字体在位置 127 有另一连字符字符，可这样设置：

```tex
\DeclareFontFamily{T1}{cmr}{\hyphenchar\font=127}
```

这会把连字符字符区分于诸如 “so‑called” 中的复合连字符。TeX 不会对已显式包含连字符的单词再进行断字，这在某些平均单词长度远大于英语的语言中可能成为问题。上述设置可解决此类问题。

每个 TeX 字体还有一组 **尺寸参数**，通过形如 `\fontdimen<number>\font=<dimen>` 的赋值进行修改。默认值从 `.tfm` 文件读取。每个字体至少有以下七个尺寸：

* `\fontdimen1` 字符的每点倾斜度，值为 0 时字体直立。
* `\fontdimen2` 单词之间的普通空格宽度（interword space）。
* `\fontdimen3` 普通空格的额外伸展度，用于产生两端对齐的段落。
* `\fontdimen4` 普通空格的收缩度，TeX 不会把空格收缩到低于此值。
* `\fontdimen5` *x‑height*，即 `1ex` 的大小。
* `\fontdimen6` *quad* 宽度，即 `1em` 的大小。
* `\fontdimen7` 在 `\nonfrenchspacing` 生效时，用于句末标点后的额外空格（若 `\xspaceskip` 非零则被其取代）。

如果想改变与字体关联的单词间距，不能使用绝对值，因为该值必须对该形状组的所有尺寸都适用。常用的做法是相对于已有的字体参数，例如：

```tex
\DeclareFontShape{0T1}{cmr}{m}{n}{...}
   {\fontdimen2\font=.7\fontdimen2\font}
```

上述声明将普通单词间距缩小到原来的 70%。同理，可修改伸展度和收缩度。

某些公式字体（如 `symbols`、`largesymbols`）需要超过七个 `\fontdimen` 参数；分别至少需要 22 与 13 个参数，以便正确定位符号。

有一个不幸的限制：TeX 只会在 **给定尺寸** 上加载一次 `.tfm` 文件。因此，不能通过两个不同的 `\DeclareFontShape` 声明分别加载同一个外部字体（如 `cmtt10`）并在其中一个修改 `\fontdimen` 参数。对两个形状组的更改会相互覆盖。例如：

```tex
\DeclareFontShape{T1}{ptm}{m}{n}{ <-> ptmr8t }{}
\DeclareFontShape{T1}{ptm}{c}{n}{ <-> ptmr8t }
                     {\fontdimen2\font=.7\fontdimen2\font}
```

第二个声明不会生效，因为加载 `ptmr8t` 时已经在第一个形状组中完成。解决方案是创建一个 **虚拟字体**，其中包含相同字符但拥有不同的尺寸参数。另一种办法是以略微不同的尺寸加载，例如：

```tex
\DeclareFontShape{T1}{ptm}{c}{n}{ <-> [0.9999] ptmr8t }
                 {\fontdimen2\font=.7\fontdimen2\font}
```

此方法让 TeX 将其视为两个不同的字体，拥有各自的 `\fontdimen` 参数。也可以直接通过设置 `\spaceskip` 来覆盖字体自带的空格参数。

## 6.3. 如何修改字体族和字体形状组

如果文档需要 **非标准的字体形状声明**，应将该私有声明放入 **包文件**或文档的 **导言区**。这样可以覆盖已有的同一形状组声明。但需要注意，使用 `\DeclareFontFamily` 会阻止后续加载相应的 `.fd` 文件（后文会讨论）。此外，新声明对已经加载的字体没有影响。

## 6.4. 如何声明新的字体编码方案

涉及 **编码方案** 变更的字体修改需要特别小心。例如，在 `T1` 编码下，大多数带重音的字母都有独立字形；而在传统的 TeX 文本编码 `OT1` 中，带重音的字母必须通过字母加重音符号（`\accent` 原语）组合得到。如果需要混合使用两种编码（例如因为某字体仅在其中一种可用），则像 `\"` 这样的命令必须根据当前字体编码做出不同的行为。

因此，每一种 **字体编码** 必须通过 `\DeclareFontEncoding` 正式引入 LaTeX，语法为三个参数。第一个参数是编码名称，后续将通过 `\fontencoding` 使用；第二个参数包含在切换编码时要执行的代码（如宏定义）；第三个参数包含每次作为数学字母访问时要执行的代码。下面的链接提供了 **标准编码方案** 的列表：

[standard encoding schemes](/tex/{{lang.url-fragment}}java/latex-fonts-low-level/#choosing-the-encoding)

LaTeX3e 项目保留了以下前缀的编码名称：

* `T` 标准文本编码（256 字符）。
* `TS` 为对应 `T` 编码扩展的符号。
* `X` 不符合严格 `T` 编码要求的文本编码。
* `M` 标准数学编码（256 字符）。
* `S` 其他符号编码。
* `A` 其他特殊用途。
* `OT` 标准文本编码（128 字符）。
* `OM` 标准数学编码（128 字符）。

字母 `O` 表示这些 128‑字符编码 **旧且已废弃**。理想情况下，这些编码将被 TeX User Group 定义的标准所取代，将来只在语言切换时才需要更改编码。

如果你要声明自己的 **私有编码**，建议使用以 `L`（local）或 `E`（experimental）开头的名称。以 `U` 开头的编码用于 **未知（Unknown）** 或 **未分类（Unclassified）** 的情况——即不符合常见模式的字体。上述命名约定保证了使用官方编码的文件具有可移植性。

`\DeclareFontEncoding` 会把新声明的编码名称存入宏 `\LastDeclaredEncoding`，这在随后声明相关信息时可能有用，例如在西里尔语言的编码声明文件中会用到。

如前文的 **字体替代** 部分所述，不同编码的 **默认族 / 系列 / 形状** 可能需要不同的默认值。此时可使用 `\DeclareFontSubstitution`，它接受 **编码** 作为第一个参数，随后三个参数分别是该编码下的 **默认族、系列、形状**。这三个参数必须对应已有的有效 **字体形状**（即已有 `\DeclareFontShape` 声明），否则在文档开始时会报错。

## 6.5. 内部文件组织

字体族可以在 **格式文件生成时** 声明、在文档导言区声明，或在需要时**按需加载**（当文档中出现未使用过的字体组合时）。第一种方式会在每次 LaTeX 运行时占用内部内存，即使未实际使用该字体。后两种方式在文档排版时会多花一点时间读取定义文件，但更为高效，因而在大多数形状组中更受推荐。

在生成 **格式文件** 时，LaTeX 会读取名为 `fonttext.ltx` 的文件，其中包含标准的字体族定义以及其他与文本字体相关的声明。

其他所有字体族定义应放在 **外部文件** 中按需加载：可以是 **包文件**或 **字体定义 (.fd) 文件**。如果将定义放在包文件中，需要在 `\documentclass` 之后显式加载该包；还有一种方式是：当 NFSS 收到对 **编码 scheme** `BAR` 中 **族** `foo` 的请求且未认识该组合时，它会尝试加载名为 `barfoo.fd` 的文件。如果该文件存在，内部应包含该族在该编码下的 **字体形状组声明**，格式如下：

```tex
\DeclareFontFamily{BAR}{foo}{...}
\DeclareFontShape{BAR}{foo}{...}{...}{...}{...}
...
\endinput
```

这就是能够在不把所有字体信息预装进内存的情况下，声明大量字体族的机制。

每个 `.fd` 文件应仅包含 **单个字体族在单一编码方案** 的全部定义。文件中必须至少出现一次 `\DeclareFontShape` 声明以及恰好一次 `\DeclareFontFamily` 声明。除此之外不应出现其他定义（除非是 `\ProvidesFile` 或用于向用户报告的 `\typeout`/`\wlog`）。如果使用 `\typeout`，请记得在需要空格时使用 `\space`，因为 `.fd` 文件会忽略空格和空行。

**新编码方案** 不能仅通过 `.fd` 机制引入。NFSS 会拒绝任何未在 LaTeX 格式（`fonttext.ltx`）、包文件或文档导言区显式声明的编码切换请求。

## 6.6. 如何声明用于数学的新字体

### 如何指定字体尺寸

对于每一种文本尺寸，NFSS 维护 **三种用于排版数学公式的尺寸**（详见链接）：用于大多数符号的尺寸（由 `\textstyle` 或 `\displaystyle` 选取），用于一阶上下标的尺寸（`\scriptstyle`），以及用于更高阶上下标的尺寸（`\scriptscriptstyle`）。如果你切换到一个尚未拥有相应数学尺寸的文本尺寸，NFSS 会尝试将它们作为文本尺寸的分数进行计算。如果不希望自动计算，可自行通过 `\DeclareMathSizes` 指定正确的值。该声明接受四个参数：**外层文本尺寸**以及对应的 **三种数学尺寸**。例如，下面的声明为 14pt（章节标题）尺寸设定数学尺寸为 14pt、10pt、7pt：

```tex
\DeclareMathSizes{14}{14}{10}{7}
```

另一个示例（用于更高层级标题）告诉 NFSS 对 36pt 文本尺寸 **不需要** 数学尺寸，从而避免不必要的字体加载：

```tex
\DeclareMathSizes{36}{}{}{}
```

### 如何添加新符号

我们已经讨论过如何使用 [math alphabet commands](/tex/{{lang.url-fragment}}java/latex-math-fonts/#81-math-alphabet-identifiers) 在公式中产生特殊形状的字母。下面演示如何添加包含特殊符号的 **符号字体**（*symbol fonts*），并使这些符号在公式中可用。

添加新符号字体的过程与声明新的 **math alphabet identifier** 类似：` \DeclareSymbolFont` 为所有数学版本设置默认值，`\SetSymbolFont` 则可为特定版本覆盖这些默认值。

符号字体通过 **符号名** 访问。例如，要安装 AMS 字体 `msbm10`（见下方字形表），首先需使用前文章节描述的声明让 NFSS 认识该字体：

![msbm10 glyph chart](/tex/images/java/tutorial/latex-font-selection-6-3.png)

对应的声明如下：

```tex
\DeclareFontFamily{U}{msb}{}
\DeclareFontShape{U}{msb}{m}{n}{ <5> <6> <7> <8> <9> gen * msbm
        <10> <10.95> <12> <14.4> <17.28> <20.74> <24.88> msbm10}{}
```

随后，通过以下命令把该符号字体声明给 **所有数学版本**：

```tex
\DeclareSymbolFont{AMSb}{U}{msb}{m}{n}
```

这样，符号形状组 `U/msb/m/n` 就以 `AMSb` 的名字可在数学中使用。如果该字体族中还有粗体系列（实际上没有），可以进一步为粗体数学版本设置：

```tex
\SetSymbolFont{AMSb}{bold}{U}{msb}{b}{n}
```

在完成字体声明后，就可以在数学模式中使用该符号字体。但要让诸如 `\lessdot` 之类的命令产生相应符号，需要使用 `\DeclareMathSymbol` 将 **符号名称** 与 **符号字体** 关联：

```tex
\DeclareMathSymbol{cmd}{type}{symbol-font}{slot}
```

* 第一个参数是你自定义的命令名。  
* 第二个参数取自下表，决定符号的类型，从而影响 LaTeX 在公式中为其预留的间距。  
* 第三个参数是之前通过 `\DeclareSymbolFont` 定义的 **符号字体名**。  
* 第四个参数是符号在该字体编码中的位置（十进制、八进制或十六进制均可）。

例如，要把 `\lessdot` 绑定到 AMSb 中的特定位置，可声明：

```tex
\DeclareMathSymbol{\lessdot}{\mathbin}{AMSb}{"6c}
```

如果第一个参数采用单个字符而非命令名，也可以使用。例如，`eulervm` 包中有如下声明：

```tex
\DeclareMathSymbol{0}{\mathalpha}{letters}{"30}
```

用于指定数字的来源。

` \DeclareMathSymbol` 实际上指定了 **符号在某符号字体中的位置**，因此所有通过 `\DeclareSymbolFont` / `\SetSymbolFont` 关联的外部字体必须在该位置拥有相同的字形。最安全的做法是只在相同 **编码**（除 `U` 外）下使用字体，以确保字符对应。

在上图中，你还能找到 **blackboard bold**（粗体黑板字）字符（`ABC…` 从位置 `'101` 开始）。如果想把这些字符用作 **数学字母**，可以使用 `\DeclareMathAlphabet`。但如果该符号字体已经加载，使用以下快捷方式更方便：

```tex
\DeclareSymbolFontAlphabet{\mathbb}{AMSb}
```

这行代码提供了 **math alphabet identifier**（`\mathbb`）以及之前声明的符号字体名。

加载过多符号字体会受到 **16 个数学字体的上限** 限制。每个符号字体计入此上限，数学字母仅在实际使用时计入，并且在每个数学版本中独立计数。因此，如果声明了 8 个符号字体，则每个版本最多只能使用 8 个（可能不同的）数学字母标识符。

**简要总结**：要引入新符号字体，需要少量的 `\DeclareSymbolFont` / `\SetSymbolFont` 声明，以及可能大量的 `\DeclareMathSymbol` 声明。因此，最好把这些工作放在 **包文件** 中完成。

### 如何引入新的数学版本

正如在 [fonts in math](/tex/{{lang.url-fragment}}java/latex-math-fonts/) 中提到的，标准设置会自动声明 **两种数学版本**：`normal`（常规）和 `bold`。若要添加额外的版本，可以使用 `\DeclareMathVersion`，其唯一参数是新数学版本的名称。所有已声明的符号字体和数学字母在新版本中都会自动可用，并使用通过 `\DeclareMathAlphabet` 或 `\DeclareSymbolFont` 指定的默认字体。

随后，可通过 `\SetMathAlphabet` 和 `\SetSymbolFont` 为 **粗体数学版本** 或其他自定义版本进行相应的设置，正如本节前面所示。通常，这类工作也放在 **包文件** 中完成。

### 如何更改符号字体设置

我们已经看到如何添加新符号字体，同样的命令也可用于 **修改已有设置**。如果想在某些或全部数学版本中使用特殊字体，这会很有用。

下面是 LaTeX 的默认设置：

```tex
\DeclareMathVersion{normal} \DeclareMathVersion{bold}
\DeclareSymbolFont{operators} {OT1}{cmr}{m} {n}
\DeclareSymbolFont{letters} {OML}{cmm}{m}{it}
\DeclareSymbolFont{symbols} {OMS}{cmsy}{m}{n}
\DeclareSymbolFont{largesymbols} {OMX}{cmex}{m}{n}

% Special bold fonts only for these:
\SetSymbolFont {operators}{bold}{OT1}{cmr}{bx}{n}
\SetSymbolFont {letters}{bold}{OML}{cmm}{b}{it}
```

在标准设置中，诸如 `\log`、`\max` 等算子产生的文本与数字来自 **operators** 符号字体。若想让这些元素与正文主字体（例如 Computer Modern Sans 而非 Computer Modern Roman）更加匹配，可使用：

```tex
\SetSymbolFont{operators}{normal}{0T1}{cmss}{m} {n}
\SetSymbolFont{operators}{bold} {0T1}{cmss}{bx}{n}
```

**symbols** 与 **largesymbols** 符号字体在 TeX 中扮演独特角色，因而需要特定数量的 `\fontdimen` 参数。只有专门准备好的字体才能用作这两类符号字体。原则上，任何字体在加载时都可以通过 `\DeclareFontFamily` 的第三个参数或 `\DeclareFontShape` 的第六个参数来添加所需的 `\fontdimen` 参数。

## 6.7. 如何定义自己的 `.fd` 文件（示例）

如果你想为（PostScript）字体建立 `.fd` 文件，可遵循本节前面讨论的步骤。若使用 `fontinst` 生成必要的字体度量文件，`.fd` 文件会自动生成。但手工编写单个字体族的 `.fd` 文件相对容易，只要知道使用的 **字体编码**。

下面以 **Bitstream Charter** 在 `T1` 编码下的 `t1bch.fd` 为例：

```tex
\ProvidesFile{t1bch.fd}[2001/06/04 font definitions for T1/bch.]
% Primary declarations
\DeclareFontFamily{T1}{bch}{}
\DeclareFontShape{T1}{bch}{m}{n}{<-> bchr8t}{}
\DeclareFontShape{T1}{bch}{m}{sc}{<-> bchrc8t}{}
\DeclareFontShape{T1}{bch}{m}{sl}{<-> bchro8t}{}
\DeclareFontShape{T1}{bch}{m}{it}{<-> bchri8t}{}
\DeclareFontShape{T1}{bch}{b}{n}{<-> bchb8t}{}
\DeclareFontShape{T1}{bch}{b}{sc}{<-> bchbc8t}{}
\DeclareFontShape{T1}{bch}{b}{sl}{<-> bchbo8t}{}
\DeclareFontShape{T1}{bch}{b}{it}{<-> bchbi8t}{}
% Substitutions
\DeclareFontShape{T1}{bch}{bx}{n}{<->ssub * bch/b/n}{}
\DeclareFontShape{T1}{bch}{bx}{sc}{<->ssub * bch/b/sc}{}
\DeclareFontShape{T1}{bch}{bx}{sl}{<->ssub * bch/b/sl}{}
\DeclareFontShape{T1}{bch}{bx}{it}{<->ssub * bch/b/it}{}
\endinput
```

第一行是 **标识行**。接下来使用 `\DeclareFontFamily` 声明字体族和编码（`bch` 与 `T1`），其参数应对应 `.fd` 文件名（编码部分使用小写）。随后，每个 **系列/形状** 组合映射到相应的 `.tfm` 文件，使用 `<->` 表示可缩放到任意尺寸。文件的第二部分设置了 **替代**，用于缺失的组合（如粗体扩展系列）。

如果你拥有 **Charter** 的额外字体（如 Black、BlackItalic），可以为它们提供相应的虚拟字体，以在 `T1` 编码下完整模拟字符集。许多字体的虚拟文件可直接从互联网下载。

创建自己的 `.fd` 文件的另一大动机是 **混合不同族的字体**，将它们组合成一个新族。例如，下面将 **Aldus**（中等系列）与 **Palatino**（粗体）混合，形成新族 `zasj`：

```tex
\ProvidesFile{t1zasj.fd}
   [2003/10/12 font definitions for T1 Aldus/Palatino mix.]
\DeclareFontFamily{T1}{zasj}{}
% Medium series
\DeclareFontShape{T1}{zasj}{m}{n} {<->pasr9d}{}
\DeclareFontShape{T1}{zasj}{m}{sc}{<->pasrc9d}{}
\DeclareFontShape{T1}{zasj}{m}{it}{<->pasri9d}{}
\DeclareFontShape{T1}{zasj}{m}{sl}{<->ssub * pasj/m/it}{}
% Bold series
\DeclareFontShape{T1}{zasj}{b}{n}{<-> pplb8t}{}
\DeclareFontShape{T1}{zasj}{b}{sc}{<->pplbc8t}{}
\DeclareFontShape{T1}{zasj}{b}{sl}{<->pplbo8t}{}
\DeclareFontShape{T1}{zasj}{b}{it}{<->pplbi8t}{}
```

要使用这个 **伪族**，只需在 `T1` 编码下选择 `zasj`，并确保 `\textbf` 切换到 **b**（而非粗体扩展），因为该 `.fd` 文件未提供替代。下面的极简包装可以实现此目的：

```tex
\ProvidesPackage{fontmix}[2003/10/12 T1 Aldus/Palatino mix.]
\RequirePackage[T1]{fontenc}
\renewcommand\rmdefault{zasj} \renewcommand\bfdefault{b}
```

加载 `fontmix` 包后，标题将使用 Aldus 与 Palatino Bold 的组合。此类混合并非总能提升排版效果，仅作示例说明。

## 6.8. 声明顺序

NFSS 要求 **所有声明** 按特定顺序出现，以便检查必需信息是否完整。若顺序错误，系统会报错。下面列出必须遵守的依赖关系：

* `\DeclareFontFamily` 必须在 **`\DeclareFontEncoding`** 已声明相应编码后使用。  
* `\DeclareFontShape` 必须在对应的 **`\DeclareFontFamily`** 已声明后使用。  
* `\DeclareSymbolFont` 需要确保 **编码方案** 已合法。  
* `\SetSymbolFont` 额外要求 **数学版本** 已通过 `\DeclareMathVersion` 声明，并且相应的 **符号字体** 已声明。  
* `\DeclareSymbolFontAlphabet` 检查 **字母标识符** 是否可用以及符号字体是否已声明。  
* `\DeclareMathAlphabet` 检查所选 **命令名** 是否可用以及编码方案是否已声明。  
* `\SetMathAlphabet` 检查 **字母标识符** 已通过 `\DeclareMathAlphabet` 或 `\DeclareSymbolFontAlphabet` 声明，并且数学版本与编码方案已知。  
* `\DeclareMathSymbol` 检查 **命令名** 可用（未定义或已声明为数学符号），且符号字体已声明。  
* 在 `\begin{document}` 处，NFSS 进行额外检查。例如，验证每个编码方案的 **默认替代** 是否指向已知的字体形状组。
