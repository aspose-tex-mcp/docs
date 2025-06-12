---
translation: true
template: /templates/_template-java.md
linktitle: 5. 分数，二项式系数和数学样式
title: 分数，二项式系数和数学样式
weight: 50
url: /java/latex-math-fractions-binomial-styles/
keywords: 乳胶，乳胶数学公式，乳胶数学，乳胶数学分数，乳胶数学二项式系数，乳胶数学样式
description: 了解诸如分数，二项式系数等等数学结构的排版以及Tex Texsets公式的数学样式。
lastmod: "2025-06-10"
---

{{<section overview>}}

您在数学公式中可能会发现的另一件常见的东西是分数和其他结构，其中像分子之类的东西放在分母之上。后者的一个例子是二项式系数。

![类似分数的数学对象](/tex/images/java/tutorial/latex-math-5-1.png)

您可以通过键入`$$ 1 \ over2 $$`和$ n+n+1 \ over3 $$和$$ \ n+1 \ select3 $$'来获取这三个公式。

命令“\over”适用于公式中的所有内容，除非您将其括在带有括号的特定子公式中，在这种情况下，“\over”适用于该子公式中的所有内容。

![分数](/tex/images/java/tutorial/latex-math-5-2.png)

不能在同一个子公式中两次使用 `\over`，例如，输入 `a\over b\over 2`。相反，你应该明确指定什么覆盖什么：

![嵌套的分数](/tex/images/java/tutorial/latex-math-5-3.png)

看来这两个公式看起来都不好。在这种情况下，通常最好将分数转换为“斜线形式”。例如，最后两个公式应键入如下：

![斜线形式的分数](/tex/images/java/tutorial/latex-math-5-4.png)

这是更复杂的例子：

![斜线形式的分数](/tex/images/java/tutorial/latex-math-5-5.png)

查看上面的示例，您可能已经注意到字母和其他符号在分数中出现时有时会变小，就像它们在下标或上标时它们变小一样。现在让我们谈谈Tex选择符号大小的方式。 Tex具有八种可以处理公式的样式：

 * 显示样式(用于线条上显示的公式)
 * 文本样式(用于嵌入文本中的公式)
 * 脚本样式(用于用作上标或下标的子形式)
 * 脚本样式（用于二阶上标或下标）
以及四种“紧凑”样式，这些样式几乎相同，只是上标和下标的凸起程度较小。我们将这八种样式称为 *D*、*D'*、*T*、*T'*、*S*、*S'*、*SS*、*SS'*，其中 *D* 表示显示样式，*D'* 表示紧凑显示样式，*T* 表示文本样式，等等。TeX 还使用三种大小来输入数学公式：文本大小、脚本大小和脚本脚本大小。

要在运行文本中排除公式，请将其包装在`$ ... $`中;这会产生样式 *t*的公式。或者，您可以将其包装在`$$ ... $$`以获取显示的公式；这将显示样式 *d*的公式。公式的子形成可能具有不同的样式。一旦知道样式，您就可以确定Tex使用的类型大小：

![尺寸映射的样式](/tex/images/java/tutorial/latex-math-5-6.png)

没有“*SSS*”样式，因为这样的微小符号甚至比Scriptscript的符号更不可阅读。

![根据公式样式的下标和超级折叠的样式](/tex/images/java/tutorial/latex-math-5-7.png)

例如，如果要以样式 *D* 排版 `x^{a_b}`，则 `a_b` 将以样式 *S* 排版，而 `b` 将以样式 *SS* 排版；结果是 ![任意程度的根源](/tex/images/java/tutorial/latex-math-5-8.png)

我们还没有看到样式 *d*和 *t*之间的任何区别。尽管在每种情况下都使用了脚本大小，但指数的定位实际上实际上有略有差异。但是，在分数的情况下，样式 *d*和 *t*之间存在很大的区别：

![分母和分子的样式，具体取决于分数样式](/tex/images/java/tutorial/latex-math-5-9.png)

因此，如果您在文本中输入 `$1\over2$`，则会获得样式 *S* 而不是样式 *S'*。但是，如果您在显示的公式中输入 `$$1\over2$$`，则会获得样式 *T* 而不是样式 *T'*。

最后，`\underline` 不会改变样式。数学重音符以及命令 `\sqrt` 和 `\overline` 会将非约束样式更改为约束样式，同时保留约束样式。

您可能不喜欢 TeX 根据自身规则选择的样式。您可以通过输入 `\displaystyle` 或 `\textstyle` 或 `\scriptstyle` 或 `\scriptscriptstyle` 来指定所需的样式；所选样式将一直应用到公式或子公式结束，或者直到您选择其他样式。例如，`$$n+\scriptstyle n+\scriptscriptstyle n.$$` 会显示以下内容：

![手动样式控制](/tex/images/java/tutorial/latex-math-5-10.png)

它表明，随着样式的变化，加号也会变得更小，并且Tex在脚本样式中均不宽。

让我们来看看另一个例子 - 持续的部分。

![持续的部分](/tex/images/java/tutorial/latex-math-5-11.png)

您可以通过打字来获得它

```tex
$$a_0+{1\over\displaystyle a_1+
        {\strut 1\over\displaystyle a_2+
          {\strut 1\over\displaystyle a_3+
            {\strut 1\over a_4}}}}$$
```

没有此公式中的“ \ strut”和`\ displayStyle`，结果将有所不同：

![持续的分数而没有美化技巧](/tex/images/java/tutorial/latex-math-5-12.png)

LaTeX 定义了宏 `\frac`，允许您使用另一种语法指定分数：`\frac{a}{b}` 等同于 `a\over b`，`\frac12` 等同于 `1\over2`。

Tex中还有另一个操作`\ atop`，就像``\ off``一样，除了它不会绘制分数线：

![\ atop命令](/tex/images/java/tutorial/latex-math-5-13.png)

乳胶格式还定义了`\ select`，就像``\ atop``一样，但将结果包含在括号中：

![\选择宏](/tex/images/java/tutorial/latex-math-5-14.png)

它被称为`\ select`，因为它是二项式系数的常见符号，该符号说明了从 *n*事物中选择 *k*事物的几种方法。

命令“\over”、“\atop”和“\choose”不能混用。例如，“$$n\choose k\over 2$$”是非法的。必须使用分组才能得到“$${n\choose k}\over2$$”或“$$n\choose{k\over2}$$”。

TeX 有一个 `\above` 命令，它是 `\over` 和 `\atop` 的通用版本。在这个命令中，你可以输入 `\above<dimen>` 来指定线段的精确粗细。例如：

```tex
$$\displaystyle{\frac{a}{b}\above1pt\displaystyle{\frac{c}{d}}$$
```

将在分子和分母中的分数之间产生具有1PT厚规则的复合部分：

![\上方宏](/tex/images/java/tutorial/latex-math-5-15.png)