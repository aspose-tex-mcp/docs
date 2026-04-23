---
translation: true
template: /templates/_template-net.md
title: Interface de saída do Aspose.TeX | .NET
linktitle: Interface de saída do Aspose.TeX
weight: 16
url: /net/aspose-tex-output/
description: A funcionalidade de conversão da solução API Aspose.TeX para .NET com TeX como formato de saída é explicada aqui com exemplos de código.
keywords: aspose tex output, .net tex, output directory, zip output, output console, output terminal, tex options, outputfiledirectory, outputzipdirectory, tex conversion
lastmod: "2026-04-22"
---

{{<section overview>}}

Consulte **Aspose.TeX para .NET** [Referência da API](https://reference.aspose.com/tex/net/aspose.tex.io/) para obter definições formais de implementação de E/S.

## O conceito de diretório de saída

Como as primitivas de E/S do idioma TeX só podem lidar com nomes de arquivos, Aspose.TeX define um diretório como um mapeamento entre nomes e volumes de dados. Os volumes de dados devem ser arquivos, fluxos, matrizes ou qualquer outra coisa. A API nos permite especificar os diretórios de trabalho de entrada e saída separadamente. Ele fornece a interface geral [IOutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputworkingdirectory/) para a saída, que o usuário pode implementar para seus próprios propósitos. Ele também fornece suas próprias implementações, que serão discutidas abaixo. A interface estende [IInputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/), pois o mecanismo pode primeiro criar e escrever um arquivo e depois lê-lo novamente. O próprio método da interface [GetOutputFile()](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputworkingdirectory/getoutputfile/) retorna o fluxo para gravar, em oposição ao fluxo para ler devolvido por [GetFile()](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/getfile/).

### Escrevendo a saída do arquivo no sistema de arquivos de disco

Como mencionamos [acima](/tex/{{lang.url-fragment}}net/latex-to-image/), o valor mais comum para o [OutputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) provavelmente seria uma instância da classe [OutputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/).

Aqui está como nós o definiríamos:

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-OutputFileSystemDirectory.cs" >}}

Este caso de uso é bastante simples, então não há mais necessidade de se concentrar nele.

### Escrevendo a saída do arquivo em um arquivo zip

Também podemos criar um arquivo (ou fluxo) e deixar o mecanismo TeX usá-lo como um arquivo ZIP para armazenar os arquivos de saída. Aqui está:

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-OutputZipDirectory.cs" >}}

Primeiro, criamos um fluxo de saída para o arquivo ZIP. Então, após criar as opções de conversão, definimos a opção [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) para ser uma instância da classe [OutputZipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/).

## O conceito do terminal de saída

Há outra parte importante da saída --- a saída do terminal. Quanto a este, **Aspose.TeX para .NET** define a interface geral [IOutputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/) com apenas uma propriedade que retorna uma instância de implementação [TextWriter](https://docs.microsoft.com/en-us/dotnet/api/system.io.textwriter). As implementações fornecidas são discutidas abaixo.

### Escrevendo saída do terminal para o console

Para fazer isso, precisamos definir a opção [TerminalOut](https://reference.aspose.com/tex/net/aspose.tex/texoptions/terminalout/) para ser uma instância da classe [OutputConsoleTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/).

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-OutputConsoleTerminal.cs" >}}

Novamente, esse é o valor padrão da opção; portanto, não há necessidade real de especificá-lo. Devido a isso, esta seção serve apenas fins de demonstração.

### Escrevendo a saída do terminal em um arquivo

Ao contrário do terminal de entrada, **Aspose.TeX para .NET** fornece uma implementação do [IOutputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/), que nos permite gravar a saída do terminal em um arquivo em algum diretório de saída.

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-OutputFileTerminal.cs" >}} 

Aqui, pedimos ao mecanismo TeX que escreva a saída do terminal no arquivo com o nome [<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trm, que será armazenado no mesmo diretório de saída que especificamos para o restante da saída. Mas isso não é necessário. Podemos também passar em qualquer outra instância de qualquer implementação do [IOutputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/) para o construtor.
