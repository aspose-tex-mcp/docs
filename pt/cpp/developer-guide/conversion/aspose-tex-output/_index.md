---
translation: true
template: /templates/_template-cpp.md
title: Interface de saída do Aspose.TeX | C ++
linktitle: Interface de saída do Aspose.TeX
weight: 16
url: /cpp/aspose-tex-output/
description: Funcionalidade de conversão do Aspose.TeX Solução da API para C ++ com TEX, pois um formato de saída é explicado aqui com os exemplos de código.
lastmod: "2025-06-16"
---

{{<section overview>}}

Consulte **Aspose.TeX para C ++** [Referência da API](https://reference.aspose.com/tex/cpp/namespace/aspose.te_x.i_o) para obter definições formais de implementação de E/S.

## O conceito de diretório de saída

Como as primitivas de E/S do idioma TEX só podem lidar com nomes de arquivos, Aspose.TeX define um diretório como um mapeamento entre nomes e volumes de dados. Os ma tetos de dados devem ser arquivos, fluxos, matrizes ou qualquer outra coisa. A API nos permite especificar os diretórios de trabalho de entrada e saída separadamente. Ele fornece a interface Geral [ioutputworkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputworkingdirectory) para a saída, que o usuário pode implementar para seus próprios propósitos. Ele também fornece suas próprias implementações, que serão discutidas abaixo. A interface estende [iInputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputworkingdirectory), pois o mecanismo pode primeiro criar e escrever um arquivo e depois leia -o novamente. O próprio método da interface [getOutputFile()](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputworkingdirectory/getoutputfile) retorna o fluxo para gravar, em oposição ao fluxo para ler devolvido por [getFile()](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputworkingdirectory/getfile).

### Escrevendo a saída do arquivo no sistema de arquivos de disco

Como mencionamos [acima](/tex/{{lang.url-fragment}}cpp/latex-to-image/), o valor mais comum para o [OputDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory) provavelmente seria uma instância da classe [outputFilesystemDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputfilesystemdirectory).

Aqui está como nós o definiríamos:

```C++
// Create conversion options instance.
...
// Specify a file system working directory for the output.
options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));

```
Este caso de uso é bastante simples, então não há mais necessidade de se concentrar nele.

### Escrevendo a saída do arquivo em um arquivo zip

Também podemos criar um arquivo (ou fluxo) e deixar o mecanismo TEX usá -lo como um arquivo zip para armazenar os arquivos de saída. Aqui está:

```C++
    // Open the stream for the ZIP archive that will serve as the output working directory.
    System::SharedPtr<System::IO::Stream> outZipStream = System::IO::File::Open(System::IO::Path::Combine(RunExamples::OutputDirectory, u"zip-pdf-out.zip"), System::IO::FileMode::Create);

    // Create conversion options instance.
    ...
    // Specify a ZIP archive working directory for the output.
    options->set_OutputWorkingDirectory(System::MakeObject<OutputZipDirectory>(outZipStream));
```

Primeiro, criamos um fluxo de saída para o arquivo zip. Então, depois de criar as opções de conversão, definimos a opção [OutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory) para ser uma instância da classe [outputzipDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputzipdirectory).

## O conceito do terminal de saída

Há outra parte importante da saída-a saída do terminal. Quanto a este, **Aspose.TeX para C ++** Define a interface Geral [ioutputMerminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputterminal) com apenas uma propriedade que retorna uma instância de implementação [textwriter](https://reference.aspose.com/tex/cpp/system.io/textwriter). As implementações desde que são discutidas abaixo.

### Escrevendo saída do terminal para o console

Para fazer isso, precisamos definir a opção [Terminalout](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_terminalout) para ser uma instância da classe [outputConsoleterminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputconsoleterminal).

```C++
// Create conversion options instance.
...
// Specify the console as the output terminal.
options->set_TerminalOut(System::MakeObject<OutputConsoleTerminal>()); // Default. No need to specify.

```

Novamente, esse é o valor padrão da opção; portanto, não há necessidade real de especificá -lo. Devido a isso, esta seção serve apenas fins de demonstração.

### Escrevendo a saída do terminal em um arquivo

Ao contrário do terminal de entrada, **Aspose.TeX para C ++** fornece uma implementação do [ioutputMerminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputterminal), que nos permite gravar a saída do terminal em um arquivo em algum diretório de saída.

```C++
// Create conversion options instance.
...
// Specify that the terminal output must be written to a file in the output working directory.
// The file name is <job_name>.trm.
options->set_TerminalOut(System::MakeObject<OutputFileTerminal>(options->get_OutputWorkingDirectory()));

```
Aqui, pedimos ao mecanismo Tex que escreva a saída do terminal no arquivo com o nome [<Job_Name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) .TRM, que será armazenado no mesmo diretório de saída que especificamos para o restante da saída. Mas isso não é necessário. Podemos também passar em qualquer outra instância de qualquer implementação do [ioutputMerminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputterminal) para o construtor.