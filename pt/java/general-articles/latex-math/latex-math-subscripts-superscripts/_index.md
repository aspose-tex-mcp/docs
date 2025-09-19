---
translation: true
template: /templates/_template-java.md
linktitle: Subscrito e subscrito
title: 2. Subscrito e subscrito no LATEX
weight: 20
url: /java/latex-math-subscripts-superscripts/
keywords: LATEX, fórmulas de matemática de LaTeX, matemática de LaTeX, subscritos de matemática do LATEX, SUPERSCRITOS DE MATHA DE LATEX, LATEX PRIME
description: Este artigo discute como criar fórmulas de matemática que contêm subscritos e superestritos com Tex e LaTeX.
lastmod: "2025-06-16"
---

{{<section overview>}}


## Introdução ao Superscript e subscritos de LaTex

**SUPERSCRIPT** é um pequeno caractere ou símbolo posicionado ligeiramente acima da linha de base do texto.  Por exemplo, na expressão `x²`, o` 2` é um superdript.

**Subscrito** é um caractere pequeno ou símbolo posicionado ligeiramente abaixo da linha de base do texto. Por exemplo, na fórmula química para a água, `h₂o`, o` 2` é um subscrito.

## Como escrever subscrito/superscript no LaTeX

Agora, vamos tentar construir fórmulas mais complexas a partir de simples. Primeiro, você pode obter superscritos e subscritos usando `^` e `_`, conforme mostrado no exemplo a seguir:

![Subscritos e superscritos de caracteres únicos](/tex/images/java/tutorial/latex-math-2-1.png)

Observe que `^` e `_`aplica apenas ao próximo caractere. Se você deseja um subscrito ou superescrito mais complexo, basta incluí -lo no aparelho:

![Subscritos e superscritos de vários caracteres](/tex/images/java/tutorial/latex-math-2-2.png)

Os aparelhos nesses exemplos especificam "subformulas" - partes mais simples de uma fórmula maior. Tex faz uma caixa para cada subformula e trata a caixa como se fosse um único símbolo. Os aparelhos também servem ao seu objetivo habitual de agrupar.

É ilegal digitar `$ x^y^z $` ou `$ x_y_z $`. Tex reclamará de um "subscrito duplo" ou "duplo superescript". Você deve deixar mais claro o que deseja digitando `$ x^{y^z} $` ou `$ x^{yz} $` ou `$ x_ {y_z} $` ou `$ x_ {yz} $`.

Um substituto ou subscrito seguindo um caractere se aplica apenas a esse personagem; Mas, ao seguir uma subformula, ele se aplica a toda essa subformula e será elevada ou reduzida de acordo.

![Subscritos e superestritos em um único símbolo e em uma subformula](/tex/images/java/tutorial/latex-math-2-3.png)

Na primeira fórmula, os `^3` e `^4 ` são superscritos nos parênteses certos que os precedem imediatamente, mas na segunda fórmula, eles são superscritos nas subformulas que estão fechadas no aparelho. A primeira versão é preferível, porque é mais fácil de digitar e é tão fácil de ler.

## Escrevendo subscrito ou superescrito em uma subformula vazia

Às vezes, pode ser necessário fazer um subscrito ou substituto em uma subformula vazia para produzir uma notação bastante rara, como *<suge> 2 </suge> f </uply> 3 </sub>*. A melhor maneira de fazer isso é digitar `$ {} _ 2f_3 $` ou `$ {_ 2} f_3 $` ou `$ {_ 2f_3} $`.

Você também pode ter "SubsupersCripts" simultâneos e especificá -los em qualquer ordem:

![Subsuperscritos simultâneos](/tex/images/java/tutorial/latex-math-2-4.png)

Esses "Subsuperscripts" simultâneos estão posicionados um sobre o outro. No entanto, para algumas cartas, um subscrito será deslocado para a esquerda; e para algumas dessas cartas de maneira bastante visível. Compare as duas fórmulas a seguir:

![Alinhamento simultâneo de subsupers](/tex/images/java/tutorial/latex-math-2-5.png)

Portanto, se você deseja que o Subscript e o Superscript sejam alinhados, poderá usar o truque mostrado na segunda versão. Mais uma vez, aproveita uma subformula vazia.

## Escrevendo Prime no LaTeX

A próxima coisa que ocorre frequentemente nas fórmulas matemáticas é o símbolo do número primo. O LaTeX disponibiliza o comando `\prime`, que produz um símbolo de número primo no tamanho de uma letra normal. Portanto, nunca deve usá-lo, exceto em sobrescrito ou subscrito. Mas pode simplesmente escrever `'` em vez de `^\prime`, e `''` em vez de `^\prime\prime`, e assim por diante.

![Primos](/tex/images/java/tutorial/latex-math-2-6.png)

## LATEX DUPLO SUPERSCRIPT

No LATEX, você pode escrever superscritos duplos, envolvendo toda a expressão de superscripts dentro dos aparelhos encaracolados {}. Aqui está um exemplo: `x^{a^b}`

## LATEX DUPLO SUNFRIPT

No LATEX, você pode escrever subscritos duplos da mesma forma, envolvendo toda a expressão do subscrito dentro dos aparelhos encaracolados {}. Aqui está um exemplo: `x_ {i_ {j}}`