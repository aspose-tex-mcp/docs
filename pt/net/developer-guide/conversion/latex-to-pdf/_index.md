---
translation: true
template: /templates/_template-net.md
title: Látex para pdf | Aspose.TeX para .NET
linktitle: Látex para pdf
weight: 11
url: /net/latex-to-pdf/
keywords: LATEX para PDF, LATEX PDF, Converta LATEX em PDF
description: Para converter Tex em PDF usando a solução API Aspose.TeX para .NET Aprenda este artigo para ver que descreve como fazer isso e os exemplos de código.
lastmod: "2025-06-16"
---

{{<section overview>}}


## Como converter LaTeX em pdf

Vamos dar uma olhada detalhada no código em C#, fornecendo a maneira mais simples de converter o LATEX em formato PDF.

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToPdf-Simplest.cs" >}}

Portanto, a primeira coisa que precisamos fazer (bem, às vezes não é a primeira) é criar uma instância da classe [Texoptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/). O único método estático que faz isso é [ConsoleAppOptions()](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions/), então não seremos intrigados com o significado de seu nome. O método pega uma [instance](https://reference.aspose.com/tex/net/aspose.tex/texconfig/objectlatex/) da classe [TexConfig](https://reference.aspose.com/tex/net/aspose.tex/texconfig/), que é exatamente adequada para converter um [arquivo de LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Esta configuração informa ao mecanismo Tex do objeto para carregar o formato de LaTeX do objeto e estar pronto para aceitar o arquivo LATEX. O formato LATEX do Object é na verdade apenas o formato [LATEX](/tex/{{lang.url-fragment}}net/what-is-latex/), exceto que ele usa as primitivas específicas [Object tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) para configurar as métricas da página.

A primeira das opções necessárias é [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) que define o espaço ou área, onde a saída TEX será gravada. [Aqui](/tex/{{lang.url-fragment}}net/aspose-tex-output/) são os detalhes sobre o conceito de diretório de saída em **aspose.tex para .NET**. Neste exemplo, usamos a classe [outputFilesystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/), que nos permite escrever a saída no diretório ou pasta especificada.

A segunda opção é uma instância de classe [saveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation/saveoptions/) que controlará a transformação do [modelo de objeto](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) no formato de destino. Como estamos convertendo LaTeX em PDF, é a instância da classe [PDFSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/).

De seguida, necessitamos de criar uma instância da classe [TeXJob](https://reference.aspose.com/tex/net/aspose.tex/texjob/). Para converter um ficheiro LaTeX armazenado no sistema de ficheiros, utilizamos [esta](https://reference.aspose.com/tex/net/aspose.tex/texjob/texjob/) versão do construtor. Devemos especificar o caminho completo para o ficheiro. Caso contrário, o motor irá procurá-lo no directório actual (que é [CurrentDirectory](https://docs.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory)) e provavelmente não o encontrará. No entanto, podemos omitir a extensão se o nosso ficheiro tiver a extensão *. tex*. O mecanismo irá anexá-la automaticamente. O segundo argumento do construtor é uma instância da classe [Device](https://reference.aspose.com/tex/net/aspose.tex.presentation/device/). Como estamos a converter LaTeX para PDF, trata-se de uma instância da classe [PdfDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/). Como último argumento, passámos as opções de conversão preparadas recentemente.

Tudo o que resta a fazer agora é [correr](https://reference.aspose.com/tex/net/aspose.tex/texjob/run/) o trabalho.

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

Encontraremos outras "frutas" do trabalho do motor na pasta que especificamos como diretório de saída. Esses serão o arquivo de transcrição e, **aqui está!**, o arquivo PDF de saída principal.

## Uma maneira alternativa de escrever o arquivo PDF de saída principal

Há outro construtor da classe [PDFDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/pdfdevice/), que nos permite obter o arquivo PDF resultante de uma maneira alternativa.

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToPdf-Alternative.cs" >}}

O arquivo *any-name.pdf* no diretório especificado será o nosso principal arquivo PDF de saída. Ao mesmo tempo, diferentemente do [saída de imagem](/tex/{{lang.url-fragment}}net/latex-to-png/#an-alternative-way-to-write-main-output-png-files), não encontraremos nenhum arquivo PDF no diretório de saída definido pelas opções de conversão. Exceção: *any-name.pdf* está localizado (por seu caminho) no mesmo diretório do sistema de arquivos atribuído à opção [outputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) usando [outputFilesystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/).

## Sobre opções de entrada

Caso nosso arquivo de entrada principal exija dependências, por exemplo, pacotes, que não estão incluídos no sistema de LaTeX básico e pacotes suportados, devemos definir a opção [requerirInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) da maneira semelhante a definir a opção [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) e colocar as dependências nesse diretório. As dependências podem ser organizadas arbitrariamente em subdiretos. Caso tenhamos nossos próprios arquivos a serem incluídos ao longo do processo de composição, digamos arquivos gráficos externos, também devemos definir o [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/inputworkingdirectory/) usando o caminho para o local onde esses arquivos são coletados. Também podemos colocar o arquivo de entrada principal em algum lugar dentro do diretório de entrada e especificar o caminho relativo no método `run()` (ou especificar nenhum caminho se o arquivo de entrada principal estiver na raiz). [Aqui](/tex/{{lang.url-fragment}}net/aspose-tex-input/) são os detalhes sobre o conceito de diretório de entrada em **aspose.tex para .NET** e fornecem implementações.

Outras opções de trabalho Tex são discutidas [aqui](/tex/{{lang.url-fragment}}net/other-options/).

**Você também pode conferir a conversão LATEX-PDF gratuita [aplicativo da web](https://products.aspose.app/tex/conversion/latex-to-pdf) construído com base em [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**