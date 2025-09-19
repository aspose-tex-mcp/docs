---
translation: true
template: /templates/_template-python-net.md
title: Pacotes de LaTeX externos | Python via .NET
linktitle: Pacotes de LaTeX externos
weight: 19
url: /python-net/external-latex-packages/
description: API Aspose.TeX para Python suporta o uso de pacotes externos que não estão incluídos na própria biblioteca, como os pacotes FancyBox e PGFPlots
lastmod: "2025-06-16"
---

{{<section overview>}}

## Pacotes de LaTeX externos

A biblioteca **Aspose.TeX** vem com uma variedade de [pacotes comuns de LaTeX](/tex/{{lang.url-fragment}}net/embedded-packages/), portanto não há necessidade de fornecer manualmente esses pacotes ao mecanismo TEX. No entanto, pode haver situações em que seu arquivo de LaTeX requer um pacote que não esteja incluído no "pacote" de pacotes da biblioteca. Nesses casos, você pode tentar fornecer a entrada necessária, como os arquivos de origem do pacote necessário, através da opção [requerir_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/) da instância da classe [texoptions](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/). Vamos explorar como isso funciona com dois exemplos.

### Entrada necessária fornecida em um formulário não embalado (o pacote `FancyBox`).

Suponha que tenhamos o seguinte arquivo BASIC LATEX chamado `requerir-input-f-fs.tex`, que faz parte da nossa [Solução de Exemplo](https://GitHub.com/aspose-tex/Aspose.TeX-for-Python-.NET):

```tex
\documentclass{article}
\usepackage[a6paper,landscape]{geometry}
\usepackage{fancybox}
\begin{document}
Test: \fbox{
  \begin{Bitemize}[b]
  \item First item
  \item A second one\\ on two lines
  \item(2pt) A third with extra space
  \end{Bitemize}
}
\par\bigskip
Test: \fbox{
  \begin{Beqnarray}[t]
  y & = & x^2 \\
  a^2 + 2ab + b^2 & = & (a + b)^2 \\
  \int_0^\infty e^{-ax} dx & = & \frac{1}{a}
  \end{Beqnarray}
}
\end{document}
```

A terceira linha do arquivo indica que requer o pacote `FancyBox`, que não está incluído no suporte" nativo ". Vamos supor que temos o arquivo de origem do pacote `FancyBox`. Como é um pacote simples composto por um único arquivo, podemos colocar esse arquivo em qualquer lugar do nosso sistema de arquivos e especificar o caminho do diretório da seguinte forma:


```Python
options.required_input_directory = InputFileSystemDirectory('path-to-directory-where-fancybox.sty-located')
```

Depois de executar um trabalho de Tex com esta opção (lembre -se de ajustar as outras opções conforme necessário), obteremos o documento de saída, que neste caso é uma imagem PNG.

![Documento de saída](/tex/images/python-net/Conversion-RequiredInputFs.png)

Aqui está o código -fonte completo para o exemplo:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-RequiredInput-FileSystem.py" >}}

### Fornecendo entrada necessária em um formulário arquivado (o pacote `pgfplots`)

Agora, suponha que tenhamos o seguinte arquivo LATEX chamado `requerir-in-zip.tex`, que também é um arquivo simples da nossa solução de exemplo:


```tex
\documentclass{article}
\usepackage[margin=0.25in]{geometry}
\usepackage{pgfplots}
\pgfplotsset{width=10cm,compat=1.18}
\begin{document}

First example is 2D and 3D math expressions plotted side-by-side.

%Here begins the 2D plot
\begin{tikzpicture}
\begin{axis}
\addplot[color=red]{exp(x)};
\end{axis}
\end{tikzpicture}
%Here ends the 2D plot
\hskip 5pt
%Here begins the 3D plot
\begin{tikzpicture}
\begin{axis}
\addplot3[
    surf,
]
{exp(-x^2-y^2)*x};
\end{axis}
\end{tikzpicture}
%Here ends the 3D plot

\end{document}
```

Na terceira linha, pode -se observar que o arquivo requer o pacote `pgfplots`, que não é suportado" nativamente ". Mais uma vez, assumindo que possuímos os arquivos de origem para o pacote `PGFPLOTS`, esses arquivos são bastante numerosos e estão localizados em dois diretórios diferentes no diretório de instalação de qualquer aplicativo de tipógrafo de LaTeX. A pasta `pgfplots` pode ser encontrada nos diretórios`\tex \generic` e `\tex \latex`. Para que a biblioteca Aspose.TeX funcione corretamente, é necessário fornecer o conteúdo dessas duas pastas como entrada. Para conseguir isso, desejamos empacotar esses arquivos de origem em um arquivo zip. Abaixo está o layout desejado do arquivo:

![Layout do arquivo](/tex/images/python-net/pgfplots-zip-layout.png)

E aqui está o método pelo qual definimos a acessibilidade a esses arquivos de origem:

```Python
with open("path-to-zip-with-pgfplots-sources") as zipStream:
    ...
    options.required_input_directory = InputZipDirectory(zipStream)
    ...
```

Depois de executar um trabalho de Tex com esta opção, obtemos o documento de saída:

![Documento de saída](/tex/images/python-net/Conversion-RequiredInputZip.png)

Aqui está o código -fonte completo para o exemplo:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-RequiredInput-Zip.py" >}}

> **_NOTA:_** O resultado foi verificado através do pacote `pgfplots` versão 1.18.1. Quanto à versão do pacote `pfg` incluída na biblioteca **Aspose.TeX** é a 3.1.9a.

<!--
### Utilização de pacotes de fontes externas

Normalmente, as distribuições LaTeX vêm com um conjunto predefinido de tipos de letra que podem ser utilizados para composição tipográfica. No entanto, para além destas fontes padrão, o Aspose.TeX inclui também vários pacotes de fontes não padrão, como `amsfonts`, `eurosym` e `wasysym`. Como discutimos anteriormente, o Aspose.TeX também suporta a utilização de pacotes externos, embora a maior parte da nossa discussão anterior se tenha centrado em pacotes que não incluem fontes.

A extensão do motor *Object TeX* do Aspose.TeX requer mapas de fontes, que são ficheiros de texto num formato específico com a extensão `. map`, para determinar as fontes físicas correspondentes para cada nome de fonte interna do TeX. Estes mapas de fontes necessitam de ser carregados para a memória do TeX durante a fase de arranque e devem ser incluídos no pacote que está a utilizar. Como o motor não reconhece os nomes de todos os mapas de fontes, procura ficheiros com a extensão `. map`. Assim, ao fornecer um valor para a opção [required_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/), a implementação da interface [IInputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/) deve permitir o acesso a coleções de nomes de ficheiros por extensão. Além disso, esta implementação deve também implementar a interface [IFileCollector](https://reference.aspose.com/tex/python-net/aspose.tex.io/ifilecollector/). As implementações padrão, como [InputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputfilesystemdirectory/) e [InputZipDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputzipdirectory/), já cumprem estes requisitos.

Abaixo, é apresentado um exemplo de um diretório de entrada obrigatório personalizado que demonstra como implementar a interface [IFileCollector](https://reference.aspose.com/tex/python-net/aspose.tex.io/ifilecollector/). Este exemplo centra-se na recolha de nomes de ficheiros por extensão e omite intencionalmente os detalhes de armazenamento e recuperação de ficheiros.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-RequiredInput-Zip.py" >}}
-->

### Restrições

Se você se deparar com um pacote desenvolvido no*Latex3e*kernel e for necessário pelo seu arquivo LaTex, é improvável que trabalhe com a biblioteca **Aspose.TeX**. Isso ocorre porque a biblioteca é baseada no kernel *LATEX2E*.

Além disso, pode haver casos em que um pacote exigido pelo seu arquivo de LaTeX use diretamente comandos primitivos dependentes do dispositivo que não são suportados pelo mecanismo **aspose.tex** da biblioteca *tex*. Nesses casos, o pacote não funcionará com a biblioteca.