---
translation: true
template: /templates/_template-python-net.md
title: Fórmulas de matemática de LaTeX Renderização | Python via .NET
linktitle: Fórmulas de matemática de LaTeX renderização
weight: 10
url: /python-net/latex-math-formula-rendering/
description: O artigo fornece uma visão geral da solução da API Aspose.Tex para o Python e sua funcionalidade para renderizar fórmulas de matemática de LaTeX. Aprenda os exemplos de código
lastmod: "2026-04-03"
---

{{<section overview>}}

## Renderizando uma fórmula de matemática de LaTeX para png

Se necessário, dê uma olhada na [seção de referência da API para este tópico](https://reference.aspose.com/tex/python-net/aspose.tex.features/). De fato, a melhor maneira de demonstrar o recurso de renderização de **fórmula matemática LaTeX** é começar com um exemplo. Aqui está:

Defina `ASPOSE_TEX_OUTPUT_DIR` como o diretório de saída ou use a pasta padrão `output`. Todo o código LaTeX está incluído nos exemplos; não são necessários arquivos de entrada externos. Aplique uma licença primeiro. [Licenciamento](/tex/pt/python-net/licensing/).

{{< gist "aspose-com-gists" "cbf380b84d7f2067481756d42da32b08" "Aspose.TeX.Examples-Features-PngLaTeXMathRendering.py" >}}

Vamos até os detalhes. Em primeiro lugar, iniciamos um objeto [Opções de renderização](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrendereroptions/), semelhante ao TypeTting Tex/Latex, que inclui a especificação para a resolução de imagem de saída desejada.

Em seguida, especificamos o preâmbulo. O preâmbulo padrão é:


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

que oferece suporte aprimorado para fórmulas matemáticas em comparação com o LaTeX padrão. Por exemplo, você pode incluir o pacote `color` para personalizar o destaque na fórmula, conforme demonstrado no exemplo de código fornecido.

Definimos `scale = 3000` para uma escala de 300% e `margin = 5` para deixar espaço ao redor do fragmento. O exemplo PNG usa `resolution = 150` DPI.

As próximas duas opções determinam as cores de primeiro plano e plano de fundo. Qualquer parte da fórmula que não seja afetada pelo destaque personalizada será exibida na cor `text_color`.

O exemplo atribui um fluxo de arquivo binário a `log_stream` e salva o registro como `math-formula.png.log` ao lado de `math-formula.png`. A instrução `with` fecha ambos os fluxos automaticamente.

`show_terminal` controla a saída do terminal no console. Os exemplos o definem como `False`; o registro continua sendo gravado no arquivo.

O processo de renderização real é realizado pelo método [MathRenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrenderer/render/), que retorna o tamanho da fórmula em pontos.

O segundo argumento é o fluxo de saída binário aberto para a imagem. O terceiro fornece as opções de renderização.

E, finalmente, o método `MathRenderer.render()` é invocado, com as opções sendo aprovadas como o terceiro argumento. O código do LATEX da fórmula é fornecido como o primeiro argumento.

As últimas linhas mostram o relatório de erros, ou `No rendering errors.` quando ele está vazio, seguido da largura e da altura em pontos.

Aqui está o resultado da renderização.

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.png">![Fórmula de matemática de LaTeX renderização para PNG](/tex/images/python-net/math-formula.png)</a>

Isso representa a aplicação mais comum e ampla da funcionalidade de **renderização de fórmula matemática LaTeX**.

**Você também pode explorar o [aplicativo web](https://products.aspose.app/tex) gratuito, que utiliza o recurso implementado do [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**

## Renderizando uma fórmula de matemática de LaTeX para SVG

Da mesma forma, podemos converter uma fórmula matemática de LaTeX em formato SVG usando a mesma abordagem.

{{< gist "aspose-com-gists" "cbf380b84d7f2067481756d42da32b08" "Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.py" >}}

Este exemplo cria `math-formula.svg` e o registro `math-formula.svg.log` no mesmo diretório de saída.

As diferenças são:

* Em vez de usar a classe [pngmathrenderoptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrendereroptions/), utilizamos a classe [svgmathrenderoptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrendereroptions/).
* Não especificamos resolução.
* Em vez de usar a classe [pngmathrenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrenderer/), usamos a classe [svgmathrenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrenderer/).
 
Aqui está o resultado:

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.svg">![Fórmula de matemática de LaTeX renderização para SVG](/tex/images/python-net/math-formula.svg)</a>

**Você também pode explorar o [aplicativo web](https://products.aspose.app/tex/equation-editor/svg) gratuito, que utiliza o recurso implementado do [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**