---
translation: true
template: /templates/_template-net.md
title: Renderização de figuras de LaTeX | .NET
linktitle: O LaTeX inclui a figura
weight: 20
url: /net/latex-figure-rendering/
description: Solução da API do Aspose.TeX para a renderização do fragmento de LaTeX .NET (Figura) é descrito neste artigo. Aprenda os exemplos de código sobre como usar a funcionalidade.
keywords: figura de LaTeX, tamanho da figura, imagem de LaTeX, imagem de LaTeX, imagem de LaTeX, figura de LaTeX, foto de LaTeX, opções de figura de LaTeX
lastmod: "2026-06-12"
---

{{<section overview>}}


Às vezes, você pode extrair algum conteúdo de um arquivo LaTeX como uma peça renderizada separadamente, ou a *"figura"*, sem nenhuma conexão com o layout da página. Pode ser uma ilustração para sua publicação na Internet, por exemplo. Você pode fazer isso com nossa API. Quanto aos formatos de destino, existem duas opções - PNG e SVG. Como é no caso do recurso de renderização de fórmulas matemáticas LaTeX. Também vale a pena notar que a **Renderização de figuras LaTeX** é uma generalização da [renderização de fórmulas matemáticas LaTeX](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/).

## Como renderizar uma figura LaTeX para PNG

A seção de referência da API relacionada a este tópico é [aqui](https://reference.aspose.com/tex/net/aspose.tex.features/). E, como na renderização de fórmula, começaremos com um exemplo. Aqui está:

{{< gist "aspose-com-gists" "cd0acc55d1634f17dcf42e02075ca005" "Example-RenderFigureToPNG.cs" >}}

Primeiro de tudo, criamos uma instância de [opções de figura LaTeX](https://reference.aspose.com/tex/net/aspose.tex.features/figurerendereroptions/). Fazemos isso aqui especificando simultaneamente a resolução da imagem de saída.

Em seguida, especificamos o preâmbulo. Não há preâmbulo padrão para a renderização de figuras de LaTeX; portanto, se você estiver, por exemplo, renderizar alguns gráficos plotados usando o pacote `pict2e` LATEX, você precisa especificá -lo no preâmbulo:


```tex
\usepackage{pict2e}
```

Em seguida, instruímos o renderizador a escalar a saída em 300%.

A próxima opção define a cor de fundo. Ao contrário da renderização da fórmula matemática, não especificamos uma cor de primeiro plano, pois assumimos que as cores estão inteiramente sob o controle do código de LaTeX. De fato, o mesmo acontece com a cor de fundo, então essa é apenas uma opção de conveniência.

A próxima linha do exemplo não faz muito sentido. Ele apenas demonstra que você pode direcionar a saída de log para algum fluxo.

E a última opção `showterminal` permite alternar a gravação da saída do terminal no console.

O método que realmente executa a renderização é [FigureRenderer.Render()](https://reference.aspose.com/tex/net/aspose.tex.features/figurerenderer/render/). Ele retorna o tamanho da figura em pontos.

O fluxo em que a imagem deve ser escrita é aceito pelo método como o segundo argumento. Criamos o fluxo a seguir.

E, finalmente, chamamos o próprio método [FigureRenderer.Render()](https://reference.aspose.com/tex/net/aspose.tex.features/figurerenderer/render/), passando as opções como o terceiro argumento. O código LaTeX da figura é passado como o primeiro argumento.

As últimas linhas do exemplo imprimem dois artefatos de renderização de figuras - o tamanho da figura e o breve relatório de erro (caso haja erros).

Aqui está o resultado da renderização.

<a href="/tex/net/latex-figure-rendering/text-and-formula.png">![Figura de LaTeX renderização para png](/tex/images/net/text-and-formula.png)</a>

Este é o caso de uso mais geral para o recurso **de renderização de figuras** **.

## Como renderizar uma figura de LaTeX para SVG

Da mesma maneira, podemos renderizar uma figura de LaTeX no formato SVG.

{{< gist "aspose-com-gists" "cd0acc55d1634f17dcf42e02075ca005" "Example-RenderFigureToSVG.cs" >}}

As diferenças são:

* Utilizamos a classe [SvgFigureRendererOptions](https://reference.aspose.com/tex/net/aspose.tex.features/svgfigurerendereroptions/) em vez de [PngFigureRendererOptions](https://reference.aspose.com/tex/net/aspose.tex.features/pngfigurerendereroptions/).
* Não especificamos a resolução.
* Utilizamos a classe [SvgFigureRenderer](https://reference.aspose.com/tex/net/aspose.tex.features/svgfigurerenderer/) em vez de [PngFigureRenderer](https://reference.aspose.com/tex/net/aspose.tex.features/pngfigurerenderer/).
 
Aqui está o resultado:

<a href="/tex/net/latex-figure-rendering/text-and-formula.svg">![Figura de LaTeX renderização para SVG](/tex/images/net/text-and-formula.svg)</a>

## Criação de um Agente de IA para Renderização de Figuras em LaTeX

Se pretende criar o seu próprio Agente de IA para renderização de figuras em LaTeX utilizando a API Aspose.TeX, aqui fica uma sugestão de workflow para tal agente:

![Esquema de blocos para o workflow de renderização de figuras em LaTeX com IA](/tex/images/net/tutorial/blockscheme-ai-for-graphic-rendering.png)

1. A camada de ingestão (núcleo LLM)
Analisa prompts de linguagem natural não estruturados ou desorganizados, convertendo-os em primitivas matemáticas LaTeX limpas e isoladas e ambientes de figuras (`\begin{picture}`, `\includegraphics`).

2. O sistema de ficheiros virtual (camada de E/S)
Armazena em segurança as dependências gráficas externas (`. png`, `. jpg`) num diretório `InputFileSystemDirectory` em memória ou em sandbox, para que o compilador possa resolver as referências de layout instantaneamente.

3. A configuração
Analisa marcadores de código estrutural e adiciona automaticamente drivers, dependências (como `graphicx` ou `pict2e`), fatores de escala e estados de transparência de fundo.

4. O nó de execução unificado (mecanismo Aspose.TeX)
Compila o ficheiro unificado e passa-o diretamente para o `FigureRenderer` especializado para calcular margens precisas de caixas delimitadoras vetoriais e gerar fragmentos de ecrã visual responsivos (SVG ou PNG de alta resolução).
