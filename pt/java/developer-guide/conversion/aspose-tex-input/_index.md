---
translation: true
template: /templates/_template-java.md
title: Interface de entrada do Aspose.TeX | Java
linktitle: Interface de entrada do Aspose.TeX
weight: 15
url: /java/aspose-tex-input/
description: Funcionalidade de conversão do Aspose.TeX Solução da API para Java com Tex, pois um formato de entrada é explicado aqui com os exemplos de código.
lastmod: "2026-04-21"
---

{{<section overview>}}

Consulte **Aspose.TeX para java** [Referência da API](https://reference.aspose.com/tex/java/com.aspose.tex/) para obter definições formais de implementação de E/S.

## O conceito do diretório de entrada

Como as primitivas de E/S do idioma TEX só podem lidar com nomes de arquivos, **aspose.tex para java** define um diretório como um mapeamento entre nomes e volumes de dados. Os ma tetos de dados devem ser arquivos, fluxos, matrizes ou qualquer outra coisa. A API nos permite especificar os diretórios de trabalho de entrada e saída separadamente. Ele fornece a interface Geral [iinputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/), que o usuário pode implementar para seus próprios fins. Ele também fornece suas próprias implementações, que serão discutidas abaixo. A interface define o método [getfile()](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-), que retorna o fluxo de dados e determina o nome completo do arquivo, enquanto toma um nome, hipoteticamente diferente, como o primeiro argumento, que, de fato, é a chave de mapeamento.

### Obtendo entrada de arquivo do sistema de arquivos de disco

Aqui está como faríamos isso:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-InputFileSystemDirectory.java" >}}

Este caso de uso é bastante simples, por isso não vamos nos debruçar por um longo tempo.

### Obtendo entrada de arquivo de um arquivo zip

Também podemos colocar os arquivos de entrada em um arquivo zip e considerá -lo um diretório de entrada. Nesse caso, devemos prosseguir da seguinte forma:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-InputZipDirectory.java" >}}

Primeiro, criamos o fluxo que contém o arquivo zip. Então, depois de criar as opções de conversão, definimos a opção [InputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getInputWorkingDirectory--) para ser uma instância da classe [InputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputzipdirectory/). O segundo argumento do construtor é o caminho base dentro do arquivo. Se queremos que todo o arquivo seja um diretório de entrada, devemos passar na string vazia. 

## O conceito do terminal de entrada

Agora, lembre -se de que há também a entrada do terminal. Quanto a este, **Aspose.TeX para Java** define a interface geral [IInputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/iinputterminal/) como tendo dois métodos. Um deles retorna uma instância [BufferedReader](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedReader.html). Outro método retorna um [inputStream](https://docs.oracle.com/javase/6/docs/api/java/io/InputStream.html) como o fluxo subjacente. As implementações fornecidas da interface são discutidas abaixo.

### Obtendo a entrada terminal do console

Para fazer isso, precisamos definir a opção [Terminalin](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getTerminalIn--) para ser uma instância da classe [inputConsoleterminal](https://reference.aspose.com/tex/java/com.aspose.tex/inputconsoleterminal/).

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-InputConsoleTerminal.java" >}}

Mas, para dizer a verdade, esse é o valor padrão da opção, portanto, não há necessidade real de especificá -la. Devido a esse fato e, desde que não haja outras implementações, esta seção serve apenas para fins de demonstração.

Teoricamente, se tivermos um arquivo tex interativo (ou script) com comportamento previsível, podemos querer implementar uma versão do terminal de entrada que contenha um script complementar para responder às solicitações do mecanismo Tex. Experimente sua mão quando tiver tempo!