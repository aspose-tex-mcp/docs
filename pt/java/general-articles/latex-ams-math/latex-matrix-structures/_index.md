---
translation: true
template: /templates/_template-java.md
linktitle: Matriz e ambientes semelhantes
title: 3. Matriz e ambientes semelhantes
weight: 30
url: /java/latex-ams-matrix/
keywords: AMS-LATEX, AMSMATH, AMSCD, MATRIXA LATEX, CASOS DE LATEX, LATEX DELARRAY, Diagramas de comutativos de LaTeX
description: Este artigo fornece uma breve introdução nas estruturas do tipo matriz de LaTeX com tipo de LaTeX usando pacotes AMS-Latex.
lastmod: "2025-06-16"
---

{{<section overview>}}

Existem vários ambientes para as estruturas semelhantes a matrizes com tipo de matriz definidas no pacote `amsmath`. Eles são todos semelhantes ao ambiente padrão do LaTex `Array` em sintaxe e layout. Em geral, uma grande variedade de estruturas matemáticas bidimensionais e layouts tabulares pode ser descrita como matrizes.

Três ambientes - `casos`, ` matrix` e `pmatrix` - substitua os comandos do LaTeX padrão. Os comandos padrão usam uma notação diferente para que não possam ser usados ​​juntamente com os formulários de ambiente discutidos aqui. O pacote `amsmath` produzirá uma mensagem de erro se um dos comandos antigos for usado. Por outro lado, se você tentar usar os formulários de ambiente `AMSMATH` sem carregar o pacote, provavelmente receberá a seguinte mensagem de erro:` "Alinhamento extraviado Caractere da guia de alinhamento &" `.


## 3.1. O ambiente `casos`

O ambiente `case` é usado para lidar com construções, onde uma única equação possui algumas variantes. Tais construções são muito comuns em matemática. Produz uma matriz com duas colunas, ambas alinhadas à esquerda.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
P_{r - j} = \begin{cases}
                     0 & \text{if $r - j$ is odd,} \\
r! \, (-1)^{(r - j)/2} & \text{if $r - j$ is even.}
\end{cases}
\end{equation}
```

![Ambiente de casos](/tex/images/java/tutorial/latex-ams-math-3-1.png)

Observe o uso do comando `\text` e o" modo de matemática incorporado "nas seqüências de texto.

## 3.2. Os ambientes da matriz

Os ambientes da matriz, diferentemente do `Array` do LATEX, não aceitam um argumento que especifica os formatos das colunas. Em vez disso, eles fornecem um formato padrão: até 10 colunas centralizadas. O espaçamento também difere um pouco do padrão em `Array`. Os exemplos a seguir ilustram os ambientes `matrix`, ` pmatrix`, `bmatrix`, ` bmatrix`, `vmatrix` e` vmatrix`.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather*}
\begin{matrix} 0 & 1 \\ 1 & 0 \end{matrix} \quad \begin{pmatrix} 0 & -i \\i & 0 \end{pmatrix} \\
\begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix} \quad \begin{Bmatrix} 1 & 0 \\ 0 & -1 \end{Bmatrix} \\
\begin{vmatrix} a & b \\ c & d \end{vmatrix} \quad \begin{Vmatrix} i & 0 \\ 0 & -i \end{Vmatrix}
\end{gather*}
```

![Ambientes Matrix](/tex/images/java/tutorial/latex-ams-math-3-2.png)

O contador `maxmatrixcols` determina o número máximo de colunas em um ambiente de matriz. Você pode alterá -lo usando o comando de contador padrão do LATEX. O valor do parâmetro de comprimento `\arrayColsep` determina a quantidade de espaço entre as colunas. Assim como em matrizes padrão, mas nenhum espaço é adicionado em ambos os lados da matriz. Mais colunas farão o LaTeX trabalhar mais e exigir mais recursos. No entanto, é possível definir `maxmatrixcols` para 20 ou mais, sem um desempenho notável, pois com as implementações típicas de Tex de hoje são menos importantes.


```tex
\usepackage{amsmath}
\setcounter{MaxMatrixCols}{20}
% -------------------------------------------------------------------------------
\[
\begin{Vmatrix}
\,a&b&c&d&e&f&g&h&i&j &\cdots\,{} \\
&a&b&c&d&e&f&g&h&i &\cdots\,{} \\
& &a&b&c&d&e&f&g&h &\cdots\,{} \\
& & &a&b&c&d&e&f&g &\cdots\,{} \\
& & & &\ddots&\ddots&\hdotsfor[2]{5}\,{}
\end{Vmatrix} \]
```

![Mais colunas em ambientes matriciais](/tex/images/java/tutorial/latex-ams-math-3-3.png)

Neste exemplo, o comando `\hdotsfor` é usado para produzir uma linha de pontos em uma matriz, abrangendo um determinado número de colunas. O parâmetro opcional (aqui 2) pode ser usado para especificar um multiplicador para o espaço padrão (3 unidades de matemática) entre os pontos. O espaço fino e o grupo BRACE `\, {}` no final de cada linha simplesmente fazem com que o layout pareça melhor; Juntos, eles produzem dois espaços finos, cerca de 6mu ou 1/3em.

Para produzir uma pequena matriz em linha para uso no texto, você pode usar o ambiente `SmallMatrix`.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
To show the effect of the matrix on surrounding lines inside a paragraph, we put it here:
$ \left( \begin{smallmatrix}
1 & 0 \\ 0 & -1
\end{smallmatrix} \right) $
and follow it with enough text to ensure that there is at least one full line below the matrix.
```

![O ambiente SmallMatrix](/tex/images/java/tutorial/latex-ams-math-3-4.png)

Observe que as linhas de texto não estão separadas, mesmo que a linha antes da pequena matriz contenha letras com descendentes.

## 3.3. Empilhando em subscritos e superestritos

Às vezes, pode ser necessário digitar várias linhas em um subscrito ou substituto. Para fazer isso, você pode usar o comando `\Substack` com `\\ `delimitando linhas.

O ambiente `Subarray` é uma estrutura um pouco mais geral que permite alinhar as linhas à esquerda ou à direita, em vez de tê -las centradas.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
\sum_{\substack{0 \le i \le m \\ 0 < j < n}} P(i, j) \\
\sum_{\begin{subarray}{l}
i \in \Lambda \\
0 \le i \le m \\
0 < j < n
\end{subarray}} P(i, j)
\end{gather}
```

![Empilhando em sub-e superestritos](/tex/images/java/tutorial/latex-ams-math-3-5.png)

> Note que ambos os ambientes necessitam de estar entre chavetas quando aparecem como subscrito ou sobrescrito.

## 3.4. Diagramas comutativos
O pacote `AMSCD` define alguns comandos para produzir diagramas comutativos simples com base em matrizes. Existem algumas formas de abreviação úteis para especificar setas decoradas e outros conectores. No entanto, possui limitações - por exemplo, esses conectores podem ser apenas horizontais ou verticais.

No ambiente `CD`, as notações `@>>> `, `@<<< `, `@vvv` e `@aaa` produzem as setas à direita, à esquerda, para baixo e para cima, respectivamente. O exemplo a seguir também mostra o uso do comando `\declaremathoperator`.


```tex
\usepackage{amsmath,amscd}
\DeclareMathOperator\add{add}
\DeclareMathOperator\cf {cf}
\DeclareMathOperator\cov{cov}
\DeclareMathOperator\non{non}
% -------------------------------------------------------------------------------
\[ \begin{CD}
\cov (L) @>>> \non (K) @>>> \cf (K) \\
@VVV @AAA @AAA \\
\add (L) @>>> \add (K) @>>> \cov (K) \\
\end{CD} \]
```

![Diagrama comutativo simples](/tex/images/java/tutorial/latex-ams-math-3-6.png)

Vamos ver como as decorações são especificadas. Para as setas horizontais, o material entre o primeiro e o segundo símbolos `>` ou `<` será digitado como um sobrescrito, e o material entre o segundo e o terceiro será com o tipógrafo como um subscrito. Da mesma forma, o material entre o primeiro e o segundo, ou o segundo e o terceiro, `a` ou` v` de setas verticais será digitado como "Script lateral" à esquerda ou direita. Veremos o uso deste formato no próximo exemplo.

As notações `@=` e `@|` dê linhas duplas horizontais e verticais.

Em vez de uma seta visível, você pode usar uma "seta nula" (`@.`) para preencher uma matriz sempre que necessário.


```tex
\usepackage{amsmath, amscd}
\DeclareMathOperator{\End}{End}
% -------------------------------------------------------------------------------
\[ \begin{CD}
S^{W_\Lambda}\otimes T @>j>> T \\
@VVV @VV{\End P}V \\
(S \otimes T)/I @= (Z\otimes T)/J
\end{CD} \]

```

![Diagrama comutativo com scripts](/tex/images/java/tutorial/latex-ams-math-3-7.png)

Um layout semelhante pode ser produzido no LaTeX padrão. Mas não parece tão bom.


```tex
\[\begin{array}{ccc}
S^{\mathcal{W}_\Lambda}\otimes T & \stackrel{j}{\longrightarrow} & T \\
\Big\downarrow & & \Big\downarrow\vcenter{\rlap{$\scriptstyle{\mathrm{End}}\,P$}} \\
(S\otimes T)/I & = & (Z\otimes T)/J
\end{array}\]
```

![Diagrama comutativo no LaTeX padrão](/tex/images/java/tutorial/latex-ams-math-3-8.png)

Este exemplo mostra claramente quão melhores os resultados o pacote `AMSCD` produz: a notação é mais fácil, as setas horizontais são mais longas, o espaçamento entre os elementos é muito melhorado. Os pacotes mais especializados ajudarão você a obter resultados ainda mais bonitos.

## 3.5. Delimitadores em torno de uma matriz: o pacote `DelArray`

Nesta seção, discutiremos uma extensão geral útil para o pacote `Array`. Usando essa extensão, o usuário pode especificar delimitadores de abertura e fechamento extensíveis para envolver um ambiente de matemática. Vejamos o exemplo:


```tex
\usepackage{delarray}
% -------------------------------------------------------------------------------
\[ \mathcal{Q} =
\begin{array}[t] ( {cc} ) X & Y \end{array}
\begin{array}[t] [ {cc} ] A & B \\ C & D \end{array}
\begin{array}[b] \lgroup{cc}\rgroup L \\ M \end{array}
\]
```

![O uso do pacote de DelArray](/tex/images/java/tutorial/latex-ams-math-3-9.png)

> Note que o pacote `delarray` é independente de `amsmath`, mas carrega automaticamente o pacote `array` se necessário.

Os delimitadores são colocados em ambos os lados do `{cc}`.

Este exemplo também ilustra o recurso mais útil do pacote `DelArray`: o uso dos argumentos `[t] e `[b]` `opcionais, que não são permitidos com os ambientes matriciais de 'amsmath'. Eles mostram que o uso da sintaxe `DelArray` não é equivalente ao ambiente ao redor do ambiente`array` com `\left` e `\right`, já que os delimitadores são elevados, assim como a própria matriz.