---
translation: true
template: /templates/_template-java.md
linktitle: Incluir Graphics
title: LaTeX includegraphics
weight: 10
url: /java/latex-includegraphics/
keywords: INCLUDEGRAPHICS LATEX, LATEX INCLUDEGRAPHIC, INSERT PERAGES LATEX, LATEX Graphicx, Latex Insert Image, Incluir Pacote de Latex Incluído, Draw IO LATEX, LATEX INCLUDE A LIDADA DE GRAPHICS, Largura de Grófics, Escala de Figura
description: Saiba sobre o LATEX incluir a macro Grachics, juntamente com transformações de imagem, viewport, recorte e a diferença entre os pacotes gráficos e Graphicx.
lastmod: "2025-06-16"
---

{{<section overview>}}

## Introdução

Enquanto trabalha em seus documentos acadêmicos e científicos, como trabalhos de pesquisa, procedimentos de conferência e apresentações acadêmicas, você pode ocasionalmente querer incluir figuras gráficas.

Por um lado, esses podem ser desenhos, parcelas, histogramas ou algo mais que geralmente é chamado de gráficos vetoriais. Os sistemas de LaTeX modernos (como `pdftex`) fornecem muitas ferramentas para criar esses gráficos em um documento. Por exemplo, os pacotes `pict2e`, ` pgf (tikz) `e` pgfplots`. Na maioria dos casos, as próprias figuras são geradas por um mecanismo TEX e incluídas no arquivo de saída como sequências de instruções gráficas vetoriais apropriadas para um formato de saída específico.

Por outro lado, você pode ter imagens rastas que também deseja incluir em sua publicação. Atualmente, os sistemas de LaTeX também são capazes de fazer isso, mas você precisa especificar o caminho para o seu arquivo de imagem no arquivo de LaTeX como um parâmetro para alguma macro de LaTeX.

Este artigo aborda imagens rasters em arquivos de LaTeX usando o `\incluirgraphics` macro do pacote` Graphics` (e o pacote `graphicx`) que o acompanha.

## Qual pacote escolher, `graphics` ou`graphicx`?

Ambos os pacotes, `graphics` e `graphicx`, são muito semelhantes. A principal diferença está na sintaxe. Embora o pacote `graphics` use um conjunto de macros separadas para aplicar transformações a uma imagem, o pacote`graphicx` usa a notação `key = value` para os parâmetros da macro`\incluirgraphics` para especificar essas transformações. Daremos exemplos de cada caso de uso para ambos os pacotes de uma só vez, para tornar a diferença mais clara.

## Incluindo o pacote escolhido

Isso é feito com o comando `\usepackage` da mesma maneira que para qualquer outro pacote de LaTeX:


```tex
\usepackage{graphics} % to use the graphics package
\usepackage{graphicx} % to use the graphicx package
```

### Especificando um driver

Se o seu sistema de composição não estiver configurado para usar, digamos, `pdftex` por padrão, você deve especificar a opção apropriada que forçará o pacote a usar o` driver 'necessário:


```tex
\usepackage[pdftex]{graphics} % graphics
\usepackage[pdftex]{graphicx} % graphicx
```

Um `driver` faz parte de um pacote que implementa a interface entre os comandos do pacote e as primitivas de extensão Tex de baixo nível dependente de formato. **ASPONHAÇÃO ASPOSE.TEX** O suporte gráfico do LaTex está configurado para usar seu próprio driver, para que você não precise especificar a opção Driver.

## LATEX `\IncluirGraphics` Macro

Agora vamos prosseguir com o exemplo mais simples. É claro que este é um caso de incluir uma imagem sem nenhuma transformação. Espera -se que o código de LaTeX usando os dois pacotes é o mesmo:


```tex
\includegraphics{sample-image.png}
```

Este exemplo pressupõe que seu arquivo de imagem esteja localizado no mesmo diretório que o arquivo de LaTeX. Mas existem várias maneiras de especificar um local diferente. O código do LATEX será novamente o mesmo para os dois pacotes:


```tex
\includegraphics{d:/sample-image.png} % absolute path
\includegraphics{./sample-image.png} % relative to the current directory
\includegraphics{../img/sample-image.png} % relative to the directory containing the current one
```

Outra maneira de especificar os arquivos gráficos Localização (s) é definir uma lista de caminhos alternativos usando o comando `\ graphicsPath`antes de ligar para `\incluirGraphics`:


```tex
\graphicspath{{d:/img}{c:/img}{d:/work/img}}
```

## Transformações gráficas de LaTeX

Os pacotes LATEX `graphics` e `graphicx` fornecem várias maneiras de manipular o conteúdo.

### Figura de escala LATEX

Assim, você pode escalar os gráficos incluídos (de fato, qualquer coisa descrita pelo código TEX/LATEX) da seguinte maneira:


```tex
% graphics examples
\scalebox{.5}{\includegraphics{sample-image.png}} % scales both width and height by 0.5
\scalebox{.5}[1.5]{\includegraphics{sample-image.png}} % scales the width and height by 0.5 and 1.5 respectively

% graphicx examples
\includegraphics[scale=.5]{sample-image.png} % scales both width and height by 0.5
% there's no analogue for the graphicx package to scale both dimensions independently
```

### Redimensione o LATEX da figura

É semelhante à escala, mas você especifica o tamanho necessário em vez de um (s) fator (s) de escala:


```tex
% graphics examples
\resizebox{10mm}{!}{\includegraphics{sample-image.png}} % changes the width to 10mm preserving the proportions
\resizebox{20mm}{10mm}{\includegraphics{sample-image.png}} % changes both width and height independently

% graphicx examples
\includegraphics[width=15mm]{sample-image.png} % changes the width to 15mm preserving the proportions
\includegraphics[height=15mm,width=25mm]{sample-image.png} % changes both width and height independently
```

### Gire o LaTeX da figura

```tex
% graphics example
\rotatebox{25}{\includegraphics{sample-image.png}} % rotates the image by 25 degrees counterclockwise

% graphicx example
\includegraphics[angle=-10]{sample-image.png} % rotates the image by 10 degrees clockwise
```

### Definindo uma viewport e recorte

```tex
% This time there's no analogue for the graphics package

% graphicx example
\includegraphics[viewport=10 10 280 220]{sample-image.png} % sets the viewport with the lower left corner
                                                           % at the point (10, 10) (coincides with (0, 0)
                                                           % of the box) and dimensions 280x220pt
\includegraphics[viewport=10 10 250 220,clip]{sample-image.png} % the same, but the image is clipped by the viewport
```

Quanto ao pacote `graphicx`, as transformações podem ser combinadas, mas o pedido é importante.
Para saber mais sobre os recursos de pacote de pacotes `graphics`, consulte a [página do pacote no CTAN](https://ctan.org/pkg/graphics) e
A [documentação do pacote](http://mirrors.ctan.org/macros/latex/required/graphics/graphics.pdf).

### O LaTeX inclui aplicativos web gráficos gratuitos

Se você não deseja trabalhar com o IncluirGraphics Latex Package programaticamente, também poderá conferir o aplicativo Web gratuito [LATEX incluir gráficos](https://products.aspose.app/tex/includegraphics/) construído com base no [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/). 

O aplicativo permite selecionar várias imagens e ajustar visualmente as transformações para elas. Ele também gera código -fonte do LATEX usando o pacote `graphicx` e renderiza o resultado na página.

### Recurso de renderização de figuras de LaTeX na biblioteca Aspose.TeX

A biblioteca **Aspose.TeX** fornece uma maneira de criar figuras raster e svg que você pode usar em suas publicações fora do contexto Tex/Latex. Por exemplo, em uma página da web. Isso é chamado de **figura de LaTeX renderização**. Resumidamente, essa parte da API permite que você renderize um fragmento de código -fonte de LaTeX, independentemente do layout da página. Para mais detalhes, consulte este [artigo](/tex/{{lang.url-fragment}}java/latex-figure-rendering/).

O artigo sobre [incluindo pacotes de LaTeX externo](/tex/{{lang.url-fragment}}java/external-latex-packages/) também pode fornecer uma pista sobre como criar figuras a partir de parcelas de LaTeX.