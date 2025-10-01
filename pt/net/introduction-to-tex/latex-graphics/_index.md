---
translation: true
template: /templates/_template-java.md
title: Graphics de LaTeX | \incluirgraphics comando
linktitle: Incluir LATEXGRAPHICS
weight: 18
url: /net/latex-graphics/
description: A inclusão de gráficos em Tex é uma questão que vale a pena mencionar. Ao falar sobre isso, a primeira coisa que vem à mente é o comando `\incluirgraphics`.
lastmod: "2025-06-16"
---

{{<section overview>}}

Na verdade, existem dois aspectos dos gráficos de LaTeX que valem a pena mencionar:

* Gráficos vetoriais descritos diretamente por meio de comandos LATEX/TEX e,
* Inclusão de gráficos externos descritos por meio de formatos externos, como EPS, PDF ou Raster PNG e PDF.

O primeiro tem apoio limitado no LaTeX original e em seus pacotes. É implementado com a ajuda das regras verticais e horizontais da TEX. Isso ocorre porque o LaTeX original é baseado no mecanismo Tex original, que produz a saída principal no formato * DVI *, que não é adequado para descrever linhas e curvas ou dados de imagem de varredura binária. Mas os mecanismos capazes de produzir para formatos de suporte a gráficos (como o PDFTEX para PDF) também podem lidar com gráficos usando pacotes ou recursos de pacote dependentes de formato. Os últimos gráficos não são suportados no LaTeX básico pelo mesmo motivo. Discutiremos os recursos de inclusão gráfica abaixo.

## O pacote de LaTeX `graphics` e `\incluirgraphics`

Ao falar sobre a inclusão de gráficos de LaTeX, a primeira coisa que vem à mente é o comando `\incluirgraphics`. Ele é definido no pacote `graphics`, que você deve mencionar no preâmbulo para ativar seus recursos.

```tex
\usepackage{graphics}
```

Se o seu sistema de composição não estiver configurado para usar, digamos, PDFTEX por padrão, você deve especificar a opção apropriada que forçará o pacote a usar o arquivo `driver 'necessário:


```tex
\usepackage[pdftex]{graphics}
```

Um arquivo `driver` faz parte de um pacote que implementa a interface entre os comandos do pacote e as primitivas de extensão Tex de baixo nível dependente de formato. O suporte gráfico do Aspose.Tex é configurado para usar seu próprio driver, para que você não precise especificar a opção Driver.

Agora, a maneira mais simples de incluir, digamos, uma imagem PNG é digitar:


```tex
\includegraphics{sample-image.png}
```

onde `sample-image.png` é o nome do arquivo que você deseja incluir. Você pode até avaliar a extensão. O pacote `graphics` contém a lista de definições de formatos suportados. Ao procurar um arquivo, ele atravessa essa lista e inclui o primeiro arquivo correspondente encontrado.

Você também pode especificar o nome completo do arquivo usando um caminho absoluto ou relativo:

```tex
\includegraphics{d:/sample-image.png} % absolute path
\includegraphics{./sample-image.png} % relative to the current directory
\includegraphics{../img/sample-image.png} % relative to the directory containing the current one
```

Outra maneira de especificar os arquivos gráficos Localização (s) é definir uma lista de caminhos alternativos usando o comando `\graphicsPath` antes de ligar para `\incluirGraphics`:

```tex
\graphicspath{{d:/img}{c:/img}{d:/work/img}}
```

### Escalando os gráficos

O pacote LATEX `graphics` fornece comandos para manipular o conteúdo. Assim, você pode escalar os gráficos incluídos (de fato, qualquer coisa descrita pelo código TEX/LATEX) da seguinte maneira:


```tex
\scalebox{.5}{\includegraphics{sample-image.png}} % scales both width and height by 0.5
\scalebox{.5}[1.5]{\includegraphics{sample-image.png}} % scales the width and height by 0.5 and 1.5 respectively
```

### Redimensionando os gráficos

É semelhante à escala, mas você especifica o tamanho necessário em vez de um (s) fator (s) de escala:


```tex
\resizebox{10mm}{!}{\includegraphics{sample-image.png}} % changes the width to 10mm preserving the proprtions
\resizebox{20mm}{10mm}{\includegraphics{sample-image.png}} % changes both width and height independently
```

### Girando os gráficos

```tex
\rotatebox{25}{\includegraphics{sample-image.png}} % rotates the image by 25 degrees counterclockwise
```

## O pacote de LaTeX `graphicx`

O pacote LATEX `graphicx` fornece a interface `key = value` para transformações de conteúdo. Para ativar seus recursos, você deve mencioná -lo no preâmbulo:


```tex
\usepackage{graphicx}
\usepackage[pdftex]{graphicx} % with the driver option
```

Você pode combinar qualquer uma das seguintes opções, mas lembre -se de que a ordem é importante.

### Viewport gráfico

```tex
\includegraphics[viewport=10 10 280 220]{sample-image.png} % sets the viewport with the lower left corner
                                                           % at the point (10, 10) (coinsides with (0, 0)
                                                           % of the box) and dimensions 280x220pt
\includegraphics[viewport=10 10 250 220,clip]{sample-image.png} % the same, but the image is clipped by the viewport
```

### Gráficos de escala

```tex
\includegraphics[scale=.5]{sample-image.png} % scales both width and height by 0.5
```

### Redimensionando gráficos

```tex
\includegraphics[width=15mm]{sample-image.png} % changes the width to 15mm preserving the proprtions
\includegraphics[height=15mm,width=25mm]{sample-image.png} % changes both width and height independently
```

### Gráficos rotativos

```tex
\includegraphics[angle=10]{sample-image.png} % rotates the image by 10 degrees counterclockwise
```

Para saber mais sobre os recursos de pacote de pacote `graphics`, consulte a documentação [aqui](https://ctan.org/pkg/graphics) e
[aqui](http://mirrors.ctan.org/macros/latex/required/graphics/graphics.pdf).

**Você também pode conferir a conversão gratuita [aplicativo da web](https://products.aspose.app/tex/conversion/latex/) construído com base em [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**