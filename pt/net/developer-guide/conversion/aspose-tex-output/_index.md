---
translation: true
template: /templates/_template-net.md
title: Interface de saída do Aspose.TeX | .NET
linktitle: Interface de saída do Aspose.TeX
weight: 16
url: /net/aspose-tex-output/
description: Funcionalidade de conversão do Aspose.TeX Solução da API para .NET com TEX, pois um formato de saída é explicado aqui com os exemplos de código.
lastmod: "2025-06-16"
---

{{<section overview>}}

Consulte **Aspose.TeX para .NET** [Referência da API](https://reference.aspose.com/tex/net/aspose.tex.io/) para obter definições formais de implementação de E/S.

## O conceito de diretório de saída

Como as primitivas de E/S do idioma TEX só podem lidar com nomes de arquivos, Aspose.TeX define um diretório como um mapeamento entre nomes e volumes de dados. Os ma tetos de dados devem ser arquivos, fluxos, matrizes ou qualquer outra coisa. A API nos permite especificar os diretórios de trabalho de entrada e saída separadamente. Ele fornece a interface Geral [ioutputworkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputworkingdirectory/) para a saída, que o usuário pode implementar para seus próprios propósitos. Ele também fornece suas próprias implementações, que serão discutidas abaixo. A interface estende [iInputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/), pois o mecanismo pode primeiro criar e escrever um arquivo e depois leia -o novamente. O próprio método da interface [getOutputFile()](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputworkingdirectory/getoutputfile/) retorna o fluxo para gravar, em oposição ao fluxo para ler devolvido por [getFile()](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/getfile/).

### Escrevendo a saída do arquivo no sistema de arquivos de disco

Como mencionamos [acima](/tex/{{lang.url-fragment}}net/latex-to-png/), o valor mais comum para o [OputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) provavelmente seria uma instância da classe [outputFilesystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/).

Aqui está como nós o definiríamos:

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-OutputFileSystemDirectory.cs" >}}

Este caso de uso é bastante simples, então não há mais necessidade de se concentrar nele.

### Escrevendo a saída do arquivo em um arquivo zip

Também podemos criar um arquivo (ou fluxo) e deixar o mecanismo TEX usá -lo como um arquivo zip para armazenar os arquivos de saída. Aqui está:

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-OutputZipDirectory.cs" >}}

Primeiro, criamos um fluxo de saída para o arquivo zip. Então, depois de criar as opções de conversão, definimos a opção [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) para ser uma instância da classe [outputzipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/).

## O conceito do terminal de saída

Há outra parte importante da saída-a saída do terminal. Quanto a este, **Aspose.TeX para .NET** define a interface Geral [ioutputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/) com apenas uma propriedade que retorna uma instância de implementação [textwriter](https://docs.microsoft.com/en-us/dotnet/api/system.io.textwriter). As implementações desde que são discutidas abaixo.

### Escrevendo saída do terminal para o console

Para fazer isso, precisamos definir a opção [Terminalout](https://reference.aspose.com/tex/net/aspose.tex/texoptions/terminalout/) para ser uma instância da classe [outputConsoleterminal](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/).

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-OutputConsoleTerminal.cs" >}}

Novamente, esse é o valor padrão da opção; portanto, não há necessidade real de especificá -lo. Devido a isso, esta seção serve apenas fins de demonstração.

### Escrevendo a saída do terminal em um arquivo

Ao contrário do terminal de entrada, **Aspose.TeX para .NET** fornece uma implementação do [ioutputMerminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/), que nos permite gravar a saída do terminal em um arquivo em algum diretório de saída.

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-OutputFileTerminal.cs" >}} 

Aqui, pedimos ao mecanismo Tex que escreva a saída do terminal no arquivo com o nome [<Job_Name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) .TRM, que será armazenado no mesmo diretório de saída que especificamos para o restante da saída. Mas isso não é necessário. Podemos também passar em qualquer outra instância de qualquer implementação do [ioutputMerminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/) para o construtor.