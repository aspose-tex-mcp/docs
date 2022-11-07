---
translation: true
template: /_templates/_customize-output-net.md
title: Criar saída personalizada TeX | API .NET
url: /net/customize-output/
description: "Solução de API .NET para trabalhar com TeX. Leia o exemplo de como criar uma saída personalizada para o arquivo TeX com algumas linhas de código C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Personalizar saída
h2: "Solução de API .NET para personalizar a saída de arquivos TeX"
---

{{<section overview>}}
---
p1: "O TeX é conhecido como uma linguagem de composição. Isso significa que você não formata seu texto no documento, mas insere o texto simples junto com os comandos."
p2: "O artigo [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) da Documentação nos ensina que um arquivo TeX não pode conter nenhum dado para compor, mas apenas sequências de controle . No entanto, geralmente contém esses dados, e um arquivo no formato de destino tem o texto composto. O arquivo também terá o mesmo nome do arquivo especificado como entrada e é o arquivo de saída principal. Para o TeX original, este é um arquivo no formato DVI. Chamaremos o nome dos arquivos de entrada e saída sem estender o nome do trabalho."
p3: "Nesta página, você encontrará um exemplo de código explicando a criação de um arquivo de formato TeX personalizado, onde você pode ver como personalizar a saída dos arquivos TeX. Para personalizar a saída de arquivos .tex, precisamos:"
p4: "Aspose.TeX for .NET API, que é uma API de conversão e manipulação de documentos rica em recursos, poderosa e fácil de usar para a plataforma C#."
p5: "Abra o gerenciador de pacotes NuGet, procure por Aspose.TeX e instale. Você também pode usar o seguinte comando do Console do Gerenciador de Pacotes."
---

{{<section feature1>}}
---
title: "Etapas para personalizar a saída do TeX C#:"
h3: "Código C# para personalização de saída do TeX"
item1: "Com a ajuda do método [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) de [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/), crie opções de mecanismo TeX para nenhum formato na extensão do mecanismo ObjectTeX."
item2: "Use a classe [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) para especificar um diretório de trabalho do sistema de arquivos para a entrada."
item3: "Use a classe [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) para especificar um diretório de trabalho do sistema de arquivos para a saída."
item4: "Para criar o novo formato use o método [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/)."
item5: Refine a saída.
---