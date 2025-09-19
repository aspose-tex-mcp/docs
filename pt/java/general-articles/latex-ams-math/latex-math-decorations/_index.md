---
translation: true
template: /templates/_template-java.md
linktitle: Símbolos decorados e estruturas compostas
title: 4. Símbolos decorados e estruturas compostas
weight: 40
url: /java/latex-math-decorations/
keywords: AMS-Latex, Amsmath, AMSXTRA, integrais de LaTeX, frações de LaTeX, decorações de LaTeX, setas de LaTeX, limites de LaTeX, relações modulares de LaTeX
description: Este artigo discute vários comandos que produzem várias estruturas de matemática de médio porte usando o pacote AMSMATH.
lastmod: "2025-06-16"
---

{{<section overview>}}

O pacote `amsmath` fornece alguns comandos para produzir estruturas como objetos semelhantes a fração e símbolos decorados. Isso discute cobre alguns deles.


## 4.1. FRAÇÕES GERAIS

O pacote `amsmath` define o comando `\genFrac`, que produz uma fração generalizada.

```tex
\genfrac{ldelim}{rdelim}{thick}{style}{num}{denom}
```

Os dois primeiros argumentos definem delimitadores esquerda e direita, respectivamente. Usando o terceiro argumento, *thick* você pode substituir a espessura padrão da regra de fração. Por exemplo, os coeficientes binominais (veja abaixo) usam o valor `0pt` para este argumento para tornar a linha invisível. O valor padrão (quando deixado vazio) da espessura da linha é determinado pela configuração atual da fonte para matemática. A lista a seguir contém padrões usados ​​nos exemplos deste artigo.

| ***Estilo*** | ***Espessura padrão*** |
|:---:|:---:|
| text/display | 0.4pt |
| script | 0.34pt |
| scriptscript | 0.24pt |

O quarto argumento, *style*, substitui (se não for deixado vazio) o estilo de matemática para o layout e o tamanho da fonte usado. O valor deve estar no intervalo 0-3: 0 - `\displayStyle`, 1 -`\textStyle`, 2 - `\scriptStyle`, 3 -`\scriptScriptStyle`. Se esse argumento for deixado vazio, o estilo será selecionado de acordo com as regras normais para as frações. Os dois últimos argumentos são o numerador e o denominador.

> Os antigos comandos de fracção `\over`, `\overwithdelims`, `\atop`, `\atopwithdelims`, `\above` e `\abovewithdelims`, que o LaTeX padrão herda do TeX, produzem avisos quando são utilizados com o pacote `amsmath`.

### 4.1.1. Frações simples

Tendo o comando `\genFrac`, o pacote `amsmath` também define três comandos como uma taquigrafia conveniente: `\frac`, `\dfrac` e `\tfrac`.

```tex
\newcommand\frac [2]{\genfrac{}{}{}{}{#1}{#2}}
\newcommand\dfrac[2]{\genfrac{}{}{}{0}{#1}{#2}}
\newcommand\tfrac[2]{\genfrac{}{}{}{1}{#1}{#2}}
```

O exemplo abaixo demonstra o uso desses comandos:

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
  \frac{1}{k} \log_2 c(f)
  \quad \tfrac{1}{k} \log_2 c(f)
\end{equation}
Text: $ \sqrt{ \frac{1}{k} \log_2 c(f) } \quad
        \sqrt{ \dfrac{1}{k} \log_2 c(f) }\, $.

```

![\ frac, \ dfrac e \ tfrac](/tex/images/java/tutorial/latex-ams-math-4-1.png)

### 4.1.2. Coeficientes binomiais

Outra estrutura semelhante a uma fração são os coeficientes binomiais. Para ajudá -lo a digitar, o pacote `amsmath` fornece comandos semelhantes` \binom`, `\dbinom` e `\tbinom`.

É assim que eles abreviam o comando `\genFrac`:


```tex
\newcommand\binom[2]{\genfrac{(}{)}{0pt}{}{#1}{#2}}
\newcommand\dbinom[2]{\genfrac{(}{)}{0pt}{0}{#1}{#2}}
\newcommand\tbinom[2]{\genfrac{(}{)}{0pt}{1}{#1}{#2}}
```

E aqui está o exemplo:

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
  \binom{k}{2} 2^{k - 1} + \tbinom{k - 1}{2} 2^{k - 2}
\end{equation}
Text: $ \binom{k}{2} 2^{k - 1} + \dbinom{k - 1}{2} 2^{k - 2} $.
```

![\binom, \dbinom e \tbinom](/tex/images/java/tutorial/latex-ams-math-4-2.png)

### 4.1.3. Frações contínuas

Se você precisar compensar uma matriz de fração, que é essencialmente uma fração infinita, também conhecida como "fração contínua", existe o comando `\cfrac` no pacote`amsmath`. Passe o argumento opcional `[l]` ou `[r]` para alinhar um numerador à esquerda ou à direita, que é centralizada por padrão.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation*}
\cfrac {1}{\sqrt{2} +
  \cfrac {1}{\sqrt{3} +
    \cfrac {1}{\sqrt{4} +
      \cfrac[r] {1}{\sqrt{5} +
        \cfrac[l] {1}{\sqrt{6} + \dotsb }
}}}}
\end{equation*}
```

![Uma fração contínua](/tex/images/java/tutorial/latex-ams-math-4-3.png)

## 4.2. Matemática em caixa

O pacote `amsmath` fornece o comando `\boxed` semelhante ao \fbox` para colocar o conteúdo do modo matemático em uma caixa.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
  \boxed { f(x_0 - x) \leq f(x_0) \leq f(x_0 + x) }
\end{equation}
```

![Uma fórmula em caixa](/tex/images/java/tutorial/latex-ams-math-4-4.png)

## 4.3. Posicionando os limites

Subscritos e superscritos em integrais, somas, produtos ou outros operadores podem ser colocados acima e abaixo do operador de matemática (a "posição limitada") ou na posição de subscrito/substituto à direita do operador. Normalmente, os limites não são usados ​​no texto (caso contrário, as linhas podem se espalhar). Em uma fórmula exibida, a colocação depende do operador. O exemplo a seguir mostra o posicionamento padrão no LATEX.

```tex
\[
\sum_{n=1}^N \qquad \int_{-\infty}^\infty \qquad \lim_{x \to x_0}
\]
Text: $\sum_{n=1}^N$, $\int_{-\infty}^\infty$, $\lim_{x \to x_0}$.
```

![O posicionamento padrão dos subscritos/superscripts no LaTeX](/tex/images/java/tutorial/latex-ams-math-4-5.png)

O pacote `amsmath` oferece opções para controlar o posicionamento. Eles estão listados abaixo, onde * padrão * marca o comportamento caso o pacote `amsmath` seja usado com uma classe padrão de documentos de LaTeX, mas sem nenhuma dessas opções.

|||
|:---:|---|
| `intlimits`, `nointlimits` | Posiciona sobrescritos/subscritos dos símbolos de integração acima e abaixo ou ao lado (padrão), respetivamente. Utilizado apenas em fórmulas exibidas. |
| `sumlimits`, `nosumlimits` | Posiciona sobrescritos/subscritos de *operadores grandes* (soma, produto, etc.) acima e abaixo (padrão) ou ao lado, respetivamente. Utilizado apenas em fórmulas exibidas. |
| `nomelimites`, `nonamelimits` | Semelhante aos `sumlimits` ou `nosumlimits`, mas para certos operadores, ou "nomes de operadores", como `inf`, `sup`, `lim`, `min`, `max`, que são tradicionalmente compostos com subscritos abaixo, pelo menos quando ocorrem numa fórmula apresentada. |

A TEX possui três comandos primitivos que, apareceram imediatamente após o nome do símbolo ou operador, controlam o posicionamento de subscritos/superscritos: `\Limits`, ` \nolimits` e `\DisplaylImits`. O comando `\DisplaylIlits` produz subscritos/superscripts na posição limitada quando o estilo de matemática atual é um estilo de exibição. Este é o comportamento padrão sempre que um símbolo do operador de classe * aparece ou um comando `\Mathop` é usado. Se você precisar digitar um operador com subscritos/superestritos na posição limitada fora de uma tela, deverá declará -lo individualmente usando o comando `\limits`.

Compare o exemplo a seguir com o anterior.

```tex
\[
\sum\nolimits_{n=1}^N \qquad \int\limits_{-\infty}^\infty \qquad \lim\displaylimits_{x \to x_0}
\]
Text: $\sum\nolimits_{n=1}^N$, $\int\limits_{-\infty}^\infty$, $\lim\displaylimits_{x \to x_0}$.
```

![Controlando a colocação dos subscritos/superescrits com as primitivas TEX](/tex/images/java/tutorial/latex-ams-math-4-6.png)

## 4.3. Múltiplas integrais

Para digitar vários sinais integrais com espaços bem ajustados entre eles no texto e nos monitores, use os comandos `\iint`, ` \iiint` e `\iiiint`. O `\iDotsint` produz dois sinais integrais com os pontos de elipse entre eles.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather*}
\iint \limits _V f(x,y) \,dx \,dy \\
\iiint \limits _V f(x,y,z) \,dx \,dy \,dz \\
\iiiint \limits _V f(t,x,y,z) \,dt \,dx \,dy \,dz \\
\idotsint \limits _V f(x_1, \dots, x_k) \,\mathbf{dx}
\end{gather*}
```

![Múltiplas integrais](/tex/images/java/tutorial/latex-ams-math-4-7.png)

## 4.4. Relações modulares

A notação "mod" para as classes de equivalência de números inteiros é governada pelas convenções de espaçamento especiais. Para lidar com isso, o pacote `amsmath` oferece os comandos`\mod`, `\bmod`, `\pmod` e `\pod`. O exemplo a seguir mostra o uso desses comandos.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align*}
u & \equiv v + 1 \mod{n^2} \\
u & \equiv v + 1 \bmod{n^2} \\
u & = v + 1 \pmod{n^2} \\
u & = v + 1 \pod{n^2}
\end{align*}
The in-text layout: $ u = v + 1 \pmod{n^2} $
\begin{gather*}
(m \bmod n) = k^2 \, ; \quad x \equiv y \pmod b \, ; \\
x \equiv y \mod c \, ; \quad x \equiv y \pod d\, .
\end{gather*}
```

![Relação modular](/tex/images/java/tutorial/latex-ams-math-4-8.png)

> Com `amsmath`, o espaçamento de `\pmod` é diminuído dentro de uma fórmula não apresentada.

## 4.5. Acentos matemáticos do ponto

Além dos detalhes em matemática `\dot` e `\ddot`, o pacote `amsmath` fornece os comandos`\dddot` e `\ddddot`, que produzem detalhes em pontas triplas e quadruplas, respectivamente.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
$ \dot{A} \quad \ddot{B} \quad \dddot{C} \quad \ddddot{D} $
```

![Acentos do ponto](/tex/images/java/tutorial/latex-ams-math-4-9.png)

## 4.6. Fazendo superestritos da Acentos: o pacote `amsxtra`

O pacote `AMSXTRA` oferece um recurso útil, uma coleção de comandos simples para colocar sotaques como superestritos na subformula:

```tex
\usepackage{amsxtra}
% -------------------------------------------------------------------------------
$(abc)\spdddot$ \quad $(abc)\spddot$ \quad $(abc) \spdot$ \\
$(abc)\spbreve$ \quad $(abc)\spcheck$ \\
$(abc)\sphat$ \quad $(abc)\sptilde$
```

![Acentos como superscritos](/tex/images/java/tutorial/latex-ams-math-4-10.png)

## 4.7. Outras decorações

O LATEX padrão possui o comando `\Stackrel` que coloca um superestrado acima de um símbolo *Relation* . Além disso, o pacote `AMSMATH` define os comandos` \overset` e `\ UnderSet`. Use -o para colocar o material acima ou abaixo de qualquer símbolo *Ordinary* ou *Relation*  ou *Operador Binário*.

O comando `\sideet`adiciona decorações a qualquer símbolo *Operator* (soma, produto, etc.), além dos limites normais. Estes são colocados nas posições subscritas e superscritões à esquerda e à direita do *Operator*.

```tex
\[ \overset{*}{X} > \underset{*}{X}
\iff \sideset{}{'}\sum_{a,b \in \mathbf{R^*}}
\overset{a}{\underset{b}{X}} = X \]
```

![Mais decoração](/tex/images/java/tutorial/latex-ams-math-4-11.png)