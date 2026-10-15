---
translation: true
template: /templates/_template-java.md
title: Interface de saída do Aspose.TeX | Java
linktitle: Interface de saída do Aspose.TeX
weight: 16
url: /java/aspose-tex-output/
description: Funcionalidade de conversão do Aspose.TeX Solução da API para Java com Tex, pois um formato de saída é explicado aqui com os exemplos de código.
lastmod: "2026-04-21"
---

{{<section overview>}}

Consulte **Aspose.TeX para java** [Referência da API](https://reference.aspose.com/tex/java/com.aspose.tex/) para obter definições formais de implementação de E/S.

Os exemplos de sistema de arquivos, ZIP e terminal compõem `hello-world.tex` em XPS. Defina `inputDirectory` como uma pasta com o arquivo TeX e `outputDirectory` como uma pasta de saída existente. Para saída ZIP, `outputZip` deve ser um `java.nio.file.Path` em uma pasta existente. Importe as classes Aspose.TeX usadas no exemplo escolhido, `com.aspose.tex.rendering.XpsDevice` e as classes necessárias de `java.io` e `java.nio.file`. O método chamador deve tratar ou declarar as exceções. Aplique uma licença conforme o [guia de licenciamento](/tex/{{lang.url-fragment}}java/licensing/) para evitar as restrições de avaliação.

## O conceito de diretório de saída

Como as primitivas de E/S do idioma TEX só podem lidar com nomes de arquivos, Aspose.TeX define um diretório como um mapeamento entre nomes e volumes de dados. Os ma tetos de dados devem ser arquivos, fluxos, matrizes ou qualquer outra coisa. A API nos permite especificar os diretórios de trabalho de entrada e saída separadamente. Ele fornece a interface Geral [ioutputworkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/) para a saída, que o usuário pode implementar para seus próprios propósitos. Ele também fornece suas próprias implementações, que serão discutidas abaixo. A interface estende [iInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/), pois o mecanismo pode primeiro criar e escrever um arquivo e depois leia -o novamente. O próprio método da interface [getouputfile()](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/#getOutputFile-java.lang.String-java.lang.String:A-) retorna o fluxo para gravar, em oposição ao fluxo para ler retornado por [getfile()](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-).

### Escrevendo a saída do arquivo no sistema de arquivos de disco

Como mencionamos [acima](/tex/{{lang.url-fragment}}/java/conversion/), o valor mais comum para o [outputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--) provavelmente seria uma instância da classe [outputFilesystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputfilesystemdirectory/).

Aqui está como nós o definiríamos:

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputFileSystemDirectory.java" >}}

Este caso de uso é bastante simples, por isso não vamos nos debruçar por um longo tempo.

### Escrevendo a saída do arquivo em um arquivo zip

Também podemos criar um arquivo (ou fluxo) e deixar o mecanismo TEX usá -lo como um arquivo zip para armazenar os arquivos de saída. Aqui está:

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputZipDirectory.java" >}}

Primeiro, criamos um fluxo de saída para o arquivo zip. Então, depois de criar as opções de conversão, definimos a opção [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--) para ser uma instância da classe [outputzipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputzipdirectory/). O exemplo armazena `hello-world.xps` e `hello-world.log` no arquivo. Após o trabalho, chame `finish()` no diretório de saída antes de fechar o fluxo subjacente. Os exemplos mantêm seus fluxos e diretórios de trabalho abertos até o término do trabalho e depois os fecham.

## O conceito do terminal de saída

Há outra parte importante da saída-a saída do terminal. Quanto a este, **Aspose.TeX para java** define a interface Geral [ioutputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputterminal/) como tendo dois métodos. Um deles retorna uma instância [BufferWriter](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedWriter.html). Outro retorna uma instância [outputStream](https://docs.oracle.com/javase/6/docs/api/java/io/OutputStream.html) como o fluxo subjacente. As implementações fornecidas da interface são discutidas abaixo.

### Escrevendo saída do terminal para o console

Para fazer isso, precisamos definir a opção [Terminalout](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getTerminalOut--) para ser uma instância da classe [outputConsoleterminal](https://reference.aspose.com/tex/java/com.aspose.tex/outputconsoleterminal/).

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputConsoleTerminal.java" >}}

`OutputConsoleTerminal` é o valor padrão desta opção. O exemplo o seleciona explicitamente e escreve a saída do terminal no console durante a conversão. Os quatro exemplos são executados sem interação; os exemplos de sistema de arquivos e ZIP capturam a saída do terminal na memória.

### Escrevendo a saída do terminal em um arquivo

Ao contrário do terminal de entrada, **Aspose.TeX para Java** fornece uma implementação do [ioutputMerminal](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputterminal/), que nos permite gravar a saída do terminal em um arquivo em algum diretório de saída.

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputFileTerminal.java" >}}

Defina o diretório de trabalho de saída antes de criar `OutputFileTerminal`. Ele escreve a saída do terminal em [<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trm, aqui `hello-world.trm`, nesse diretório. Esse arquivo do terminal é separado da transcrição TeX `hello-world.log`. Para escrever a saída do terminal em outro local, passe ao construtor outra implementação de [IOutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/).