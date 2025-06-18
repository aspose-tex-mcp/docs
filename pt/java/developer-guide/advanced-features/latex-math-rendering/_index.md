---
translation: true
template: /templates/_template-java.md
title: Fórmulas de matemática de LaTeX Renderização | Java
linktitle: Fórmulas de matemática de LaTeX renderização
weight: 10
url: /java/latex-math-formula-rendering/
description: Fórmulas de matemática de LaTeX renderizar dentro da API Aspose.TeX para Java é descrito neste artigo. Aprenda os exemplos de código de como usar a funcionalidade.
lastmod: "2025-06-16"
---

{{<section overview>}}

## Como renderizar uma fórmula de matemática de LaTeX para png

De fato, a maneira mais fácil de demonstrar o recurso de renderização **de fórmula de matemática** ** é começar com o exemplo. Aqui está:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-PngLaTeXMathRendering.java" >}}

Vamos até os detalhes. Primeiro de tudo, criamos uma instância [de renderização](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRendererOptions), semelhante à digitação Tex/LaTex. Fazemos isso aqui especificando simultaneamente a resolução da imagem de saída.

Em seguida, especificamos o preâmbulo. O preâmbulo padrão é:


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

que fornece suporte a fórmula matemática um pouco mais avançado do que o LaTeX básico. Você pode, por exemplo, adicionar o pacote `color` se quiser usar seu próprio destaque na fórmula, como mostramos no exemplo do código.

Em seguida, instruímos o renderizador a escalar a saída em 300%.

As próximas duas opções definem as cores de primeiro plano e fundo. As partes da fórmula que não são cobertas ("coloridas") pelo destaque personalizado serão exibidas na cor `textColor`.

A próxima linha do exemplo não faz muito sentido. Ele apenas demonstra que você pode direcionar a saída de log para algum fluxo.

E a última opção `showterminal` permite alternar a gravação da saída do terminal no console.

O método que realmente executa a renderização é [MathRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/mathrenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.MathRendererOptions-). Ele retorna o tamanho da fórmula em pontos.

O fluxo em que a imagem deve ser escrito é aceito pelo método como o segundo argumento. Criamos o fluxo a seguir.

E, finalmente, chamamos o próprio método de `MathRenderer.render()`, passando as opções como o terceiro argumento. O código do LATEX da fórmula é aprovado como o primeiro argumento.

As últimas linhas do exemplo imprimem dois artefatos de renderização de fórmula matemática - o tamanho da fórmula e o breve relatório de erro (caso haja erros).

Aqui está o resultado da renderização.

<a href="/tex/images/java/math-formula.png">![Figura de LaTeX renderização para png](/tex/images/java/math-formula.png)</a>

Este é o caso de uso mais geral para **fórmula de matemática de LaTeX** renderização.

**Você também pode conferir o [aplicativo da web] gratuito (4) construído com base no recurso implementado no [Aspose.TeX para .NET](https://products.aspose.com/tex/net/) API. [Aqui](https://products.aspose.com/tex/java/) é a página da versão Java.**

## Como renderizar uma fórmula de matemática de LaTeX para SVG

Da mesma maneira, podemos renderizar uma fórmula matemática de LaTeX ao formato SVG.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.java" >}}

As diferenças são:

* Utilizamos [svgmathrenderoptions](https://reference.aspose.com/tex/java/com.aspose.tex/SvgMathRendererOptions) Classe em vez de [pngmathrenderoptions](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRendererOptions).
* Não especificamos resolução.
* Utilizamos a classe [svgmathrenderer](https://reference.aspose.com/tex/java/com.aspose.tex/SvgMathRenderer) em vez de [pngmathrenderer](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRenderer).

Aqui está o resultado:

<a href="/tex/images/java/math-formula.svg">![Fórmula de matemática de LaTeX renderização para SVG](/tex/images/java/math-formula.svg)</a>

**Você também pode conferir o [aplicativo web] gratuito (12) construído com base no recurso implementado em [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**