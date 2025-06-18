---
translation: true
template: /templates/_template-java.md
title: Látex para pdf | Aspose.TeX para java
linktitle: Látex para pdf
weight: 11
url: /java/latex-to-pdf/
keywords: LATEX para PDF, LATEX PDF, Converta LATEX em PDF
description: Para converter Tex para PDF usando a solução API Aspose.TeX para Java, aprenda este artigo para ver que descreve como fazer isso e os exemplos de código.
lastmod: "2025-06-16"
---

{{<section overview>}}


## Como converter LaTeX em pdf

Vamos dar uma olhada no código Java, fornecendo a maneira mais simples de converter o LATEX para o formato PDF.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-LaTeXToPdf-Simplest.java" >}}

Portanto, a primeira coisa que precisamos fazer (às vezes não é a primeira, como descobriremos mais tarde) é criar uma instância da classe [Texoptions](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions). O único método estático que faz isso é [consoleAppOptions()](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#consoleAppOptions-com.aspose.tex.TeXConfig-), então não vamos nos incomodar com o significado de seu nome. O método pega uma [instance](https://reference.aspose.com/tex/java/com.aspose.tex/TeXConfig#objectLaTeX--) da classe [TexConfig](https://reference.aspose.com/tex/java/com.aspose.tex/TeXConfig), que é exatamente adequada para converter um [arquivo de LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Esta configuração instrui o mecanismo Tex do objeto a carregar o formato de LaTeX de objeto e estar pronto para aceitar o arquivo LATEX. O formato LATEX de objeto é apenas o formato [LATEX](/tex/{{lang.url-fragment}}net/what-is-latex/), exceto que ele usa [Object tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) Primitives específicas para configurar as métricas da página.

A primeira das opções necessárias é [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--) que define o espaço ou área, onde a saída TEX será gravada. [Aqui](/tex/{{lang.url-fragment}}java/aspose-tex-output/) são os detalhes sobre o conceito de diretório de saída em **aspose.tex para java**. Neste exemplo, usamos a classe [outputFilesystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/OutputFileSystemDirectory), que nos permite gravar a saída no diretório ou pasta especificada.

A segunda opção é uma instância de classe [saveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/SaveOptions) que controlará a transformação do [modelo de objeto](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) no formato de destino. Como estamos convertendo LaTeX em PDF, é a instância da classe [PDFSaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfSaveOptions).

Then we need to create an instance of the [TeXJob](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob) class. Wanting to convert a LaTeX file stored in the file system, we use [this](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob#TeXJob-java.lang.String-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-) version of the constructor. We should specify the full path to the file. Otherwise, the engine will look for it in the current directory (which is defined [here](https://docs.oracle.com/javase/7/docs/api/java/io/File.html)) and most likely will not find it. Nevertheless, we may omit the extension if our file has the *.tex* one.
1,073 / 5,000
De seguida, precisamos de criar uma instância da classe [TeXJob](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob). Para converter um ficheiro LaTeX armazenado no sistema de ficheiros, utilizamos [esta](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob#TeXJob-java.lang.String-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-) versão do construtor. Devemos especificar o caminho completo para o ficheiro. Caso contrário, o motor irá procurá-lo no directório actual (definido [aqui](https://docs.oracle.com/javase/7/docs/api/java/io/File.html)) e provavelmente não o encontrará. No entanto, podemos omitir a extensão se o nosso ficheiro tiver a extensão *. tex*. O mecanismo irá anexá-la automaticamente. O segundo argumento do construtor é uma instância da classe [Device](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/Device). Como estamos a converter LaTeX para PDF, trata-se de uma instância da classe [PdfDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfDevice). Como último argumento, passámos as opções de conversão preparadas recentemente.

Tudo o que precisamos fazer agora é [correr](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob#run--) o trabalho.

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
Output written on hello-world.pdf (1 page).
Transcript written on hello-world.log.
```

Encontraremos outros produtos da execução do mecanismo na pasta que especificamos como diretório de saída. Esses serão o arquivo transcript (.log) e **pronto!**, o arquivo PDF de saída principal.

## Uma maneira alternativa de escrever o arquivo PDF de saída principal

Há outro construtor da classe [PDFDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfDevice#PdfDevice-java.io.OutputStream-), que nos permite obter o arquivo PDF resultante de uma maneira alternativa.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-LaTeXToPdf-Alternative.java" >}}

O arquivo *any-name.pdf* no diretório especificado será o nosso principal arquivo PDF de saída. Ao mesmo tempo, diferentemente do [saída de imagem](/tex/{{lang.url-fragment}}java/latex-to-png/#an-alternative-way-to-write-main-output-png-files), não encontraremos nenhum arquivo PDF no diretório de saída definido pelas opções de conversão. Exceção: *any-name.pdf* está localizado (por seu caminho) no mesmo diretório do sistema de arquivos atribuído à opção [outputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--) usando [outputFilesystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/OutputFileSystemDirectory).

## Sobre opções de entrada
Caso nosso arquivo de entrada principal exija dependências, por exemplo, pacotes, que não estão incluídos no sistema de LaTeX básico e pacotes suportados, devemos definir a opção [requerirInputDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getRequiredInputDirectory--) da maneira semelhante a definir a opção [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--) e colocar as dependências nesse diretório. As dependências podem ser organizadas arbitrariamente em subdiretos. Caso tenhamos nossos próprios arquivos a serem incluídos ao longo do processo de composição, digamos arquivos gráficos externos, também devemos definir o [InputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getInputWorkingDirectory--) usando o caminho para o local onde esses arquivos são coletados. Também podemos colocar o arquivo de entrada principal em algum lugar dentro do diretório de entrada e especificar o caminho relativo no método `run()` (ou especificar nenhum caminho se o arquivo de entrada principal estiver na raiz). [Aqui](/tex/{{lang.url-fragment}}java/aspose-tex-input/) são os detalhes sobre o conceito de diretório de entrada em **aspose.tex para java** e fornecem implementações.

Outras opções de trabalho Tex são discutidas [aqui](/tex/{{lang.url-fragment}}java/other-options/).

**Você também pode conferir a conversão LATEX-PDF gratuita [aplicativo da Web](https://products.aspose.app/tex/conversion/latex-to-pdf) construído com base na API [Aspose.TeX para .NET](https://products.aspose.com/tex/net/). [Aqui](https://products.aspose.com/tex/java/) é a página da versão Java.**