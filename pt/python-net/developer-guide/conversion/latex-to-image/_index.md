---
translation: true
template: /templates/_template-python-net.md
title: Látex para imagem | Python via .NET
linktitle: Látex para imagem
weight: 10
url: /python-net/latex-to-image/
keywords: Latex para PNG, LATEX PNG, LATEX para imagem, imagem LATEX, LATEX para JPG, LATEX JPG, LATEX para JPEG, LATEX JPEG, LATEX para TIFF, LATEX TIFF, LATEX para BMP, LATEX BMP
description: Para converter os formatos Tex em imagem usando a solução da API Aspose.TeX para Python, aprenda este artigo para ver que descreve como fazer isso e os exemplos de código.
lastmod: "2025-06-16"
---

{{<section overview>}}

**Aspose.TeX for python** nos fornece a capacidade de converter arquivos de LaTeX em vários formatos de imagem raster.

## Converter LaTeX em png

Agora, vamos examinar o código Python que oferece a abordagem mais direta para converter o LaTeX em formato PNG em profundidade.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToPng-Simplest.py" >}}

Para começar, precisamos criar uma instância da classe [texoptions](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/) usando o método [console_app_options ()](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/console_app_options/#aspose.tex.TeXConfig). Não se preocupe com o nome, é apenas o método estático que cria a instância. Este método pega a instância [object_latex](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_latex/) da classe [texconfig](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/), que é perfeita para converter um [arquivo de LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Essa configuração configura o mecanismo Tex Object para carregar o formato LATEX do objeto e estar pronto para processar o arquivo LATEX. O formato LATEX de objeto é essencialmente o mesmo que o [formato de LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), mas usa [objeto tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) primitivas específicas para definir as métricas da página.

A primeira das opções necessárias é [output_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/output_working_directory/), que especifica o local onde a saída TEX será salva. Se estiver interessado, você pode aprender mais informações sobre o conceito do [diretório de saída em **aspose.tex for python**](/tex/{{lang.url-fragment}}python-net/aspose-tex-output/). Neste exemplo em particular, utilizamos a classe [outputFilesystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputfilesystemdirectory/) para gravar a saída em um diretório ou pasta específica.

A segunda opção é uma instância da classe [SaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/saveoptions/), responsável pelo gerenciamento da conversão do [Modelo de Objeto](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) para o formato desejado. Nesse caso, como estamos convertendo LaTeX em PNG, usamos a instância da classe [pngSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.image/pngsaveoptions/), que nos permite especificar a resolução das imagens de saída.

De seguida, criamos uma instância da classe [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/). Neste caso, como queremos converter um ficheiro LaTeX armazenado no sistema de ficheiros, utilizamos [esta versão do construtor](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#str-aspose.tex.presentation.Device-aspose.tex.TeXOptions). Precisamos de fornecer o caminho completo para o ficheiro, caso contrário, o motor irá procurá-lo no diretório atual (que é o diretório de trabalho do script) e poderá não o encontrar. No entanto, a extensão `.tex` pode ser omitida, uma vez que o motor irá anexá-la automaticamente. O segundo argumento do construtor é uma instância da classe [Device](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/device/). Como estamos a converter LaTeX para PNG, trata-se de uma instância da classe [ImageDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.image/imagedevice/), comum a todos os formatos de imagem suportados. Por fim, passamos as opções de conversão preparadas como último argumento.

Agora, tudo o que resta é [correr](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/run/#) o trabalho.

Após a execução do trabalho, independentemente de seu sucesso ou falha, a primeira saída que encontraremos é a saída do terminal. No caso de uma corrida bem -sucedida, a saída se parecerá com o seguinte:


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

Os resultados do trabalho do motor podem ser encontrados no diretório de saída que especificamos. Isso incluirá o arquivo de transcrição e, o mais importante, o (s) arquivo (s) da (s) imagem (s) da imagem de saída principal.

## Uma maneira alternativa de escrever o (s) arquivo (s) principal (s) de saída da saída

Existe um método alternativo para obter dados de imagem como uma matriz de matrizes de bytes, onde cada matriz na segunda dimensão representa os dados da imagem para uma página separada.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToPng-Alternative.py" >}}

Os arquivos "Page-n.png" podem ser gravados em qualquer caminho especificado. Ao contrário de [saída em PDF](/tex/{{lang.url-fragment}}python-net/latex-to-pdf/#an-alternative-way-to-write-the-main-output-pdf-file), esses arquivos PNG duplicarão os arquivos PNG de saída gravados no diretório de saída.

## Em relação às opções de entrada

Se nosso arquivo de entrada principal exigir dependências, como pacotes que não estão incluídos no sistema de LaTeX básico ou em pacotes suportados, precisamos definir a opção [requerir_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/) de maneira semelhante à como definirmos a opção * output_working_directory * e colocamos as dependências nesse diretório. As dependências podem ser organizadas nos subdiretos, conforme necessário. Se tivermos nossos arquivos a serem incluídos no processo de composição, como arquivos gráficos externos, também precisamos definir o [input_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/input_working_directory/) para o local onde esses arquivos são armazenados. Também podemos colocar o arquivo de entrada principal no diretório de entrada e especificar o caminho relativo no método `run()` ou especificar nenhum caminho se o arquivo de entrada principal estiver no diretório raiz. Também existem mais detalhes sobre o [conceito de diretório de entrada](/tex/{{lang.url-fragment}}python-net/aspose-tex-input/) em **aspose.tex** e as implementações fornecidas descritas.

Aprenda também as [outras opções de emprego tex aqui](/tex/{{lang.url-fragment}}python-net/other-options/).

**Você também pode explorar o [aplicativo web] gratuito (24) para conversão de LaTeX-para-png, que é desenvolvida usando o [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**

Abaixo, explicaremos brevemente a conversão de LaTeX em outros formatos de imagem raster suportados, sem mergulhar em muitos detalhes, pois não há diferenças significativas. A única variação está no tipo de propriedade [Save_Options](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/save_options/) nas opções de conversão.

## Converter LaTeX em jpg

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToJpeg.py" >}}


**Você também pode explorar o aplicativo gratuito [da web para conversão de LaTeX-para-jpg](https://products.aspose.app/tex/conversion/latex-to-jpg), que é desenvolvido usando o [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**

## Convertendo LaTeX em tiff

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToTiff.py" >}}

**Você também pode explorar o aplicativo gratuito [da web para conversão de LaTeX-para-tiff](https://products.aspose.app/tex/conversion/latex-to-tiff), que é desenvolvido usando o [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**

## Converter LaTeX em BMP

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToBmp.py" >}}

**Você também pode explorar o aplicativo gratuito [da web para conversão de LaTeX para BMP](https://products.aspose.app/tex/conversion/latex-to-bmp), que é desenvolvido usando o [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**


## Converter LaTeX em SVG

Outro formato de destino suportado é [**svg**](https://en.wikipedia.org/wiki/SVG). **Gráficos vetoriais escaláveis ​​(SVG)** é um formato de imagem vetorial baseado em XML que é usado para definir gráficos bidimensionais. Ele suporta interatividade e animação.

**As imagens SVG** são armazenadas em arquivos de texto XML e definidas em um formato gráfico vetorial. Isso significa que as imagens **SVG** podem ser escalonadas em tamanho sem perder a qualidade e os próprios arquivos **SVG** podem ser pesquisados, indexados, scripts e compactados. Os arquivos de texto XML podem ser criados e editados usando editores de texto ou editores de gráficos vetoriais, e eles podem ser renderizados pelos navegadores da web mais usados.

A API [**Aspose.svg**](https://products.aspose.com/svg/) oferece uma variedade de recursos para trabalhar com **SVG**, como criar, carregar, editar e converter **SVG** documentos.

A conversão de LaTeX em SVG é tão direta quanto [converter em formatos de imagem raster](/tex/{{lang.url-fragment}}python-net/latex-to-image/), com a única diferença que as [Save_Options](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/save_options/) devem ser definidas como uma instância da classe [svgSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.svg/svgsaveoptions/) e o dispositivo deve ser alterado para uma instância da classe [SvgDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.svg/svgdevice/).

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToSvg-Simplest.py" >}}

**Você também pode explorar o aplicativo gratuito [da web para conversão de LaTeX para SVG](https://products.aspose.app/tex/conversion/latex-to-svg), que é desenvolvido usando o [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**