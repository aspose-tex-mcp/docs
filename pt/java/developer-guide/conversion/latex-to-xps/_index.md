---
translation: true
template: /templates/_template-java.md
title: Látex para xps | Java
linktitle: Látex para XPS
weight: 12
url: /java/latex-to-xps/
description: A funcionalidade de conversão do Aspose.TeX API Solution for Java permite converter arquivos de LaTeX no formato XPS. Aprenda os exemplos de código.
lastmod: "2026-04-21"
---

{{<section overview>}}


Outro formato de destino é [**xps**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). Um arquivo **xps** é fisicamente um pacote ZIP que contém conteúdo paginado de um documento, bem como os metadados necessários para a exibição adequada por visualizadores específicos (como o Windows XPS Viewer) e a impressão. Todos os dados em um pacote são organizados como arquivos nos diretórios. Alguns deles contêm recursos como imagens, fontes e perfis da ICC. Outros são arquivos XML em vários esquemas específicos. Este último inclui arquivos que contêm os dados do documento em si. Os dados do documento são um conjunto de arquivos - cada arquivo contém dados para uma página individual do documento. Esses arquivos consistem em um elemento de página única e uma árvore de elementos filhos - *Canvas*, *Paths* e *Glyphs*. *Canvas*é um elemento de agrupamento que pode conter outras*Canvas*, *Paths* e *Glyphs*. Seu objetivo é o controle sobre o aparecimento de todos os elementos filhos como um grupo. *Os elementos do caminho* são usados ​​para definir os caminhos gráficos vetoriais. E *Glyphs* elementos são usados ​​para definir o conteúdo de texto. Todos os três elementos têm propriedades para definir vários aspectos da aparência.

Existe a biblioteca [**Aspose.page**](https://products.aspose.com/page/) que fornece uma API para manipular documentos XPS, além de convertê -los em formatos de imagem PDF e raster.

## Como converter LaTeX em xps

A conversão em XPS é tão simples quanto a [conversão em formatos de imagem raster](/tex/{{lang.url-fragment}}java/latex-to-image/), exceto que, além das [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getSaveOptions--), precisamos usar uma instância da classe [xpsDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/xpsdevice/) .

Defina `inputFile` como o caminho completo do arquivo LaTeX, como `hello-world.ltx`, e `outputDirectory` como uma pasta de saída existente. Importe as classes de `com.aspose.tex` e `com.aspose.tex.rendering` usadas no trecho. O método que faz a chamada deve tratar ou declarar as exceções. Aplique uma licença conforme o [guia de licenciamento](/tex/{{lang.url-fragment}}java/licensing/) para evitar as restrições de avaliação. O exemplo utiliza processamento não interativo e fecha seus recursos de saída. Para o arquivo de entrada independente `hello-world.ltx`, a saída padrão é `hello-world.xps`.

{{< gist "aspose-com-gists" "1d90376049c44b97cffb85e4ac382a5b" "Example-ConvertLaTeXToXPS-Simplest.java" >}}

### Uma maneira alternativa de escrever o arquivo XPS de saída principal

Há outro construtor da classe [XPSDEVICE](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/xpsdevice/#XpsDevice-java.io.OutputStream-), que nos permite obter o arquivo XPS resultante de uma maneira alternativa.

Use os mesmos valores de `inputFile` e `outputDirectory` indicados acima. Defina `xpsFile` como um `java.nio.file.Path`, por exemplo `Paths.get(outputDirectory, "any-name.xps")`. Além das classes Aspose.TeX, importe `java.io.OutputStream`, `java.nio.file.Files`, `java.nio.file.Path` e `java.nio.file.Paths`. O fluxo controla o destino do arquivo XPS; os arquivos auxiliares continuam sendo gravados em `outputDirectory`.

{{< gist "aspose-com-gists" "1d90376049c44b97cffb85e4ac382a5b" "Example-ConvertLaTeXToXPS-Alternative.java" >}}

O efeito é o mesmo que chegamos [aqui](/tex/{{lang.url-fragment}}java/latex-to-pdf/#uma-maneira-alternativa-de-escrever-o-arquivo-pdf-de-saída-principal).

**Você também pode conferir a conversão LATEX-XPS gratuita [aplicativo da Web](https://products.aspose.app/tex/conversion/latex-to-xps) construído com base no [Aspose.TeX para .NET](https://products.aspose.com/tex/net/) API. [Aqui](https://products.aspose.com/tex/java/) é a página da versão Java.**