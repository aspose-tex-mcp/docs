---
translation: true
template: /templates/_template-java.md
title: Outras opções de gerenciamento de Tex | Java
linktitle: Outras opções
weight: 17
url: /java/other-options/
description: Funcionalidade de conversão do Aspose.TeX Solução da API para Java vamos definir o modo de interação inicial no qual o motor inicia. Aqui estão alguns exemplos de código.
lastmod: "2025-06-16"
---

{{<section overview>}}


Cada exemplo cria `TeXOptions` para LaTeX e configura uma opção. Passe essas opções a um `TeXJob`, forneça uma entrada LaTeX adequada e defina um diretório de trabalho de saída antes da execução. Importe `com.aspose.tex.TeXOptions`, `TeXConfig` e as classes usadas no exemplo escolhido: `Interaction`, `com.aspose.tex.rendering.XpsSaveOptions` ou `PdfSaveOptions`, e `java.util.Calendar`/`GregorianCalendar` para o exemplo de data. Trate ou declare as exceções no método chamador. Os exemplos de rasterização e subconjuntos de fontes usam `PdfSaveOptions`; renderize com um `PdfDevice` compatível. Aplique uma licença conforme o [guia de licenciamento](/tex/{{lang.url-fragment}}java/licensing/).

## Como definir o modo de interação

Como mencionamos [aqui](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes), **Aspose.TeX para java** nos permite definir o modo de interação inicial no qual o motor inicia. Aqui está como fazemos isso:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-InteractionMode.java" >}}

## Como definir o nome do trabalho

Quando passamos o arquivo de entrada principal como um nome de arquivo, obtemos arquivos de saída com o mesmo nome, embora com outras extensões. O mecanismo TEX chama o nome do arquivo de entrada de * nome do trabalho * e o usa para arquivos de saída, exceto nos casos em que os arquivos auxiliares com outros nomes especificados explicitamente são gravados. Quando passamos pelo arquivo de entrada principal como um [Stream](/tex/{{lang.url-fragment}}java/other-ways-of-main-input/#providing-the-main-input-file-to-the-tex-engine-as-a-stream), o mecanismo TEX usa o nome da tarefa padrão, que é *texput*.
Nos dois casos, podemos substituir o nome do trabalho atribuindo a opção de conversão apropriada.

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-JobName.java" >}}

## Como "parar o tempo"

O LATEX possui um recurso para gerar automaticamente um título de algumas definições no preâmbulo. Este título normalmente contém a data atual. Podemos querer congelar a data em algum valor desejado. Aqui está como isso pode ser feito:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-DateTime.java" >}}

## Como ignorar pacotes ausentes

Um arquivo LaTeX pode fazer referência a pacotes indisponíveis na biblioteca Aspose.TeX para Java. O mecanismo normalmente para com um erro ao tentar carregar um desses pacotes. Use `ignoreMissingPackages(true)` para ignorar pacotes indisponíveis. Isso não fornece os comandos que esses pacotes definiriam; a entrada não deve depender deles.

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-IgnoreMissingPackages.java" >}}

## Como evitar a construção de ligaduras

Normalmente, o mecanismo Tex cria ligações para certos pares de caracteres se a fonte fornecer os dados necessários para fazê -lo. Podemos instruir o motor a pular o edifício da ligadura com o seguinte código:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-NoLigatures.java" >}}

## Como repetir o trabalho

Como mencionamos [acima](/tex/{{lang.url-fragment}}net/latex-io/#latex-input) em relação a rótulos e referências, há casos em que podemos querer executar o mesmo trabalho duas vezes. Aqui está como isso pode ser feito:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-Repeat.java" >}}

## Como transformar fórmulas de matemática para imagens raster

Às vezes, podemos precisar ter fórmulas matemáticas como imagens rasters, em vez de digitadas em fontes. A opção a seguir pode servir para esse fim:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RasterizeFormulas.java" >}}

## Como transformar gráficos para imagens rasters

O mecanismo ObjectTex nos permite incluir arquivos gráficos nos formatos raster (PNG e JPG), bem como formatos de PS (EPS) e XPS (OXPS). Os dois últimos formatos geralmente contêm elementos e textos vetoriais. Para tê -los rasterizados e incluídos como imagens sólidas, podemos usar a seguinte opção:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RasterizeIncludedGraphics.java" >}}

## Como subconjuntar fontes

Os subconjuntos de fontes limitam as fontes incorporadas aos glifos usados no documento. O efeito sobre o tamanho da saída depende da fonte e de como o dispositivo de saída a incorpora. Atribua as opções de salvamento antes de ativar `subsetFonts(true)`, como mostrado abaixo:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-SubsetFonts.java" >}}