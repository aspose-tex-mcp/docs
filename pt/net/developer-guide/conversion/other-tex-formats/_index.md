---
translation: true
template: /templates/_template-net.md
title: Outros formatos de saída de conversão TeX | .NET
linktitle: Outros formatos de TeX
weight: 18
url: /net/other-tex-formats/
description: A funcionalidade de conversão do Aspose.TeX API Solution for .Net permite a conversão de arquivos de LaTeX e seus próprios arquivos TeX personalizados. Aqui estão alguns exemplos de código.
lastmod: "2026-04-22"
---

{{<section overview>}}

É altamente improvável que você queira converter um arquivo TeX escrito em qualquer outro formato que não seja o LaTeX. Mas isso é possível se você estiver estudando o idioma TeX e/ou internos por algum motivo. De qualquer forma, **Aspose.TeX para .NET** permite converter arquivos escritos no formato TeX simples. Ele também permite criar formatos personalizados e documentos de composição tipográfica projetados nesses formatos.

Começaremos com a criação de um formato personalizado.

## Criando um formato personalizado

Lembre -se de que o arquivo de formato é um depósito binário do estado interno do mecanismo TeX.

{{< gist "aspose-com-gists" "c0eb6cbcfb001b7e6355cafa4611afed" "Example-CreateCustomFormat.cs" >}}

Como você pode ver, o código é semelhante ao código para converter um arquivo TeX. Mas existem algumas diferenças.

Primeiro, aqui usamos a configuração do trabalho [TeXConfig.ObjectIniTeX](https://reference.aspose.com/TeX/net/aspose.TeX/TeXconfig/objectiniTeX/). Esta é uma configuração especial que deixa o estado do motor "virgem", ou seja, os parâmetros internos têm seus valores padrão e o conjunto de sequências de controle coincide com o conjunto de primitivas. Em nosso exemplo, o conjunto de primitivas é estendido no sentido mencionado [aqui](/TeX/{{lang.url-fragment}}net/aspose-TeX-and-object-TeX/#object-TeX).

Em seguida, configuramos os diretórios de trabalho de entrada e saída, como de costume. O diretório de trabalho de entrada precisa conter o arquivo de origem do formato principal e todas as suas dependências.

E a segunda diferença importante é a maneira como executamos o trabalho. Desta vez, usamos o método estático [CreateFormat()](https://reference.aspose.com/TeX/net/aspose.TeX/TeXjob/createformat/), que, juntamente com as opções, pega o nome do arquivo de origem principal, que deve ser o mesmo que o nome do formato.

## Compondo um arquivo TeX em seu formato personalizado

Agora que temos nosso próprio formato TeX, queremos compor um arquivo TeX escrito neste formato. Aqui está o código:

{{< gist "aspose-com-gists" "c0eb6cbcfb001b7e6355cafa4611afed" "Example-TypesetWithCustomFormat.cs" >}}

Obviamente, temos que especificar o formato de alguma forma. Primeiro de tudo, precisamos criar uma instância da classe [FormatProvider](https://reference.aspose.com/TeX/net/aspose.TeX.resourceproviders/formatprovider/). Em seguida, no construtor de opções, usamos a configuração [TeXConfig.ObjectTeX()](https://reference.aspose.com/TeX/net/aspose.TeX/TeXconfig/objectTeX/), que toma nosso provedor de formato como um argumento e carrega o formato no topo do estado "virgem" do motor.

O restante do código deve ser familiar para você. Ele usa os recursos discutidos anteriormente neste [guia](/TeX/{{lang.url-fragment}}net/conversion/).

## Compondo um arquivo TeX no formato Plain TeX

Se jogarmos fora o provedor de formato do código que acabamos de demonstrar, o motor carregará o formato padrão, que é [objeto TeX](/TeX/{{lang.url-fragment}}net/aspose-TeX-and-object-TeX/) em seu quarto sentido. Assim, se você tiver um arquivo TeX escrito no formato PLAIN TEX, dessa maneira poderá convertê -lo em qualquer formato de destino suportado.
