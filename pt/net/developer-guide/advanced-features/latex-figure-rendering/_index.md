---
translation: true
template: /templates/_template-net.md
title: Renderização de figuras de LaTeX | .NET
linktitle: O LaTeX inclui a figura
weight: 20
url: /net/latex-figure-rendering/
description: Solução da API do Aspose.TeX para a renderização do fragmento de LaTeX .NET (Figura) é descrito neste artigo. Aprenda os exemplos de código sobre como usar a funcionalidade.
keywords: figura de LaTeX, tamanho da figura, imagem de LaTeX, imagem de LaTeX, imagem de LaTeX, figura de LaTeX, foto de LaTeX, opções de figura de LaTeX
lastmod: "2025-06-16"
---

{{<section overview>}}


Às vezes, você pode extrair algum conteúdo de um arquivo de LaTeX como uma peça renderizada separadamente, ou a *"figura"*, sem nenhuma conexão com o layout da página. Pode ser uma ilustração para sua publicação na Internet, por exemplo. Você pode fazer isso com nossa API. Quanto aos formatos de destino, existem duas opções - PNG e SVG. Como é no caso do recurso de renderização de fórmula matemática do LATEX. Também vale a pena notar que **Renderização de figuras de LaTeX** é uma generalização da [renderização de fórmula matemática do LATEX](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/).

## Como renderizar uma figura de LaTeX para png

A seção de referência da API relacionada a este tópico é [aqui](https://reference.aspose.com/tex/net/aspose.tex.features/). E, como na renderização de fórmula, começaremos com um exemplo. Aqui está:

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.cs" >}}

Primeiro de tudo, criamos uma instância [Figura do LATEX](https://reference.aspose.com/tex/net/aspose.tex.features/figurerendereroptions/). Fazemos isso aqui especificando simultaneamente a resolução da imagem de saída.

Em seguida, especificamos o preâmbulo. Não há preâmbulo padrão para a renderização de figuras de LaTeX; portanto, se você estiver, por exemplo, renderizar alguns gráficos plotados usando o pacote `pict2e` LATEX, você precisa especificá -lo no preâmbulo:


```tex
\usepackage{pict2e}
```

Em seguida, instruímos o renderizador a escalar a saída em 300%.

A próxima opção define a cor de fundo. Ao contrário da renderização da fórmula matemática, não especificamos uma cor de primeiro plano, pois assumimos que as cores estão inteiramente sob o controle do código de LaTeX. De fato, o mesmo acontece com a cor de fundo, então essa é apenas uma opção de conveniência.

A próxima linha do exemplo não faz muito sentido. Ele apenas demonstra que você pode direcionar a saída de log para algum fluxo.

E a última opção `showterminal` permite alternar a gravação da saída do terminal no console.

O método que realmente executa a renderização é [figuureRender.render()](https://reference.aspose.com/tex/net/aspose.tex.features/figurerenderer/render/). Ele retorna o tamanho da figura em pontos.

O fluxo em que a imagem deve ser escrito é aceito pelo método como o segundo argumento. Criamos o fluxo a seguir.

E, finalmente, chamamos o próprio método de `figuureRender.render()`, passando as opções como o terceiro argumento. O código do LATEX da figura é aprovado como o primeiro argumento.

As últimas linhas do exemplo imprimem dois artefatos de renderização de figuras - o tamanho da figura e o breve relatório de erro (caso haja erros).

Aqui está o resultado da renderização.

<a href="/tex/net/latex-figure-rendering/text-and-formula.png">![Figura de LaTeX renderização para png](/tex/images/net/text-and-formula.png)</a>

Este é o caso de uso mais geral para o recurso **de renderização de figuras** **.

## Como renderizar uma figura de LaTeX para SVG

Da mesma maneira, podemos renderizar uma figura de LaTeX no formato SVG.

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.cs" >}}

As diferenças são:

* Utilizamos [svgfigureReroptions](https://reference.aspose.com/tex/net/aspose.tex.features/svgfigurerendereroptions/) Classe em vez de [pngfigureReroptions](https://reference.aspose.com/tex/net/aspose.tex.features/pngfigurerendereroptions/).
* Não especificamos a resolução.
* Utilizamos a classe [svgfigurerenderer](https://reference.aspose.com/tex/net/aspose.tex.features/svgfigurerenderer/) em vez de [pngfigurerenderer](https://reference.aspose.com/tex/net/aspose.tex.features/pngfigurerenderer/).
 
Aqui está o resultado:

<a href="/tex/net/latex-figure-rendering/text-and-formula.svg">![Figura de LaTeX renderização para SVG](/tex/images/net/text-and-formula.svg)</a>