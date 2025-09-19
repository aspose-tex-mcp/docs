---
translation: true
template: /templates/_template-cpp.md
title: Látex para xps | C++
linktitle: Látex para XPS
weight: 12
url: /cpp/latex-to-xps/
description: Funcionalidade de conversão da solução API Aspose.TeX para C ++ Vamos converter arquivos de LaTeX no formato XPS. Aqui estão alguns exemplos de código.
lastmod: "2025-06-16"
---

{{<section overview>}}

Outro formato de destino suportado por **Aspose.TeX** é [**xps**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). Um arquivo **xps** é na verdade um pacote zip que contém conteúdo paginado de um documento, juntamente com os metadados necessários para a exibição adequada por visualizadores específicos (como o Windows XPS Viewer) e a impressão. Todos os dados em um pacote são representados por arquivos. Alguns deles são binários e contêm recursos como imagens, fontes e perfis da ICC. Outros são arquivos XML em vários esquemas específicos. Este último inclui arquivos que contêm os dados do documento em si. Os dados do documento consistem em um conjunto de arquivos - cada arquivo contém dados para uma página individual do documento. Esses arquivos consistem em um elemento de página única e uma árvore de elementos filhos - *Canvas*, *Paths* e *Glyphs*. *Canvas* é um elemento de agrupamento que pode conter outras *Canvas*, *Paths* e *Glyphs*. Sua missão é controlar a aparência de todos os elementos infantis como um grupo. * Os elementos do caminho* são usados ​​para definir os caminhos gráficos vetoriais. E *Glyphs* elementos são usados ​​para definir conteúdo textual. Todos os três elementos têm propriedades para definir vários aspectos da aparência.

Existe a biblioteca [**Aspose.page**](https://products.aspose.com/page/) que fornece uma API para manipular documentos XPS, além de convertê -los em formatos de imagem PDF e raster.

## Como converter LaTeX em xps

A conversão em XPS é tão simples quanto a [conversão em formatos de imagem raster](/tex/{{lang.url-fragment}}cpp/latex-to-image/), exceto que, além das [SaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_saveoptions), precisamos alterar o dispositivo para uma instância da classe [XPSDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_device).

```C++
...
// Initialize the options for saving in Xps format.
options->set_SaveOptions(System::MakeObject<XpsSaveOptions>());

System::MakeObject<Aspose::TeX::TeXJob>(u"hello-world.ltx", System::MakeObject<XpsDevice>(), options)->Run();
```

### Uma maneira alternativa de escrever o arquivo XPS de saída principal

Há outro construtor da classe [XPSDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_device#aa24d2c38c5d134d90782b27ba090116a), que permite obter o arquivo XPS resultante de uma maneira alternativa.

```C++
    // Create the stream to write the XPS file to.
    {
        System::SharedPtr<System::IO::Stream> xpsStream = System::IO::File::Open(System::IO::Path::Combine(RunExamples::OutputDirectory, u"any-name.xps"), System::IO::FileMode::Create);
        // Clearing resources under 'using' statement
        System::Details::DisposeGuard<1> __dispose_guard_0({ xpsStream});
        // ------------------------------------------
        
        try
        {
            // Create conversion options for Object LaTeX format on Object TeX engine extension.
            System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::get_ObjectLaTeX());
            // Specify the file system working directory for the output.
            options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
            // Initialize the options for saving in XPS format.
            options->set_SaveOptions(System::MakeObject<XpsSaveOptions>());
            // Default value.
            // Run LaTeX to XPS conversion.
            System::MakeObject<TeXJob>(System::IO::Path::Combine(RunExamples::InputDirectory, u"hello-world.ltx"), System::MakeObject<XpsDevice>(xpsStream), options)->Run();
        }
        catch(...)
        {
            __dispose_guard_0.SetCurrentException(std::current_exception());
        }
    }
```

O efeito é o mesmo que chegamos [aqui](/tex/{{lang.url-fragment}}cpp/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file).

**Você também pode conferir a conversão LATEX-XPS gratuita [aplicativo da Web](https://products.aspose.app/tex/conversion/latex-to-xps) construído com base no [Aspose.TeX para .NET](https://products.aspose.com/tex/net/) API. [Aqui](https://products.aspose.com/tex/cpp/) é a página da versão C ++.**