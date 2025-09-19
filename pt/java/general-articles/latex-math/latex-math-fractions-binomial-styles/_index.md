---
translation: true
template: /templates/_template-java.md
linktitle: Frações, coeficientes binomiais e estilos de matemática
title: 5. Frações, coeficientes binomiais e estilos de matemática
weight: 50
url: /java/latex-math-fractions-binomial-styles/
keywords: LATEX, fórmulas de matemática de LaTeX, matemática de LaTeX, frações matemáticas de LaTeX, coeficientes binomiais matemáticos de LaTeX, estilos de matemática de LaTeX
description: Aprenda sobre a digitação de construções matemáticas como frações, coeficientes binomiais, etc. e os estilos de matemática nos quais Tex typeats fórmulas.
lastmod: "2025-06-16"
---

{{<section overview>}}

Outra coisa comum que você pode encontrar nas fórmulas matemáticas são as frações e outras construções, onde algo como um numerador é colocado em cima de algo como um denominador. Um exemplo deste último são os coeficientes binomiais.

![Objetos matemáticos semelhantes a fração](/tex/images/java/tutorial/latex-math-5-1.png)

Você pode obter essas três fórmulas como equações exibidas digitando `$$ 1 \over2 $$` e `$$ n+1 \over3 $$ e $$ \ n+1 \ escolha3 $$`.

O comando `\over`aplica -se a tudo na fórmula, a menos que você o inclua em uma subformula específica com o aparelho, caso em que `\over` se aplica a tudo nessa subformula.

![Frações](/tex/images/java/tutorial/latex-math-5-2.png)

Você não pode usar `\over` duas vezes na mesma subformula, ou seja, tipo`a \over b \over 2`. Em vez disso, você deve especificar explicitamente o que passa sobre o que:

![Frações aninhadas](/tex/images/java/tutorial/latex-math-5-3.png)

Parece que ambas as fórmulas não parecem muito boas. Nesses casos, geralmente é melhor converter frações em uma "forma reduzida". Por exemplo, as duas últimas fórmulas devem ser digitadas da seguinte forma:

![Frações em suas formas reduzidas](/tex/images/java/tutorial/latex-math-5-4.png)

Aqui estão exemplos mais complexos:

![Frações em suas formas reduzidas](/tex/images/java/tutorial/latex-math-5-5.png)

Olhando para os exemplos acima, você deve ter notado que as cartas e outros símbolos às vezes ficam menores quando aparecem em frações, assim como elas ficam menores quando estão em subscritos ou sobrescritos. Vamos agora falar sobre a maneira como Tex escolhe os tamanhos dos símbolos. Tex tem oito estilos nos quais pode tratar fórmulas:

 * Estilo de exibição (para fórmulas exibidas em linhas sozinhas)
 * Estilo de texto (para fórmulas incorporadas em texto)
 * Estilo de script (para subformulas usadas como superestrts ou subscritos)
 * Estilo de scriptscript (para superestritos ou subscritos de segunda ordem)
e quatro estilos "apertados" que são quase os mesmos, exceto que subscritos e superscritos não são tão levantados. We will refer to the eight styles as *D*, *D'*, *T*, *T'*, *S*, *S'*, *SS*, *SS'*, where *D* is display style, *D'* is cramped display style, *T* is text style, etc. TeX also uses three sizes to type math formulas: text size, script size, and scriptscript size.

Para digitar uma fórmula no texto em execução, você o inclui em `$ ... $`; Isso produz a fórmula em estilo *t*. Ou você pode incluí -lo em `$$ ... $$` para obter uma fórmula exibida; Isso exibe a fórmula em estilo *d *. As subformulas de uma fórmula podem estar em diferentes estilos. Depois de conhecer o estilo, você pode determinar o tamanho do tipo que o TEX usará:

![Estilos para mapeamento de tamanho](/tex/images/java/tutorial/latex-math-5-6.png)

Não há estilo "*SSS*", pois esses pequenos símbolos seriam ainda menos legíveis que os scriptscript.

![Estilos de subscritos e superesctips, dependendo de um estilo de fórmula](/tex/images/java/tutorial/latex-math-5-7.png)

For example, if `x^{a_b}` is to be typeset in style *D*, the `a_b` will be set in style *S*, and `b` in style *SS*; the result is ![Raízes de grau arbitrário](/tex/images/java/tutorial/latex-math-5-8.png)

Ainda não vimos nenhuma diferença entre os estilos *d* e *t*. Na verdade, há uma pequena diferença no posicionamento dos expoentes, embora o tamanho do script seja usado em cada caso. Mas há uma grande distinção entre os estilos *d* e *t* em caso de frações:

![Estilos de denominador e numerador, dependendo de um estilo de fração](/tex/images/java/tutorial/latex-math-5-9.png)

Então, se você digitar `$ 1 \overs2 $` (em um texto), você recebe estilo *s* over style *s'*. Mas se você digitar `$$ 1 \over2 $$` você obtém estilo *t* style *t'* em uma fórmula exibida.

Finalmente, `\sublline` não muda o estilo. Acentos de matemática e os comandos `\sqrt` e `\overline`alteram os estilos não arranhados para seus colegas apertados, mantendo estilos apertados.
Pode acontecer que você não goste do estilo que a TEX seleciona de acordo com suas próprias regras. Você está livre para especificar o estilo desejado digitando `\displaystyle` ou`\textStyle` ou `\scriptstyle` ou`\scriptscriptStyle`; O estilo selecionado será aplicado até o final da fórmula ou subformula, ou até você selecionar outro estilo. Por exemplo, `$$ n+\ scriptstyle n+\ scriptscriptstyle n. $$` produz a seguinte tela:

![Controle de estilo manual](/tex/images/java/tutorial/latex-math-5-10.png)

Isso mostra que o sinal de plus também fica menor à medida que o estilo muda, e que Tex não coloca espaço em torno de + nos estilos de script.

Vamos dar uma olhada em outro exemplo - uma fração contínua.

![Uma fração contínua](/tex/images/java/tutorial/latex-math-5-11.png)

Você pode obtê -lo digitando

```tex
$$a_0+{1\over\displaystyle a_1+
        {\strut 1\over\displaystyle a_2+
          {\strut 1\over\displaystyle a_3+
            {\strut 1\over a_4}}}}$$
```

Sem `\strut` e `\displaystyle` nesta fórmula, o resultado seria diferente:

![Uma fração contínua sem truques embelezados](/tex/images/java/tutorial/latex-math-5-12.png)

O LATEX define a macro `\frac` que permite especificar frações usando outra sintaxe:`\frac {a} {b} `é equivalente a `a \over b` e `\frac12` é equivalente a` 1 \over2`.

Há outra operação `\no top` em Tex, que é como` \over ', exceto que não desenha a linha de fração:

![O comando \ no topo](/tex/images/java/tutorial/latex-math-5-13.png)

O formato LATEX também define `\escolha`, que é como`\no top`, mas envolve o resultado em parênteses:

![O \ Escolha macro](/tex/images/java/tutorial/latex-math-5-14.png)

É chamado de `\escolha` porque é uma notação comum para o coeficiente binomial que informa quantas maneiras há para escolher as coisas * k * das coisas * n *.

Os comandos `\over`, `\no top` e `\escolha` não podem ser misturados um com o outro. Por exemplo, `$$ n \ escolha k \ mais de 2 $$` é ilegal. Você deve usar o agrupamento para obter `$$ {n \ escolha k} \over2 $$` ou `$$ n \ escolha {k \over2} $$`.

Tex possui o comando `\acima`, que é uma versão generalizada de `\over` e `\no top`. Neste comando, você especifica a espessura exata da regra da linha digitando `\acima <Dimen>`. Por exemplo, 

```tex
$$\displaystyle{\frac{a}{b}\above1pt\displaystyle{\frac{c}{d}}$$
```

produzirá uma fração composta com uma regra de espessura de 1 p. Entre as frações no numerador e denominador:

![A macro \ acima](/tex/images/java/tutorial/latex-math-5-15.png)