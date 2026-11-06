---
translation: true
template: /templates/_template-python-net.md
title: Látex para xps | Python via .NET
linktitle: Látex para XPS
weight: 12
url: /python-net/latex-to-xps/
description: A solução da API Aspose.TeX para Python fornece funcionalidade de conversão para converter arquivos de LaTeX em formato XPS. Aqui estão alguns exemplos de código.
lastmod: "2025-06-16"
---

{{<section overview>}}

Outro formato de destino é [**xps**](https://docs.aspose.com/page/net/what-is-xps-file/). Um arquivo [**xps**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification) é essencialmente um pacote ZIP que contém conteúdo paginado de um documento, juntamente com os metadados necessários para exibição adequada por visualizadores específicos (como o Windows XPS Viewer) e a impressão. O pacote consiste em vários arquivos, alguns dos quais são binários e contêm recursos como imagens, fontes e perfis da ICC. Outros são arquivos XML em esquemas específicos, incluindo arquivos que contêm os dados do documento. Os dados do documento são divididos em vários arquivos, com cada arquivo representando uma página individual do documento. Esses arquivos consistem em um elemento de página única e uma árvore de elementos filhos, incluindo *Canvas*, *Paths* e *Glyphs*. O elemento *Canvas* é um elemento de agrupamento que pode conter outras *telas*, *caminhos *e *Glyphs*, e controla a aparência de todos os elementos filhos como um grupo. *Os elementos do caminho* são usados ​​para definir os caminhos gráficos vetoriais, enquanto os elementos* glifos* são usados ​​para definir conteúdo textual. Todos os três elementos têm propriedades que definem vários aspectos da aparência.

Existe a biblioteca [**Aspose.Page**](https://products.aspose.com/page/), que oferece uma API para manipular documentos XPS e também permite a conversão desses documentos em formatos de imagem PDF e raster.

## Converter LaTeX em xps

O processo de conversão de LaTeX em XPS é igualmente direto, semelhante à [conversão em formatos de imagem raster](/tex/{{lang.url-fragment}}python-net/latex-to-image/). No entanto, requer a definição da [Save_Options](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/save_options/) em uma instância da classe [XPSSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.xps/xpssaveoptions/) (por padrão ou explicitamente) e alterando o dispositivo para uma instância da classe [XPSDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.xps/xpsdevice/).

Defina `ASPOSE_TEX_INPUT_FILE` como o arquivo LaTeX e `ASPOSE_TEX_OUTPUT_DIR` como o diretório de saída, ou edite os caminhos do exemplo. Os valores padrão são `hello-world.ltx` e `output`. Aplique uma licença antes da conversão. Os arquivos de entrada adicionais são procurados junto ao documento principal; o processamento não é interativo. [Licenciamento](/tex/pt/python-net/licensing/)

{{< gist "aspose-com-gists" "3616f5e300517031e6a4ae4158e24776" "Aspose.TeX.Examples-Conversion-LaTeXToXps-Simplest.py" >}}

### Uma maneira alternativa de escrever o arquivo XPS de saída principal

Existe um construtor alternativo disponível para a classe * xpsDevice *, que permite obter o arquivo XPS resultante de uma maneira diferente.

{{< gist "aspose-com-gists" "3616f5e300517031e6a4ae4158e24776" "Aspose.TeX.Examples-Conversion-LaTeXToXps-Alternative.py" >}}

O fluxo binário grava `any-name.xps` no diretório de saída configurado. Não é criado outro arquivo XPS com o nome padrão; os arquivos auxiliares e o registro continuam em `output_working_directory`.

**Você também pode explorar o aplicativo gratuito [da web para conversão Latex-para-XPS](https://products.aspose.app/tex/conversion/latex-to-xps), que é desenvolvido usando o [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**