---
translation: true
template: /templates/_template-java.md
title: Látex para imagem | Java
linktitle: Látex para imagem
weight: 10
url: /java/latex-to-image/
keywords: Latex para PNG, LATEX PNG, LATEX para imagem, imagem LATEX, LATEX para JPG, LATEX JPG, LATEX para JPEG, LATEX JPEG, LATEX para TIFF, LATEX TIFF, LATEX para BMP, LATEX BMP
description: Para converter os formatos Tex em imagem usando a solução ASPOLE.TEX API para Java, aprenda este artigo que descreve como fazer isso e os exemplos de código.
lastmod: "2026-04-21"
---

{{<section overview>}}

**Aspose.TeX para java** fornece recursos para converter arquivos de LaTeX em vários formatos de imagem raster.

## Como converter LaTeX para png

Vamos dar uma olhada no código Java, fornecendo a maneira mais simples de converter o LATEX para o formato PNG.

Defina `inputFile` como o caminho completo do arquivo LaTeX, como `hello-world.ltx`, e `outputDirectory` como uma pasta de saída existente. Importe as classes de `com.aspose.tex` e `com.aspose.tex.rendering` usadas no trecho. O método que faz a chamada deve tratar ou declarar as exceções. Aplique uma licença conforme o [guia de licenciamento](/tex/{{lang.url-fragment}}java/licensing/) para evitar as restrições de avaliação. O exemplo utiliza processamento não interativo e fecha seus recursos de saída. O exemplo PNG utiliza uma resolução de 300 DPI. Para a entrada de uma página `hello-world.ltx`, os arquivos de saída automáticos são `hello-world.png`, `hello-world.jpg`, `hello-world.tif`, `hello-world.bmp` ou `hello-world.svg`, conforme o formato selecionado.

{{< gist "aspose-com-gists" "9d6b3df9df43d8caf00a0d519c504cf5" "Example-ConvertLaTeXToPNG-Simplest.java" >}}

Portanto, a primeira coisa que precisamos fazer (às vezes não é a primeira, como descobriremos mais tarde) é criar uma instância da classe [Texoptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/). O único método estático que faz isso é [consoleAppOptions()](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#consoleAppOptions-com.aspose.tex.TeXConfig-), então não vamos nos incomodar com o significado de seu nome. O método pega a instância [objectLaTeX()](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/#objectLaTeX--) da classe [texconfig](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/), que é exatamente adequada para converter um [arquivo de LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Esta configuração instrui o mecanismo Tex do objeto a carregar o formato de LaTeX de objeto e estar pronto para aceitar o arquivo LATEX. O formato LATEX do Object é na verdade apenas o formato [LATEX](/tex/{{lang.url-fragment}}net/what-is-latex/), exceto que ele usa as primitivas específicas [Object tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) para configurar as métricas da página.

A primeira das opções necessárias é [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--) que define o espaço ou área, onde a saída TEX será gravada. [Aqui](/tex/{{lang.url-fragment}}java/aspose-tex-output/) são os detalhes sobre o conceito de diretório de saída em **aspose.tex para java**. Neste exemplo, usamos a classe [outputFilesystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputfilesystemdirectory/), que nos permite gravar a saída no diretório ou pasta especificada.

A segunda opção é uma instância de classe [saveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/saveoptions/) que controlará a transformação do [modelo de objeto](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) no formato de destino. Como estamos convertendo o LATEX em PNG, é a instância da classe [pngSaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/pngsaveoptions/), que nos permite especificar a resolução das imagens de saída.

De seguida, precisamos de criar uma instância da classe [TeXJob](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/). Para converter um ficheiro LaTeX armazenado no sistema de ficheiros, utilizamos [esta](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#TeXJob-java.lang.String-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-) versão do construtor. Devemos especificar o caminho completo para o ficheiro. Caso contrário, o motor irá procurá-lo no directório actual (definido [aqui](https://docs.oracle.com/javase/7/docs/api/java/io/File.html)) e provavelmente não o encontrará. No entanto, podemos omitir a extensão se o nosso ficheiro tiver a extensão *. tex*. O mecanismo irá anexá-la automaticamente. O segundo argumento do construtor é uma instância da classe [Device](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/device/). Como estamos a converter LaTeX para PNG, trata-se de uma instância da classe [ImageDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/imagedevice/) (que é comum a todos os formatos de imagem suportados). Como último argumento, passámos as opções de conversão preparadas recentemente.
Tudo o que precisamos fazer agora é [correr](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#run--) o trabalho.

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

Encontraremos outros produtos da execução do mecanismo na pasta que especificamos como diretório de saída. Esse será o arquivo transcriptista (.log) e, **pronto!**, o (s) arquivo (s) da imagem (s) da imagem de saída principal.

## Uma maneira alternativa de escrever o (s) arquivo (s) principal (s) de saída da saída

Há outra maneira de obter dados da imagem como uma matriz de matrizes de bytes, cada matriz na segunda dimensão representa dados de imagem para uma página separada.

{{< gist "aspose-com-gists" "9d6b3df9df43d8caf00a0d519c504cf5" "Example-ConvertLaTeXToPNG-Alternative.java" >}}

O exemplo manual também requer `java.nio.file.Files` e `java.nio.file.Paths`. Ele salva os dados das páginas de `ImageDevice.getResult()` como `page-1.png`, `page-2.png` e assim por diante. Como define `deviceWritesImages(false)`, a saída PNG automática é desativada e as páginas salvas manualmente não são duplicadas no diretório de saída. Isso difere da [saída PDF por fluxo](/tex/{{lang.url-fragment}}java/latex-to-pdf/#uma-maneira-alternativa-de-escrever-o-arquivo-pdf-de-saída-principal), em que o fluxo define o destino de um único documento PDF.

## Sobre opções de entrada

Caso nosso arquivo de entrada principal exija dependências, por exemplo, pacotes, que não estão incluídos no sistema de LaTeX básico e pacotes suportados, devemos definir a opção [requerirInputDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getRequiredInputDirectory--) da maneira semelhante a definir a opção [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--) e colocar as dependências nesse diretório. As dependências podem ser organizadas arbitrariamente em subdiretos. Caso tenhamos nossos próprios arquivos a serem incluídos ao longo do processo de composição, digamos arquivos gráficos externos, também devemos definir o [InputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getInputWorkingDirectory--) usando o caminho para o local onde esses arquivos são coletados. Também podemos colocar o arquivo de entrada principal em algum lugar dentro do diretório de entrada e passar o caminho relativo ao construtor de `TeXJob` (ou especificar nenhum caminho se o arquivo de entrada principal estiver na raiz). [Aqui](/tex/{{lang.url-fragment}}java/aspose-tex-input/) são os detalhes sobre o conceito de diretório de entrada em **aspose.tex para java** e fornecem implementações.

Outras opções de trabalho Tex são discutidas [aqui](/tex/{{lang.url-fragment}}java/other-options/).

**Você também pode conferir a conversão LATEX-PNG GRATUITA [aplicativo da Web](https://products.aspose.app/tex/conversion/latex-to-png) construído com base no [Aspose.TeX para .NET](https://products.aspose.com/tex/net/) API. [Aqui](https://products.aspose.com/tex/java/) é a página da versão Java.**

Abaixo, discutimos a conversão de LaTeX para outros formatos de imagem raster suportados. Não vamos entrar em detalhes apenas porque não há realmente detalhes. A única diferença está no tipo de propriedade [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getSaveOptions--) nas opções de conversão.

## Como converter LaTeX em jpg

{{< gist "aspose-com-gists" "9d6b3df9df43d8caf00a0d519c504cf5" "Example-ConvertLaTeXToJPEG.java" >}}

**Você também pode conferir a conversão LATEX-JPG GRATUITA [aplicativo da Web](https://products.aspose.app/tex/conversion/latex-to-jpg) construído com base na API [Aspose.TeX para .NET](https://products.aspose.com/tex/net/). [Aqui](https://products.aspose.com/tex/java/) é a página da versão Java.**

## Como converter LaTeX para TIFF

{{< gist "aspose-com-gists" "9d6b3df9df43d8caf00a0d519c504cf5" "Example-ConvertLaTeXToTIFF.java" >}}

**Você também pode conferir a conversão LATEX-TIFF GRATUITA [aplicativo da web](https://products.aspose.app/tex/conversion/latex-to-tiff) construído com base na API [Aspose.TeX para .NET](https://products.aspose.com/tex/net/). [Aqui](https://products.aspose.com/tex/java/) é a página da versão Java.**

## Como converter LaTeX para BMP

{{< gist "aspose-com-gists" "9d6b3df9df43d8caf00a0d519c504cf5" "Example-ConvertLaTeXToBMP.java" >}}

**Você também pode conferir a conversão LATEX-BMP GRATUITA [aplicativo da Web](https://products.aspose.app/tex/conversion/latex-to-bmp) construído com base na API [Aspose.TeX para .NET](https://products.aspose.com/tex/net/). [Aqui](https://products.aspose.com/tex/java/) é a página da versão Java.**


## Como converter LaTeX para SVG

E ainda outro formato de destino suportado é [**svg**](https://en.wikipedia.org/wiki/SVG). **Gráficos vetoriais escaláveis ​​(SVG)** é um formato de imagem vetorial baseado em XML para definir gráficos bidimensionais, tendo suporte para interatividade e animação.

**As imagens SVG** são definidas em um formato de gráfico vetorial e armazenadas em arquivos de texto XML. Isso significa que as imagens **SVG** podem ser escalonadas em tamanho sem perda de qualidade e os arquivos **SVG** podem ser pesquisados, indexados, scripts e compactados. Os arquivos de texto XML podem ser criados e editados com editores de texto ou editores de gráficos vetoriais. Thay é renderizado pelos navegadores da web mais usados.

Além disso, existe a biblioteca [**Aspose.svg**](https://products.aspose.com/svg/) que possui vários recursos baseados no formato **svg**. Isso inclui a criação, carregamento, edição e conversão de documentos **SVG**.

A conversão para SVG é tão simples quanto a [conversão em formatos de imagem raster](/tex/{{lang.url-fragment}}java/latex-to-image/), exceto que, além das [saveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getSaveOptions--), precisamos alterar o dispositivo para uma instância da classe [svgDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/SvgDevice).

{{< gist "aspose-com-gists" "9d6b3df9df43d8caf00a0d519c504cf5" "Example-ConvertLaTeXToSVG-Simplest.java" >}}

**Você também pode conferir a conversão LATEX-SVG GRATUITA [aplicativo da Web](https://products.aspose.app/tex/conversion/latex-to-svg) construído com base no [Aspose.TeX para .NET](https://products.aspose.com/tex/net/). [Aqui](https://products.aspose.com/tex/java/) é a página da versão Java.**