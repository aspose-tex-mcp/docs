---
translation: true
template: /templates/_template-java.md
linktitle: Текст в математических формулах
title: 6. Текст в математических формулах 
weight: 60
url: /java/latex-text-in-math-formula/
keywords: ams-latex, amsmath, латехные математические операторы, латехные математические функции, латехный математический текст
description: В этой статье рассматривается вставка текста в математические формулы LaTeX, а также математические функции и операторы, а также метод их определения.
lastmod: "2024-09-24"
---

{{<section overview>}}

## 6.1. Команда `\text`

Чтобы поместить обычный текст в математику, лучше использовать команду `\text`, а не такие команды, как `\mathrm`. Команда `\text` гарантирует, что текст будет установлен с использованием правильного размера шрифта. Шрифт будет текстовым шрифтом, используемым вне текущего математического материала.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
\text{Also, if } \Delta_{\text{max up}} = \Delta_{\text{min down}} \notag \\
\text{(for all ups and downs) then} \notag \\
\Delta_{\text{sum of ups}} = \Delta_{\text{sum of downs}}
\end{gather}
```

![Текст внутри математики](/tex/images/java/tutorial/latex-ams-math-6-1.png)

## 6.2. Имена операторов

Имена общих математических функций (например, *sin* и *log*) и операторов (например, *min* и *sup*) обычно предпочитают отличать от имен переменных, выделенных курсивом. Так, они традиционно задаются в виде текста латинским шрифтом. В стандартном LaTeX есть предопределенные команды для наиболее распространенных функций и операторов. Пакет amsmath достаточно расширяет набор таких команд. В следующей таблице перечислены как «стандартные» команды, так и команды, предоставляемые amsmath. Последние выделены жирным шрифтом. Те, что выделены курсивом, могут иметь нижний/верхний индекс в предельном положении при использовании в отображаемых формулах.

|||||||
|:---:|---|:---:|---|:---:|---|
| !["Arccos"](/tex/images/java/tutorial/latex-ams-math-foper-6-1.png) | `\arccos` | !["Arcsin"](/tex/images/java/tutorial/latex-ams-math-foper-6-14.png) | `\arcsin` | !["Arctan"](/tex/images/java/tutorial/latex-ams-math-foper-6-27.png) | `\arctan` |
| !["Arg"](/tex/images/java/tutorial/latex-ams-math-foper-6-2.png) | `\arg` | !["Cos"](/tex/images/java/tutorial/latex-ams-math-foper-6-15.png) | `\cos` | !["Cosh"](/tex/images/java/tutorial/latex-ams-math-foper-6-28.png) | `\cosh` |
| !["Cot"](/tex/images/java/tutorial/latex-ams-math-foper-6-3.png) | `\cot` | !["Coth"](/tex/images/java/tutorial/latex-ams-math-foper-6-16.png) | `\coth` | !["Csc"](/tex/images/java/tutorial/latex-ams-math-foper-6-29.png) | `\csc` |
| !["Deg"](/tex/images/java/tutorial/latex-ams-math-foper-6-4.png) | `\deg` | !["Det"](/tex/images/java/tutorial/latex-ams-math-foper-6-17.png) | *`\det`* | !["Dim"](/tex/images/java/tutorial/latex-ams-math-foper-6-30.png) | `\dim` |
| !["Exp"](/tex/images/java/tutorial/latex-ams-math-foper-6-5.png) | `\exp` | !["Gcd"](/tex/images/java/tutorial/latex-ams-math-foper-6-18.png) | *`\gcd`* | !["Hom"](/tex/images/java/tutorial/latex-ams-math-foper-6-31.png) | `\hom` |
| !["Inf"](/tex/images/java/tutorial/latex-ams-math-foper-6-6.png) | *`\inf`* | !["Injlim"](/tex/images/java/tutorial/latex-ams-math-foper-6-19.png) | ***`\injlim`*** | !["Ker"](/tex/images/java/tutorial/latex-ams-math-foper-6-32.png) | `\ker` |
| !["Lg"](/tex/images/java/tutorial/latex-ams-math-foper-6-7.png) | `\lg` | !["Lim"](/tex/images/java/tutorial/latex-ams-math-foper-6-20.png) | *`\lim`* | !["Liminf"](/tex/images/java/tutorial/latex-ams-math-foper-6-33.png) | *`\liminf`* |
| !["Limsup"](/tex/images/java/tutorial/latex-ams-math-foper-6-8.png) | *`\limsup`* | !["Ln"](/tex/images/java/tutorial/latex-ams-math-foper-6-21.png) | `\ln` | !["Log"](/tex/images/java/tutorial/latex-ams-math-foper-6-34.png) | `\log` |
| !["Max"](/tex/images/java/tutorial/latex-ams-math-foper-6-9.png) | *`\max`* | !["Min"](/tex/images/java/tutorial/latex-ams-math-foper-6-22.png) | *`\min`* | !["Pr"](latex-ams-math-foper-6-35.png) | *`\Pr`* |
| !["Projlim"](/tex/images/java/tutorial/latex-ams-math-foper-6-10.png) | ***`\projlim`*** | !["Sec"](/tex/images/java/tutorial/latex-ams-math-foper-6-23.png) | `\sec` | !["Sin"](/tex/images/java/tutorial/latex-ams-math-foper-6-36.png) | `\sin` |
| !["Sinh"](/tex/images/java/tutorial/latex-ams-math-foper-6-11.png) | `\sinh` | !["Sup"](/tex/images/java/tutorial/latex-ams-math-foper-6-24.png) | *`\sup`* | !["Tan"](/tex/images/java/tutorial/latex-ams-math-foper-6-37.png) | `\tan` |
| !["Tanh"](/tex/images/java/tutorial/latex-ams-math-foper-6-12.png) | `\tanh` | !["Varinjlim"](/tex/images/java/tutorial/latex-ams-math-foper-6-25.png) | ***`\varinjlim`*** | !["Varliminf"](/tex/images/java/tutorial/latex-ams-math-foper-6-38.png) | ***`\varliminf`*** |
| !["Varlimsup"](latex-ams-math-foper-6-13.png) | ***`\varlimsup`*** | !["Varprojlim"](/tex/images/java/tutorial/latex-ams-math-foper-6-26.png) | ***`\varprojlim`*** |  |  |


```tex
\usepackage[fleqn]{amsmath}
\newcommand\abs[1]{\lvert#1\rvert}
\setlength\mathindent{0pt}
% -------------------------------------------------------------------------------
\begin{gather*}
\lim_{x \rightarrow 0} \frac{ \sin^2(x) }{ x^2 } = 1 \\
\varliminf_{n \rightarrow \infty}
\abs{a_{n+1}} / \abs{a_n} = 0 \\
\varinjlim (m_i^\lambda \cdot M)^* \le
\varprojlim_{A/p \rightarrow \lambda(A)}A_p \le 0
\end{gather*}
```

![Функции и операторы](/tex/images/java/tutorial/latex-ams-math-6-2.png)

Зачастую оказывается, что этого списка недостаточно. Пакет amsmath определяет общий метод определения новых «имен операторов».


```tex
\DeclareMathOperator*{cmd}{text}
```

Команда `\DeclareMathOperator` определяет `cmd` для создания `текста` в соответствующем шрифте для «текстовых операторов». Если ожидается, что новый оператор будет иметь индексы/верхние индексы в предельной позиции (при использовании в дисплеях), то следует использовать звездчатую форму `\DeclareMathOperator*`. В дополнение к использованию правильного шрифта, `\DeclareMathOperator` устанавливает хороший интервал по обе стороны от имени оператора. Текстовый аргумент обрабатывается с использованием «псевдотекстового режима», в котором

 - Символ дефиса печатается как текстовый дефис (а не знак минуса) (см. `\supminus` в следующем примере).
 - Символ звездочки `*` печатается в виде выпуклой текстовой звездочки (не по центру).
 - В противном случае текст обрабатывается в математическом режиме, поэтому пробелы игнорируются, и вы можете использовать нижние и верхние индексы и другие элементы.


В следующем примере показано, как предоставить команду `\meas` для нового имени функции "meas" (мера) и операторных функций `\essup` и `\supminus` (обе могут иметь нижние/верхние индексы в предельной позиции).


```tex
\usepackage[fleqn]{amsmath}
\DeclareMathOperator \meas {meas}
\DeclareMathOperator*\esssup {ess \, sup}
\DeclareMathOperator*\supminus{sup - minus*}
\newcommand\abs [1]{\lvert#1\rvert}
\newcommand\norm[1]{\lVert#1\rVert}
% -------------------------------------------------------------------------------
\begin{gather*}
  \norm{f}_\infty = \esssup_{x \in R^n} \abs{f(x)} \\
  \meas_1 \{ u \in R_+^1 \colon f^*(u)>\alpha \} \\
  \quad \esssup_{x \in R^i} \; \meas_i
  \{ u \in R^n \colon \abs{f(u)} \geq \alpha \} \\
  \quad (\forall \alpha \in \supminus_{f^*} R_{*+})
\end{gather*}
```

![Новые имена функций и имена операторов](/tex/images/java/tutorial/latex-ams-math-6-3.png)

Такие декларации должны присутствовать в преамбуле, и временно изменить их невозможно. Строго говоря, `\DeclareMathOperator` можно использовать только для имен команд, которые ранее не использовались. Чтобы заменить существующую команду, необходимо сначала удалить предыдущее определение, прежде чем переобъявлять его.


```tex
\usepackage{amsmath}
%% Low-level TeX needed here to cancel the old the definition of \csc:
\let \csc \relax
\DeclareMathOperator\csc{cosec}
\newcommand\calQ{\mathcal{Q}}
% -------------------------------------------------------------------------------
\[
\varlimsup_{n\to\infty} \calQ (u_n, u_n - u^{\#})
  \ge \csc (\calQ' (u^{\#}))
\]
```

![Переопределение имени функции](/tex/images/java/tutorial/latex-ams-math-6-4.png)