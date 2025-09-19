---
translation: true
template: /templates/_template-java.md
linktitle: Características da fonte
title: 2. Características da fonte
weight: 20
url: /java/latex-font-attributes/
keywords: LATEX, fontes de LaTeX, codificações de fontes de LaTeX, NFSS
description: Este artigo abrange classificações de fontes de LaTeX em relação a várias características da fonte. Também menciona o conceito de codificações de fontes de LaTeX.
lastmod: "2025-06-16"
---

{{<section overview>}}

As fontes podem ser divididas em classes sobrepostas individuais com base em várias características. Muitas vezes, é útil conhecer essas características quando precisamos decidir qual família de fontes usar em um contexto específico. Veja também o artigo de documentação de [Aspose.font](https://products.aspose.com/font/) sobre [diferentes tipos de fontes](/font/net/what-is-font/font-types/).

## 2.1. Fontes proporcionais e monofactas

As fontes podem ser proporcionais ou monofactas. Em uma fonte proporcional, os glifos têm larguras diferentes, dependendo de sua forma.  Ao mesmo tempo, em uma fonte monoespacial, todos os glifos têm a mesma largura. Os espaços extras em torno de glifos de fontes monoespaciais tornam mais difícil reconhecer os limites das palavras e, assim, tornam o texto digitado em tais fontes menos legíveis. Por outro lado, as fontes proporcionais (ou *tipográficas *) geralmente permitem que mais palavras sejam colocadas em uma página e são mais legíveis que as fontes monoespactadas. Veja a figura abaixo:

![Fontes proporcionais e monofactas](/tex/images/java/tutorial/latex-font-selection-2-1.png)
 
Embora as fontes monofacacadas pareçam menos legíveis, elas ainda têm seu uso. Um exemplo são tabelas ou listagens de programas, onde é importante o alinhamento adequado do conteúdo. Você sempre encontrará programas de computador exibidos em uma fonte monoespersa em qualquer computador desde o livro. Isso distingue facilmente os programas do texto circundante.

Você pode até escolher uma fonte monoespacial como fonte base para um documento completo, porque essa fonte parece feita à mão quando usada com parágrafos injustificados, dando-lhe um sabor de uma máquina de escrever.

## 2.2. Fontes serifas e sem serifas

Em algumas fontes, os glifos têm *serifas*, enquanto em outras, eles não. Esse fato nos leva a outra classificação útil. Setrifs são pequenos movimentos horizontais nas extremidades dos glifos. Originalmente, eles foram produzidos pelo cinzel quando as capitais romanas foram gravadas em pedra. É por isso que as fontes serifitas são frequentemente chamadas de fontes *romanas*.

![Fontes serifas e sem serifas](/tex/images/java/tutorial/latex-font-selection-2-2.png)
 
As fontes serifitas eram pensadas há muito tempo como mais legíveis, pois dão aos olhos mais pistas de identificação. Mas pesquisas dedicadas mostraram que a velocidade de leitura não é substancialmente afetada pela ausência de serifas.

## 2.3. Famílias de fontes e seus atributos

Além das classificações grosseiras que discutimos acima, as fontes são agrupadas em famílias de fontes. Os membros de uma família de fontes compartilham princípios comuns de design e se diferenciam por variações de tamanho, peso, largura e forma.

### Formas de fonte

Quase toda família de fontes tem uma forma chamada de forma *vertical*. A fonte que você está lendo agora está na forma vertical. Essa forma de fonte é geralmente usada para digitar texto regular.

Outra forma importante incluída na maioria das famílias é a forma * itálica *, que parece

![Texto em itálico](/tex/images/java/tutorial/latex-font-selection-2-3.png)
 
Os glifos itálicos são inclinados para a direita e as letras são desenhadas de maneira diferente de suas contrapartes na vertical, como mostrado na figura abaixo:

![Comparação de formas na vertical, em Índia e em Índia](/tex/images/java/tutorial/latex-font-selection-2-4.png)
 
A primeira linha mostra cartas da família Modern Serif Modern em forma ereta, e a terceira linha mostra as mesmas letras em formato em itálico. Para tornar a diferença no desenho mais aparente, a segunda linha fornece às letras itálicas sem a inclinação usual. Em outras palavras, essas são letras itálicas em uma posição vertical.

As famílias de fontes de San Serif geralmente não têm uma forma de itálico adequada; Em vez disso, eles têm uma forma *inclinada* na qual os caracteres verticais regulares se inclinam para a direita. Tais fontes também são frequentemente chamadas de *oblíquas* ou *inclinadas*.
Outra forma comum da fonte é a forma  pequena tampa*, na qual as letras minúsculas são representadas como capitais com uma altura reduzida. Se a forma de pequenas tampas não estiver disponível para uma fonte específica, os tipógrafos às vezes usam capitais na vertical de tamanhos menores, mas isso não produz a mesma qualidade que uma fonte de pequenas caps bem projetada. As pequenas tampas verdadeiras têm larguras e peso diferentes das letras maiúsculas da mesma fonte que foram reduzidas à altura das pequenas tampas projetadas. Você pode ver na figura abaixo que os golpes nas capitais falsificados são muito finos.

![Comparação verdadeira e falsa de pequenas capitões](/tex/images/java/tutorial/latex-font-selection-2-5.png) 

### Peso e largura

As fontes de uma certa forma dentro de uma família podem diferir em *peso *. Essa característica está relacionada à espessura dos traços usados ​​para desenhar as formas individuais. Alguns fabricantes de fontes chamam os pesos da fonte destinados a serem usados ​​para texto normal *livro*, enquanto outros os chamam de *Média*. Para traços finos, o nome *luz* é comum, enquanto os traços mais espessos são geralmente chamados de *negrito*. Em famílias de fontes maiores, às vezes encontramos um alcance começando com *Ultra Light*, passando por *luz extra*, *luz*, *semi -luz *e assim por diante, e terminando com *Ultra Bold* na outra extremidade. Mas muitas vezes apenas alguns pesos estão disponíveis em algumas famílias. A família romana moderna do computador, por exemplo, tem apenas pesos médios e ousados.

A fonte *largura* é outro atributo importante. Refere -se à quantidade de expansão ou contração em relação à largura normal ou média da família. O Roman moderno do computador tem fontes ousadas em *largura média * e *largura estendida*. As fontes condensadas são frequentemente usadas em títulos e títulos, onde fontes de largura de média, quando usadas em grandes tamanhos, consumiriam muito espaço.

### Tamanhos de fonte

A unidade de medição para tamanhos de fonte é um ponto de impressora (PT). Existem 72,27 pontos em uma polegada. O tamanho da fonte não se refere a nenhuma característica específica, mas é um valor escolhido pelo designer de fontes para orientar o usuário. Por exemplo, em uma fonte de 10pt, as letras do alfabeto geralmente têm menos de 10pt de altura, e apenas caracteres como parênteses têm aproximadamente essa altura.

A aparência de uma fonte depende de muitos fatores, como a altura das letras minúsculas (o *X-Height *), a largura do curso e a profundidade dos descendentes (a parte das letras abaixo da linha de base, como na letra 'Q'). É por isso que duas fontes do mesmo tamanho podem não se misturar bem.

No mundo do LaTeX, as fontes geralmente estão disponíveis em tamanhos que são poderes de 1,2, o que significa que seguem uma progressão geométrica. Esse arranjo facilita a produção de uma cópia mestre ampliada que mais tarde pode ser fotograficamente reduzida, aumentando efetivamente a resolução final de saída. Atualmente, as fontes geralmente são vetorizadas e, portanto, podem ser dimensionadas à vontade. Como conseqüência, muitas famílias de fontes comerciais são fornecidas em apenas um único tamanho de design.

O uso de fontes em escala em vez de fontes projetadas para um tamanho específico geralmente fornece resultados menos satisfatórios. Isso se deve ao fato de que as fontes não escalam de maneira linear para o olho humano. Você pode ver a diferença na figura abaixo:

![Um verdadeiro 10pt e uma ampliada fontes 5pt](/tex/images/java/tutorial/latex-font-selection-2-6.png)
 
Os glifos em fontes artesanais de tamanhos maiores são geralmente mais estreitos do que as fontes ampliadas de um tamanho menor da mesma família. Deve -se usar fontes projetadas para o tamanho desejado sempre que possível, embora seja aceitável escalar fontes dentro de uma pequena faixa de tamanho, se necessário.

## 2.4. Codificações de fontes

Como mencionamos na introdução, o TEX refere -se aos glifos de uma fonte, abordando -os por códigos. Esse mapeamento é chamado de codificação *de fonte*. No LATEX, duas fontes com a mesma codificação de fonte devem ser intercambiáveis ​​no sentido em que, dada a mesma entrada, elas produzem os "mesmos" glifos na página impressa.

Ao classificar as fontes por suas codificações de fontes, é possível modificar outras características, como a família de fontes ou a série de fontes, e ainda garantir que o resultado do tipógrafo permaneça compreensível.

Originalmente, as distribuições TEX incluíam as fontes que possuem apenas 128 glifos por fonte. Portanto, essas fontes não incluem caracteres acentuados como glifos individuais. Todos esses glifos tiveram que ser construídos usando o `\accent` do TEX 'primitivo ou por métodos semelhantes. Como resultado, qualquer palavra que contenha diacríticas não pode ser automaticamente hifenizada pelo LATEX e Kerning (a correção do espaçamento entre certas letras na fonte) não pode ser aplicada automaticamente. A codificação dessas fontes é chamada de `ot1`. Embora continue sendo a codificação padrão para o LATEX, não é aconselhável usar `ot1` para outros idiomas que não o inglês.

A comunidade de usuários da TEX definiu uma codificação de 256 caracteres chamada `T1` que permite que a TEX digita corretamente em mais de 30 idiomas com base no alfabeto latino. Portanto, o uso da codificação `T1` é altamente recomendado, pois, hoje em dia, quase todas as famílias de fontes que podem ser usadas com LaTeX estão disponíveis nesta codificação. De fato, alguns estão *apenas* disponíveis na codificação `T1`. Especificando `\usepackage [t1] {FONTENC}`após o comando `\documentclass` faz` t1`a codificação padrão em um documento.