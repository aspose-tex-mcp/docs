---
translation: true
template: /templates/_template-cpp.md
title: Outros formatos de saída de conversão Tex | C++
linktitle: Outros formatos de Tex
weight: 18
url: /cpp/other-tex-formats/
description: A funcionalidade de conversão do Aspose.TeX API Solution for C ++ permite a conversão de arquivos de LaTeX e seus próprios arquivos tex personalizados. Aqui estão alguns exemplos de código.
lastmod: "2025-06-16"
---

{{<section overview>}}

É altamente improvável que você queira converter um arquivo tex escrito em qualquer outro formato que não seja o LATEX. Mas isso é possível se você estiver estudando o idioma tex e/ou internos por algum motivo. De qualquer forma, **Aspose.TeX para C ++** permite converter arquivos gravados no formato PLAIN TEX. Ele também permite criar formatos personalizados e documentos de tiponete projetados nesses formatos.

Começaremos com a criação de um formato personalizado.

## Criando um formato personalizado

Lembre -se de que o arquivo de formato é um depósito binário do estado interno do mecanismo Tex.

```C++
// Create typesetting options for no format on ObjectTeX engine extension.
System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::get_ObjectIniTeX());
// Specify a file system working directory for input.
options->set_InputWorkingDirectory(System::MakeObject<InputFileSystemDirectory>(RunExamples::InputDirectory));
// Specify a file system working directory for output.
options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
    
// Run format creation.
Aspose::TeX::TeXJob::CreateFormat(u"customtex", options);
    
// For further output to look write.
options->get_TerminalOut()->get_Writer()->WriteLine();
```
Como você pode ver, o código é semelhante ao código para converter um arquivo tex. Mas existem algumas diferenças.

Primeiro, aqui usamos a configuração do trabalho [texconfig.objectinitex](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_config#aefa7bbdf2ed28d6499f2dc5d5ad2ca3e). Esta é uma configuração especial que deixa o estado do motor "virgem", ou seja, os parâmetros internos têm seus valores padrão e o conjunto de sequências de controle coincide com o conjunto de primitivas. Em nosso exemplo, o conjunto de primitivas é estendido no sentido mencionado [aqui](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex).

Em seguida, configuramos os diretórios de trabalho de entrada e saída, como de costume. O diretório de trabalho de entrada precisa conter o arquivo de origem do formato principal e todas as suas dependências.

E a segunda diferença importante é a maneira como executamos o trabalho. Desta vez, usamos o método estático [createFormat ()](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/), que, juntamente com as opções, pega o nome do arquivo de origem principal, que deve ser o mesmo que o nome do formato.

## Tipando um arquivo tex em seu formato personalizado

Agora que temos nosso próprio formato Tex, queremos digitar um arquivo tex escrito neste formato. Aqui está o código:

```C++
// Create typesetting options for a custom format on ObjectTeX engine extension.
System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::ObjectTeX(formatProvider));
options->set_JobName(u"typeset-with-custom-format");
// Specify the input working directory.
options->set_InputWorkingDirectory(wd);
// Specify a file system working directory for output.
options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
            
// Run typesetting.
System::MakeObject<Aspose::TeX::TeXJob>(System::MakeObject<System::IO::MemoryStream>(System::Text::Encoding::get_ASCII()->GetBytes(u"Congratulations! You have successfully typeset this text with your own TeX format!\\end")), System::MakeObject<XpsDevice>(), options)->Run();
            
// For further output to look write.
options->get_TerminalOut()->get_Writer()->WriteLine();
```
Obviamente, temos que especificar o formato de alguma forma. Primeiro de tudo, precisamos criar uma instância da classe [FormatProvider](https://reference.aspose.com/tex/cpp/class/aspose.te_x.resource_providers.format_provider). Em seguida, no construtor de opções, usamos a configuração [TeXConfig.ObjectIniTeX](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_config#aefa7bbdf2ed28d6499f2dc5d5ad2ca3e), que toma nosso provedor de formato como um argumento e carrega o formato no topo do estado "virgem" do motor.

O restante do código deve ser familiar para você. Ele usa os recursos discutidos anteriormente neste [guia](/tex/{{lang.url-fragment}}cpp/conversion/).

## Tipando um arquivo tex no formato PLAin Tex

Se jogarmos fora o provedor de formato do código que acabamos de demonstrar, o motor carregará o formato padrão, que é [objeto tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/) em seu quarto sentido. Assim, se você tiver um arquivo tex escrito no formato PLAIN TEX, dessa maneira poderá convertê -lo em qualquer formato de destino suportado.