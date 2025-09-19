---
translation: true
template: /templates/_template-net.md
title: Pacotes de LaTeX externos | Aspose.TeX para .NET
linktitle: Pacotes de LaTeX externos
weight: 20
url: /net/external-latex-packages/
description: API Aspose.TeX para .NET permite o uso de pacotes externos, ou seja, os que não estão incluídos na própria biblioteca, como pacotes FancyBox e PGFPlots.
lastmod: "2025-06-16"
---

{{<section overview>}}

## Pacotes de LaTeX externos

A biblioteca **Aspose.TeX** inclui vários [pacotes de LaTeX comuns](/tex/{{lang.url-fragment}}net/embedded-packages/). Portanto, você não precisa se preocupar com como fornecer esses pacotes ao mecanismo Tex da biblioteca. Mas, às vezes (ou com bastante frequência), seu arquivo de LaTeX pode exigir um pacote além do pacote "nativamente" suportado "de pacotes. Se for esse o caso, você pode tentar fornecer a entrada necessária, ou seja, os arquivos de origem do pacote necessário, através da opção [RequerirdIpputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) da instância da classe [Texoptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/). Veremos como isso funciona com dois exemplos.

### Pacote necessário de entrada necessária (pacote `FancyBox`)

Digamos que temos o seguinte arquivo de LaTeX simples, que é ` requerir-input-f-fs.tex` da nossa [Solução de exemplo](https://GitHub.com/aspose-tex/Aspose.TeX-for-.NET):


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

Na terceira linha, podemos ver que o arquivo requer o pacote `FancyBox`, que não é suportado" nativamente ". Vamos também assumir que temos o arquivo de origem do pacote 'FancyBox'. É um pacote simples, por isso realmente consiste em um único arquivo. Podemos colocar esse arquivo em qualquer lugar do nosso sistema de arquivos e especificar o caminho do diretório, como simplesmente como mostrado abaixo:


```C#
options.RequiredInputDirectory = new InputFileSystemDirectory("path-to-directory-where-fancybox.sty-located");
```

Depois de executar um trabalho de Tex com esta opção (não se esqueça de ajustar as outras opções conforme necessário), obtemos o documento de saída (ou seja, uma imagem PNG).

![Documento de saída](/tex/images/net/Conversion-RequiredInputFs.png)

Aqui está o código -fonte completo para o exemplo:

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-RequiredInput-FileSystem.cs" >}}

### Entrada necessária arquivada (pacote `pgfplots`)

Digamos agora que temos o seguinte arquivo de LaTeX bastante simples, que é `` requerida-input-zip.tex` da nossa solução de exemplo:


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

Na 3ª linha, podemos ver que o arquivo requer o pacote `pgfplots`, que também não é suportado" nativamente ". Novamente, assumimos que temos os arquivos de origem do pacote `pgfplots`. É um grande número de arquivos divididos entre dois locais se você os encontrar no diretório de instalação de qualquer aplicativo de tipógrafo de LaTeX. Você pode encontrar a pasta `pgfplots` nas pastas`\tex \generic` e `\tex \latex`. E o conteúdo de ambas as pastas deve ser fornecido conforme a entrada necessária para a biblioteca Aspose.TeX. Queremos que esse arquivo de origem seja embalado em um arquivo zip, então aqui está o layout do arquivo:

![Layout do arquivo](/tex/images/net/pgfplots-zip-layout.png)

E é assim que especificamos o acesso a esses arquivos de origem:


```C#
using (Stream zipStream = File.Open("path-to-zip-with-pgfplots-sources"), FileMode.Open))
{
    ...
    options.RequiredInputDirectory = new InputZipDirectory(zipStream);
    ...
}
```

Depois de executar um trabalho de Tex com esta opção, obtemos o documento de saída:

![Documento de saída](/tex/images/net/Conversion-RequiredInputZip.png)

Aqui está o código -fonte completo para o exemplo:

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-RequiredInput-Zip.cs" >}}

> **_NOTA:_** O resultado foi verificado através do pacote `pgfplots` versão 1.18.1. Quanto à versão do pacote `pfg` incluída na biblioteca **Aspose.TeX** é a 3.1.9a.

### Empregando pacotes de fontes externos

Como regra, as distribuições de LaTeX fornecem um conjunto de fontes padrão disponíveis para o tipothting. Exceto essas fontes, **Aspose.TeX** Inclui vários pacotes de fontes não padrão. Por exemplo, `amsfonts`, ` eurosym` e `wasysym '. Como vimos acima, Aspose.TeX também permite empregar pacotes externos. Mas principalmente estávamos conversando sobre pacotes que não contêm fontes.
O **Aspose.TeX** 's*objeto Tex*A extensão do motor precisa de mapas de fonte (que são arquivos de texto em um determinado formato com a extensão `.map` por convenção) para determinar quais fontes físicas correspondem ao nome da fonte interna de cada Tex. Esses mapas de fonte devem ser carregados na memória do TEX durante a fase de inicialização. E, é claro, eles devem estar presentes entre os arquivos do pacote que você está conectando. Como o mecanismo não sabe os nomes de todos os mapas de fonte, ele procura todos os arquivos com a extensão `.map`. Portanto, uma implementação da interface [iInputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/) que é usada como um valor da opção [requerirDutDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) deve fornecer uma maneira de acessar coleções de nomes de arquivos por extensão. Mais especificamente, essa implementação também deve implementar a interface [ifileCollector](https://reference.aspose.com/tex/net/aspose.tex.io/ifilecollector/). As implementações padrão - [InputFilesystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) e [inputzipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/) - já o fazem.

Abaixo, fornecemos um exemplo ilustrativo de um diretório de entrada personalizado que também implementa a interface [ifileCollector](https://reference.aspose.com/tex/net/aspose.tex.io/ifilecollector/). Enquanto focamos em coletar nomes de arquivos por extensão, omitimos intencionalmente os detalhes do armazenamento e recuperação de arquivos.

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-RequiredInputDirectory.cs" >}}

### Restrições

Pode acontecer que um pacote exigido pelo seu arquivo de LaTeX seja desenvolvido no kernel *LateX3e*. Esse pacote provavelmente não funcionará com a biblioteca **Aspose.TeX**, pois este é baseado no kernel *LateX2e*.

Também pode acontecer que um pacote exigido pelo seu arquivo de LaTeX chama diretamente de comandos primitivos dependentes do dispositivo que não são suportados pelo mecanismo **Aspose.TeX** ** da biblioteca *Tex*. Infelizmente, esse pacote não funcionará com certeza.