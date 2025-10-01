---
translation: true
template: /templates/_template-net.md
title: Fórmulas de matemática de LaTeX Renderização | .NET
linktitle: Fórmulas de matemática de LaTeX renderização
weight: 10
url: /net/latex-math-formula-rendering/
description: Solução da API do Aspose.TeX para a renderização do .NET LATEX MATH FORMULAS é descrita neste artigo. Aprenda os exemplos de código sobre como usar a funcionalidade.
lastmod: "2025-06-16"
---

{{<section overview>}}


## Como renderizar uma fórmula de matemática de LaTeX para png

A seção de referência da API relacionada a este tópico é [aqui](https://reference.aspose.com/tex/net/aspose.tex.features/). De fato, a maneira mais fácil de demonstrar o recurso **FORMULAÇÃO DE FORMULAÇÃO DE MATHA DE LATEX** é começar com o exemplo. Aqui está:

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Features-PngLaTeXMathRendering.cs" >}}

Vamos até os detalhes. Primeiro de tudo, criamos uma instância [de renderização](https://reference.aspose.com/tex/net/aspose.tex.features/mathrendereroptions/), semelhante à digitação Tex/Latex. Fazemos isso aqui especificando simultaneamente a resolução da imagem de saída.

Em seguida, especificamos o preâmbulo. O preâmbulo padrão é:

```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

que fornece suporte a fórmula matemática um pouco mais avançado do que o LaTeX básico. Você pode, por exemplo, adicionar o pacote `color` se quiser usar seu próprio destaque na fórmula, como mostramos no exemplo do código.

Em seguida, instruímos o renderizador a escalar a saída em 300%.

As próximas duas opções definem as cores de primeiro plano e fundo. As partes da fórmula que não são cobertas ("coloridas") pelo destaque personalizado serão exibidas na cor 'textColor`.

A próxima linha do exemplo não faz muito sentido. Ele apenas demonstra que você pode direcionar a saída de log para algum fluxo.

E a última opção `showterminal` permite alternar a gravação da saída do terminal no console.

O método que realmente executa a renderização é [MathRenderer.render()](https://reference.aspose.com/tex/net/aspose.tex.features/mathrenderer/render/). Ele retorna o tamanho da fórmula em pontos.

O fluxo em que a imagem deve ser escrito é aceito pelo método como o segundo argumento. Criamos o fluxo a seguir.

E, finalmente, chamamos o próprio método de `MathRenderer.render()`, passando as opções como o terceiro argumento. O código do LATEX da fórmula é aprovado como o primeiro argumento.

As últimas linhas do exemplo imprimem dois artefatos de renderização de fórmula matemática - o tamanho da fórmula e o breve relatório de erro (caso haja erros).

Aqui está o resultado da renderização.

<a href="/tex/net/latex-math-formula-rendering/math-formula.png">![Fórmula de matemática de LaTeX renderização para PNG](/tex/images/net/math-formula.png)</a>

Este é o caso de uso mais geral para o recurso **de fórmula matemática**.

**Você também pode conferir o [aplicativo web](https://products.aspose.app/tex) gratuito construído com base no recurso implementado em [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**

## Como renderizar uma fórmula de matemática de LaTeX para SVG

Da mesma maneira, podemos renderizar uma fórmula matemática de LaTeX ao formato SVG.

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.cs" >}}

As diferenças são:

* Utilizamos [svgmathrenderoptions](https://reference.aspose.com/tex/net/aspose.tex.features/svgmathrendereroptions/) Classe em vez de [pngmathrenderoptions](https://reference.aspose.com/tex/net/aspose.tex.features/pngmathrendereroptions/).
* Não especificamos resolução.
* Utilizamos a classe [svgmathrenderer](https://reference.aspose.com/tex/net/aspose.tex.features/svgmathrenderer/) em vez de [pngmathrenderer](https://reference.aspose.com/tex/net/aspose.tex.features/pngmathrenderer/).
 
Aqui está o resultado:

<a href="/tex/net/latex-math-formula-rendering/math-formula.svg">![Fórmula de matemática de LaTeX renderização para SVG](/tex/images/net/math-formula.svg)</a>

**Você também pode conferir o [aplicativo web] gratuito (12) construído com base no recurso implementado em [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**