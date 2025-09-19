---
translation: true
template: /templates/_template-net.md
title: Látex para imagem | .NET
linktitle: Látex para imagem
weight: 10
url: /net/latex-to-image/
keywords: Latex para PNG, LATEX PNG, LATEX para imagem, imagem LATEX, LATEX para JPG, LATEX JPG, LATEX para JPEG, LATEX JPEG, LATEX para TIFF, LATEX TIFF, LATEX para BMP, LATEX BMP
description: Para converter os formatos Tex em imagem usando a solução da API Aspose.TeX para .NET Aprenda este artigo para ver que descreve como fazer isso e os exemplos de código.
lastmod: "2025-06-16"
---

{{<section overview>}}

**Aspose.TeX para .NET** nos permite converter arquivos de LaTeX em vários formatos de imagem raster.

## Como converter LaTeX para png

Vamos dar uma olhada detalhada no código em C#, fornecendo a maneira mais simples de converter o LATEX em formato PNG.

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToPng-Simplest.cs" >}}

Portanto, a primeira coisa que precisamos fazer (bem, às vezes não é a primeira) é criar uma instância da classe [Texoptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/). O único método estático que faz isso é [ConsoleAppOptions()](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions/), então não seremos intrigados com o significado de seu nome. O método pega a [ObjectLateX Instância](https://reference.aspose.com/tex/net/aspose.tex/texconfig/objectlatex/) da classe [TexConfig](https://reference.aspose.com/tex/net/aspose.tex/texconfig/), que é exatamente adequada para converter um [arquivo LATEX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Esta configuração informa ao mecanismo Tex do objeto para carregar o formato de LaTeX do objeto e estar pronto para aceitar o arquivo LATEX. O formato LATEX do Object é na verdade apenas o formato [LATEX](/tex/{{lang.url-fragment}}net/what-is-latex/), exceto que ele usa as primitivas específicas [Object tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) para configurar as métricas da página.

A primeira das opções necessárias é [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) que define o espaço ou área, onde a saída TEX será gravada. [Aqui](/tex/{{lang.url-fragment}}net/aspose-tex-output/) são os detalhes sobre o conceito de diretório de saída em **aspose.tex para .NET**. Neste exemplo, usamos a classe [outputFilesystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/), que nos permite escrever a saída no diretório ou pasta especificada.

A segunda opção é uma instância de classe [saveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation/saveoptions/) que controlará a transformação do [modelo de objeto](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) no formato de destino. Como estamos convertendo o LATEX em PNG, é a instância da classe [pngSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.image/pngsaveoptions/), que nos permite especificar a resolução das imagens de saída.

De seguida, necessitamos de criar uma instância da classe [TeXJob](https://reference.aspose.com/tex/net/aspose.tex/texjob/). Para converter um ficheiro LaTeX armazenado no sistema de ficheiros, utilizamos [esta](https://reference.aspose.com/tex/net/aspose.tex/texjob/texjob/) versão do construtor. Precisamos de especificar o caminho completo para o ficheiro. Caso contrário, o motor irá procurá-lo no directório actual (que é [CurrentDirectory](https://docs.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory)) e provavelmente não o encontrará. No entanto, a extensão *. tex* pode ser omitida. O mecanismo irá anexá-la automaticamente. O segundo argumento do construtor é uma instância da classe [Device](https://reference.aspose.com/tex/net/aspose.tex.presentation/device/). Como estamos a converter LaTeX para PNG, trata-se de uma instância da classe [ImageDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.image/imagedevice/), comum a todos os formatos de imagem suportados. Como último argumento, passámos as opções de conversão preparadas recentemente.

Tudo o que resta a fazer agora é [correr](https://reference.aspose.com/tex/net/aspose.tex/texjob/run/) o trabalho.

Independentemente de a execução ter sido bem -sucedida ou não, o primeiro resultado que veremos será a saída do terminal. Se a corrida tiver sido bem -sucedida, será algo assim:


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

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToPng-Alternative.cs" >}}

Os arquivos * "página-n.png" * serão gravados em qualquer caminho que especifique. Ao contrário de [saída em PDF](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file), eles duplicarão os arquivos PNG de saída gravados no diretório de saída.

## Sobre opções de entrada

Caso nosso arquivo de entrada principal exija dependências, por exemplo, pacotes, que não estão incluídos no sistema de LaTeX básico e pacotes suportados, devemos definir a opção [requerirInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) da maneira semelhante a definir a opção [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) e colocar as dependências nesse diretório. As dependências podem ser organizadas arbitrariamente em subdiretos. Caso tenhamos nossos próprios arquivos a serem incluídos ao longo do processo de composição, digamos arquivos gráficos externos, também devemos definir o [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/inputworkingdirectory/) usando o caminho para o local onde esses arquivos são coletados. Também podemos colocar o arquivo de entrada principal em algum lugar dentro do diretório de entrada e especificar o caminho relativo no método `run()` (ou especificar nenhum caminho se o arquivo de entrada principal estiver na raiz). [Aqui](/tex/{{lang.url-fragment}}net/aspose-tex-input/) são os detalhes sobre o conceito de diretório de entrada em **Aspose.TeX para .NET** e fornecem implementações.

Outras opções de trabalho Tex são discutidas [aqui](/tex/{{lang.url-fragment}}net/other-options/).

**Você também pode conferir a conversão de LaTeX-para-png gratuita [aplicativo da web](https://products.aspose.app/tex/conversion/latex-to-png) construído com base em [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**

Abaixo, discutimos a conversão de LaTeX para outros formatos de imagem raster suportados sem afundar profundamente em detalhes, pois na verdade não há detalhes. A única diferença está no tipo de propriedade [saveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) nas opções de conversão.

## Como converter LaTeX em jpg

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToJpeg.cs" >}}

**Você também pode conferir a conversão de LaTex-para-JPG gratuita [aplicativo da web](https://products.aspose.app/tex/conversion/latex-to-jpg) construído com base em [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**

## Como converter LaTeX para TIFF

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToTiff.cs" >}}

**Você também pode conferir a conversão LATEX-TIFF GRATUITA [Web App](https://products.aspose.app/tex/conversion/latex-to-tiff) construída com base em [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**

## Como converter LaTeX para BMP

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToBmp.cs" >}}

**Você também pode conferir a conversão LATEX-para-BMP gratuita [aplicativo da web](https://products.aspose.app/tex/conversion/latex-to-bmp) construído com base em [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**

## Como converter LaTeX para SVG

E ainda outro formato de destino suportado é [**svg**](https://en.wikipedia.org/wiki/SVG). **Gráficos vetoriais escaláveis ​​(SVG)** é um formato de imagem vetorial baseado em XML para definir gráficos bidimensionais, tendo suporte para interatividade e animação.

**As imagens SVG** são definidas em um formato de gráfico vetorial e armazenadas em arquivos de texto XML. **As imagens SVG** podem, portanto, ser dimensionadas em tamanho sem perda de qualidade e os arquivos **SVG** podem ser pesquisados, indexados, script e compactados. Os arquivos de texto XML podem ser criados e editados com editores de texto ou editores de gráficos vetoriais e são renderizados pelos navegadores da web mais usados.

Existe a biblioteca [**Aspose.svg**](https://products.aspose.com/svg/) que fornece vários recursos relacionados a **svg**. Isso inclui a criação, carregamento, edição e conversão de documentos **svg**.

A conversão LATEX para SVG também é tão simples quanto a [conversão em formatos de imagem raster](/tex/{{lang.url-fragment}}net/latex-to-image/), exceto que as [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) devem ser definidas como uma instância da classe [svgSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.svg/svgsaveoptions/) e o dispositivo deve ser alterado para uma instância da classe [SVGDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.svg/svgdevice/).

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToSvg-Simplest.cs" >}}

**Você também pode conferir a conversão LATEX-SVG GRATUITA [aplicativo da web](https://products.aspose.app/tex/conversion/latex-to-svg) construído com base em [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**