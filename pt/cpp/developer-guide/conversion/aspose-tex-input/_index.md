---
translation: true
template: /templates/_template-cpp.md
title: Interface de entrada do Aspose.TeX | C ++
linktitle: Interface de entrada do Aspose.TeX
weight: 15
url: /cpp/aspose-tex-input/
description: Funcionalidade de conversão do Aspose.TeX Solução da API para C ++ com TEX, pois um formato de entrada é explicado aqui com os exemplos de código.
lastmod: "2025-06-16"
---

{{<section overview>}}

Consulte **Aspose.TeX para C ++** [Referência da API](https://reference.aspose.com/tex/cpp/namespace/aspose.te_x.i_o) para obter definições formais de implementação de E/S.

## O conceito do diretório de entrada

Como as primitivas de E/S do idioma TEX só podem lidar com nomes de arquivos, **aspose.tex para c ++** define um diretório como um mapeamento entre nomes e volumes de dados. Os ma tetos de dados devem ser arquivos, fluxos, matrizes ou qualquer outra coisa. A API nos permite especificar os diretórios de trabalho de entrada e saída separadamente. Ele fornece a interface Geral [iinputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputworkingdirectory), que o usuário pode implementar para seus próprios fins. Ele também fornece suas próprias implementações, que serão discutidas abaixo. A interface define o método [getfile()](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputworkingdirectory/getfile), que retorna o fluxo de dados e determina o nome completo do arquivo, enquanto toma um nome, hipoteticamente diferente, como o primeiro argumento, que, de fato, é a chave de mapeamento.

### Obtendo entrada de arquivo do sistema de arquivos de disco

Aqui está como faríamos isso:

```C++
// Create conversion options instance.
...
// Specify a file system working directory for input.
options->set_InputWorkingDirectory(System::MakeObject<InputFileSystemDirectory>(RunExamples::InputDirectory));

```

Este caso de uso é bastante simples, então não há mais necessidade de se concentrar nele.

### Obtendo entrada de arquivo de um arquivo zip

Também podemos colocar os arquivos de entrada em um arquivo zip e considerá -lo um diretório de entrada. Nesse caso, devemos prosseguir da seguinte forma:

```C++
    // Open a stream on a ZIP archive that will serve as the input working directory.
    System::SharedPtr<System::IO::Stream> inZipStream = System::IO::File::Open(System::IO::Path::Combine(RunExamples::InputDirectory, u"zip-in.zip"), System::IO::FileMode::Open);

    // Create conversion options instance.
    ...
    // Specify a ZIP archive working directory for input.
    options->set_InputWorkingDirectory(System::MakeObject<InputZipDirectory>(inZipStream, u"in"));
```

Primeiro, criamos o fluxo que contém o arquivo zip. Então, depois de criar as opções de conversão, definimos a opção [InputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_inputworkingdirectory) para ser uma instância da classe [InputZipDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/inputzipdirectory). O segundo argumento do construtor é o caminho base dentro do arquivo. Se queremos que todo o arquivo seja um diretório de entrada, devemos passar na string vazia. 

## O conceito do terminal de entrada

Agora é hora de lembrar que há também a entrada do terminal. Quanto a este, **Aspose.TeX para C ++** Define a interface Geral [IInputTerminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputterminal) com apenas uma propriedade que retorna uma instância de implementação [Textreader](https://reference.aspose.com/tex/cpp/class/system.i_o.text_reader). As implementações desde que são discutidas abaixo.

### Obtendo a entrada terminal do console

Para fazer isso, precisamos definir a opção [Terminalin](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_terminalin) para ser uma instância da classe [inputConsoleterminal](https://reference.aspose.com/tex/cpp/class/aspose.te_x.i_o.input_console_terminal).

```C++
// Create conversion options instance.
...
// Specify the console as the input terminal.
options->set_TerminalIn(System::MakeObject<InputConsoleTerminal>()); // Default. Not necessary to specify.

```

Mas, para dizer a verdade, esse é o valor padrão da opção, portanto, não há necessidade real de especificá -la. :-) Devido a esse fato e, desde que não haja outras implementações, esta seção serve apenas fins de demonstração.

Teoricamente, se tivermos um arquivo tex interativo (ou script) com comportamento previsível, podemos querer implementar uma versão do terminal de entrada que contenha um script complementar para responder às solicitações do mecanismo Tex. Experimente sua mão quando tiver tempo!