---
translation: true
template: /templates/_template-net.md
title: LaTeX para XPS | .NET
linktitle: Látex para XPS
weight: 12
url: /net/latex-to-xps/
description: Funcionalidade de conversão do Aspose. Aqui estão alguns exemplos de código.
lastmod: "2026-11-02"
---

{{<section overview>}}


Outro formato de destino é [**xps**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). Um arquivo **XPS** é fisicamente um pacote ZIP que contém conteúdo paginado de um documento, juntamente com os metadados necessários para a exibição adequada por visualizadores específicos (como o Windows XPS Viewer) e a impressão. Todos os dados em um pacote são representados por arquivos. Alguns deles são binários e contêm recursos como imagens, fontes e perfis da ICC. Outros são arquivos XML em vários esquemas específicos. Este último inclui arquivos que contêm os dados do documento em si. Os dados do documento consistem em um conjunto de arquivos - cada arquivo contém dados para uma página individual do documento. Esses arquivos consistem em um elemento de página única e uma árvore de elementos filhos - *Canvas*, *Paths* e *Glyphs*. *Canvas*é um elemento de agrupamento que pode conter outras*Canvas*, *Paths* e *Glyphs*. Serve para controlar a aparência de todos os elementos filhos como um grupo. *Os elementos do caminho* são usados ​​para definir os caminhos gráficos vetoriais. E *Glyphs* elementos são usados ​​para definir conteúdo textual. Todos os três elementos têm propriedades para definir vários aspectos da aparência.

Existe a biblioteca [**Aspose.page**](https://products.aspose.com/page/) que fornece uma API para manipular documentos XPS, além de convertê -los em formatos de imagem PDF e raster.

## Como converter LaTeX em xps

A conversão de LaTeX para XPS é tão simples quanto a [conversão em formatos de imagem raster](/tex/{{lang.url-fragment}}net/latex-to-image/), exceto que as [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) devem ser definidas como uma instância da classe [XpsSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpssaveoptions/) (por padrão ou explicitamente) e o dispositivo deve ser alterado para uma instância do [XpsDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/).

**Exemplo de conversão mais simples**

O exemplo abaixo mostra como converter um arquivo LaTeX para XPS em poucos passos:

1. Crie `TeXOptions` para o formato ObjectLaTeX com `TeXOptions.ConsoleAppOptions(TeXConfig.ObjectLaTeX)`.
2. Especifique o diretório de trabalho de saída, por exemplo, um `OutputFileSystemDirectory`.
3. Defina `SaveOptions` como uma instância de `XpsSaveOptions`.
4. Execute um `TeXJob` para o arquivo de origem `.tex` com um `XpsDevice`. O arquivo XPS é gravado no diretório de trabalho de saída.

Este código demonstra a forma mais direta de produzir um arquivo XPS a partir do LaTeX.

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToXPS-Simplest.cs" >}}

### Uma maneira alternativa de escrever o arquivo XPS de saída principal

Há outro construtor da classe [XpsDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/xpsdevice/), que nos permite obter o arquivo XPS resultante de uma maneira alternativa.

**Exemplo de conversão alternativo**

Este excerto demonstra a utilização do construtor `XpsDevice` que aceita um `Stream`. Os passos são:

1. Abra o fluxo no qual o documento XPS será gravado (aqui, um fluxo de arquivo; um `MemoryStream` funciona da mesma forma).
2. Crie `TeXOptions`, especifique o diretório de trabalho de saída e defina `SaveOptions` como uma instância de `XpsSaveOptions`, como no exemplo anterior.
3. Execute um `TeXJob` com um `XpsDevice` criado com o fluxo. O documento XPS é gravado no fluxo; os outros arquivos de saída, como a transcrição, continuam sendo gravados no diretório de trabalho de saída.

Esta abordagem é útil quando você precisa gravar o documento XPS em um fluxo de sua escolha, por exemplo, para mantê-lo na memória ou enviá-lo pela rede.

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToXPS-Alternative.cs" >}}

O efeito é o mesmo que chegamos [aqui](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-the-main-output-pdf-file).

**Você também pode conferir a conversão LATEX-XPS GRATUITA [aplicativo da Web](https://products.aspose.app/tex/conversion/latex-to-xps) construído com base em [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**
