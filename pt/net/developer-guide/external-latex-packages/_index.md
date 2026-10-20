---
translation: true
template: /templates/_template-net.md
title: Pacotes de LaTeX externos | Aspose.TeX para .NET
linktitle: Pacotes de LaTeX externos
weight: 20
url: /net/external-latex-packages/
description: API Aspose.TeX para .NET permite o uso de pacotes externos, ou seja, os que não estão incluídos na própria biblioteca, como pacotes FancyBox e PGFPlots.
keywords: latex extern packages, aspose tex, .net tex, latex packages, fancybox, pgfplots, required input directory, input zip, custom input directory, TeX conversion
lastmod: "2026-06-17"
---

{{<section overview>}}

## Pacotes de LaTeX externos

A biblioteca **Aspose.TeX** inclui vários [pacotes de LaTeX comuns](/tex/{{lang.url-fragment}}net/embedded-packages/). Portanto, você não precisa se preocupar com como fornecer esses pacotes ao TeX engine da biblioteca. Mas, às vezes (ou com bastante frequência), seu arquivo de LaTeX pode exigir um pacote além do pacote "nativamente" suportado "de pacotes. Se for esse o caso, você pode tentar fornecer a entrada necessária, ou seja, os arquivos de origem do pacote necessário, através da opção [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) da instância da classe [TeXOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/). Veremos como isso funciona com dois exemplos.

### Pacote necessário de entrada necessária (pacote `FancyBox`)

Digamos que temos o seguinte arquivo de LaTeX simples, que é `required-input-fs.tex` da nossa [Solução de exemplo](https://GitHub.com/aspose-tex/Aspose.TeX-for-.NET):


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

Depois de executar um TeXJob com esta opção (não se esqueça de ajustar as outras opções conforme necessário), obtemos o documento de saída (ou seja, uma imagem PNG).

![Documento de saída](/tex/images/net/Conversion-RequiredInputFs.png)

Aqui está o código -fonte completo para o exemplo:

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-RequiredInput-FileSystem.cs" >}}

### Entrada necessária arquivada (pacote `pgfplots`)

Digamos agora que temos o seguinte arquivo de LaTeX bastante simples, que é `required-input-zip.tex` da nossa solução de exemplo:


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

Depois de executar um TeXJob com esta opção, obtemos o documento de saída:

![Documento de saída](/tex/images/net/Conversion-RequiredInputZip.png)

Aqui está o código -fonte completo para o exemplo:

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-RequiredInput-Zip.cs" >}}

> **_NOTA:_** O resultado foi verificado através do pacote `pgfplots` versão 1.18.1. Quanto à versão do pacote `pfg` incluída na biblioteca **Aspose.TeX** é a 3.1.9a.

### Empregando pacotes de fontes externos

Como regra, as distribuições de LaTeX fornecem um conjunto de fontes padrão disponíveis para o tipothting. Exceto essas fontes, **Aspose.TeX** Inclui vários pacotes de fontes não padrão. Por exemplo, `amsfonts`, ` eurosym` e `wasysym '. Como vimos acima, Aspose.TeX também permite empregar pacotes externos. Mas principalmente estávamos conversando sobre pacotes que não contêm fontes.
O **Aspose.TeX** 's*Object TeX*A extensão do motor precisa de mapas de fonte (que são arquivos de texto em um determinado formato com a extensão `.map` por convenção) para determinar quais fontes físicas correspondem ao nome da fonte interna de cada Tex. Esses mapas de fonte devem ser carregados na TeX memory durante a fase de inicialização. E, é claro, eles devem estar presentes entre os arquivos do pacote que você está conectando. Como o mecanismo não sabe os nomes de todos os mapas de fonte, ele procura todos os arquivos com a extensão `.map`. Portanto, uma implementação da interface [IInputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/) que é usada como um valor da opção [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) deve fornecer uma maneira de acessar coleções de nomes de arquivos por extensão. Mais especificamente, essa implementação também deve implementar a interface [IFileCollector](https://reference.aspose.com/tex/net/aspose.tex.io/ifilecollector/). As implementações padrão - [InputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) e [InputZipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/) - já o fazem.

Abaixo, fornecemos um exemplo ilustrativo de um diretório de entrada personalizado que também implementa a interface [IFileCollector](https://reference.aspose.com/tex/net/aspose.tex.io/ifilecollector/). Enquanto focamos em coletar nomes de arquivos por extensão, omitimos intencionalmente os detalhes do armazenamento e recuperação de arquivos.

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-RequiredInputDirectory.cs" >}}

### Restrições

Pode acontecer que um pacote exigido pelo seu arquivo de LaTeX seja desenvolvido no kernel *LaTeX3e*. Esse pacote provavelmente não funcionará com a biblioteca **Aspose.TeX**, pois este é baseado no kernel *LaTeX2e*.

Também pode acontecer que um pacote exigido pelo seu arquivo de LaTeX chame diretamente comandos primitivos dependentes do dispositivo que não são suportados pelo mecanismo Object TeX da biblioteca Aspose.TeX. Infelizmente, esse pacote não funcionará com certeza.

## Criação de um Agente de IA para Otimização de Pacotes LaTeX Incorporado

Se precisar de criar um agente de IA que otimize o conteúdo para o inventário de pacotes integrado sem recuperações de rede dinâmicas e lentas ou pesquisas no sistema de ficheiros durante a geração, pode utilizar o fluxo de trabalho descrito abaixo.

Em vez de obrigar um LLM a adivinhar quais os pacotes que são seguros ou rápidos de utilizar, o agente utiliza este inventário de pacotes pré-compilado específico para garantir uma composição de documentos 100% fiável.

![Arquitetura de Montagem de Documentos Incorporada do Agente de IA](/tex/images/net/tutorial/blockscheme-for-ai-latex-package-optimization.png)

1. Extração da intenção de layout (camada de análise do LLM)
O utilizador fornece dados não estruturados em múltiplos formatos ou diretivas conversacionais. O LLM mapeia os pedidos diretamente para a lista de pacotes incorporados do Aspose (`colortbl` para sombreado de linhas, `geometry` para margens, `hyperref` para espaçamento entre letras e `tabularx` para colunas de largura variável).

2. Isolamento da AST e injeção de preâmbulo
Em vez de escrever importações de pacotes inchadas, o agente verifica os requisitos do código em relação ao seu manifesto pré-armazenado de motores nativos.

Escreve caminhos de otimização estrutural diretamente na string do preâmbulo do código.

3. Isolamento e execução de fluxo (Nó do motor Aspose.TeX)
O fluxo de tokens compilado, juntamente com os seus ambientes de macro, é despachado para os nomes de trabalhadores isolados. O sistema configura um perfil de tempo de execução da aplicação TeXOptions estrito utilizando o perfil de assembly otimizado (por exemplo, TeXConfig.ObjectLaTeX). Executa com segurança um pipeline de execução TeXJob não bloqueante inteiramente dentro do buffer de fluxo de memória.

```tex
\usepackage[a4paper,margin=0.5in]{geometry}
\usepackage{amsmath,tabularx,colortbl,hyperref}
```

4. Serialização de ativos (Camada de renderização de saída)
O sistema mapeia alvos de coordenadas e processa limites de saída, utilizando matrizes de execução vetorial (PdfDevice ou SvgDevice) para devolver layouts de documentação nítidos instantaneamente para a interface do cliente.