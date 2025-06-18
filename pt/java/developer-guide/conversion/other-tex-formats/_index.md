---
translation: true
template: /templates/_template-java.md
title: Outros formatos de saída de conversão Tex | Java
linktitle: Outros formatos de Tex
weight: 18
url: /java/other-tex-formats/
description: A funcionalidade de conversão do Aspose.TeX API Solution for Java permite a conversão de arquivos de LaTeX e seus próprios arquivos Tex personalizados. Aqui estão alguns exemplos de código.
lastmod: "2025-06-16"
---

{{<section overview>}}

É altamente improvável que você queira converter um arquivo tex escrito em qualquer outro formato que não seja o LATEX. Mas isso é possível se você estiver estudando o idioma tex e/ou internos por algum motivo. De qualquer forma, **Aspose.TeX para java** permite converter arquivos escritos no formato Tex simples. Ele também permite criar formatos personalizados e documentos de tiponete projetados nesses formatos.

Começaremos com a criação de um formato personalizado.

## Criando um formato personalizado

Lembre -se de que o arquivo de formato é um depósito binário do estado interno do mecanismo Tex.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-CreateCustomTeXFormatFile.java" >}}

Como você pode ver, o código é semelhante ao código para converter um arquivo tex. Mas existem algumas diferenças.

Primeiro, aqui usamos o [TexConfig.Objectinitex ()](https://reference.aspose.com/tex/java/com.aspose.tex/TeXConfig#objectIniTeX--) Configuração do trabalho. Esta é uma configuração especial que deixa o estado do motor "virgem", ou seja, os parâmetros internos têm seus valores padrão e o conjunto de sequências de controle coincide com o conjunto de primitivas. Em nosso exemplo, o conjunto de primitivas é estendido no sentido mencionado [aqui](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex).

Em seguida, configuramos os diretórios de trabalho de entrada e saída, como de costume. O diretório de trabalho de entrada precisa conter o arquivo de origem do formato principal e todas as suas dependências.

E a segunda diferença importante é a maneira como executamos o trabalho. Desta vez, usamos o método estático [createFormat ()](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob#createFormat-java.lang.String-com.aspose.tex.TeXOptions-), que, juntamente com as opções, pega o nome do arquivo de origem principal, que deve ser o mesmo que o nome do formato.

## Tipando um arquivo tex em seu formato personalizado

Agora que temos nosso próprio formato Tex, queremos digitar um arquivo tex escrito neste formato. Aqui está o código:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-TypesetWithCustomTeXFormat.java" >}}

Obviamente, temos que especificar o formato de alguma forma. Primeiro de tudo, precisamos criar uma instância da classe [FormatProvider](https://reference.aspose.com/tex/java/com.aspose.tex/FormatProvider). Em seguida, no construtor de opções, usamos a configuração [TeXConfig.ObjectIniTeX](https://reference.aspose.com/tex/java/com.aspose.tex/TeXConfig#objectTeX--), que toma nosso provedor de formato como um argumento e carrega o formato no topo do estado "virgem" do motor.

O restante do código deve ser familiar para você. Ele usa os recursos discutidos anteriormente neste [guia](/tex/{{lang.url-fragment}}java/conversion/).

## Tipando um arquivo tex no formato PLAin Tex

Se jogarmos fora o provedor de formato do código que acabamos de demonstrar, o motor carregará o formato padrão, que é [objeto tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/) em seu quarto sentido. Assim, se você tiver um arquivo tex escrito no formato PLAIN TEX, dessa maneira poderá convertê -lo em qualquer formato de destino suportado.