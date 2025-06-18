---
translation: true
template: /templates/_template-java.md
title: Gráficos embutidos de LaTeX | API para Java
linktitle: Gráficos embutidos de LaTeX
weight: 18
url: /java/latex-graphics-embedding/
keywords: Incluir Gráficos de LATEX, LATEX INCEDENTE64, LATEX BASE64 GRAPHICS codificados, Write18, Shell-Escape, Comando de Latex Shell
description: Neste artigo, você explorará como injetar imagens codificadas por Base64 no código-fonte do LATEX e aprender o recurso \ write18 que torna isso possível.
lastmod: "2025-06-16"
---

{{<section overview>}}

## Uma maneira alternativa de incluir imagens

Alguns sistemas TEX/LATEX permitem a inclusão de imagens que não são armazenadas externamente em relação ao próprio arquivo de LaTeX; Em vez disso, essas imagens são incorporadas diretamente no arquivo de LaTeX. No entanto, como os arquivos TEX/LATEX são texto simples e não podem conter dados binários, precisamos de um método para representar dados binários em um formato de texto. Isso significa que os dados binários devem ser codificados em uma representação textual. O desafio é que um mecanismo TEX não pode interpretar diretamente essas imagens codificadas. No final, as imagens são incluídas usando o comando `\incluigraphics` conhecido do pacote `graphicx`, mas esse comando é limitado ao manuseio de arquivos de imagem externos. Portanto, um arquivo de imagem externo (juntamente com um arquivo intermediário adicional) ainda deve ser criado fora do arquivo LATEX, mas isso ocorrerá apenas durante o Typeetting. A vantagem é que você só precisa distribuir o próprio arquivo de LaTeX, em vez de um conjunto de arquivos.

Tudo bem, suponha que de alguma forma tenhamos incorporado uma imagem codificada no arquivo LATEX. Como decodificamos esta imagem? Infelizmente, não podemos decodificá -lo diretamente lendo -o do arquivo LATEX e gravando -o em um arquivo de imagem externo. Em vez disso, a sequência de texto que representa a imagem codificada deve primeiro ser gravada em um arquivo de texto externo, que pode ser decodificado para gerar o arquivo de imagem.

Neste ponto, podemos descrever as seguintes etapas para alcançar o resultado desejado:

1. Codificar a imagem.
2. Insira a sequência de texto que representa os dados da imagem no arquivo LATEX.
3. Escreva a sequência de texto representando os dados da imagem em um arquivo externo.
4. Decode o arquivo externo criado na etapa 3.
5. Inclua a imagem decodificada.

As duas primeiras etapas são realizadas pelo autor do arquivo LATEX. O mecanismo TEX lidará com as etapas restantes, desde que seja instruído adequadamente, é claro.

Vamos passar para **Etapa 1**. Como podemos codificar nossa imagem para obter uma sequência de caracteres? Um dos métodos para fazer isso (e provavelmente o mais popular) é **base64**.

## Codificação de dados binários usando base64

[**base64**](https://en.wikipedia.org/wiki/Base64) é um grupo de esquemas de codificação binários para texto que transforma dados binários em uma sequência de caracteres imprimíveis, usando um conjunto de 64 caracteres únicos. Especificamente, os dados binários de origem são processados ​​em grupos de 6 bits, com cada grupo mapeado para um dos 64 caracteres únicos. Como todos os esquemas de codificação binária ao texto, o Base64 pretende facilitar a transmissão de dados armazenados em formatos binários em canais que suportam predominantemente o conteúdo de texto.

Esta breve explicação mostra que **base64** é exatamente o que precisamos. Para codificar um arquivo de imagem para **base64**, você pode usar um utilitário de linha de comando (se disponível no seu sistema operacional), recursos padrão ou de terceiros de quase todas as linguagens de programação ou ferramentas on-line como [base64.guru](https://base64.guru/converter/encode/file) ou similares.

## Incorporando a imagem codificada no arquivo de LaTeX

A sequência de caracteres gerados a partir do processo de codificação deve ser colocada no ambiente padrão do LATEX `FILECONTENTS` dentro do preâmbulo de um arquivo de LaTeX, como segue:

```tex
\documentclass{article}
\begin{filecontents*}[overwrite]{sample-image.64}
iVBORw0KGgoAAAANSUhEUgAAAPgAAABdCAYAAAH/B5vAAAAAGXRFWHRTb2Z0d2FyZQBBZ......
\end{filecontents*}
\begin{document}
...
\end{document}
```

Aqui está! **Etapa 2** está completo. Incorporamos com sucesso a imagem no arquivo de LaTeX! Mas o que acontecerá quando executarmos a digitação deste arquivo com o LaTeX?
Um processador LATEX gravará a sequência de caracteres do ambiente para um arquivo externo chamado `sample-image.64`. Devido à opção `overwrite`, o arquivo será substituído se já existir (por exemplo, se for criado durante uma execução anterior). É assim que **Etapa 3** também é realizada!

## Decodificar uma string base64

**Etapa 4** do nosso plano é onde as diferenças nas implementações de Tex entram em jogo. A decodificação de uma sequência de caracteres base64 é realizada por meio de uma coisa mais comum conhecida como o recurso `\write18`.

### `\write18`

Nos mecanismos clássicos tex, `\write <número> (<Lista de token>)` é o primitivo usado para escrever uma *lista de tokens *. Quando usado, este primitivo é seguido por um número inteiro. Se o número inteiro for negativo, os tokens serão gravados no arquivo transcript (log). Se o número inteiro for maior que `15 `, os tokens serão enviados ao terminal. Se o número inteiro ficar dentro do intervalo de `0..15`, os tokens serão gravados em um arquivo cujo nome é especificado por uma ocorrência anterior do `\openout` primitivo. O `\openout <4-bit Integer> = <nome do arquivo>` primitivo associa um nome de arquivo a um número.

As implementações mais recentes do Tex, como o PDF TEX, permitem o uso de `\write18`. Nesse caso, eles interpretam a `<token list>` como uma linha de comando a ser executada no shell do sistema operacional. Como esse recurso obviamente representa um risco potencial de segurança, você pode sentir uma pitada de mistério sempre que for referenciado na documentação relacionada a Tex ou na Internet. Por esse motivo, os executáveis ​​PDF Tex/LateX oferecem opções de comando para controlar o ACESS nesse recurso.

Normalmente, existem três níveis de acessibilidade: desativados, ativados com restrições e totalmente ativados.

Em **Aspose.TeX**, existe uma opção de emprego tex chamada `shellmode`, que pode assumir um dos dois valores possíveis:` Noshellescape` e `shellRestritis`. O valor `Noshellescape` indica que o recurso está desativado. O último valor significa que qualquer comando que requer execução deve ser implementado pelo usuário como uma extensão da classe `executável`. Não entraremos nas especificidades de tais implementações aqui, mas é importante observar que a emulação de comando `base64` já foi implementada no Aspose.TeX e está incluída por padrão na propriedade 'Executables' da coleta da instância da classe 'texoptions`.

### Decodificação de dados codificados por base64

Para decodificar o conteúdo de um arquivo que deve conter dados codificados por Base64, normalmente usaríamos a seguinte linha de comando:


```
base64 -d  FILE1 > FILE2
```

onde o arquivo1 é o arquivo "codificado" e o `> file2` redireciona a saída para o arquivo` file2`.

Portanto, devemos incluir a seguinte linha no corpo de nosso arquivo de LaTeX:


```tex
\immediate\write18{base64 -d  sample-image.64 > sample-image.png}
```

> O prefixo `\immediate` é necessário para garantir que a operação `\write` é executada imediatamente quando o scanner TeX encontra esta primitiva. Caso contrário, será processada durante o envio da página.

Se executarmos a digitação do arquivo agora, descobriremos que o arquivo de imagem `sample-image.png` foi criado. Vá em frente e abra -o em um espectador para verificar!

## Incluindo a imagem decodificada

Como observamos no início do artigo, para incluir a imagem decodificada, usamos o conhecido comando LaTeX `\incluirgraphics`:


```tex
\includegraphics[options]{sample-image.png}
```

Portanto, o arquivo completo (quase) de LaTeX pode aparecer o seguinte:


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

E o código Java que utiliza a API **Aspose.TeX** é semelhante ao que pode ser encontrado em outros artigos, com exceção de especificar a opção Modo Shell:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-EmbeddedBase64EncodedImage.java" >}}

E agora **Etapa 5** está completo. Para exemplos verdadeiramente abrangentes, explore nosso [Exemplo de Projeto](https://github.com/aspose-tex/Aspose.TeX-for-Java).

**Você também pode conferir a conversão gratuita [aplicativo da web](https://products.aspose.app/tex/conversion/latex/) construído com base em [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**