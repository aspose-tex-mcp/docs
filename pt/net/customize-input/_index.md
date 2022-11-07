---
translation: true
template: /_templates/_customize-input-net.md
title: Criar entrada personalizada TeX | API .NET
url: /net/customize-input/
description: "Solução de API .NET para trabalhar com TeX. Aprenda no exemplo como criar uma entrada personalizada para o arquivo TeX com algumas linhas de código C#."
keywords: 'entrada personalizada tex net api, C# api para personalizar tex'
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Personalizar entrada
h2: "Solução de API .NET para personalizar a entrada de arquivos TeX"
---

{{<section overview>}}
---
p1: "O TeX é conhecido como uma linguagem de composição. Isso significa que você não formata seu texto no documento, mas insere o texto simples junto com os comandos. Conforme descrito no artigo [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) da Documentação, o trabalho TeX é executado em um arquivo TeX explicitamente especificado. Então, incluímos este arquivo na entrada de um determinado trabalho do TeX."
p2: "Nesta página, você encontrará um exemplo de código explicando como personalizar a entrada de arquivos de origem do TeX levando em consideração que a entrada deve seguir a sintaxe do TeX e, idealmente, conter apenas comandos conhecidos pelo mecanismo."
p3: "Para personalizar a entrada de arquivos .tex, precisamos:"
p4: "Aspose.TeX for .NET API, que é uma API de conversão e manipulação de documentos rica em recursos, poderosa e fácil de usar para a plataforma C#."
p5: "Abra o gerenciador de pacotes NuGet, procure por Aspose.TeX e instale. Você também pode usar o seguinte comando do Console do Gerenciador de Pacotes."
---

{{<section feature1>}}
---
title: "Etapas para personalizar a entrada do TeX C#:"
h3: "Código C# para personalização de entrada TeX"
item1: "Usando [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Método de [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/), crie opções de mecanismo TeX para nenhum formato na extensão do mecanismo ObjectTeX."
item2: "Usando a classe [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/), especifique um diretório de trabalho do sistema de arquivos para a entrada."
item3: "Com a ajuda do método [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/), crie o formato personalizado."
---