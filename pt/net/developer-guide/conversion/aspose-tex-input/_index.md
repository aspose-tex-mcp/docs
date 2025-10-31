---
translation: true
template: /templates/_template-net.md
title: Interface de entrada do Aspose.TeX | .NET
linktitle: Interface de entrada do Aspose.TeX
weight: 15
url: /net/aspose-tex-input/
description: Funcionalidade de conversão do Aspose.TeX Solução da API para .NET com TEX, pois um formato de entrada é explicado aqui com os exemplos de código.
keywords: entrada aspose tex, . net tex, input directory, zip input, input console, tex options, iinputworkingdirectory, inputzipdirectory, inputterminal, tex conversion
lastmod: "2025-06-16"
---

{{<section overview>}}

Consulte **Aspose.TeX para .NET** [Referência da API](https://reference.aspose.com/tex/net/aspose.tex.io/) para obter definições formais de implementação de E/S.

## O conceito do diretório de entrada

Como as primitivas de E/S do idioma TEX só podem lidar com nomes de arquivos, **aspose.tex para .NET** define um diretório como um mapeamento entre nomes e volumes de dados. Os ma tetos de dados devem ser arquivos, fluxos, matrizes ou qualquer outra coisa. A API nos permite especificar os diretórios de trabalho de entrada e saída separadamente. Ele fornece a interface Geral [iinputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/), que o usuário pode implementar para seus próprios fins. Ele também fornece suas próprias implementações, que serão discutidas abaixo. A interface define o método [getfile()](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/getfile/), que retorna o fluxo de dados e determina o nome completo do arquivo, enquanto toma um nome, hipoteticamente diferente, como o primeiro argumento, que, de fato, é a chave de mapeamento.

### Obtendo entrada de arquivo do sistema de arquivos de disco

Aqui está como faríamos isso:

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-InputFileSystemDirectory.cs" >}}

Este caso de uso é bastante simples, então não há mais necessidade de se concentrar nele.

### Obtendo entrada de arquivo de um arquivo zip

Também podemos colocar os arquivos de entrada em um arquivo zip e considerá -lo um diretório de entrada. Nesse caso, devemos prosseguir da seguinte forma:

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-InputZipDirectory.cs" >}}

Primeiro, criamos o fluxo que contém o arquivo zip. Então, depois de criar as opções de conversão, definimos a opção [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/inputworkingdirectory/) para ser uma instância da classe [InputZipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/). O segundo argumento do construtor é o caminho base dentro do arquivo. Se queremos que todo o arquivo seja um diretório de entrada, devemos passar na string vazia. 

## O conceito do terminal de entrada

Agora é hora de lembrar que há também a entrada do terminal. Quanto a este, **Aspose.TeX para .NET** define a interface geral [IInputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/iinputterminal/) com apenas uma propriedade que retorna uma instância de implementação [Textreader](https://docs.microsoft.com/en-us/dotnet/api/system.io.textreader). As implementações desde que são discutidas abaixo.

### Obtendo a entrada terminal do console

Para fazer isso, precisamos definir a opção [Terminalin](https://reference.aspose.com/tex/net/aspose.tex/texoptions/terminalin/) para ser uma instância da classe [inputConsoleterminal](https://reference.aspose.com/tex/net/aspose.tex.io/inputconsoleterminal/).

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-InputConsoleTerminal.cs" >}}

Mas, para dizer a verdade, esse é o valor padrão da opção, portanto, não há necessidade real de especificá -la. Devido a esse fato e, desde que não haja outras implementações, esta seção serve apenas para fins de demonstração.

Teoricamente, se tivermos um arquivo tex interativo (ou script) com comportamento previsível, podemos querer implementar uma versão do terminal de entrada que contenha um script complementar para responder às solicitações do mecanismo Tex. Experimente sua mão quando tiver tempo!
