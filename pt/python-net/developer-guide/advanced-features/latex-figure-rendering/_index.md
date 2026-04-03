---
translation: true
template: /templates/_template-python-net.md
title: Renderização de figuras de LaTeX | Python via .NET
linktitle: O LaTeX inclui a figura
weight: 20
url: /python-net/latex-figure-rendering/
description: O artigo fornece uma visão geral do Aspose.Tex API Solution for Python e sua funcionalidade para renderizar fragmentos de LaTeX (figuras). Aprenda os exemplos de código.
keywords: figura de LaTeX, tamanho da figura, imagem de LaTeX, imagem de LaTeX, imagem de LaTeX, figura de LaTeX, foto de LaTeX, opções de figura de LaTeX
lastmod: "2026-04-03"
---

{{<section overview>}}

Em determinadas situações, pode ser necessário extrair conteúdo específico de um arquivo de LaTeX como uma peça renderizada independente, comumente referida como uma *figura*, sem nenhuma conexão com o layout da página. Isso pode ser útil, por exemplo, ao criar ilustrações para uma publicação on -line. Nossa API permite que você faça isso. Os formatos de destino para renderizar os números são PNG e SVG, assim como com o recurso de renderização de fórmula matemática do LATEX. Vale a pena notar que **Renderização de figuras de LaTeX** é um recurso mais geral em comparação com [renderização de fórmula matemática do LATEX](/tex/{{lang.url-fragment}}python-net/latex-math-formula-rendering/).

## Renderizando uma figura de LaTeX para png

Se necessário, primeiro dê uma olhada na [seção de referência da API para este tópico](https://reference.aspose.com/tex/python-net/aspose.tex.features/). Semelhante à renderização da fórmula, começaremos com um exemplo. Aqui está:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.py" >}}

Para começar, criamos uma instância da classe [Opções do renderizador de figuras do LATEX](https://reference.aspose.com/tex/python-net/aspose.tex.features/figurerendereroptions/), onde especificamos simultaneamente a resolução da imagem de saída.

Em seguida, precisamos especificar o preâmbulo. Ao contrário da renderização de fórmula matemática do LATEX, não há preâmbulo padrão para renderização de figuras de LaTeX. Portanto, se você está planejando renderizar gráficos criados usando o pacote `pict2e` LATEX, por exemplo, precisará especificá -lo no preâmbulo:

```tex
\usepackage{pict2e}
```

Em seguida, instruímos o renderizador a escalar a saída em 300%.

A próxima opção determina a cor do fundo. Ao contrário da renderização da fórmula matemática, não precisamos especificar uma cor de primeiro plano, pois assumimos que as cores são totalmente controladas pelo código do LATEX. Da mesma forma, a cor do plano de fundo também é controlada pelo código do LATEX; portanto, essa opção é simplesmente fornecida por conveniência.

A linha a seguir no exemplo pode não ser particularmente significativa. É simplesmente destinado a demonstrar que você tem a opção de direcionar a saída de log para um fluxo específico.

A opção final, `ShowTerminal`, permite controlar se a saída do terminal deve ser exibida no console.

O método responsável por renderizar a figura é [FigureRenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/figurerenderer/render/). Ele retorna o tamanho da figura em pontos.

O método aceita um fluxo como o segundo argumento, que é o fluxo em que a imagem será gravada. Criamos o fluxo na próxima linha.

Por fim, invocamos o método `FigureRenderer.render()`, passando as opções como o terceiro argumento. O código do LATEX da figura é fornecido como o primeiro argumento.

As últimas linhas do exemplo exibem duas informações relacionadas à renderização de figuras - o tamanho da figura e um breve relatório de erro (se houver algum erro).

Aqui está o resultado da renderização.

<a href="/tex/python-net/latex-figure-rendering/text-and-formula.png">![Figura de LaTeX renderização para png](/tex/images/python-net/text-and-formula.png)</a>

Isso representa o caso de uso mais geral para o recurso de **renderização de figuras de LaTeX**.

## Renderizando uma figura de LaTeX para SVG

Da mesma forma, também podemos renderizar uma figura de LaTeX no formato SVG.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.py" >}}

As diferenças são:

* Em vez de usar a classe [pngfigureReRoptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerendereroptions/), utilizamos a classe [svgfigureReRoptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerendereroptions/).
* Não precisamos especificar a resolução.
* Em vez de usar a classe [pngfigurerenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerenderer/), utilizamos a classe [svgfigurerenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerenderer/).
 
Aqui está o resultado:

<a href="/tex/python-net/latex-figure-rendering/text-and-formula.svg">![Figura de LaTeX renderização para SVG](/tex/images/python-net/text-and-formula.svg)</a>