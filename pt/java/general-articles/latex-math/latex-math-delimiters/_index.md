---
translation: true
template: /templates/_template-java.md
linktitle: 7. Delimitadores
title: Delimitadores | Manual de LaTeX | Aspose.TeX
weight: 70
url: /java/latex-math-delimiters/
keywords: LATEX, fórmulas de matemática de LaTeX, matemática de LaTeX, delimitadores de matemática de LaTeX, aparelhos matemáticos de LaTeX, suportes de matemática de LaTeX, parênteses matemáticos de LaTeX
description: Este artigo discute como dividir logicamente as fórmulas em subformulas com diferentes tipos de delimitadores.
lastmod: "2025-06-16"
---

{{<section overview>}}

Qualquer que seja uma fórmula de matemática grande, a Tex sabe uma maneira de criar alguns símbolos grandes o suficiente para ter uma aparência adequada. Por exemplo, o resultado de digitar

```tex
$$\sqrt{1+\sqrt{1+\sqrt{1+
            \sqrt{1+\sqrt{1+\sqrt{1+\sqrt{1+x}}}}}}}$$
```

Mostra uma variedade de sinais radicais ou quadrados disponíveis: sinais:

![Radicais de tamanhos diferentes](/tex/images/java/tutorial/latex-math-7-1.png)

Os três maiores sinais aqui são os mesmos, exceto por um segmento vertical que é repetido quantas vezes forem necessários para atingir o tamanho necessário. Ao mesmo tempo, os sinais menores são personagens distintos retirados das fontes de matemática do Tex.

Algo semelhante acontece com parênteses e outros símbolos "delimitadores". Tais símbolos são importantes na matemática, porque dão pistas visuais à estrutura subjacente de expressões complexas. Em outras palavras, eles limitam os limites de subformulas individuais. Aqui está a lista dos 22 delimitadores básicos fornecidos pelo LATEX:

![Os 22 delimitadores básicos definidos no LaTeX](/tex/images/java/tutorial/latex-math-7-2.png)

Para obter uma versão um pouco maior de qualquer um desses símbolos, basta digitar `\bigl` ou`\bigr` para abrir ou fechar delimitadores, respectivamente. Isso facilita a leitura fórmulas com delimitadores aninhados:

![Os exemplos de uso \ grandes delimitadores](/tex/images/java/tutorial/latex-math-7-3.png)

Os delimitadores `\big` são suficientes o suficiente do que os comuns, para que a diferença possa ser notada e ainda pequena o suficiente para ser usada no texto de um parágrafo:

![Os \ grandes delimitadores em comparação com os normais](/tex/images/java/tutorial/latex-math-7-4.png)

Você pode obter mais um passo em símbolos maiores adequados para exibições, se você digitar `\bigl` e `\bigr` em vez de `\bigl` e `\bigr`:

![Os \ grandes delimitadores](/tex/images/java/tutorial/latex-math-7-5.png)

Estes são 50% mais altos que as versões na etapa anterior. As fórmulas exibidas geralmente usam delimitadores ainda mais altos (o dobro do tamanho de `\big`). Você pode obtê -los digitando `\biggl` e `\biggr`:

![Os delimitadores \ bigg](/tex/images/java/tutorial/latex-math-7-6.png)

Finalmente, você pode digitar versões `\biggl` e `\biggr`, 2,5 vezes mais altas que os delimitadores `\bigl` e `\bigr`:

![Os delimitadores \ bigg](/tex/images/java/tutorial/latex-math-7-7.png)

O LATEX também fornece comandos `\bigm`, `\bigm`, `\biggm` e `\biggm` para produzir delimitadores que podem ser usados ​​no meio das fórmulas. Esse delimitador age como uma relação, então Tex coloca um pouco de espaço em ambos os lados:

![Delimitadores no meio das fórmulas](/tex/images/java/tutorial/latex-math-7-8.png)

Também é possível dizer apenas `\big`, `\big`, `\bigg` ou`\bigg` para produzir um delimitador que se comporta como uma variável comum. Esses comandos seriam usados ​​principalmente com barras e barras de barriga:

![Grandes símbolos comuns](/tex/images/java/tutorial/latex-math-7-9.png)

A Tex implementa um algoritmo que descobre a altura de um par de delimitadores, para incluir uma determinada subformula. Você pode usá -lo, em vez de decidir se um delimitador deve ser `\big` ou `\bigg` ou qualquer outra coisa. Apenas diga


```tex
\left<delim1><subformula>\right<delim2>
```

E Tex digitará uma subformula, colocando os delimitadores especificados à esquerda e à direita. O tamanho dos delimitadores será grande o suficiente para cobrir a subformula:

![Delimitadores definidos por \ comandos à esquerda e \ Right](/tex/images/java/tutorial/latex-math-7-10.png)

Ao utilizar `\left` e `\right`, devem ser emparelhados, tal como as chaves fazem com os grupos. Não pode ter `\left` numa subfórmula e `\right` noutra. Além disso, não pode digitar coisas como `\left(...{...\right...}` ou `\left(...\begingroup...\right)...\endgroup`. Isto deve-se ao facto de o TeX ter de compor a subfórmula que aparece entre `\left` e `\right` antes de decidir o tamanho dos delimitadores. Quando não estiver a utilizar `\left` e `\right`, não terá de corresponder os parênteses e os parêntesis rectos. Assim, pode digitar algo como `$[0,1)$` ou `$)($` ou ainda `$)$`. E mesmo quando se utiliza `\left` e `\right`, não será necessário corresponder os símbolos específicos, pelo que `\left)` ou `\right(` não causarão erro.

Mas por que se preocupar em aprender sobre `\bigl` e `\bigr` e outros do gênero, quando a Tex pode calcular automaticamente os tamanhos para `\left` e `\right`? Existem pelo menos três casos em que você deseja decidir por si mesmo na seleção do tamanho adequado do delimitador:

(1) Basta comparar as duas fórmulas a seguir:

![\ esquerda e \ direita vs. \ bigl e \ bigr com barras verticais](/tex/images/java/tutorial/latex-math-7-11.png)

De fato, usar `\left` e `\right` não foi uma escolha sábia, pois eles não conseguiam descobrir o tamanho do delimitador apropriado para a melhor legibilidade.

(2) Por outro lado, às vezes `\esquerda` e `\right` escolhe um delimitador maior do que você deseja. Isso acontece principalmente quando eles incluem um grande operador em uma tela:

![\ esquerda e \ direita vs. \ bigl e \ bigr com um resumo](/tex/images/java/tutorial/latex-math-7-12.png)

O algoritmo do TEX causa `\left` e `\right`, envolve o `\sum` junto com seus limites, mas em casos especiais como esse, parece melhor deixar os limites sair um pouco. Portanto, os delimitadores \ \ bigg` são melhores aqui.

(3) Quando você precisa digitar uma enorme fórmula exibida, você deve dividi -la em duas ou mais linhas. E você deseja garantir que os delimitadores de abertura e fechamento tenham o mesmo tamanho; Mas você não pode usar `\left` na primeira linha e `\right` no último, já que `\esquerda` e `\right` deve ocorrer em pares. A única solução é usar `\biggl` (por exemplo) na primeira linha e `\biggr` no último.

> Embora `\left` e `\right` possam geralmente formar delimitadores arbitrariamente grandes, as barras e os parêntesis angulares têm um tamanho máximo. Se encomendar versões realmente grandes destes símbolos, obterá os maiores disponíveis.

Você também pode usar um truque que produz o chamado delimitador nulo (em branco). Você precisaria desse delimitador quando precisar digitar uma fórmula que contém visualmente apenas um delimitador grande. Por exemplo,

![Um delimitador nulo nos casos](/tex/images/java/tutorial/latex-math-7-13.png)

tem '{' mas não '}'. Pode ser produzido por uma construção do formulário


```tex
$$|x|=\left\{ ... \right.$$ 
```

onde `\right.` gera o delimitador nulo certo.

O LATEX também fornece mais alguns delimitadores, que não estão listados no conjunto básico de 22 porque são meio especiais. Os comandos `\arrowvert`, `\Arrowvert` e `\bracevert` produzem delimitadores feitos a partir das partes repetíveis das setas verticais, setas verticais duplas e aparelhos grandes, respectivamente, sem pontas de seta ou as partes ocuficiente dos aparelhos. Eles produzem resultados semelhantes a `\vert` e `\vert`, mas estão cercados por mais espaço em branco e têm um peso diferente. Existem também `\lGroup` e `\rgroup`, que são construídos a partir de aparelhos sem as partes do meio; e `\lmoustache` e `\rmoustache`, que produzem as metades superior e inferior de aparelhos grandes. Aqui estão as exibições com as versões `\big` e `\bigg` de `\vert`, `\vert`, e esses sete delimitadores especiais:

![Delimitadores adicionais fornecidos pelo LATEX](/tex/images/java/tutorial/latex-math-7-14.png)

Você pode descobrir que `\lgroup` e `\rgroup` são parecidos em negrito, com curvas mais nítidas nos cantos; Isso os torna atraentes para certas exposições grandes. Observe que você não pode usá -los exatamente como parênteses, porque eles estão disponíveis apenas em tamanhos `\big` e muito mais.