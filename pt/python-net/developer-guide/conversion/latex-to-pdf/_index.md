---
translation: true
template: /templates/_template-python-net.md
title: Látex para pdf | Python via .NET
linktitle: Látex para pdf
weight: 11
url: /python-net/latex-to-pdf/
keywords: LATEX para PDF, LATEX PDF, Converta LATEX em PDF
description: Aprenda a converter Tex para PDF usando a solução API Aspose.TeX para Python com este artigo, que fornece uma explicação detalhada e exemplos de código.
lastmod: "2025-06-16"
---

{{<section overview>}}

## Converter LaTeX em pdf

Agora, vamos examinar o código Python que oferece a abordagem mais direta para converter o LATEX em formato PDF em profundidade.

Defina `ASPOSE_TEX_INPUT_FILE` como o arquivo LaTeX e `ASPOSE_TEX_OUTPUT_DIR` como o diretório de saída, ou edite os caminhos do exemplo. Os valores padrão são `hello-world.ltx` e `output`. Aplique uma licença antes da conversão. Os arquivos de entrada adicionais são procurados junto ao documento principal; o processamento não é interativo. [Licenciamento](/tex/pt/python-net/licensing/)

{{< gist "aspose-com-gists" "3616f5e300517031e6a4ae4158e24776" "Aspose.TeX.Examples-Conversion-LaTeXToPdf-Simplest.py" >}}

Para começar, precisamos criar uma instância da classe [Texoptions](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/). O método [Console_App_Options ()](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/console_app_options/#aspose.tex.TeXConfig)   é o único método estático que realiza isso, portanto, não se preocupe com o nome. Este método pega uma instância [object_latex](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_latex/) da classe [texconfig](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/), que é perfeita para converter um [arquivo de LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Essa configuração instrui o mecanismo Tex do objeto a carregar o formato de LaTeX de objeto e estar preparado para processar o arquivo LATEX. O formato LATEX de objeto é essencialmente o mesmo que o formato [LATEX](/tex/{{lang.url-fragment}}net/what-is-latex/), mas utiliza [objeto tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) primitivos específicos para definir as métricas da página.

A primeira opção que precisa ser especificada é [output_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/output_working_directory/), que determina o local em que a saída TEX será salva. Se necessário, você pode encontrar mais informações sobre o [conceito do diretório de saída em **aspose.tex**](/tex/{{lang.url-fragment}}net/aspose-tex-output/). Neste caso em particular, utilizamos a classe [O outputFilesystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputfilesystemdirectory/), que nos permite escrever a saída em um diretório ou pasta designada.

A segunda opção requer uma instância da classe [SaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/saveoptions/), que determina como o [modelo de objeto](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) é transformado no formato desejado. No nosso caso, à medida que estamos convertendo LaTeX em pdf, ele se refere a uma instância da classe [pdfSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfsaveoptions/).

Para converter um ficheiro LaTeX armazenado no sistema de ficheiros, necessitamos de criar uma instância da classe [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/) utilizando o [construtor](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#str-aspose.tex.presentation.Device-aspose.tex.TeXOptions)   que recebe como parâmetro o caminho completo do ficheiro. Se não especificarmos o caminho completo, o motor irá procurar o ficheiro no diretório atual (que é o diretório de trabalho do script) e poderá não o encontrar. No entanto, podemos omitir a extensão se o nosso ficheiro tiver a extensão `. tex`, uma vez que o motor irá anexá-la automaticamente. O segundo argumento do construtor é uma instância da classe [Device](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/device/). No nosso caso, como estamos a converter LaTeX para PDF, é uma instância da classe [PdfDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfdevice/). Por fim, passamos as opções de conversão recentemente preparadas como último argumento.

Agora, tudo o que resta é [correr](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/run/#) o trabalho.

O exemplo captura a saída do terminal em `OutputMemoryTerminal`. O diretório de saída também contém um registro `.log`. Uma conversão bem-sucedida gera um registro semelhante ao seguinte; os dados da versão podem variar:

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

Na pasta que especificamos como diretório de saída, encontraremos o arquivo de transcrição e, **aqui está!**, o principal arquivo PDF de saída, entre outros resultados do trabalho do mecanismo.

## Uma maneira alternativa de escrever o arquivo PDF de saída principal

A classe *pdfDevice* possui outro [construtor](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfdevice/__init__/#io.RawIOBase) que nos permite obter o arquivo PDF resultante de maneira diferente.

{{< gist "aspose-com-gists" "3616f5e300517031e6a4ae4158e24776" "Aspose.TeX.Examples-Conversion-LaTeXToPdf-Alternative.py" >}}

O fluxo binário grava `any-name.pdf` no diretório de saída configurado. Não é criado outro arquivo PDF com o nome padrão; os arquivos auxiliares e o registro continuam em `output_working_directory`.

## Sobre opções de entrada

Se nosso arquivo de entrada principal exigir dependências, como pacotes que não estão incluídos no sistema de LaTeX básico e pacotes suportados, é necessário definir a opção [requerir_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/) de uma maneira semelhante à opção * output_working_directory * e colocar as dependências nesse diretório. As dependências podem ser organizadas nos subdiretos, conforme desejado. Além disso, se tivermos nossos próprios arquivos a serem incluídos no processo de tipoTTing, como arquivos gráficos externos, também devemos definir o [input_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/input_working_directory/) usando o caminho para o local em que esses arquivos são armazenados. Também podemos colocar o arquivo de entrada principal dentro do diretório de entrada e especificar o caminho relativo ao construtor `TeXJob` ou especificar nenhum caminho se o arquivo de entrada principal estiver na raiz. Para obter mais detalhes sobre o conceito de diretório de entrada em **aspose.tex para python** e as implementações fornecidas, consulte [aqui](/tex/{{lang.url-fragment}}python-net/aspose-tex-input/).

Há também [outras opções de emprego no TEX](/tex/{{lang.url-fragment}}python-net/other-options/) discutidas.

**Você também pode explorar o aplicativo gratuito [da web para conversão de LaTeX para PDF](https://products.aspose.app/tex/conversion/latex-to-pdf), que é desenvolvido usando o [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**