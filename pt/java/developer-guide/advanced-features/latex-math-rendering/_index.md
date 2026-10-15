---
translation: true
template: /templates/_template-java.md
title: Fórmulas de matemática de LaTeX Renderização | Aspose.TeX para Java
linktitle: Fórmulas de matemática de LaTeX renderização
weight: 10
url: /java/latex-math-formula-rendering/
description: Fórmulas de matemática de LaTeX renderizar dentro da API Aspose.TeX para Java é descrito neste artigo. Aprenda os exemplos de código de como usar a funcionalidade.
lastmod: "2026-04-21"
---

{{<section overview>}}

## Como renderizar uma fórmula de matemática de LaTeX para png

De fato, a maneira mais fácil de demonstrar o recurso de renderização **de fórmula de matemática** ** é começar com o exemplo. Aqui está:

Defina `outputFile` como um `java.nio.file.Path` em uma pasta existente, por exemplo `Paths.get(outputDirectory, "math-formula.png")` para PNG ou `Paths.get(outputDirectory, "math-formula.svg")` para SVG. Importe as classes de renderizador, opções e `Size2D` de Aspose.TeX usadas, além de `java.awt.Color`, `java.io.ByteArrayOutputStream`, `java.io.OutputStream`, `java.nio.file.Files`, `java.nio.file.Path`, `java.nio.file.Paths`. O método que faz a chamada deve tratar ou declarar as exceções. Aplique uma licença conforme o [guia de licenciamento](/tex/{{lang.url-fragment}}java/licensing/) para evitar as restrições de avaliação.

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderMathToPNG.java" >}}

Vamos até os detalhes. Primeiro de tudo, criamos uma instância [de renderização](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrendereroptions/), semelhante à digitação Tex/LaTex. Fazemos isso aqui especificando simultaneamente a resolução da imagem de saída.

Em seguida, especificamos o preâmbulo. O preâmbulo padrão é:


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

que fornece suporte a fórmula matemática um pouco mais avançado do que o LaTeX básico. Você pode, por exemplo, adicionar o pacote `color` se quiser usar seu próprio destaque na fórmula, como mostramos no exemplo do código.

Em seguida, instruímos o renderizador a escalar a saída em 300%.

As duas opções definem as cores de primeiro plano e fundo. As partes da fórmula sem destaque personalizado usam a cor definida por `setTextColor()`.

O exemplo direciona os logs de renderização a um `ByteArrayOutputStream` com `setLogStream()`. Os fluxos do log e da imagem são fechados automaticamente após a renderização.

`showTerminal()` controla a saída do terminal no console. Os exemplos usam `false`; defina `true` para exibi-la.

[MathRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/mathrenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.MathRendererOptions-) é chamado em uma instância de `PngMathRenderer` ou `SvgMathRenderer` e retorna as dimensões da fórmula em pontos como um `Size2D`.

O método aceita o fluxo de saída da imagem como segundo argumento. O exemplo o abre em um bloco try-with-resources, que o fecha após a renderização.

Por fim, chamamos `render()` na instância do renderizador: a fórmula LaTeX é o primeiro argumento, o fluxo da imagem o segundo e as opções de renderização o terceiro.

As últimas linhas do exemplo imprimem dois artefatos de renderização de fórmula matemática - o tamanho da fórmula e o breve relatório de erro (caso haja erros).

Aqui está o resultado da renderização.

<a href="/tex/images/java/math-formula.png">![Figura de LaTeX renderização para png](/tex/images/java/math-formula.png)</a>

Este é o caso de uso mais geral para **fórmula de matemática de LaTeX** renderização.

**Você também pode conferir o [aplicativo da web](https://products.aspose.app/tex) gratuito construído com base no recurso implementado no [Aspose.TeX para .NET](https://products.aspose.com/tex/net/) API. [Aqui](https://products.aspose.com/tex/java/) é a página da versão Java.**

## Como renderizar uma fórmula de matemática de LaTeX para SVG

Da mesma maneira, podemos renderizar uma fórmula matemática de LaTeX ao formato SVG.

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderMathToSVG.java" >}}

As diferenças são:

* Utilizamos a classe [SvgMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/svgmathrendereroptions/) em vez de [PngMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrendereroptions/).
* Não especificamos resolução.
* Utilizamos a classe [SvgMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/svgmathrenderer/) em vez de [PngMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrenderer/).

Aqui está o resultado:

<a href="/tex/images/java/math-formula.svg">![Fórmula de matemática de LaTeX renderização para SVG](/tex/images/java/math-formula.svg)</a>

**Você também pode conferir o [aplicativo web] gratuito (12) construído com base no recurso implementado em [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**