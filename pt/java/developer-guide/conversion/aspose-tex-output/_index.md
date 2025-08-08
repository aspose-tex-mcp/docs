---
translation: true
template: /templates/_template-java.md
title: Interface de saída do Aspose.TeX | Java
linktitle: Interface de saída do Aspose.TeX
weight: 16
url: /java/aspose-tex-output/
description: Funcionalidade de conversão do Aspose.TeX Solução da API para Java com Tex, pois um formato de saída é explicado aqui com os exemplos de código.
lastmod: "2025-06-16"
---

{{<section overview>}}

Consulte **Aspose.TeX para java** [Referência da API](https://reference.aspose.com/tex/java/com.aspose.tex/package-frame) para obter definições formais de implementação de E/S.

## O conceito de diretório de saída

Como as primitivas de E/S do idioma TEX só podem lidar com nomes de arquivos, Aspose.TeX define um diretório como um mapeamento entre nomes e volumes de dados. Os ma tetos de dados devem ser arquivos, fluxos, matrizes ou qualquer outra coisa. A API nos permite especificar os diretórios de trabalho de entrada e saída separadamente. Ele fornece a interface Geral [ioutputworkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputWorkingDirectory) para a saída, que o usuário pode implementar para seus próprios propósitos. Ele também fornece suas próprias implementações, que serão discutidas abaixo. A interface estende [iInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory), pois o mecanismo pode primeiro criar e escrever um arquivo e depois leia -o novamente. O próprio método da interface [getouputfile()](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputWorkingDirectory#getOutputFile-java.lang.String-java.lang.String:A-) retorna o fluxo para gravar, em oposição ao fluxo para ler retornado por [getfile()](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-).

### Escrevendo a saída do arquivo no sistema de arquivos de disco

Como mencionamos [acima](/tex/{{lang.url-fragment}}/java/conversion/), o valor mais comum para o [outputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--) provavelmente seria uma instância da classe [outputFilesystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/OutputFileSystemDirectory).

Aqui está como nós o definiríamos:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-OutputFileSystemDirectory.java" >}}

Este caso de uso é bastante simples, por isso não vamos nos debruçar por um longo tempo.

### Escrevendo a saída do arquivo em um arquivo zip

Também podemos criar um arquivo (ou fluxo) e deixar o mecanismo TEX usá -lo como um arquivo zip para armazenar os arquivos de saída. Aqui está:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-OutputZipDirectory.java" >}}

Primeiro, criamos um fluxo de saída para o arquivo zip. Então, depois de criar as opções de conversão, definimos a opção [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--) para ser uma instância da classe [outputzipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/OutputZipDirectory).

## O conceito do terminal de saída

Há outra parte importante da saída-a saída do terminal. Quanto a este, **Aspose.TeX para java** define a interface Geral [ioutputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputTerminal) como tendo dois métodos. Um deles retorna uma instância [BufferWriter](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedWriter.html). Outro retorna uma instância [outputStream](https://docs.oracle.com/javase/6/docs/api/java/io/OutputStream.html) como o fluxo subjacente. As implementações fornecidas da interface são discutidas abaixo.

### Escrevendo saída do terminal para o console

Para fazer isso, precisamos definir a opção [Terminalout](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getTerminalOut--) para ser uma instância da classe [outputConsoleterminal](https://reference.aspose.com/tex/java/com.aspose.tex/OutputConsoleTerminal).

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-OutputConsoleTerminal.java" >}}

Novamente, esse é o valor padrão da opção; portanto, não há necessidade real de especificá -lo. Devido a isso, esta seção serve apenas fins de demonstração.

### Escrevendo a saída do terminal em um arquivo

Ao contrário do terminal de entrada, **Aspose.TeX para Java** fornece uma implementação do [ioutputMerminal](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputTerminal), que nos permite gravar a saída do terminal em um arquivo em algum diretório de saída.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-OutputFileTerminal.java" >}}  

Aqui, pedimos ao mecanismo Tex que escreva a saída do terminal no arquivo com o nome [<Cob_Name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) .TRM, que será armazenado no mesmo diretório de saída que especificamos para o restante da saída. Mas isso não é necessário. Podemos também passar em qualquer outra instância de qualquer implementação do [ioutputMerminal](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputTerminal) para o construtor.