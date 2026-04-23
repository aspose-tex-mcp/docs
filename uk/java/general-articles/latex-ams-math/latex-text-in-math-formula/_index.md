---
translation: true
template: /templates/_template-java.md
linktitle: Текст у математичних формулах
title: 6. Текст у математичних формулах 
weight: 60
url: /java/latex-text-in-math-formula/
keywords: ams-latex, amsmath, латексні математичні оператори, латексні математичні функції, латексний математичний текст
description: У цій статті розглядається вставка тексту в математичні формули LaTeX. Він також описує математичні функції та оператори, а також метод їх визначення.
lastmod: "2026-04-21"
---

{{<section overview>}}

## 6.1. Команда `\text`

Щоб розмістити звичайний текст у математиці, краще використовувати команду `\text`, а не такі команди, як `\mathrm`. Команда `\text` гарантує, що текст встановлено з використанням правильного розміру шрифту. Шрифт буде текстовим шрифтом, який використовується поза поточним математичним матеріалом.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
\text{Also, if } \Delta_{\text{max up}} = \Delta_{\text{min down}} \notag \\
\text{(for all ups and downs) then} \notag \\
\Delta_{\text{sum of ups}} = \Delta_{\text{sum of downs}}
\end{gather}
```

![Текст всередині математики](/tex/images/java/tutorial/latex-ams-math-6-1.png)

## 6.2. Імена операторів

Назви загальних математичних функцій (наприклад, *sin* і *log*) і операторів (наприклад, *min* і *sup*) зазвичай бажано відрізняти від назв змінних, виділених курсивом. Отже, вони традиційно встановлюються як текст латиницею. У стандартному LaTeX є попередньо визначені команди для найпоширеніших функцій і операторів. Пакет `amsmath` достатньо розширює набір таких команд. У наведеній нижче таблиці перераховано як «стандартні» команди, так і команди, надані `amsmath`. Останні виділені жирним шрифтом. Ті, виділені курсивом, можуть мати нижній/верхній індекс у граничній позиції під час використання у відображених формулах.

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

![Функції та оператори](/tex/images/java/tutorial/latex-ams-math-6-2.png)

Часто виявляється, що цього списку недостатньо. Пакет `amsmath` визначає загальний метод для визначення нових "імен операторів".


```tex
\DeclareMathOperator*{cmd}{text}
```

Команда `\DeclareMathOperator` визначає `cmd` для створення `тексту` у відповідному шрифті для "текстових операторів". Якщо очікується, що новий оператор матиме нижні/верхні індекси в граничній позиції (при використанні в дисплеях), тоді слід використовувати форму із зірочкою `\DeclareMathOperator*`. На додаток до використання належного шрифту, `\DeclareMathOperator` встановлює хороші інтервали з обох боків імені оператора. Текстовий аргумент обробляється за допомогою "псевдотекстового режиму", в якому

 - Дефіс char друкується як текстовий дефіс (а не знак мінус) (див. `\supminus` у наступному прикладі).
 - Символ зірочки `*` друкується як рельєфна текстова зірочка (не по центру).
 - В іншому випадку текст обробляється в математичному режимі, тому пробіли ігноруються, і ви можете використовувати нижні, верхні індекси та інші елементи.


У наступному прикладі показано, як надати команду `\meas` для нової назви функції "meas" (вимірювання) і операторних функцій `\esssup` і `\supminus` (обидві можуть мати нижній/надрядковий індекс у граничній позиції).


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

![Нові назви функцій і назви операторів](/tex/images/java/tutorial/latex-ams-math-6-3.png)

Такі декларації повинні бути в преамбулі, і їх неможливо тимчасово змінити. Строго кажучи, `\DeclareMathOperator` можна використовувати лише для імен команд, які раніше не використовувалися. Щоб замінити існуючу команду, ви повинні спочатку видалити попереднє визначення, перш ніж повторно оголосити його.


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

![Перевизначення назви функції](/tex/images/java/tutorial/latex-ams-math-6-4.png)