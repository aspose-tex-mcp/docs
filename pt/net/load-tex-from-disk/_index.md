---
translation: true
template: /_templates/_load-tex-from-disk-net.md
title: Carregando TeX de um disco | API .NET
url: /net/load-tex-from-disk/
description: "Solução de API .NET para trabalhar com TeX. Aprenda no exemplo como carregar um arquivo TeX do disco com algumas linhas de código C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Carregar arquivos de origem TeX do disco
h2: "Solução de API .NET para carregar arquivos TeX/LaTeX do disco"
---

{{<section overview>}}
---
p1: "O TeX é conhecido como uma linguagem de composição. Isso significa que você não formata seu texto no documento, mas insere o texto simples junto com os comandos. Como saída, você obterá o arquivo formatado do formato necessário (especificado). [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) é o núcleo central do sistema de conjunto de publicações (computação tipográfica). Um trabalho TeX é executado em um arquivo TeX especificado explicitamente. Para entender melhor a entrada e saída do TeX, aprenda o [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) da Documentação."
p2: "Como se sabe, o principal objetivo do TeX é ajudar a criar textos matemáticos ou técnicos. Mas antes de qualquer manipulação, o arquivo deve ser carregado primeiro. Aqui você encontrará trechos de código explicando como carregar arquivos fonte TeX do disco usando diretórios do sistema de arquivos para entrada e saída, saída para dispositivo XPS, gravação de saída de terminal para console."
p3: "Para executar os exemplos, precisamos:"
p4: "Aspose.TeX for .NET API, que é uma API de conversão e manipulação de documentos rica em recursos, poderosa e fácil de usar para a plataforma C#."
p5: "Abra o gerenciador de pacotes NuGet, procure por Aspose.TeX e instale. Você também pode usar o seguinte comando do Console do Gerenciador de Pacotes."
---

{{<section feature1>}}
---
title: Etapas para carregar o TeX de um disco C#.
h3: "Código C# para carregar o TeX"
item1: "Crie opções de conversão para um formato personalizado na extensão do mecanismo ObjectTeX usando [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Método de [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Classe."
item2: "Especifique um diretório de trabalho do sistema de arquivos para a entrada. Use a classe [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) para isso."
item3: "Especifique um diretório de trabalho do sistema de arquivos para a saída usando a classe [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)."
item4: "Especifique o console como o terminal de saída usando a classe [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)."
item5: "Especifique um terminal de memória como terminal de saída, se necessário. Para isso, use a classe [*OutputMemoryTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputmemoryterminal/)."
item6: "Execute o trabalho [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Método para [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item7: Refine a saída.
---