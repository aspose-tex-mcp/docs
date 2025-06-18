---
translation: true
template: /templates/_template-python-net.md
title: Fórmulas de matemática de LaTeX Renderização | Python
linktitle: Fórmulas de matemática de LaTeX renderização
weight: 10
url: /python-net/latex-math-formula-rendering/
description: O artigo fornece uma visão geral da solução da API Aspose.Tex para o Python e sua funcionalidade para renderizar fórmulas de matemática de LaTeX. Aprenda os exemplos de código
lastmod: "2025-06-16"
---

{{<section overview>}}

## Renderizando uma fórmula de matemática de LaTeX para png

Se necessário, dê uma olhada na [seção de referência da API para este tópico](https://reference.aspose.com/tex/python-net/aspose.tex.features/). De fato, a melhor maneira de demonstrar o recurso **de fórmula de matemática** ** é começar com um exemplo. Aqui está:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Features-PngLaTeXMathRendering.py" >}}

Vamos até os detalhes. Em primeiro lugar, iniciamos um objeto [Opções de renderização](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrendereroptions/), semelhante ao TypeTting Tex/Latex, que inclui a especificação para a resolução de imagem de saída desejada.

Em seguida, especificamos o preâmbulo. O preâmbulo padrão é:


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

que oferece suporte aprimorado para fórmulas matemáticas em comparação com o LaTeX padrão. Por exemplo, você pode incluir o pacote `color` para personalizar o destaque na fórmula, conforme demonstrado no exemplo de código fornecido.

Em seguida, instruímos o renderizador a escalar a saída em 300%.

As próximas duas opções determinam as cores de primeiro plano e plano de fundo. Qualquer parte da fórmula que não seja afetada pelo destaque personalizada será exibida na cor `textColor`.

A linha a seguir no exemplo serve como uma ilustração de que você tem a opção de redirecionar a saída do log para um fluxo específico.

E, finalmente, a opção `showterminal` permite controlar se a saída do terminal deve ser exibida no console.

O processo de renderização real é realizado pelo método [MathRenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrenderer/render/), que retorna o tamanho da fórmula em pontos.

O método aceita o fluxo em que a imagem será escrita como seu segundo argumento. Posteriormente, passamos a criar o fluxo.

E, finalmente, o método `MathRenderer.render()` é invocado, com as opções sendo aprovadas como o terceiro argumento. O código do LATEX da fórmula é fornecido como o primeiro argumento.

As linhas finais do exemplo exibem duas saídas do processo de renderização da fórmula matemática - o tamanho da fórmula e um relatório de erro conciso, se ocorrerem erros.

Aqui está o resultado da renderização.

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.png">![Fórmula de matemática de LaTeX renderização para PNG](/tex/images/python-net/math-formula.png)</a>

Isso representa a aplicação mais comum e ampla da funcionalidade **FORMULAÇÃO DE FORMULAÇÃO DE MATHA DE LATEX**.

**Você também pode explorar o [aplicativo web] gratuito (5), que utiliza o recurso implementado do [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**

## Renderizando uma fórmula de matemática de LaTeX para SVG

Da mesma forma, podemos converter uma fórmula matemática de LaTeX em formato SVG usando a mesma abordagem.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.py" >}}

As diferenças são:

* Em vez de usar a classe [pngmathrenderoptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrendereroptions/), utilizamos a classe [svgmathrenderoptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrendereroptions/).
* Não especificamos resolução.
* Em vez de usar a classe [pngmathrenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrenderer/), usamos a classe [svgmathrenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrenderer/).
 
Aqui está o resultado:

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.svg">![Fórmula de matemática de LaTeX renderização para SVG](/tex/images/python-net/math-formula.svg)</a>

**Você também pode explorar o [aplicativo web] gratuito (12), que utiliza o recurso implementado do [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**