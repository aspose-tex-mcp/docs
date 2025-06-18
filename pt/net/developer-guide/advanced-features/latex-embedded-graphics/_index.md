---
translation: true
template: /templates/_template-net.md
title: Gráficos embutidos de LaTeX | Inclua gráficos no código de LaTeX
linktitle: Gráficos embutidos de LaTeX
weight: 18
url: /net/latex-embedded-graphics/
keywords: Incluir Gráficos de LATEX, LATEX INCEDENTE64, LATEX BASE64 GRAPHICS codificados, Write18, Shell-Escape, Comando de Latex Shell
description: Este artigo aborda como incluir imagens codificadas por base64 no código-fonte do LATEX, bem como o recurso \ write18 que torna isso possível.
lastmod: "2025-06-16"
---

{{<section overview>}}

## Outra maneira de incluir imagens

Alguns sistemas TEX/LATEX permitem a inclusão de imagens que não são armazenadas externamente em relação ao próprio arquivo de LaTeX, mas incluídas diretamente dentro do arquivo LATEX. No entanto, como os arquivos TEX/LATEX são arquivos de texto sem formatação e, portanto, não podem conter dados binários, precisamos de uma maneira de representar dados binários no formulário de texto. Em outras palavras, os dados binários devem ser codificados em alguma representação de texto. O problema é que um mecanismo TEX não pode interpretar essas imagens codificadas diretamente. De fato, a inclusão de uma imagem é realizada usando o comando `\incluigraphics`, do pacote `graphicx`. No entanto, esse comando pode lidar apenas com arquivos de imagem externos. Sim, um arquivo de imagem externo (junto com outro arquivo intermediário) ainda será criado fora do arquivo LATEX. O ponto principal é que você só precisa distribuir apenas o arquivo de LaTeX.

Ok, digamos que de alguma forma colocamos uma imagem codificada no arquivo LATEX. Mas como temos a imagem decodificada? Infelizmente, não podemos decodificar o arquivo lendo -o do arquivo LATEX e gravando -o no arquivo de imagem externa. A sequência de texto que representa a imagem codificada deve primeiro ser gravada em um arquivo de texto externo, que pode ser decodificado para produzir um arquivo de imagem.

Até agora, podemos descrever as etapas a seguir para obter o resultado desejado:

1. Codificar a imagem.
2. Injete a sequência de texto representando os dados da imagem no arquivo LATEX.
3. Saia a sequência de texto que representa os dados da imagem para um arquivo externo.
4. Decode o arquivo externo da etapa 3.
5. Inclua a imagem decodificada.

As duas primeiras etapas são concluídas pelo autor do arquivo LATEX. Um mecanismo TEX cuidará das etapas restantes, desde que seja instruído corretamente, é claro.

Vamos começar desde o início. Como podemos codificar nossa imagem para obter uma sequência de caracteres? Um dos métodos para fazer isso (e provavelmente o mais popular) é **base64**.

## Codificação de dados binários usando base64

[**base64**](https://en.wikipedia.org/wiki/Base64) é um grupo de esquemas de codificação binários para texto que transforma dados binários em uma sequência de caracteres imprimíveis, limitados a um conjunto de 64 caracteres únicos. Mais especificamente, os dados binários de origem são tomados 6 bits por vez, então esse grupo de 6 bits é mapeado para um dos 64 caracteres únicos. Como em todos os esquemas de codificação binária ao texto, **base64** foi projetado para transportar dados armazenados em formatos binários em canais que apenas suportam com segurança o conteúdo de texto.

Podemos ver nesta breve explicação que **base64** é o que precisamos. Para codificar um arquivo de imagem para **base64**, você pode usar um utilitário de linha de comando (se disponível no seu sistema operacional), recursos padrão ou de terceiros de quase todas as linguagens de programação ou ferramentas on-line como [base64.guru](https://base64.guru/converter/encode/file) ou similares.

## Colocando a imagem codificada no arquivo de LaTeX

A sequência de caracteres que você obtém como resultado da codificação deve ser colocada no ambiente padrão do LATEX 'FILECONTENTS` no preâmbulo de um arquivo de LaTeX da seguinte forma:


```tex
\documentclass{article}
\begin{filecontents*}[overwrite]{sample-image.64}
iVBORw0KGgoAAAANSUhEUgAAAPgAAABdCAYAAAH/B5vAAAAAGXRFWHRTb2Z0d2FyZQBBZ......
\end{filecontents*}
\begin{document}
...
\end{document}
```

Aqui está. A etapa 2 é realizada. Temos a imagem dentro do arquivo LATEX! Mas o que acontecerá quando executarmos a digitação deste arquivo com o LATEX?

Um processador de LaTeX gravará a sequência de caracteres no ambiente em um arquivo externo chamado `sample-image.64`. Devido ao uso da opção `overwrite`, o arquivo será substituído se já existir (por exemplo, se for produzido por uma execução anterior). E é isso que realiza a Etapa 3 também!
## Decodificar uma string base64

A etapa 4 do nosso plano é onde as diferenças nas implementações de Tex entram em jogo. A decodificação de uma sequência de caracteres Base64 é feita por meio de uma coisa mais comum conhecida como o recurso `\write18`.

### `\write18`

Nos mecanismos clássicos tex, `\write <número> (<Lista de token>)` é o primitivo que escreve uma *lista de tokens *. Quando usado, este primitivo é seguido por um número inteiro. Se esse número for negativo, os tokens serão gravados no arquivo transcript (log). Se o número for maior que `15 `, os tokens serão gravados no terminal. Se o número estiver no intervalo `0..15`, os tokens serão gravados em um arquivo cujo nome é especificado por uma ocorrência anterior do` \ openout` primitivo. O `\ openout <4-bit inteiro> = <nome do arquivo>` Primitivo mapeia um nome de arquivo em um número.

As implementações mais recentes do TEX (como PDF TEX) permitem o uso de `\write18`. Nesse caso, eles interpretam a `<Lista de token> 'como uma linha de comando a ser executada no shell do sistema operacional. Como esse recurso é obviamente um backdoor em potencial, você pode sentir um toque de mistério sempre que for mencionado na documentação relacionada a Tex ou na Internet. Por esse motivo, os executáveis ​​do PDF Tex/LateX têm opções de comando para gerenciar a acessibilidade desse recurso.

Geralmente, existem três níveis de acessibilidade: desativados, ativados com restrições e totalmente ativados.

Em **Aspose.TeX**, existe uma opção de emprego tex chamada `shellmode`, mas existem apenas dois valores adequados:` Noshellescape` e `shellRestritist`. O valor `Noshellescape` significa que o recurso está desativado. O segundo valor indica que qualquer comando que precise ser executado deve ser implementado pelo usuário como uma extensão da classe `executável`. Aqui, não vamos nos aprofundar nos detalhes de tais implementações, mas mencionaremos que a emulação de comando `base64` já foi implementada no Aspose.TeX. Por padrão, você pode encontrar sua instância de protótipo na propriedade `Executables`, da instância da classe` texoptions`.

### Decodificação de dados codificados por base64

Para decodificar o conteúdo de um arquivo que deveria ser alguns dados codificados por Base64, normalmente usaríamos a seguinte linha de comando:


```
base64 -d  FILE1 > FILE2
```

onde o arquivo1 é o arquivo "codificado" e `> file2` significa que a saída deve ser redirecionada para o arquivo` file2`.

Assim, no corpo do nosso arquivo de LaTeX, devemos adicionar a seguinte linha:


```tex
\immediate\write18{base64 -d  sample-image.64 > sample-image.png}
```

> O prefixo `\immediate` é necessário para garantir que a operação `\write` é executada assim que o comando primitivo é encontrado pelo scanner TeX. Caso contrário, será processado no momento do envio da página.

Se executarmos a digitação do arquivo agora, veremos que o arquivo de imagem `sample-image.png` foi criado. Vamos lá, abra -o em um espectador para verificar!

## Incluindo a imagem decodificada

Como mencionamos no início do artigo, para incluir a imagem decodificada, usamos o conhecido comando LATEX `\IncluirGraphics`:


```tex
\includegraphics[options]{sample-image.png}
```

Portanto, o arquivo completo (quase) de LaTeX pode parecer o seguinte:


```tex
\documentclass{article}
\begin{filecontents*}[overwrite]{sample-image.64}
iVBORw0KGgoAAAANSUhEUgAAAPgAAABdCAYAAAH/B5vAAAAAGXRFWHRTb2Z0d2FyZQBBZ......
\end{filecontents*}
\begin{document}
  \write18{base64 -d  sample-image.64 > sample-image.png}
  \includegraphics[options]{sample-image.png}
\end{document}
```

E o código C# usando a API **Aspose.TeX** é semelhante ao de outros artigos, exceto para especificar a opção `shellmode`:

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-EmbeddedBase64EncodedImage.cs" >}}

E agora terminamos o **Etapa 5**. Para exemplos verdadeiramente completos, explore nosso [Projeto de exemplo](https://github.com/aspose-tex/Aspose.TeX-for-.NET).

**Você também pode conferir a conversão gratuita [aplicativo da web](https://products.aspose.app/tex/conversion/latex/) construído com base em [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**