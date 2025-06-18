---
translation: true
template: /templates/_template-java.md
title: Como configurar novas fontes | Aspose.TeX para java
linktitle: 6. Como configurar novas fontes
weight: 60
url: /java/latex-fonts-setup/
keywords: LaTeX, fontes de LaTeX, substituição de fontes de LaTeX, configuração de fontes de LaTeX
description: Este artigo abrange a configuração de novas fontes para uso com o LATEX e também inclui um exemplo de definição de fonte.
lastmod: "2025-06-16"
---

{{<section overview>}}

Para configurar novas fontes para uso com o LATEX, você basicamente precisa preencher as tabelas de seleção de fontes internas com as informações necessárias para associar posteriormente uma solicitação de fonte em um documento ao arquivo `.tfm` externo que contém informações de caracteres usadas pelo LATEX. Portanto, as tabelas são responsáveis ​​por associar o arquivo externo `cmdunh10.tfm` com a seguinte solicitação:

```tex
\fontencoding{OT1}\fontfamily{cmdh}\fontseries{m}\fontshape{n}%
\fontsize{10}{12pt}\selectfont
```

Para adicionar novas fontes, você deve reverter o processo. Para cada nova fonte externa, você deve responder a cinco perguntas:

1. Qual é a codificação da fonte - ou seja, quais personagens estão em quais posições?
2. Qual é o nome de sua família?
3. Qual é a sua série (peso e largura)?
4. Qual é a sua forma?
5. Qual é o seu tamanho?

As respostas a essas perguntas fornecerão as informações necessárias para classificar suas fontes externas de acordo com as convenções de LaTeX. Nas próximas seções, discutiremos como inserir novas fontes nas tabelas NFSS para que elas possam ser usadas no texto principal. Você normalmente precisa dessas informações se deseja usar novas fontes, como criar um arquivo de embalagem curto para acessar uma nova família de fontes. Nas seções posteriores, discutiremos conceitos mais complicados que são importantes se você quiser usar, por exemplo, fontes especiais para matemática em vez das padrão.

## 6.1. A convenção de nomenclatura para fontes externas

Um esquema de nomeação de fontes padrão de fato no Tex classifica todos os nomes de arquivos de fontes usando oito caracteres alfanuméricos, onde o caso não é significativo. Esse limite de oito caracteres garante que os mesmos nomes de arquivos possam ser usados ​​em todas as plataformas de computador. O princípio do esquema é descrito na tabela abaixo, onde as peças entre colchetes podem ser omitidas se corresponderem a um padrão. Por exemplo, um tamanho de design é fornecido apenas se a fonte não for escalada linearmente.

![A convenção de nomenclatura para fontes externas](/tex/images/java/tutorial/latex-font-selection-6-1.png)

Abaixo está a classificação das fontes PostScript "básicas" de 35 de acordo com a interface de fonte do LATEX. Para cada fonte, é fornecido o nome completo do Adobe e o nome de arquivo curto correspondente (na classificação atualmente sendo discutida). Para `ot1`, ` t1` ou `ts1`, seria necessário anexar` 7t`, `8t` ou` 8C`, respectivamente, para obter o nome completo do arquivo. Por exemplo, `putr8t` para utopia regular na codificação` t1`.  Isso será útil em uma discussão mais aprofundada.

![Classificação das fontes PostScript](/tex/images/java/tutorial/latex-font-selection-6-2.png)

A Convenção de Nomeação abrange nomes internos de Tex para fontes (ou seja, aquelas usadas em `\declarafontshape` declarações, conforme descrito na próxima seção), nomes para fontes virtuais e seus componentes (por exemplo, refodimentos específicos de fontes físicas) e os nomes das fontes físicas. No caso de fontes PostScript, os nomes de fontes físicos geralmente são diferentes daqueles usados ​​internamente pela TEX.
Neste último caso, os nomes de fontes internos devem ser mapeados para as fontes externas correspondentes quando o resultado de uma execução de LaTeX é visualizado ou impresso. Por exemplo, o driver PostScript `DVIPS` usa arquivos de mapeamento (extensão padrão` .map`) que contêm linhas como

```
putr8r Utopia-Regular "TeXBase1Encoding ReEncodeFont " <8r.enc <putr8a.pfb
```

Dizendo que a fonte `putr8r` pode ser obtida da fonte externa` putr8a.pfb`, reencodendo -a através de um vetor de codificação especial (`8R.Enc`). No entanto, você não encontrará nenhuma referência a esse `putr8r` no arquivo` t1put.fd`, que contém as declarações `\declarafontshape` para a família Utopia na codificação` T1`. O motivo é que o `putr8t` é uma fonte virtual (construída com a ajuda do utilitário` fontinst`) que referências `putr8r`. O último link só pode ser encontrado nas fontes das fontes virtuais.

## 6.2. Como declarar novas famílias de fontes e grupos de forma de fontes

Cada combinação de família/codificação deve ser introduzida no LATEX com a ajuda do comando `\declarafontfamily`, que leva três argumentos. Os dois primeiros são o esquema de codificação e o nome da família. O terceiro geralmente está vazio, mas pode conter opções especiais para carregamento de fontes e é explicado mais neste artigo. Então, se você quiser declarar uma nova família - digamos, Computer Modern Dunhill com a codificação antiga Tex - você escreveria

```tex
\DeclareFontFamily{OT1}{cmdh}{}
```

Normalmente, existem muitas fontes individuais em uma família de fontes. Para reduzir o número de declarações, você deve combinar fontes que diferem apenas no tamanho e as declararem como um grupo em vez de anunciar cada membro da família individualmente.

Esse grupo é inserido nas tabelas internas do LATEX com o comando `\declarafontshape`, que leva seis argumentos. Os quatro primeiros argumentos são o esquema de codificação, o nome da família, o nome da série e o nome da forma sob o qual você deseja acessar essas fontes. O quinto argumento é uma lista de tamanhos e nomes de fontes externos, fornecidos em um formato especial discutido abaixo. O sexto argumento geralmente está vazio e seu uso é explicado mais adiante neste artigo.

Por exemplo, uma entrada de tabela NFSS para o computador moderno Dunhill Mediats no antigo esquema de codificação Tex poderia ser inserido como

```tex
\DeclareFontShape{OT1}{cmdh}{m}{n}{ <10> cmdunh10 }{}
```

Supondo que apenas uma fonte externa para o tamanho 10pt esteja disponível. Se você também tiver essa fonte disponível em 12pt (escalada de 10pt), a declaração seria

```tex
\DeclareFontShape{OT1}{cmdh}{m}{n}{ <10> <12>cmdunh10 }{}
```

Se o arquivo externo estiver disponível em todos os tamanhos possíveis, a declaração se tornará muito simples. É o caso das fontes PostScript (esboço) do tipo 1, ou quando o programa de driver é capaz de gerar fontes sob demanda ligando para o MetaFont.

Por exemplo, Times Roman Roman Bold Tretich no esquema de codificação do LATEX `T1` poderia ser introduzido da seguinte maneira

```tex
\DeclareFontShape{T1}{ptm}{b}{n}{ <-> ptm8t }{}
```

Este exemplo declara uma faixa de tamanho com duas extremidades abertas. Como resultado, o mesmo arquivo externo `ptmb8t.tfm` é usado para todos os tamanhos e é dimensionado para o tamanho desejado. Se você tiver mais de um arquivo `.tfm` para uma fonte - por exemplo,` emtt10` para tamanhos de texto e `emtt12` para tamanhos de exibição (máquina de escrever moderna europeia) - a declaração pode ser

```tex
\DeclareFontShape{T1}{emtt}{m}{n}{<-12> emtt10 <12-> emtt12}{}
```

Nesse caso, o arquivo `emtt10.tfm` seria usado para tamanhos menores que 12pt e` emtt12.tfm` para todos os tamanhos maiores ou iguais a 12pt.

Os exemplos acima demonstram que o quinto argumento do comando `\declarafontshape` consiste em especificações de tamanho cercadas por colchetes de ângulo misturados com informações de carregamento para os tamanhos individuais (por exemplo, nomes de fontes). A peça dentro dos colchetes do ângulo é chamada de INFO *TAMANHO *, e a peça após o suporte de ângulo de fechamento é chamada de *Informações da fonte *.  As informações da fonte são ainda mais estruturadas em uma função de tamanho * (geralmente vazia) e seus argumentos. Dentro dos argumentos de `\declarafontshape`, os espaços em branco são ignorados para tornar as entradas mais legíveis. Em circunstâncias incomuns, quando um espaço real deve ser inserido, você pode usar o comando `\space`.

### Tamanhos e intervalos de tamanho simples

O tamanho infos pode ser dividido em tamanhos simples e *faixas de tamanho*. Um tamanho simples é dado por um número único (decimal), como `<10>` ou `<17.28>`, e pode ter algum valor positivo. No entanto, você provavelmente não encontrará valores inferiores a 4 ou superior a 120 porque o número representa um tamanho de fonte medido em pontos. Uma faixa de tamanho é dada por dois tamanhos simples separados por um hífen, para indicar uma variedade de tamanhos de fonte que compartilham as mesmas informações de fonte. O limite inferior está incluído no intervalo, enquanto o limite superior é excluído. Por exemplo, `<5-10>` significa tamanhos maiores ou iguais a 5pt e menos de 10pt. É possível omitir o número em qualquer tamanho do hífen em uma faixa de tamanho: `<->` significa todos os tamanhos possíveis, `<-10>` representa todos os tamanhos menores que 10pt, e `<2->` significa todos os tamanhos maiores ou iguais a 12pt.
Vários tamanhos simples geralmente têm as mesmas informações de fonte. Nesse caso, uma abreviação conveniente é omitir todos, exceto a última informação:

```tex
\DeclareFontShape{OT1}{panr}{m}{n}{ <5> <6> <7> <8> <9> <10>
    <10.95> <12> <14.4> <17.28> <20.74> <24.88> pan10 }{}
```

Isso declara o meio de Roman Pandora, disponível em vários tamanhos, todos produzidos pela escalagem do mesmo tamanho de design.

### Funções de tamanho

Como mencionado acima, as informações da fonte são ainda mais estruturadas em uma função de tamanho e seu argumento. Se um `*`aparecer na sequência de informações da fonte, tudo à esquerda forma o nome da função e tudo à direita é o argumento. Se não houver asterisco, como em todos os exemplos até agora, toda a string é considerada como o argumento, e o nome da função está *vazio*.

As funções de tamanho produzem a especificação necessária para o LaTeX encontrar a fonte externa e carregá -la no tamanho desejado. Esse processo é baseado no tamanho solicitado pelo usuário e nas informações no comando `\declarafontshape`. As funções de tamanho também são responsáveis ​​por notificar o usuário sobre eventos especiais. Por exemplo, algumas funções diferem apenas se emitem avisos. Esse recurso permite que o mantenedor do sistema configure o LaTeX da maneira mais adequada para o site específico.

O nome de uma função de tamanho consiste em zero ou mais letras. Algumas das funções de tamanho podem levar dois argumentos: um opcional e um obrigatório. Um parâmetro opcional deve ser incluído em colchetes. Por exemplo, a seguinte especificação selecionaria, para todos os tamanhos possíveis, a função de tamanho `s` com o argumento opcional` 0.9 'e o argumento obrigatório `cmfbi10`:

```tex
<-> s * [0.9] cmfib8
```

As especificações de tamanho em `\declarafontshape` são inspecionadas na ordem em que são fornecidos. Quando uma informação de tamanho corresponde ao tamanho solicitado, a função de tamanho correspondente é executada. Se esse processo produzir uma fonte válida, nenhuma entrada adicional será inspecionada. Caso contrário, a pesquisa continua com a próxima entrada. As funções de tamanho padrão estão listadas abaixo.

**A função "vazia"** A função vazia carrega as informações da fonte exatamente no tamanho solicitado, se for um tamanho simples. Se houver um intervalo de tamanho e o tamanho solicitado pelo usuário se enquadra nesse intervalo, ele carrega a fonte exatamente no tamanho do usuário.
Por exemplo, se o usuário solicitar `14.4`, então a especificação

```tex
<-> panr10
```

Carregaria o arquivo `panr10.tfm` em 14.4pt. Todos os valores no arquivo `.tfm` são dimensionados em 1,44 porque essa fonte foi projetada para 10pt.

Às vezes, você pode querer carregar uma fonte em um tamanho ligeiramente diferente da solicitada pelo usuário. Esse ajuste pode ser necessário quando as fontes de uma família parecem ser muito grandes em comparação com as fontes de outras famílias usadas no mesmo documento. Para esse fim, a função de tamanho vazio permite que um argumento opcional especifique um fator de escala multiplicado pelo tamanho solicitado para produzir o tamanho real a ser carregado.

Por isso, 

```tex
<-> [0.95] phvr8t
```

sempre carregaria o arquivo `phvr8t.tfm` (helvetica na codificação` t1`) a 95% do tamanho solicitado. Se o argumento opcional for usado, a função de tamanho vazio emitirá um aviso para notificar o usuário de que a fonte não está sendo carregada no tamanho pretendido.

**A função "S"** A função `s` faz o mesmo que a função vazia, exceto que nenhuma mensagem será gerada no terminal. As mensagens ainda serão gravadas no arquivo de transcrição, para que você possa descobrir quais fontes foram usadas se algo der errado.

**A função "gen"** nomes de fontes externos são frequentemente construídos anexando o tamanho da fonte a uma string que representa o tipo de letra. Por exemplo, `cmtt8`, ` cmtt9` e `cmtt10` são os nomes externos da máquina de escrever moderna do computador Fonts em 8, 9 e 10pt, respectivamente. Com os nomes de fontes organizados de acordo com esse esquema, você pode usar a função `gen 'para reduzir a entrada. Esta função combina as informações da fonte e o tamanho solicitado para gerar os nomes de fontes externos. Assim, se você escrever

```tex
<8> <9> <10> gen * cmtt
```

isso seria uma abreviação para
```tex
<8> cmtt8 <9> cmtt9 <10> cmtt10
```

que salva oito caracteres nas tabelas NFSS internas. Esta função combina ambas as partes literalmente, portanto, você não deve usá -la com tamanhos decimais como `14.4`. Você também deve garantir que os dígitos no nome da fonte externa realmente representem o tamanho do design (por exemplo, `CMR17` é na verdade o Computer Modern Roman em 17.28pt).

Em todos os outros aspectos, a função `gen 'se comporta como a função vazia. Ou seja, o argumento opcional, se especificado, representa um fator de escala e, se usado, gera uma mensagem de informação.

**A função "sgen"** A função `sgen` é a versão silenciosa da função Gen. Ele grava qualquer mensagem apenas no arquivo de transcrição.

**A função "genb"** Essa função de tamanho é semelhante à GEN, mas é destinada a fontes nas quais o tamanho é codificado no nome da fonte nos centriptonos, como as fontes CE. Como conseqüência, uma linha como 

```tex
<9> <10> <10.95> <12> genb * ecrm
```

atua como uma abreviação

```tex
<9> ecrm0900 <10> ecrm1000 <10.95> ecrm1095 <12> ecrm1200
```

Um argumento opcional, se presente, terá o mesmo efeito que teria com a função vazia.

**A função "sgenb"** A função `sgenb` é a versão silenciosa da função` genb`. Ele grava qualquer mensagem apenas no arquivo de transcrição.

**A função "sub"** A função `sub` é usada para substituir um grupo de forma de fonte diferente se não houver fonte externa para o grupo atual da forma da fonte. Nesse caso, o argumento não é um nome de fonte externo, mas uma família, série e combinação de formas diferentes, separadas por barras. Por exemplo, o computador SANS Modern não tem formato em itálico, apenas uma forma inclinada. Portanto, é razoável declarar a forma inclinada como substituto do itálico:

```tex
\DeclareFontShape{OT1}{cmss}{m}{it}{ <-> sub * cmss/m/sl }{}
```

Sem essa declaração, o mecanismo de substituição automática do LATEX substituiria a forma padrão, o computador moderno sem vertical.

Existem outros bons usos para a função `sub`. Veja o seguinte código:

```tex
\DeclareFontShape{OT1}{cmss}{m}{sl}{ <-8> sub * cmss/m/n
   <8> cmssi8 <9> cmssi9 <10><10.95> cmssi10 <12><14.4> cmssi12
   <17.28><20.74><24.88> cmssi17 }{}
```

Esta declaração afirma que, para tamanhos menores que 8pt, o LaTeX deve procurar a declaração da forma da fonte para `ot1/cmsS/m/n`. Tais substituições podem ser acorrentadas. Por exemplo, não existe uma fonte moderna do computador menor que 8pt; portanto, o grupo de forma de fonte substituído provavelmente conterá outra entrada de substituição. No entanto, o uso desse método tem a vantagem de que, quando você obtém uma fonte adicional, é necessário alterar apenas uma declaração de grupo de forma de fonte - outras declarações que usam essa fonte se beneficiarão automaticamente.

**A função "ssub"** A função `ssub` tem a mesma funcionalidade que a sub-função, mas não produz avisos na tela (o primeiro 's' significa" silencioso ").

**A função "Subf"** A função `subf` carrega fontes da mesma maneira que a função vazia, mas produz um aviso de que essa operação foi feita como uma substituição porque a forma da fonte solicitada não está disponível. Esta função pode ser usada para substituir algumas fontes externas sem a necessidade de declarar um grupo de forma de fonte separado para elas, como no caso da função `sub`. Por exemplo, 

```tex
\DeclareFontShape{OT1}{ptm}{bx}{n}{ <-> subf * ptmb7t }{}
```

alertaria o usuário que a combinação solicitada não está disponível e, portanto, que a fonte `ptmb7t` foi carregada. Como isso é menos informativo do que usar a função `sub`, o último deve ser preferido.

**A função "ssubf"** A versão silenciosa do `subf`, esta função grava suas mensagens apenas no arquivo de transcrição.

**A função "fixo"** Esta função ignora o tamanho solicitado e, em vez disso, carrega a fonte externa dada como argumento. Se presente, o argumento opcional indica o tamanho (em pontos) em que a fonte será carregada. Assim, essa função permite especificar faixas de tamanho para as quais uma fonte em algum tamanho fixo será carregada.

**A função "sfixed"** A versão silenciosa de `fix`, esta função é usada, por exemplo, para carregar a fonte que contém os grandes símbolos de matemática, que geralmente estão disponíveis apenas em um tamanho.

### Opções de carregamento de fontes
Como mencionado acima, cada família de fontes precisa ser declarada usando o comando `\declarafontfamily`. O argumento deste comando, bem como o sexto argumento para `\declarafontshape`, pode ser usado para especificar operações especiais que são realizadas quando uma fonte é carregada. Dessa forma, você pode alterar os parâmetros associados a uma fonte como um todo.

Além das informações sobre cada caractere, a TEX mantém para cada fonte externa um conjunto de dimensões globais e outros valores associados à fonte. Por exemplo, toda fonte tem seu próprio "personagem de hífen", o personagem que é inserido quando a Tex hifenata uma palavra. Outro exemplo é a largura normal e a extensão do espaço em branco entre as palavras; Um valor é mantido para cada fonte e alterado sempre que o Tex muda para uma nova fonte. Ao alterar esses valores no momento em que a fonte é carregada, efeitos especiais podem ser alcançados.

Normalmente, as mudanças se aplicam a uma família inteira; Por exemplo, você pode proibir a hifenação para todas as palavras Typenet na família da máquina de escrever. Nesse caso, o terceiro argumento de `\declarafontfamily` deve ser usado. Se as alterações se aplicarem apenas a um grupo de formas de fonte específico, você deverá usar o sexto argumento de `\declarafontshape`. Em outras palavras, quando uma fonte é carregada, o NFSS aplica primeiro o argumento de `\declarafontfamily` e depois o sexto argumento de `\declarafontshape`, para que possa substituir as opções de carga especificadas para toda a família, se necessário.

Com `\hyphenchar \ font = <número>`, tex especifica o caractere usado para hifenação. O `<Number>` representa a posição desse caractere dentro do esquema de codificação. O padrão é o valor de `\defaulthyphenchar`, que é` 45`, representando a posição do caractere'-'na maioria dos esquemas de codificação. Se você definir esse número como `-1`, a hifenação será suprimida. Portanto, declarando

```tex
\DeclareFontFamily{0T1}{cmtt}{\hyphenchar\font=-1}
```

Você pode suprimir a hifenação para todas as fontes na família `cmtt` com o esquema de codificação` ot1`. Fontes com a codificação `T1` têm um caractere de hífen alternativo na posição 127, para que você possa definir, por exemplo,

```tex
\DeclareFontFamily{T1}{cmr}{\hyphenchar\font=127}
```

O que torna o caractere de hífen diferente do painel de palavras compostas inserido em palavras como "chamado". O TEX não hifenata palavras que já contêm caracteres explícitos de hífen (exceto logo após o hífen), o que pode ser um problema nos idiomas nos quais o comprimento médio da palavra é muito maior do que em inglês. Com as configurações acima, esse problema pode ser resolvido.

Toda fonte Tex possui um conjunto associado de dimensões, que são alteradas por atribuições do formulário `\fontdimen <número Os valores padrão são recuperados do arquivo `.tfm` quando a fonte é carregada. Cada fonte tem pelo menos sete dessas dimensões:

* `\fontdimen1` especifica a inclinação por ponto dos caracteres. Se o valor for zero, a fonte estará na vertical.

* `\fontdimen2` especifica a largura normal de um espaço usado entre palavras (espaço entre palavras).

* `\fontdimen3` Especifica a extensão adicional do espaço entre palavras, que é a quantidade extra de espaço em branco que o TEX pode adicionar ao espaço entre as palavras para produzir linhas justificadas em um parágrafo. Em uma emergência, a TEX pode adicionar mais espaço do que esse valor permitido; Nesse caso, uma caixa * Underfull * será relatada.

* `\fontdimen4` especifica a contração permitida do espaço entre palavras, que é a quantidade de espaço que a TEX pode subtrair do espaço integral normal (\ Fontdimen2) para produzir linhas justificadas em um parágrafo. A TEX nunca encolherá o espaço entre palavras para menos do que esse mínimo.

* `\fontdimen5` especifica a *x-height *. Ele define a dimensão orientada para a fonte `1ex`.

* `\fontdimen6` especificou a largura * quad *. Ele define a dimensão orientada para a fonte `1em`.
* `\fontdimen7` especifica a quantidade pretendida como espaço extra a ser adicionado após certos caracteres de pontuação de final de sentença quando`\não-Frenchspacing` estiver em vigor. É sempre ignorado ou melhor, substituído pelo valor `\ xspaceskip` quando esse valor é diferente de zero.

Quando você altera o espaçamento entre palavras associado a uma fonte, não pode usar um valor absoluto, porque esse valor deve ser utilizável para todos os tamanhos em um grupo de forma. Portanto, você deve definir o valor usando algum outro parâmetro que depende da fonte. Você poderia dizer, por exemplo,

```tex
\DeclareFontShape{0T1}{cmr}{m}{n}{...}
   {\fontdimen2\font=.7\fontdimen2\font}
```

Esta declaração reduz o espaço integral normal para 70% do seu valor original. Da mesma forma, a extensão e a redução podem ser alteradas.

Algumas fontes em fórmulas precisam de mais de sete dimensões da fonte. Ou seja, as fontes de símbolo chamadas de `símbolos` e` largesymbols`. A TEX não será capaz de digitar uma fórmula se essas fontes tiverem menos de 22 e 13 parâmetros `\fontdimen`, respectivamente. Os valores desses parâmetros são usados ​​para posicionar os caracteres em uma fórmula matemática.

Há uma otimização infeliz no sistema TEX: Tex carrega todos os arquivos `.tfm` apenas uma vez para um determinado tamanho. Portanto, é impossível definir um grupo de forma de fonte (com o comando `\declarafontshape`) para carregar alguma fonte externa - digamos,` cmtt10` - e usar outro comando `\declarafontshape` para carregar os mesmos parâmetros externos, que altera os parâmetros de` `Fontdimen '. Uma tentativa de fazer isso altera os valores para os dois grupos de forma de fonte.

Por exemplo, suponha que você tente definir uma forma de fonte com espaçamento apertado, tornando o espaço entre palavras menor:

```tex
\DeclareFontShape{T1}{ptm}{m}{n}{ <-> ptmr8t }{}
\DeclareFontShape{T1}{ptm}{c}{n}{ <-> ptmr8t }
                     {\fontdimen2\font=.7\fontdimen2\font}
```

Esta declaração não funcionará. O espaçamento entre palavras para a forma média mudará quando a forma apertada for carregada com os valores especificados lá, e não é isso que se espera. A melhor maneira de lidar com essa situação é definir uma fonte virtual que contém os mesmos caracteres da fonte original, mas difere nas configurações das dimensões da fonte. Outra solução possível é carregar a fonte em um tamanho ligeiramente diferente, como na seguinte declaração:

```tex
\DeclareFontShape{T1}{ptm}{c}{n}{ <-> [0.9999] ptmr8t }
                 {\fontdimen2\font=.7\fontdimen2\font}
```

Esse método os torna diferentes fontes para Tex com parâmetros separados `\fontdimen`, alternativamente, nesse caso em particular, você pode controlar o espaço entre palavras definindo `\spaceskip`, substituindo assim os valores da fonte.

## 6.3. Como modificar as famílias de fontes e grupos de forma de fontes

Se for necessária uma declaração de forma de fonte fora do padrão para um documento específico, essa declaração privada deverá ser colocada em um pacote ou no preâmbulo do documento. Ele substituirá qualquer declaração existente para a combinação de formas de fonte. No entanto, é importante que o uso de `\declarafontfamily` impeça um carregamento posterior do arquivo `.fd` correspondente (discutido posteriormente neste artigo). Além disso, essa nova declaração não afeta as fontes que já estão carregadas.

## 6.4. Como declarar um novo esquema de codificação de fonte

As alterações de fonte que envolvem alterações no esquema de codificação requerem certas precauções. Na codificação `T1`, por exemplo, a maioria das letras acentuadas tem seus próprios glifos, enquanto na codificação tradicional de texto tex (` ot1`), letras acentuadas devem ser geradas a partir de letras e sotaques usando o `\ \ Accent` primitivo. Se as duas abordagens precisarem ser mistas, talvez porque uma fonte esteja disponível apenas em uma das codificações, a definição de um comando como `\" `deve se comportar de maneira diferente, dependendo da codificação atual da fonte.

É por isso que cada codificação de fonte deve ser formalmente introduzida no LATEX com um comando `\declareFontecnoding`, que leva três argumentos. O primeiro argumento é o nome da codificação, que mais tarde será usada para acessar a codificação com o comando `\fontecoding`. A lista de [esquemas de codificação padrão](/tex/{{lang.url-fragment}}java/latex-fonts-low-level/#choosing-the-encoding) e seus nomes internos é fornecida na tabela na Seção 5.1.
O segundo argumento contém qualquer código (como definições) a ser executado sempre que o LATEX muda de um codificando para outro usando o comando `\fontecoding`. O último argumento contém código a ser usado sempre que a fonte é acessada como um alfabeto matemático. Assim, esses três argumentos podem ser usados ​​para redefinir os comandos que dependem das posições dos caracteres na codificação.

O projeto LATEX3E se reserva o uso de codificações começando com as seguintes cartas:

* `T` - codificações de texto padrão com 256 caracteres.
* `Ts` - símbolos projetados para estender a codificação` t` correspondente.
* `X` - codificações de texto que não estão em conformidade com os requisitos estritos para codificações` T`.
* `M` - codificações de matemática padrão com 256 caracteres.
* `S` - Outras codificações de símbolos.
* `A` - Outras aplicações especiais.
* `Ot` - codificações de texto padrão com 128 caracteres.
* `Om` - codificações de matemática padrão com 128 caracteres.

A letra `o` enfatiza que as codificações de 128 caracteres são antigas e *obsoletas *. Idealmente, essas codificações serão substituídas por padrões definidos pelo grupo de usuários TEX, para que, no futuro, uma mudança de codificação seja necessária apenas se estiver mudando de um idioma para outro.

Ao declarar suas próprias codificações privadas, você deve escolher nomes começando com `l` para" local "ou` e` para "experimental". As codificações começando com `u` são para codificações" desconhecidas "ou" não classificadas " - ou seja, para fontes que não se encaixam em um padrão de codificação comum. A Convenção de Nomeação Introduzida garante que os arquivos usando codificações oficiais sejam portáteis.

O comando `\declararFonteCoding`armazena o nome da codificação recém -declarada no comando`\lastDecLaredEncoding`. Às vezes, isso é útil quando você está declarando outras informações de codificação relacionadas e, por exemplo, é usado nos arquivos de declaração de codificação para os idiomas cirílicos.

Além disso, como mencionamos na discussão da substituição de fontes no artigo anterior, os valores padrão da família, série e forma podem precisar ser diferentes para diferentes codificações. Para esse caso, o NFSS fornece o comando `\declarafontsubstitution`, que toma a codificação como o primeiro argumento. Os próximos três argumentos são os valores padrão (associados a essa codificação) para a família, série e forma para uso no processo de substituição automática. É importante que esses três argumentos devam formar uma forma de fonte válida. Em outras palavras, existe uma declaração `\declarafontshape` para eles. Caso contrário, uma mensagem de erro será emitida quando o NFSS verificar suas tabelas internas em `\ BEGIN {Document}`.

## 6.5. Organização de arquivos interna

As famílias de fontes podem ser declaradas quando um arquivo de formato é gerado, declarado no preâmbulo do documento ou carregado sob demanda quando um comando de mudança de fonte no documento solicita uma combinação que ainda não tenha sido usada. A primeira maneira leva ao consumo de memória interna em todas as corridas de LaTeX, mesmo que a fonte não seja usada. As duas últimas opções demoram um pouco mais durante a formatação do documento, porque as definições de fonte precisam ser lidas em tempo de execução. No entanto, as últimas soluções são preferíveis para a maioria dos grupos de forma, porque permitem que você digita uma ampla variedade de documentos com um único formato de LaTeX.

Quando o arquivo de formato está sendo gerado, o LATEX lê um arquivo chamado `fontText.ltx`, que contém o conjunto padrão de definições da família de fontes e algumas outras declarações relacionadas às fontes de texto.
Todas as outras definições da família de fontes devem ser declaradas em arquivos externos carregados sob demanda: arquivos de pacote ou arquivos de definição de fontes (`.fd`).  Se as definições da família de fontes forem colocadas em um arquivo de pacote, você deverá carregar explicitamente este pacote após o comando `\documentClass`. No entanto, existe uma terceira possibilidade: sempre que o NFSS recebe uma solicitação para uma família de fontes `foo` em um esquema de codificação` bar`, e não sabe nada sobre essa combinação, ele tentará carregar um arquivo chamado `Barfoo.fd`. Se esse arquivo existir, deve conter definições de grupo de formato de fontes para a família `foo` no esquema de codificação` bar` - isto é, declarações da forma

```tex
\DeclareFontFamily{BAR}{foo}{...}
\DeclareFontShape{BAR}{foo}{...}{...}{...}{...}
...
\endinput
```

É assim que se torna possível declarar um grande número de famílias de fontes para LaTeX sem preencher uma memória valiosa com informações que provavelmente nunca são usadas.

Cada arquivo `.fd` deve conter todas as definições de fonte para uma família de fontes em um esquema de codificação. No arquivo, deve haver uma ou mais declarações `\declarafontshape` e exatamente uma declaração`\declarafontfamily`. Nenhuma outra definição deve aparecer no arquivo, exceto talvez uma declaração `\fornecefile` ou algumas instruções` \ typeout`, informando ao usuário sobre o carregamento da fonte. Em vez do comando `\typeout`, você pode usar o comando PLAIN TEX` \ wlog`, que grava seu argumento apenas no arquivo de transcrição. Informações detalhadas no arquivo de transcrição devem ser geradas por todos os arquivos `.fd` que são usados ​​na produção, porque analisar essa transcrição ajudará a identificar erros, fornecendo informações sobre os arquivos e suas versões usadas em um trabalho específico. Se os comandos `\typeout` ou` \ wlog` forem usados, é importante lembrar que os espaços e as linhas vazias em um arquivo `.fd` serão ignoradas. Portanto, é necessário usar o comando `\space` no argumento para` \ typeout` ou `\ wlog` para obter um espaço em branco na tela e no arquivo de transcrição.

Novos esquemas de codificação não podem ser introduzidos através do mecanismo `.fd`. O NFSS rejeitará qualquer solicitação para alternar para um esquema de codificação que não foi declarado explicitamente no formato LATEX (ou seja, `FontText.ltx`), em um arquivo de pacote ou no preâmbulo do documento.

## 6.6. Como declarar novas fontes para uso em matemática

### Como especificar tamanhos de fonte

Para cada tamanho de texto, o NFSS mantém [três tamanhos usados ​​para fórmulas matemáticas com tipo de composição](/tex/{{lang.url-fragment}}java/latex-math-fractions-binomial-styles/): o tamanho para digitar a maioria dos símbolos (selecionados por `\textstyle` ou`\displaystyle`); o tamanho para subscritos e superscritos de primeira ordem (`\scriptstyle`); e o tamanho para subscritos e superscritos de ordem superior (`\scriptscriptstyle`). Se você mudar para um novo tamanho de texto para o qual os tamanhos de matemática correspondentes ainda não são conhecidos, o NFSS tentará calculá -los como frações do tamanho do texto. Se você não deseja que o NFSS calcule esses tamanhos, poderá especificar os valores corretos por meio de `\declaremathSizes`. Esta declaração leva quatro argumentos: o tamanho do texto externo e os três tamanhos de matemática para o tamanho deste texto. Por exemplo, a declaração a seguir define os tamanhos de matemática para que o tamanho 14pt (título) seja 14pt, 10pt e 7pt, respectivamente::

```tex
\DeclareMathSizes{14}{14}{10}{7}
```

Outra declaração abaixo (para títulos de um nível superior) informa o NFSS que nenhum tamanho de matemática é necessário para o tamanho do texto de 36pt. Isso pode ajudar a evitar o carregamento desnecessário de muitas fontes.

```tex
\DeclareMathSizes{36}{}{}{}
```

### Como adicionar novos símbolos

Já discutimos como usar [comandos do alfabeto matemático](/tex/{{lang.url-fragment}}java/latex-math-fonts/#81-math-alphabet-identifiers) para produzir letras com formas especiais em uma fórmula. Aqui, mostraremos como adicionar fontes contendo símbolos especiais, chamados *fontes de símbolo *e como tornar esses símbolos acessíveis nas fórmulas.

A adição de novas fontes de símbolo é semelhante à declaração de um novo identificador de alfabetismo matemático: `\declaresymbolfont` define os padrões para todas as versões de matemática,`\setSymbolfont` substitui os padrões de uma versão específica.

As fontes de símbolo de matemática são acessíveis por meio de um nome simbólico. Por exemplo, se você deseja instalar a fonte AMS `msbm10` (consulte o gráfico de glifos abaixo), primeiro você deve divulgar o tipo de letra no NFSS usando as declarações descritas nas seções anteriores.

![MSBM10 GLYPH GLAT](/tex/images/java/tutorial/latex-font-selection-6-3.png)

Essas instruções seriam como

```tex
\DeclareFontFamily{U}{msb}{}
\DeclareFontShape{U}{msb}{m}{n}{ <5> <6> <7> <8> <9> gen * msbm
        <10> <10.95> <12> <14.4> <17.28> <20.74> <24.88> msbm10}{}
```

e geralmente são colocados em um arquivo `.fd`. Então, você deve declarar essa fonte de símbolo para todas as versões de matemática pelo seguinte comando:

```tex
\DeclareSymbolFont{AMSb}{U}{msb}{m}{n}
```

Ele torna o grupo de forma da fonte `u/msb/m/n` disponível como uma fonte de símbolo sob o nome`amsb`. Se houvesse uma série ousada nesta família de fontes (na verdade, não existe), você poderia alterar posteriormente a configuração da versão em matemática ousada dizendo

```tex
\SetSymbolFont{AMSb}{bold}{U}{msb}{b}{n}
```

Depois de cuidar das declarações da fonte, você pode usar essa fonte de símbolo no modo de matemática. Mas como dizer ao NFSS que, por exemplo, o comando `\LessDot` no modo matemático deve produzir o símbolo correspondente na saída? Para fazer isso, você precisa apresentar seus próprios nomes de símbolos ao NFSS usando `\declaremathsymbol`:

```tex
\DeclareMathSymbol{cmd}{type}{symbol-font}{slot}
```

O primeiro argumento é o nome do comando que você escolhe. O segundo argumento é um dos comandos mostrados na tabela abaixo e determina a natureza do símbolo, que, por sua vez, determina a quantidade de espaço que o LaTeX coloca em torno do símbolo quando ocorre em uma fórmula.

![Tipos de objetos matemáticos](/tex/images/java/tutorial/latex-font-selection-6-4.png)

Aliás, exceto para `\mathalpha`, esses comandos podem ser usados ​​nas fórmulas matemáticas como funções com um argumento; nesse caso, espancam seu argumento (possível complexo) como se fosse do tipo correspondente.

O terceiro argumento identifica a fonte do símbolo da qual o símbolo deve ser buscado - isto é, o nome simbólico definido pelo comando `\declaresymbolfont`. O quarto argumento fornece a posição do símbolo na codificação da fonte, como valor decimal, octal ou hexadecimal. Você pode descobrir facilmente as posições de todos os glifos nesta fonte do gráfico de glifos acima. Por exemplo, `\lessDot` pode ser declarado como

```tex
\DeclareMathSymbol{\lessdot}{\mathbin}{AMSb}{"6c}
```

Em vez de um nome de comando, você pode usar um único caractere como o primeiro argumento. Por exemplo, o pacote `eulervm` tem várias declarações do formulário

```tex
\DeclareMathSymbol{0}{\mathalpha}{letters}{"30}
```

Para especificar de onde buscar os dígitos.

O comando `\declaraMathSymbol` especifica uma posição em alguma fonte de símbolo. Portanto, é importante que todas as fontes externas associadas a essa fonte de símbolo por meio dos comandos `\declaraymbolfont` e `\setSymbolfont` tenham o mesmo caráter nessa posição. A maneira mais simples de garantir que isso seja usar apenas fontes com a mesma codificação (a menos que seja `u`, ou desconhecida, codificando, pois duas fontes nessa codificação não precisam conter os mesmos caracteres).

No gráfico de glifos acima, você também pode encontrar letras "Blackboard Bold" (ABC ... começando na posição `'101`). Se você deseja usar essas letras como um alfabeto de matemática, poderá defini -las usando `\declaraMathalphabet`. No entanto, se essa fonte de símbolo já estiver carregada, é melhor usar um atalho para acessar símbolos individuais:

```tex
\DeclareSymbolFontAlphabet{\mathbb}{AMSb}
```

Ou seja, você fornece o nome do seu identificador de alfabetos matemáticos e o nome simbólico da fonte de símbolo declarada anteriormente.

Uma razão importante para não carregar fontes desnecessariamente duas vezes é que existe um limite superior de 16 fontes matemáticas que podem ser ativas a qualquer momento no Tex. Ao calcular esse limite, cada fonte de símbolo conta; Os alfabetos de matemática contam apenas se forem realmente usados ​​no documento e contam localmente em cada versão matemática. Portanto, se oito fontes de símbolos forem declaradas, você poderá usar no máximo oito (possivelmente diferentes) identificadores de alfabetos matemáticos em todas as versões.

Como um breve resumo: para introduzir novas fontes de símbolos, você precisa emitir um pequeno número de declarações de `\declaresymbolfont` e `\setSymbolfont` e um número potencialmente grande de declarações de `\declaraMathsymbol` . Portanto, a adição dessas fontes é melhor feita em um arquivo de embalagem.

### Como introduzir novas versões matemáticas

Já referimos que a configuração padrão declara automaticamente duas versões matemáticas: normal e negrito. Para introduzir versões adicionais, pode utilizar a declaração `\DeclareMathVersion`, que recebe um argumento — o nome da nova versão matemática. Todas as fontes de símbolos e todos os alfabetos matemáticos anteriormente enunciados estão automaticamente disponíveis nesta versão matemática; são-lhes atribuídas as fontes padrão — ou seja, as fontes que especificou com `\DeclareMathAlphabet` ou `\DeclareSymbolFont`.

Em seguida, você pode alterar a configuração da sua nova versão emitindo os comandos `\setMathalphabet` e `\ \ setSymbolfont` para a versão em negrito de matemática, conforme mostrado anteriormente nesta seção e no artigo sobre [fontes em matemática](/tex/{{lang.url-fragment}}java/latex-math-fonts/). Novamente, a introdução de uma nova versão matemática é normalmente feita em um arquivo de pacote.


### Como alterar a configuração da fonte do símbolo

Vimos como adicionar novas fontes de símbolo para acessar mais símbolos. Os mesmos comandos podem ser usados ​​para modificar uma configuração existente. Esse recurso pode ser interessante se você decidir usar fontes especiais em algumas ou em todas as versões de matemática.

Abaixo estão as configurações padrão de LaTeX:

```tex
\DeclareMathVersion{normal} \DeclareMathVersion{bold}
\DeclareSymbolFont{operators} {OT1}{cmr}{m} {n}
\DeclareSymbolFont{letters} {OML}{cmm}{m}{it}
\DeclareSymbolFont{symbols} {OMS}{cmsy}{m}{n}
\DeclareSymbolFont{largesymbols} {OMX}{cmex}{m}{n}

% Special bold fonts only for these:
\SetSymbolFont {operators}{bold}{OT1}{cmr}{bx}{n}
\SetSymbolFont {letters} {bold}{OML}{cmm}{b}{it}
```

Na configuração padrão, os dígitos e o texto produzidos por operadores como `\log` e `\max` são retirados da fonte de símbolo chamada `operadores`. Para alterar isso para que esses elementos se misturem bem com a fonte principal de texto - digamos, o computador moderno, em vez de o computador Roman Modern - você pode emitir os seguintes comandos:

```tex
\SetSymbolFont{operators}{normal}{0T1}{cmss}{m} {n}
\SetSymbolFont{operators}{bold} {0T1}{cmss}{bx}{n}
```

Fontes de símbolo com nomes `símbolos` e` largesymbols` desempenham um papel único no Tex. É por isso que eles exigem um número especial de `\fontdimen` parâmetros associados a eles. Portanto, apenas fontes especialmente preparadas podem ser usadas como essas duas fontes de símbolo. Em princípio, pode -se adicionar esses parâmetros a qualquer fonte no tempo de carregamento usando o terceiro parâmetro de `\declarafontfamily` ou o sexto parâmetro de `\declarafontshape`.

## 6.7. Como definir seu próprio arquivo `.fd` (exemplo)

Se você deseja configurar fontes (PostScript) e criar o arquivo `.fd` necessário, siga o procedimento discutido anteriormente neste artigo. Se `fontinst` for usado para gerar os arquivos métricos de font necessários, os arquivos` .fd` correspondentes também serão gerados automaticamente. No entanto, é fácil escrever um arquivo `.fd` para uma única família de fontes manualmente, desde que você saiba qual codificação de fonte é usada. Como exemplo, vamos estudar o arquivo de declaração `t1bch.fd` para *BitStream Charter* na codificação` t1`:

```tex
\ProvidesFile{t1bch.fd}[2001/06/04 font definitions for T1/bch.]
% Primary declarations
\DeclareFontFamily{T1}{bch}{}
\DeclareFontShape{T1}{bch}{m}{n}{<-> bchr8t}{}
\DeclareFontShape{T1}{bch}{m}{sc}{<-> bchrc8t}{}
\DeclareFontShape{T1}{bch}{m}{sl}{<-> bchro8t}{}
\DeclareFontShape{T1}{bch}{m}{it}{<-> bchri8t}{}
\DeclareFontShape{T1}{bch}{b}{n}{<-> bchb8t}{}
\DeclareFontShape{T1}{bch}{b}{sc}{<-> bchbc8t}{}
\DeclareFontShape{T1}{bch}{b}{sl}{<-> bchbo8t}{}
\DeclareFontShape{T1}{bch}{b}{it}{<-> bchbi8t}{}
% Substitutions
\DeclareFontShape{T1}{bch}{bx}{n}{<->ssub * bch/b/n}{}
\DeclareFontShape{T1}{bch}{bx}{sc}{<->ssub * bch/b/sc}{}
\DeclareFontShape{T1}{bch}{bx}{sl}{<->ssub * bch/b/sl}{}
\DeclareFontShape{T1}{bch}{bx}{it}{<->ssub * bch/b/it}{}
\endinput
```

A primeira linha é uma *linha de identificação*. Em seguida, segue a declaração da família de fontes e da codificação (`BCH` e` T1`) usando `\declarafontfamily`. O argumento deste comando deve corresponder ao nome do arquivo `.fd`, exceto que a codificação no nome do arquivo é minúscula. Em seguida, cada combinação de série e forma é mapeada para o nome de um arquivo `.tfm`. Essas fontes serão dimensionadas para qualquer tamanho desejado (observe `<->`). A segunda parte do arquivo configura algumas substituições por combinações pelas quais nenhuma fonte está disponível (ou seja, substituindo a série estendida em negrito pela série Bold).

Supondo que você tenha as fontes adicionais *Charter* (preto e preto), pode então adicionar as definições correspondentes ao arquivo `.fd`. Você precisaria primeiro fornecer as fontes virtuais apropriadas, é claro, para emular o conjunto de caracteres `T1`. Felizmente, para muitas fontes, elas podem ser baixadas da Internet.

Outro motivo possível para criar seus próprios arquivos `.fd` pode surgir da necessidade de combinar fontes de famílias diferentes e apresentá -las ao LaTeX como uma única nova família de fontes. Por exemplo, existe a família *Aldus* projetada como um companheiro para o tipo de letra *Palatino* (que foi originalmente projetado como um tipo de letra de exibição). Como Aldus não tem série em negrito, Palatino é uma escolha natural de usar como substituto ousado. No exemplo abaixo, combinamos o Aldus em sua série média com Palatino Bold, chamando a família de fontes composta de `Zasj`. Apenas um fragmento de um arquivo `.fd` completo é apresentado, o que é suficiente para ilustrar a ideia.

```tex
\ProvidesFile{t1zasj.fd}
   [2003/10/12 font definitions for T1 Aldus/Palatino mix.]
\DeclareFontFamily{T1}{zasj}{}
% Medium series
\DeclareFontShape{T1}{zasj}{m}{n} {<->pasr9d}{}
\DeclareFontShape{T1}{zasj}{m}{sc}{<->pasrc9d}{}
\DeclareFontShape{T1}{zasj}{m}{it}{<->pasri9d}{}
\DeclareFontShape{T1}{zasj}{m}{sl}{<->ssub * pasj/m/it}{}
% Bold series
\DeclareFontShape{T1}{zasj}{b}{n}{<-> pplb8t}{}
\DeclareFontShape{T1}{zasj}{b}{sc}{<->pplbc8t}{}
\DeclareFontShape{T1}{zasj}{b}{sl}{<->pplbo8t}{}
\DeclareFontShape{T1}{zasj}{b}{it}{<->pplbi8t}{}
```

Para acessar isso "pseudo-família", precisamos selecionar `zasj` na codificação` T1`. Também temos que garantir que o `\textbf` mude para negrito, não para o BOLD Extended, pois nosso arquivo` .fd` não fornece nenhuma substituição. Tudo isso pode ser fornecido automaticamente por um pequeno pacote como este:

```tex
\ProvidesPackage{fontmix}[2003/10/12 T1 Aldus/Palatino mix.]
\RequirePackage[T1]{fontenc}
\renewcommand\rmdefault{zasj} \renewcommand\bfdefault{b}
```

Então, ao carregar o pacote `Fontmix`, obtemos Aldus e Palatino Bold para manchetes. Essa mistura de fonte não pode melhorar seu texto; portanto, este exemplo não sugere a criação de combinações aleatórias.

## 6.8. A ordem das declarações

O NFSS exige que você forneça todas as declarações em uma ordem específica, para que possa verificar se você especificou todas as informações necessárias. Se você declarar objetos na ordem errada, ele reclamará. Aqui estão as dependências que você deve honrar:

* `\declarafontfamily`ls verifica se o esquema de codificação foi declarado anteriormente com `\declareFonteCoding`.
* `\declarafontshape` verifica se a família de fontes foi declarada disponível na codificação solicitada (`\declarafontfamily`).
* `\declaresymbolfont` garante que o esquema de codificação seja válido.
* `\SetSymbolfont` garante também que a versão matemática solicitada tenha sido declarada (`\declaraMathversion`) e que a fonte de símbolo solicitada tenha sido declarada (`\declaraysymbolfont`).
* `\declaresymbolfontalphabet` verifica se o nome do comando para o identificador de alfabetos pode ser usado e se a fonte do símbolo foi declarada.
* `\declaremathalphabet` verifica se o nome do comando escolhido pode ser usado e se o esquema de codificação foi declarado.
* `\SetMathalphabet` verifica se o identificador do alfabeto foi declarado anteriormente com `\decloneMathalphabet` ou `\declarafaresmbolfontalphabet` e que a versão matemática e o esquema de codificação são conhecidos.
* `\declaremathSymbol` garante que o nome do comando possa ser usado (ou seja, não é definido ou foi declarado anteriormente um símbolo de matemática) e que a fonte do símbolo foi declarada anteriormente.
* Quando o comando `\begin {document}` é atingido, o NFSS faz algumas verificações adicionais. Por exemplo, ele verifica que a substituição dos padrões para cada esquema de codificação aponta para as declarações conhecidas do grupo de forma de fontes.