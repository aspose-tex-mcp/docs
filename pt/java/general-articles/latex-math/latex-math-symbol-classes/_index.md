---
translation: true
template: /templates/_template-java.md
linktitle: 4. Personagens diferentes nas fórmulas de matemática
title: O significado de diferentes caracteres nas fórmulas matemáticas
weight: 40
url: /java/latex-math-symbol-classes/
keywords: LATEX, fórmulas de matemática de LaTeX, matemática de LaTeX, símbolos de matemática de LaTeX, variáveis ​​matemáticas de LaTeX, operações binárias de matemática de LaTeX, relações matemáticas de LaTeX, detalhes em matemática de LaTeX
description: Este artigo discute a divisão dos símbolos de matemática Tex nas classes e o significado dessas classes em matemática.
lastmod: "2025-06-16"
---

{{<section overview>}}

As 52 letras (`a` para` z` e `a`a` z`) denotam símbolos itálicos, que um matemático chamaria de "variáveis". A Tex os chama apenas de "símbolos comuns", porque eles compõem a maior parte das fórmulas de matemática. O LATEX também trata os 18 caracteres a seguir

`` 0 1 2 3 4 5 6 7 8 9! ? . | ` @" ``

Como símbolos comuns, o que significa que ele não insere nenhum espaço extra quando esses símbolos ocorrem um ao lado do outro ou ao lado das letras. Ao contrário das letras, esses 18 caracteres permanecem no tipo romano em fórmulas.

Os três caracteres `+`, `-` e`**`são chamados de" operações binárias ", porque operam em duas partes da fórmula. O asterisco (*) é raro, mas também se comporta como uma operação binária. Aqui estão alguns exemplos de operações binárias de tipografia quando aparecem ao lado de símbolos comuns:

![Operações binárias](/tex/images/java/tutorial/latex-math-4-1.png)

O TEX não trata `/` como uma operação binária, pois levaria ao espaçamento incorreto em fórmulas como `$ 1/2 $`. Assim, Tex trata `/` como um símbolo comum.

Aqui estão mais alguns exemplos de operações binárias:

![Operações binárias mais complexas](/tex/images/java/tutorial/latex-math-4-2.png)

Aliás, as operações binárias são tratadas como símbolos comuns se não ocorrerem entre duas quantidades em que podem operar. Assim, nenhum espaço extra inserido ao lado de +, -e * em casos como o seguinte:

![Operação binária como símbolos comuns](/tex/images/java/tutorial/latex-math-4-3.png)

Os exemplos a seguir mostram que as operações binárias podem ser usadas como símbolos comuns em superscritos e subscritos:

![Operação binária como símbolos comuns em superestritos e subscritos](/tex/images/java/tutorial/latex-math-4-4.png)

O LATEX trata os quatro caracteres `=`, `<`, `>` e `:` como "relações" porque eles expressam uma relação entre duas quantidades. Tais relacionamentos têm um significado bastante diferente das operações binárias, e os símbolos são compensados ​​de maneira um pouco diferente:

![Relações](/tex/images/java/tutorial/latex-math-4-5.png)

Os dois personagens ',' (vírgula) e ';' (Semicolon) são tratados como marcas de pontuação nas fórmulas, o que significa que Tex coloca um pouco de espaço extra depois delas, mas não antes deles.

![Marcos de pontuação](/tex/images/java/tutorial/latex-math-4-6.png)

Não é costume colocar espaço extra depois de ''. (Período) Em fórmulas, o Tex trata um período como um símbolo comum. Se você deseja que o personagem ':' seja um ponto de pontuação em vez de uma relação, basta chamá -lo de `\colon`. E se você deseja que uma vírgula seja tratada como um símbolo comum, basta colocá -lo no aparelho. Tex trata qualquer coisa no aparelho como um símbolo comum.

![Cólon como pontuação e vírgula como símbolo comum](/tex/images/java/tutorial/latex-math-4-7.png)

Os personagens `(` e `[` são chamados de aberturas ", enquanto`) `e`] `são chamados de" fechamentos ". Eles agem como símbolos comuns, mas ajudam a Tex a decidir quando uma operação binária não está realmente sendo usada de maneira binária.

Finalmente, o LaTeX se reserva os outros 10 caracteres:

`\ $ % # & ~ {} _ ^`

Você não pode usá -los no modo de matemática. Embora '{' e '}' especifique o agrupamento, os comandos `\ {` e `\}` podem ser usados ​​para obter '{' como uma abertura e '}' como um fechamento.

Os caracteres especiais `^` e `_` não devem ser usados, exceto nas fórmulas. Por outro lado, os nomes dos símbolos de matemática como `\alpha` e `\ aprox` e os comandos para operações de matemática como `\overline` não devem aparecer no texto comum. Além disso, uma linha em branco ou `\par` não é permitida no modo de matemática.
Os matemáticos também gostam de usar sotaques sobre letras como uma maneira eficaz de indicar relacionamentos entre objetos de matemática. Também estende muito o número de símbolos disponíveis sem aumentar o número de fontes necessárias. Os sotaques matemáticos são um pouco diferentes dos sotaques usados ​​no texto comum. O espaçamento não é o mesmo; A TEX segue regras especiais para sotaques em fórmulas, para que os dois tipos de sotaques não sejam confundidos entre si. O LATEX fornece os seguintes sotaques matemáticos:

![Acentos](/tex/images/java/tutorial/latex-math-4-8.png)

Os nove primeiros são chamados `\^`, `\v`, ` \ ~ `, ` \ '``, `` \ `` `, ` \.', `` `` `` \ U`, e `` ``, respectivamente, quando parecem em text; Tente usar `\^` ou `\v`, etc., em fórmulas, ou se você tentar usar `\hat` ou `\check`, etc., no texto comum.

Geralmente, é melhor definir macros para letras acentuadas necessárias com frequência. Você pode colocar

```tex
\def\Ahat{{\hat A}}
\def\chat{{\hat c}}
\def\scheck{{\check s}}
```

No início de um arquivo de LaTeX. Isso economiza muitas teclas de teclas e facilita a leitura do arquivo.

Quando as letras *i* e *j* são acentuadas nas fórmulas de matemática, você deve usar bases de símbolos sem pontos que são chamadas de `\iMath` e `\jmath`. Portanto, um artigo que usa o chapéu i e j pode começar com as seguintes definições:

```tex
\def\ihat{{\hat\imath}}
\def\jhat{{\hat\jmath}}
```

É possível colocar sotaques matemáticos em qualquer subformula. Mas geralmente não há muito sentido em fazê -lo, porque Tex apenas centra o sotaque em toda a subformula. Em particular, um `\bar` sotaque sempre permanece do mesmo tamanho; Não é como `\overline`, que cresce com a fórmula embaixo dela. Algumas pessoas preferem a linha mais longa de `\overline`, mesmo quando se aplica a uma única letra. No entanto, o LaTeX fornece dois sotaques que crescem; Eles são chamados de `\widehat` e `\ widetilde`. Agora, vejamos os exemplos de casos discutidos no presente parágrafo.

![Acentos largos](/tex/images/java/tutorial/latex-math-4-9.png)

O último exemplo mostra o tamanho máximo disponível.