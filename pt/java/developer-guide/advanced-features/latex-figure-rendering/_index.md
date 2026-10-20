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

Defina `outputFile` como um `java.nio.file.Path` em uma pasta existente, por exemplo `Paths.get(outputDirectory, "text-and-formula.png")` para PNG ou `Paths.get(outputDirectory, "text-and-formula.svg")` para SVG. Importe as classes de renderizador, opções e `Size2D` de Aspose.TeX usadas, além de `java.awt.Color`, `java.io.ByteArrayOutputStream`, `java.io.OutputStream`, `java.nio.file.Files`, `java.nio.file.Path`, `java.nio.file.Paths`. O método que faz a chamada deve tratar ou declarar as exceções. Aplique uma licença conforme o [guia de licenciamento](/tex/{{lang.url-fragment}}java/licensing/) para evitar as restrições de avaliação.

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderFigureToPNG.java" >}}

Primeiro de tudo, criamos uma instância [de renderização](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerendereroptions/). Fazemos isso aqui, além de especificar a resolução da imagem de saída.

Em seguida, especificamos o preâmbulo. Não há preâmbulo padrão para renderização de figuras de LaTeX; portanto, se você quiser, por exemplo, renderizar alguns gráficos plotados usando o pacote `pict2e` LATEX, você precisa especificá -lo no preâmbulo:

```tex
\usepackage{pict2e}
```

Em seguida, instruímos o renderizador a escalar a saída em 300%. Os exemplos também definem uma margem de 5 pontos com `setMargin(5)` ao redor da figura. O exemplo PNG utiliza 150 DPI.

A próxima opção define a cor de fundo. Ao contrário da renderização da fórmula matemática, não especificamos uma cor de primeiro plano, pois assumimos que as cores estão inteiramente sob o controle do código de LaTeX. De fato, o mesmo acontece com a cor de fundo, então essa é apenas uma opção de conveniência.

O exemplo direciona os logs de renderização a um `ByteArrayOutputStream` com `setLogStream()`. Os fluxos do log e da imagem são fechados automaticamente após a renderização.

`showTerminal()` controla a saída do terminal no console. Os exemplos usam `false`; defina `true` para exibi-la.

[FigureRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/figurerenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.FigureRendererOptions-) é chamado em uma instância de `PngFigureRenderer` ou `SvgFigureRenderer` e retorna as dimensões da figura em pontos como um `Size2D`.

O método aceita o fluxo de saída da imagem como segundo argumento. O exemplo o abre em um bloco try-with-resources, que o fecha após a renderização.

Por fim, chamamos `render()` na instância do renderizador: a figura LaTeX é o primeiro argumento, o fluxo da imagem o segundo e as opções de renderização o terceiro.

As últimas linhas do exemplo imprimem dois artefatos de renderização de figuras - o tamanho da figura e o breve relatório de erro (caso haja erros).

Aqui está o resultado da renderização.

![Figura de LaTeX renderização para png](/tex/images/java/text-and-formula.png)

Este é o caso de uso mais geral para o recurso **de renderização de figuras** .

## Como renderizar uma figura de LaTeX para SVG

Da mesma maneira, podemos renderizar uma figura de LaTeX ao formato SVG.

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderFigureToSVG.java" >}}

As diferenças são:

* Utilizamos a classe [SvgFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/svgfigurerendereroptions/) em vez de [PngFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerendereroptions/).
* Não especificamos a resolução.
* Usamos a classe [SvgFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/svgfigurerenderer/) em vez de [PngFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerenderer/).
 
Aqui está o resultado:

<a href="/tex/images/java/text-and-formula.svg">![Figura de LaTeX renderização para SVG](/tex/images/java/text-and-formula.svg)</a>
