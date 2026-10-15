---
translation: true
template: /templates/_template-java.md
title: Pacotes de LaTeX externos | Aspose.TeX para Java
linktitle: Pacotes de LaTeX externos
weight: 30
url: /java/external-latex-packages/
description: A API Aspose.TeX para Java permite o uso de pacotes externos, ou seja, os que não estão incluídos na própria biblioteca como pacotes FancyBox ou PGFPlots.
lastmod: "2025-06-16"
---

{{<section overview>}}

## Pacotes de LaTeX externos

Há vários [pacotes comuns de LaTeX](/tex/{{lang.url-fragment}}net/embedded-packages/) incluídos na biblioteca **Aspose.TeX** para Java. Portanto, você não precisa cuidar de como fornecer esses pacotes ao mecanismo Tex da biblioteca. Mas, às vezes (talvez frequentemente), seu arquivo de LaTeX pode exigir um pacote além do pacote "nativamente" suportado "de pacotes. Nesse caso, você pode tentar fornecer a entrada necessária, ou seja, os arquivos de origem do pacote necessário, usando o método [setRequiredInputDirectory ()](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#setRequiredInputDirectory-com.aspose.tex.IInputWorkingDirectory-) da instância da classe [texoptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/). Veremos como isso funciona com dois exemplos.

Defina `inputFile` como o caminho completo do documento LaTeX correspondente e `outputDirectory` como uma pasta de saída existente. Ambos os exemplos de conversão geram PNG a 150 DPI. Importe as classes Aspose.TeX usadas no exemplo escolhido, `com.aspose.tex.rendering.ImageDevice`, `com.aspose.tex.rendering.PngSaveOptions` e, para entrada ZIP, `java.io.InputStream` e `java.nio.file.Files`. Trate ou declare as exceções no método chamador. Aplique uma licença conforme o [guia de licenciamento](/tex/{{lang.url-fragment}}java/licensing/).

### Pacote necessário de entrada necessária (pacote `FancyBox`)

Digamos que temos o seguinte arquivo de LaTeX simples, que é `` requerir-input-f-fs.tex` da nossa [Solução de exemplo](https://GitHub.com/aspose-tex/Aspose.TeX-for-Java):

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
  \begin{Beqnarray}
  y & = & x^2 \\
  a^2 + 2ab + b^2 & = & (a + b)^2 \\
  \int_0^\infty e^{-ax} dx & = & \frac{1}{a}
  \end{Beqnarray}
}
\end{document}
```

A terceira linha requer o pacote externo `fancybox`. Defina `packagesDirectory` como uma pasta local com `fancybox.sty` e suas dependências. O exemplo completo abaixo atribui essa pasta a `RequiredInputDirectory` e gera uma imagem PNG. O dispositivo e os diretórios de trabalho permanecem abertos até o término do trabalho e depois são liberados ou fechados.

![Documento de saída](/tex/images/java/Conversion-RequiredInputFs.png)

Aqui está o código -fonte completo para o exemplo:

{{< gist "aspose-com-gists" "be002eee5d3f1f880cf1b77424b754e1" "Example-RequiredInput-FileSystem.java" >}}

### Entrada necessária arquivada (pacote `pgfplots`)

Vamos agora assumir que temos o seguinte arquivo de LaTeX bastante simples, que é `requerir-input-zip.tex` da nossa solução de exemplo:


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

Na terceira linha, vemos que o arquivo requer o pacote `PGFPLOTS`, que também não é suportado" nativamente ". Novamente, assumimos que temos os arquivos de origem do pacote `PGFPLOTS`. É um grande conjunto de arquivos divididos entre dois locais se você os encontrar no diretório de instalação de qualquer aplicativo de tipógrafo de LaTeX. Você pode encontrar a pasta `pgfplots` nas pastas`\tex \generic` e `\tex \ latex`. E o conteúdo de ambas as pastas deve ser fornecido conforme a entrada necessária para a biblioteca Aspose.TeX. Queremos que esse arquivo de origem seja embalado em um arquivo zip, então aqui está o layout do arquivo:

![Layout do arquivo](/tex/images/java/pgfplots-zip-layout.png)

Defina `packagesZip` como um `java.nio.file.Path` para o arquivo contendo os fontes genéricos e LaTeX do pacote. O exemplo Java completo abaixo o abre com `Files.newInputStream(...)` e atribui um `InputZipDirectory` a `RequiredInputDirectory`. O argumento de caminho base vazio seleciona o arquivo inteiro. Mantenha o fluxo ZIP e o diretório abertos até o término do trabalho TeX e depois os feche. O resultado é uma imagem PNG com os dois gráficos.

![Documento de saída](/tex/images/java/Conversion-RequiredInputZip.png)

Aqui está o código -fonte completo para o exemplo:

{{< gist "aspose-com-gists" "be002eee5d3f1f880cf1b77424b754e1" "Example-RequiredInput-Zip.java" >}}

> **_NOTA:_** O resultado foi verificado através do pacote `pgfplots` versão 1.18.1. Quanto à versão do pacote `pfg` incluída na biblioteca **Aspose.TeX** é a 3.1.9a.

### Usando pacotes de fontes externos

Normalmente, as distribuições de LaTeX vêm com uma seleção de fontes padrão que podem ser usadas para digitar. Além dessas fontes, **Aspose.TeX** oferece vários pacotes de fontes fora do padrão, como `amsfonts`, ` eurosym` e `wasysym`. Como mencionado anteriormente, **Aspose.TeX** também suporta o uso de pacotes externos, embora nosso foco tenha sido principalmente em pacotes que não incluem fontes.
A extensão*Object Tex*Engine em **Aspose.TeX** requer mapas de fonte, que são arquivos de texto com a extensão `.map` que especificam as fontes físicas correspondentes ao nome da fonte interna de cada TEX. Esses mapas de fonte precisam ser carregados na memória do TEX durante a fase de inicialização e devem ser incluídos nos arquivos do pacote. Como o mecanismo não está ciente dos nomes de todos os mapas de fonte, ele procura quaisquer arquivos com a extensão `.map`. Portanto, a implementação da interface [iInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/) usada como o valor da opção [requerirInputDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getRequiredInputDirectory--) deve fornecer uma maneira de acessar coleções de nomes de arquivos com base em sua extensão. Especificamente, essa implementação também deve implementar a interface [ifileCollector](https://reference.aspose.com/tex/java/com.aspose.tex/ifilecollector/). As implementações padrão, [InputFilesystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputfilesystemdirectory/) e [inputzipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputzipdirectory/), já atendem a esse requisito.

O `RequiredInputDirectory` personalizado abaixo implementa ambas as interfaces e lê arquivos locais registrados explicitamente. Salve-o como `RequiredInputDirectory.java` com os imports incluídos. Registre cada arquivo com `storeFileName(...)`, atribua a instância com `options.setRequiredInputDirectory(...)` e feche-a após o trabalho. É um registro plano: os nomes dos arquivos devem ser únicos quando solicitados sem um caminho completo. As extensões são comparadas sem diferenciar maiúsculas e minúsculas; o caminho de coleta opcional seleciona um diretório do sistema de arquivos. Registre todos os arquivos necessários de pacotes, mapas de fontes, métricas e fontes físicas. A coleta torna os mapas detectáveis, mas não fornece dados de fontes ausentes.

{{< gist "aspose-com-gists" "be002eee5d3f1f880cf1b77424b754e1" "Example-RequiredInputDirectory.java" >}}

### Restrições

Um pacote exigido pelo seu arquivo de LaTeX pode ser desenvolvido no kernel *LateX3e*. Esse pacote provavelmente não funcionará com a biblioteca **Aspose.TeX**, pois este é baseado no kernel *LateX2e*.

Além disso, um pacote exigido pelo seu arquivo LaTeX pode chamar diretamente de comandos primitivos dependentes do dispositivo que não são suportados pelo mecanismo **Aspose.TeX** Library *Tex*. Infelizmente, esse pacote não funcionará com certeza.