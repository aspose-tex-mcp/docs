---
translation: true
template: /templates/_template-net.md
title: Látex para xps | .NET
linktitle: Látex para XPS
weight: 12
url: /net/latex-to-xps/
description: Funcionalidade de conversão do Aspose. Aqui estão alguns exemplos de código.
lastmod: "2025-06-16"
---

{{<section overview>}}


Outro formato de destino é [**xps**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). Um arquivo **XPS** é fisicamente um pacote ZIP que contém conteúdo paginado de um documento, juntamente com os metadados necessários para a exibição adequada por visualizadores específicos (como o Windows XPS Viewer) e a impressão. Todos os dados em um pacote são representados por arquivos. Alguns deles são binários e contêm recursos como imagens, fontes e perfis da ICC. Outros são arquivos XML em vários esquemas específicos. Este último inclui arquivos que contêm os dados do documento em si. Os dados do documento consistem em um conjunto de arquivos - cada arquivo contém dados para uma página individual do documento. Esses arquivos consistem em um elemento de página única e uma árvore de elementos filhos - *Canvas*, *Paths* e *Glyphs*. *Canvas*é um elemento de agrupamento que pode conter outras*Canvas*, *Paths* e *Glyphs*. Serve para controlar a aparência de todos os elementos filhos como um grupo. *Os elementos do caminho* são usados ​​para definir os caminhos gráficos vetoriais. E *Glyphs* elementos são usados ​​para definir conteúdo textual. Todos os três elementos têm propriedades para definir vários aspectos da aparência.

Existe a biblioteca [**Aspose.page**](https://products.aspose.com/page/) que fornece uma API para manipular documentos XPS, além de convertê -los em formatos de imagem PDF e raster.

## Como converter LaTeX em xps

A conversão de LaTeX para XPS é tão simples quanto a [conversão em formatos de imagem raster](/tex/{{lang.url-fragment}}net/latex-to-image/), exceto que as [saveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) devem ser definidas como uma instância da classe [XPSSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpssaveoptions/) (por padrão ou explicitamente) e o dispositivo deve ser alterado para uma instância do [XPSDEVICE](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/).

**Exemplo de conversão mais simples**

O exemplo abaixo mostra como converter um ficheiro LaTeX para XPS em poucos passos:

1. Crie uma instância `TexDocument`.
2. Carregue o ficheiro de origem `. tex` utilizando `TexDocument. Load`.
3. (Opcional) Configure `XpsSaveOptions`, como definições de compressão.
4.  Guarde o documento em XPS chamando `document. Save` com um `XpsDevice`.

Este código demonstra a forma mais direta de produzir um ficheiro XPS a partir do LaTeX.

{{< gist "aspose-com-gists" "1d10927e18d23e49096c91ce726e9d6f" "Example-ConvertLaTeXToXPS-Simplest.cs" >}}

### Uma maneira alternativa de escrever o arquivo XPS de saída principal

Há outro construtor da classe [XPSDEVICE](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/xpsdevice/), que nos permite obter o arquivo XPS resultante de uma maneira alternativa.

**Exemplo de conversão alternativo**

Este excerto demonstra a utilização do construtor `XpsDevice` que aceita um `Stream`. Os passos são:

1. Crie um `TexDocument` e carregue o código-fonte LaTeX.
2. Crie um `MemoryStream` para armazenar a saída XPS.
3. Instancie `XpsDevice` com o fluxo.
4. Guarde o documento no dispositivo e depois poderá utilizar o fluxo (por exemplo, enviá-lo pela rede ou armazená-lo numa base de dados).

Esta abordagem é útil quando necessita dos dados XPS na memória em vez de como um ficheiro em disco.

{{< gist "aspose-com-gists" "1d10927e18d23e49096c91ce726e9d6f" "Example-ConvertLaTeXToXPS-Alternative.cs" >}}

O efeito é o mesmo que chegamos [aqui](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file).

**Você também pode conferir a conversão LATEX-XPS GRATUITA [aplicativo da Web](https://products.aspose.app/tex/conversion/latex-to-xps) construído com base em [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**
