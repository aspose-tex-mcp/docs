---
translation: true
template: /templates/_template-java.md
title: Renderização de figuras de LaTeX | Aspose.TeX para Java
linktitle: Renderização de figuras de LaTeX
weight: 20
url: /java/latex-figure-rendering/
description: Solução da API de Aspose.TeX para o fragmento de LaTeX Java (Figura) A renderização é descrita neste artigo. Aprenda os exemplos de código sobre como usar a funcionalidade.
lastmod: "2026-04-21"
---

{{<section overview>}}

Pode acontecer que você queira extrair algum conteúdo (um desenho, uma escrita, um enredo etc.) de um arquivo de LaTeX como uma peça renderizada separadamente, ou a *"figure"*, independentemente de seu local em uma página de documento de saída. Uma ilustração para sua publicação na Internet, por exemplo, é o caso. Nossa API pode ajudá -lo com a tarefa. Existem dois formatos de destino disponíveis - PNG e SVG. Assim como na renderização da fórmula matemática do LaTeX. Também devemos observar que **Renderização de figuras de LaTeX** é uma generalização da [renderização de fórmula matemática do LATEX](/tex/{{lang.url-fragment}}java/latex-math-formula-rendering/).

## Como renderizar uma figura de LaTeX para png

E, como na renderização de fórmula, começaremos com um exemplo. Aqui está:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.java" >}}

Primeiro de tudo, criamos uma instância [de renderização](https://reference.aspose.com/tex/java/com.aspose.tex/PngFigureRendererOptions). Fazemos isso aqui, além de especificar a resolução da imagem de saída.

Em seguida, especificamos o preâmbulo. Não há preâmbulo padrão para renderização de figuras de LaTeX; portanto, se você quiser, por exemplo, renderizar alguns gráficos plotados usando o pacote `pict2e` LATEX, você precisa especificá -lo no preâmbulo:

```tex
\usepackage{pict2e}
```

Em seguida, instruímos o renderizador a escalar a saída em 300%.

A próxima opção define a cor de fundo. Ao contrário da renderização da fórmula matemática, não especificamos uma cor de primeiro plano, pois assumimos que as cores estão inteiramente sob o controle do código de LaTeX. De fato, o mesmo acontece com a cor de fundo, então essa é apenas uma opção de conveniência.

A próxima linha do exemplo não faz muito sentido. Ele apenas demonstra que você pode direcionar a saída de log para algum fluxo.

E a última opção `showterminal` permite alternar a gravação da saída do terminal no console.

O método que realmente executa a renderização é [figuureRender.render()](https://reference.aspose.com/tex/java/com.aspose.tex/figurerenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.FigureRendererOptions-). Ele retorna o tamanho da figura em pontos.

O fluxo em que a imagem deve ser escrito é aceito pelo método como o segundo argumento. Criamos o fluxo a seguir.

E, finalmente, chamamos o próprio método de `figuureRender.render()`, passando as opções como o terceiro argumento. O código do LATEX da figura é aprovado como o primeiro argumento.

As últimas linhas do exemplo imprimem dois artefatos de renderização de figuras - o tamanho da figura e o breve relatório de erro (caso haja erros).

Aqui está o resultado da renderização.

![Figura de LaTeX renderização para png](/tex/images/java/text-and-formula.png)

Este é o caso de uso mais geral para o recurso **de renderização de figuras** .

## Como renderizar uma figura de LaTeX para SVG

Da mesma maneira, podemos renderizar uma figura de LaTeX ao formato SVG.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.java" >}}

As diferenças são:

* Utilizamos a classe [SvgFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/SvgFigureRendererOptions) em vez de [PngFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/PngFigureRendererOptions).
* Não especificamos a resolução.
* Usamos a classe [SvgFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/SvgFigureRenderer) em vez de [PngFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/PngFigureRenderer).
 
Aqui está o resultado:

<a href="/tex/images/java/text-and-formula.svg">![Figura de LaTeX renderização para SVG](/tex/images/java/text-and-formula.svg)</a>
