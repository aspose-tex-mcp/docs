---
translation: true
template: /templates/_template-net.md
title: Outras opções de gerenciamento de TeX | .NET
linktitle: Outras opções
weight: 17
url: /net/other-options/
description: Funcionalidade de conversão do Aspose.TeX Solução da API para .NET Vamos definir o modo de interação inicial no qual o motor inicia. Aqui estão alguns exemplos de código.
lastmod: "2026-04-22"
---

{{<section overview>}}

## Como definir o modo de interação

Como mencionamos [aqui](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes), **Aspose.TeX para .NET** permite definir o modo de interação inicial no qual o motor inicia. Aqui está como fazemos isso:

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-InteractionMode.cs" >}}

## Como definir o nome do trabalho

Quando passamos o arquivo de entrada principal como um nome de arquivo, obtemos arquivos de saída com o mesmo nome, embora com outras extensões. O mecanismo TeX chama o nome do arquivo de entrada de * nome do trabalho * e o usa para arquivos de saída, exceto nos casos em que os arquivos auxiliares com outros nomes especificados explicitamente são gravados. Quando passamos pelo arquivo de entrada principal como um [Stream](/tex/{{lang.url-fragment}}net/other-ways-of-main-input/#providing-the-main-input-file-as-a-stream), o mecanismo TeX usa o nome da tarefa padrão, que é *texput*.
Nos dois casos, podemos substituir o nome do trabalho atribuindo a opção de conversão apropriada.

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-JobName.cs" >}}

## Como "parar o tempo"

O LATeX possui um recurso para gerar automaticamente um título de algumas definições no preâmbulo. Este título normalmente contém a data atual. Podemos querer congelar a data em algum valor desejado. Aqui está como isso pode ser feito:

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-DateTime.cs" >}}

## Como ignorar pacotes ausentes

Podemos querer converter um arquivo de LaTeX que faz referência a alguns pacotes que não são suportados pelo Aspose.TeX for .Net Library. Nesse caso, o mecanismo TeX interromperá com um erro ao tentar carregar esse pacote. Para evitar isso, podemos usar a seguinte opção:

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-IgnoreMissingPackages.cs" >}}

## Como evitar a construção de ligaduras

Normalmente, o mecanismo TeX cria ligações para certos pares de caracteres se a fonte fornecer os dados necessários para fazê -lo. Podemos instruir o motor a pular o edifício da ligadura com o seguinte código:

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-NoLigatures.cs" >}}

## Como repetir o trabalho

Como mencionamos [acima](/tex/{{lang.url-fragment}}net/latex-io/#latex-input) em relação a rótulos e referências, há casos em que gostaríamos de executar o mesmo trabalho duas vezes. Aqui está como isso pode ser feito:

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-Repeat.cs" >}}

## Como transformar fórmulas de matemática para imagens raster

Às vezes, podemos precisar ter fórmulas matemáticas como imagens rasters, em vez de digitadas em fontes. A opção a seguir pode servir para esse fim:

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-RasterizeFormulas.cs" >}}

## Como transformar gráficos para imagens rasters

O mecanismo ObjectTeX nos permite incluir arquivos gráficos nos formatos raster (PNG e JPG), bem como formatos de PS (EPS) e XPS (OXPS). Os dois últimos formatos geralmente contêm elementos e textos vetoriais. Para tê -los rasterizados e incluídos como imagens sólidas, podemos usar a seguinte opção:

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-RasterizeIncludedGraphics.cs" >}}

## Como subconjuntar fontes

Caso queremos reduzir o tamanho do arquivo de saída, podemos recorrer à subconjunto de fontes, o que significa que as fontes no documento de saída conterão apenas dados sobre os glifos que são usados ​​no documento. Veja como podemos resolver isso:

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-SubsetFonts.cs" >}}
