---
translation: true
template: /templates/_template-conversion-cpp.md
title: Látex para imagem | C++
linktitle: Látex para imagem
weight: 10
url: /cpp/latex-to-image/
keywords: Latex para PNG, LATEX PNG, LATEX para imagem, imagem LATEX, LATEX para JPG, LATEX JPG, LATEX JPEG, LATEX TIFF, LATEX BMP
description: Para converter os formatos Tex em imagem usando a solução ASPOLE.TEX API para C ++, aprenda este artigo que descreve como fazer isso e os exemplos de código.
lastmod: 2023-03-23
---

{{<section overview>}}

**Aspose.TeX para C ++** Também nos permite converter arquivos de LaTeX em vários outros formatos de imagem raster.

## Como converter LaTeX para png

Vamos dar uma olhada detalhada no código em C ++, fornecendo a maneira mais simples de converter o LATEX em formato PNG.

{{<app/converter 
  input="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images.input">}}"  
  formats="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images.output">}}"
  title="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images.title">}}"
>}}
{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images">}}
{{</app/converter>}}
        

Portanto, a primeira coisa que precisamos fazer (bem, às vezes não é a primeira) é criar uma instância da classe [Texoptions](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/). O único método estático que faz isso é [ConsoleAppOptions()](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/consoleappoptions/), então não seremos intrigados com o significado de seu nome. O método pega a instância [get_objectLaTeX()](https://reference.aspose.com/tex/cpp/aspose.tex/texconfig/get_objectlatex/) da classe [texconfig](https://reference.aspose.com/tex/cpp/aspose.tex/texconfig/), que é exatamente adequada para converter um [arquivo LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Esta configuração informa ao mecanismo Tex do objeto para carregar o formato de LaTeX do objeto e estar pronto para aceitar o arquivo LATEX. O formato LATEX do Object é na verdade apenas o formato [LATEX](/tex/{{lang.url-fragment}}net/what-is-latex/), exceto que ele usa as primitivas específicas [Object tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) para configurar as métricas da página.

A primeira das opções necessárias é [OutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory/) que define o espaço ou área, onde a saída TEX será gravada. [Aqui](/tex/{{lang.url-fragment}}cpp/aspose-tex-output/) são os detalhes sobre o conceito de diretório de saída em **aspose.tex para c ++**. Neste exemplo, usamos a classe [outputFilesystemDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputfilesystemdirectory/), que nos permite escrever a saída no diretório ou pasta especificada.

A segunda opção é uma instância de classe [saveOptions](https://reference.aspose.com/tex/cpp/aspose.tex.presentation/saveoptions/) que controlará a transformação do [modelo de objeto](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) no formato de destino. Como estamos convertendo o LATEX em PNG, é a instância da classe [pngSaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex.presentation.image/pngsaveoptions/), que nos permite especificar a resolução das imagens de saída.

De seguida, precisamos de criar uma instância da classe [TeXJob](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/). Para converter um ficheiro LaTeX armazenado no sistema de ficheiros, utilizamos [esta](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/texjob/#texjobtexjobsystemstring-systemsharedptrpresentationdevice-systemsharedptrtexoptions-constructor) versão do construtor. Precisamos de especificar o caminho completo para o ficheiro. Caso contrário, o motor irá procurá-lo no directório actual (que é [CurrentDirectory](https://learn.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory?view=net-10.0)) e provavelmente não o encontrará. No entanto, podemos omitir a extensão se o nosso ficheiro tiver a extensão *. tex*. O mecanismo irá anexá-la automaticamente. O segundo argumento do construtor é uma instância da classe [Device](https://reference.aspose.com/tex/cpp/aspose.tex.presentation/device/). Como estamos a converter LaTeX para PNG, trata-se de uma instância da classe [ImageDevice](https://reference.aspose.com/tex/cpp/aspose.tex.presentation.image/imagedevice/) (que é comum a todos os formatos de imagem suportados). Como último argumento, passámos as opções de conversão preparadas recentemente.

Tudo o que resta a fazer agora é [correr](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/#a0bc7f8b329ea1f19cbba84bf2060f6fb) o trabalho.

Independentemente de a execução ter sido bem -sucedida ou não, o primeiro resultado que veremos será a saída do terminal. Em caso de sucesso, parece algo assim:

```text
This is ObjectTeX, Version 3.1415926-1.0 (Aspose.TeX 21.8)
entering extended mode

(<input_directory>\hello-world.ltx
LaTeX2e <2011/06/27>
(article.cls
Document Class: article 2007/10/19 v1.4h Standard LaTeX document class
(size10.clo))
No file hello-world.aux.
[1]
(<output_directory>\hello-world.aux) )
Output written on hello-world.png (1 page).
Transcript written on hello-world.log.
```

Encontraremos outras "frutas" do trabalho do motor na pasta que especificamos como diretório de saída. Esse será o arquivo de transcrição e, ** aqui está!

## Uma maneira alternativa de escrever o (s) arquivo (s) principal (s) de saída da saída

Há outra maneira de obter dados da imagem como uma matriz de matrizes de bytes, cada matriz na segunda dimensão representa dados de imagem para uma página separada.

```C++
    // Create conversion options for Object LaTeX format on Object TeX engine extension.
    System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::get_ObjectLaTeX());
    // Specify the file system working directory for the output.
    options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
    // Initialize the options for saving in PNG format.
    options->set_SaveOptions(System::MakeObject<PngSaveOptions>());
    // Run LaTeX to PNG conversion.
    System::SharedPtr<ImageDevice> device = System::MakeObject<ImageDevice>();
    System::MakeObject<TeXJob>(System::IO::Path::Combine(RunExamples::InputDirectory, u"hello-world.ltx"), device, options)->Run();
    
    // Save pages file by file.
    for (int32_t i = 0; i < device->get_Result()->get_Length(); i++)
    {
        {
            System::SharedPtr<System::IO::Stream> fs = System::IO::File::Open(System::IO::Path::Combine(RunExamples::OutputDirectory, System::String(u"page-") + (i + 1) + u".png"), System::IO::FileMode::Create);
            // Clearing resources under 'using' statement
            System::Details::DisposeGuard<1> __dispose_guard_0({ fs});
            // ------------------------------------------
            
            try
            {
                fs->Write(device->get_Result()[i], 0, device->get_Result()[i]->get_Length());
            }
            catch(...)
            {
                __dispose_guard_0.SetCurrentException(std::current_exception());
            }
        }
    }
```

Os arquivos * "página-n.png" * serão gravados em qualquer caminho que especifique. Ao contrário de [saída em PDF](/tex/{{lang.url-fragment}}cpp/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file), eles duplicarão os arquivos PNG de saída gravados no diretório de saída.

## Sobre opções de entrada

Caso nosso arquivo de entrada principal exija dependências, por exemplo, pacotes, que não estão incluídos no sistema de LaTeX básico e pacotes suportados, devemos definir a opção [requerirInputDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_requiredinputdirectory/) da maneira semelhante a definir a opção [OutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory/) e colocar as dependências nesse diretório. As dependências podem ser organizadas arbitrariamente em subdiretos. Caso tenhamos nossos próprios arquivos a serem incluídos ao longo do processo de composição, digamos arquivos gráficos externos, também devemos definir o [InputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_inputworkingdirectory/) usando o caminho para o local onde esses arquivos são coletados. Também podemos colocar o arquivo de entrada principal em algum lugar dentro do diretório de entrada e especificar o caminho relativo no método `run()` (ou especificar nenhum caminho se o arquivo de entrada principal estiver na raiz). [Aqui](/tex/{{lang.url-fragment}}cpp/aspose-tex-input/) são os detalhes sobre o conceito de diretório de entrada em **aspose.tex para c ++** e fornecidas implementações.

Outras opções de trabalho Tex são discutidas [aqui](/tex/{{lang.url-fragment}}cpp/other-options/).

**Você também pode conferir a conversão LATEX-PNG GRATUITA [aplicativo da Web](https://products.aspose.app/tex/conversion/latex-to-png) construído com base no [Aspose.TeX para .NET](https://products.aspose.com/tex/net/) API. [Aqui](https://products.aspose.com/tex/cpp/) é a página da versão C ++.**

Abaixo, discutimos a conversão de LaTeX para outros formatos de imagem raster suportados. Não vamos entrar em detalhes apenas porque não há realmente detalhes. A única diferença está no tipo de propriedade [SaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_saveoptions/) nas opções de conversão.

## Como converter LaTeX em jpeg

```C++
...
// Initialize the options for saving in JPEG format.
options->set_SaveOptions(System::MakeObject<JpegSaveOptions>());
```

**Você também pode conferir a conversão LATEX-JPEG GRATUITA [aplicativo da web](https://products.aspose.app/tex/conversion/latex-to-jpg) construído com base na API [Aspose.TeX para .NET](https://products.aspose.com/tex/net/). [Aqui](https://products.aspose.com/tex/cpp/) é a página da versão C ++.**

## Como converter LaTeX para TIFF

```C++
...
// Initialize the options for saving in TIFF format.
options->set_SaveOptions(System::MakeObject<TiffSaveOptions>());
```

**Você também pode conferir a conversão LATEX-TIFF GRATUITA [aplicativo da web](https://products.aspose.app/tex/conversion/latex-to-tiff) construído com base na API [Aspose.TeX para .NET](https://products.aspose.com/tex/net/). [Aqui](https://products.aspose.com/tex/cpp/) é a página da versão C ++.**

## Como converter LaTeX para BMP

```C++
...
// Initialize the options for saving in BMP format.
options->set_SaveOptions(System::MakeObject<BmpSaveOptions>());
```

**Você também pode conferir a conversão LATEX-BMP GRATUITA [aplicativo da Web](https://products.aspose.app/tex/conversion/latex-to-bmp) construído com base na API [Aspose.TeX para .NET](https://products.aspose.com/tex/net/). [Aqui](https://products.aspose.com/tex/cpp/) é a página da versão C ++.**