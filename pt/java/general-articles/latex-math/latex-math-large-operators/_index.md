---
translation: true
template: /templates/_template-java.md
linktitle: Grandes operadores
title: 6. Grandes operadores
weight: 60
url: /java/latex-math-large-operators/
keywords: LaTeX, fórmulas de matemática de LaTeX, matemática de LaTeX, latex matemática grandes operadores, soma de LaTeX, integral de LaTeX
description: Este artigo discute como construir fórmulas de matemática que contêm grandes operadores, como soma e integração com Tex e LaTeX.
lastmod: "2025-06-16"
---

{{<section overview>}}

Em matemática, existem símbolos que denotam, por exemplo, as operações de "soma" ou "integração". Eles são chamados de "grandes operadores" e você os digita exatamente como digita símbolos e letras comuns. A diferença é que a TEX escolherá um símbolo maior para o grande operador no estilo de exibição do que no estilo de texto.

![Soma e integração sem super/subscritos](/tex/images/java/tutorial/latex-math-6-1.png)

Um `\sum` exibido geralmente ocorre com" limites ", isto é, com subformulas que aparecem acima e abaixo dele. Os limites devem ser digitados como se fossem subscritos e superestritos;
`$$ \ sum_ {n = 1}^m $$` ou `$$ \ sum^m_ {n = 1} $$`ambos produzem produtos

![Resumo com limites](/tex/images/java/tutorial/latex-math-6-2.png)

As convenções normais de tipo de texto matemática presumem que a fórmula acima deve ser alterada para

![Resumo sem limites](/tex/images/java/tutorial/latex-math-6-3.png)

(ou seja, sem limites) se ocorrer no texto e não em uma tela. E Tex segue essas convenções.

Superscripts e subscritos no sinal de integração não são definidos como limites, mesmo no estilo de exibição:

![Integração no texto e em uma tela](/tex/images/java/tutorial/latex-math-6-4.png)

Definir subscritos e superscritos como limites dão uma aparência melhor se as subformulas forem complexas, embora ocupem mais espaço na página. Você pode forçar a TEX a processar a fórmula dessa maneira digitando `\limits` imediatamente após o `\int`, ou `\sum`, ou outro operador, independentemente de qual estilo será usado na subformula. Por outro lado, os limites dos sinais de soma exibidos às vezes não são desejáveis. Você pode alterar a convenção do Tex digitando `\nolimits` imediatamente após o grande operador.

![Forçando limites e sem limites para soma e integração](/tex/images/java/tutorial/latex-math-6-5.png)

Se você disser `\nolimits \limits` (por exemplo, algumas macros como` \int` especificar `\nolimits`), o último comando tem precedência. O comando `\displaylImits` pode ser usado para mudar para as convenções normais da TEX; ou seja, os limites serão exibidos apenas nos estilos *d *e *d ' *.

Se você precisar colocar mais de uma fileira de limites sob um grande operador, poderá fazê -lo com `\no topo` '`. A maneira correta de digitar a seguinte fórmula é 

```tex
$$\sum_{\scriptstyle0\le i\le m\atop\scriptstyle0<j<n}P(i,j)$$.
```

![Limites de várias fileiras sob o sinal de soma](/tex/images/java/tutorial/latex-math-6-6.png)

O comando `\scriptstyle` é necessário aqui, caso contrário, ambas as linhas do limite teriam sido no tamanho do scriptscript, que é muito pequeno. Este é outro caso raro em que as regras do estilo de Tex precisam ser substituídas.