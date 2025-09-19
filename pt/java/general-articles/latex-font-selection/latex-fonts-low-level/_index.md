---
translation: true
template: /templates/_template-java.md
linktitle: Interface de baixo nível
title: 5. A interface de baixo nível
weight: 50
url: /java/latex-fonts-low-level/
keywords: LaTeX, fontes de LaTeX, substituição de fontes de LaTeX, famílias de fontes de LaTeX, série de fontes de LaTeX, formas de fontes de LaTeX
description: Este artigo abrange a interface de fonte de baixo nível de LaTex, que é usada principalmente nas definições de comando.
lastmod: "2025-06-16"
---

{{<section overview>}}

Em contraste com os comandos de fontes de alto nível, destinados ao uso em um documento, os comandos de baixo nível são principalmente para definir novos comandos em pacotes ou no preâmbulo do documento. Para fazer o melhor uso de tais comandos, é útil entender a organização interna das fontes no esquema de seleção de fontes do LateX (NFSS).

Por um lado, o objetivo do esquema de seleção de fontes do LATEX é permitir a seleção racional de fontes com algoritmos guiados pelos princípios da marcação genérica. Para esse fim, seria desejável permitir alterações independentes para o maior número possível de atributos da fonte. Por outro lado, as famílias de fontes na vida real normalmente contêm apenas um subconjunto da inúmeras combinações de atributos de fontes imagináveis. Assim, permitir mudanças independentes em muitos atributos resulta em muitas combinações para as quais nenhuma fonte externa real está disponível e um padrão deve ser substituído.

Internamente, o LATEX acompanha cinco atributos de fonte independentes: a codificação *atual*, a família *atual*, a *série atual*, a forma *atual*e o tamanho *atual*. O atributo de codificação foi introduzido no NFSS Release 2, quando ficou claro que o suporte a vários idiomas não seria possível sem manter o esquema de codificação de caracteres independentemente dos outros atributos da fonte.

Os valores desses atributos determinam a fonte atualmente em uso. O LATEX também mantém um grande conjunto de tabelas usadas para associar combinações de atributos a fontes externas (ou seja, `.tfm`arquivos que contêm os dados necessários para que o LATEX faça seu trabalho). A seleção de fontes é feita em duas etapas:

1. Vários atributos de fonte são alterados usando os comandos de baixo nível `\fontecoding`, `\fontfamily`, `\fontSeries`, `\fontshape` e `\fontSize`.

2. A fonte correspondente a essas novas configurações de atributo é selecionada chamando o comando `\selectFont`.

O segundo passo consiste em várias ações. Primeiro, o LATEX verifica se a fonte correspondente às configurações de atributo desejada é conhecida pelo sistema (ou seja, o arquivo `.tfm` já está carregado) e, se sim, essa fonte é selecionada. Caso contrário, as tabelas internas são pesquisadas para encontrar o nome da fonte externa associado a essas configurações. Se esse nome de fonte for encontrado, o arquivo `.tfm` correspondente será lido na memória e, em seguida, a fonte será selecionada para o TypeSetting. Se o nome da fonte não for encontrado, o LATEX tentará encontrar uma fonte alternativa, conforme explicado mais adiante neste artigo.


## 5.1. Definindo atributos de fonte individuais

Existe um comando para cada atributo de fonte para alterar seu valor atual. Todos esses comandos aceitam mais ou menos qualquer sequência de caracteres como argumento, mas apenas alguns valores fazem sentido. Esses valores não são conectados ao NFSS, mas são convenções configuradas nas tabelas internas. As seções a seguir introduzem as convenções de nomenclatura usadas na configuração padrão de LaTeX, mas qualquer pessoa pode alterar essa configuração adicionando novas declarações de fonte nas tabelas internas. Normalmente, qualquer pessoa que configure novas fontes para uso com o LATEX deve tentar honrar essas convenções sempre que possível, porque apenas uma convenção de nomeação consistente pode garantir que as fontes apropriadas sejam selecionadas em um documento genericamente marcado.

Se você deseja selecionar uma fonte específica usando esta interface - por exemplo, o computador moderno Dunhill condensado em Índia 14pt - um conhecimento das convenções da interface por si só não é suficiente, pois não existe uma fonte externa para cada combinação de valores de atributo. Você pode tentar especificar algo como o seguinte:

```tex
\fontencoding{OT1}\fontfamily{cmdh}\fontseries{bc}\fontshape{it}%
\fontsize{14}{16pt}\selectfont
```

Esse código estaria correto de acordo com as convenções de nomenclatura, como veremos abaixo. No entanto, devido ao fato de que essa combinação de atributos não corresponde a uma fonte real, o LaTeX teria que substituir uma fonte diferente. O mecanismo de substituição pode escolher uma fonte bem diferente da desejada, portanto, você deve consultar as tabelas de fontes para verificar se a combinação desejada está disponível. Aqui estão mais detalhes sobre o [processo de substituição da fonte](/tex/{{lang.url-fragment}}java/latex-fonts-low-level/#53-automatic-substitution-of-fonts).

### Escolhendo a família de fontes

A família de fontes é selecionada pelo comando `\fontfamily`. Como argumento, é preciso uma sequência de personagens que se refere a uma família de fontes declarada nas tabelas internas. A sequência de personagens foi definida quando essas tabelas foram montadas e geralmente é uma sequência de letras curtas - por exemplo, `CMR` para a família romana moderna do computador. Os nomes da família não devem ter mais de cinco letras, porque serão combinados com possivelmente mais três letras para formar um nome de arquivo, que em alguns sistemas pode ter no máximo oito letras.

### Escolhendo a série de fontes

O comando `\fontSeries`altera o atributo da série. A série combina um peso e uma largura em seu argumento, o que significa que é impossível alterar a largura da fonte atual independentemente de seu peso. Isso é aceitável porque é improvável que seja necessário alterar peso ou largura individualmente. Pelo contrário, uma mudança de peso é frequentemente acompanhada por uma mudança de largura na especificação do designer. Isso não é uma surpresa, pois as mudanças de peso alteram a aparência horizontal das letras e, portanto, requerem ajustes na expansão (largura) para produzir uma aparência bem equilibrada.

Os nomes para o peso e a largura são abreviados nos nomes da série, para que cada combinação seja única. Essas convenções de nomenclatura são mostradas na tabela abaixo. Qualquer instância de `m` (em peso médio ou largura) é omitido, exceto quando o peso e a largura são médios; nesse caso, um único `m` é usado. Por exemplo, expandido em negrito seria `bx`, enquanto o meio expandido seria `x` e o meio em negrito seria `b`.

![Convenções de nomeação da série de fontes](/tex/images/java/tutorial/latex-font-selection-5-1.png)

### Escolhendo a forma da fonte

O comando `\fontshape`altera o atributo de forma. Para formas padrão, são usadas abreviações de uma e duas letras. Essas formas estão listadas na tabela abaixo:

![Convenções de nomeação de fontes](/tex/images/java/tutorial/latex-font-selection-5-2.png)

### Escolhendo o tamanho da fonte

O comando `\fontSize {<tamanho>} {<kip>}`altera o tamanho da fonte. São necessários dois argumentos: o `<Sear>` para alternar e a linha de base `<kip>` (a distância entre as linhas de base para esse tamanho). Os tamanhos das fontes são normalmente medidos em pontos; portanto, por convenção, a unidade é omitida. O mesmo vale para o segundo argumento. No entanto, se o salto da linha de base for um comprimento de borracha, você precisará especificar uma unidade. Portanto, uma mudança de tamanho válida pode ser solicitada por


```tex
\fontsize{14.4}{17}\selectfont
```

Mesmo que essa solicitação seja válida, pode não haver uma fonte externa correspondente nesse tamanho. Nesse caso, o LATEX tentará encontrar um tamanho próximo se suas tabelas internas permitirem correção de tamanho ou relatar um erro de outra forma.

Se você usar fontes existentes em tamanhos arbitrários, poderá selecionar qualquer tamanho desejar, é claro:


```tex
\fontsize{1in}{1.2in}\selectfont A text in an arbitrary font size
```

### Escolhendo a codificação

O comando `\fontecoding` é usado para alterar a codificação. O argumento é o nome interno para a codificação desejada. Esse nome deve ser conhecido pelo LaTex, como uma das codificações predefinidas (carregadas pelo kernel) ou como declarado com o comando `\declarafontencoding`. Aqui estão mais informações sobre [declarar codificações de fontes](/tex/{{lang.url-fragment}}java/latex-fonts-setup/#64-how-to-declare-a-new-font-encoding-scheme). Nomes de codificação de fontes padrão estão listados na tabela abaixo:

![Nomes de codificação de fontes padrão](/tex/images/java/tutorial/latex-font-selection-5-3.png)

O NFSS é baseado no pressuposto de que a maioria (ou melhor, todas) fontes para o texto estão disponíveis na mesma codificação, desde que sejam usadas para digitar o mesmo idioma. Em outras palavras, a codificação de alterações deve ser necessária apenas se você estiver mudando de um idioma para outro. Nesse caso, os pacotes de suporte ao idioma (por exemplo, do sistema `Babel`) devem normalmente cuidar das codificações nos bastidores.

No exemplo a seguir, alteramos a codificação manualmente, definindo um ambiente `cyr` para digitar o tipógrafo em cirílico. Nesse ambiente, a codificação da fonte e a codificação de entrada são alteradas localmente. Obviamente, para suporte adequado à linguagem, seria necessário um trabalho adicional, como alterar as regras de hifenação. As codificações são declaradas para o LATEX carregando -as com o pacote `FONTENC`. `T2a` especifica uma das codificações cirílicas padrão. `T1` se torna a codificação padrão, pois é carregada por último.

![ENCONNECIMENTOS Código fonte](/tex/images/java/tutorial/latex-font-selection-5-4.png)

![ENCONNECIMENTOS EXMPLE SAUT](/tex/images/java/tutorial/latex-font-selection-5-5.png)

Infelizmente, `T1` não pode ser totalmente implementado para a maioria das fontes PostScript. É provável que cinco caracteres no exemplo a seguir sejam exibidos como blobs de tinta, indicando glifos ausentes na fonte. Observe que os símbolos 'por mil' e 'por dez mil' são realmente formados juntando -se a um sinal percentual e um ou dois zeros adicionais; Somente o último glifo está faltando.


```tex
\usepackage[T1]{fontenc}
-----------------------------------------
\fontfamily{cmr}\selectfont
\j{} \ng{} \NG{} \textperthousand{}\textpertenthousand \par
\fontfamily{ptm}\selectfont
\j{} \ng{} \NG{} \textperthousand{}\textpertenthousand{}

```

![T1 para fontes PostScript](/tex/images/java/tutorial/latex-font-selection-5-5.png)

## 5.2. Definindo vários atributos de fonte

Ao projetar estilos de página ou comandos orientados para o layout, você geralmente deseja selecionar uma fonte específica - ou seja, você precisa especificar valores para todos os atributos. Para isso, o LATEX fornece o comando `\usefont`, que leva quatro argumentos: a codificação, a família, a série e a forma. O comando atualiza esses atributos e chama `\selectFont`. Se você deseja especificar o tamanho e o pulo da linha de base, coloque um comando `\fontsize` antes de `\usefont`. Por exemplo,


```tex
\fontsize{14}{16pt}\usefont{OT1}{cmdh}{bc}{it}
```

produziria o mesmo resultado que os seguintes comandos:


```tex
\fontencoding{OT1}\fontfamily{cmdh}\fontseries{bc}\fontshape{it}%
\fontsize{14}{16pt}\selectfont
```

O LATEX também fornece a declaração `\declarafixedfont`, que pode ser usada para definir novos comandos que mudam para uma fonte completamente fixa. Tais comandos são muito rápidos porque não precisam procurar tabelas internas. Portanto, eles são muito úteis nas definições de comando que precisam alternar entre as fontes. Por exemplo, se quisermos declarar um comando para digitar determinados texto no tamanho do script, podemos fazê -lo o seguinte:


```tex
\DeclareFixedFont\ScriptSizeFont{\encodingdefault}{\familydefault}
    {\seriesdefault}{\shapedefault}{7pt}
\newcommand\theScript[1]{{\ScriptSizeFont #1}}
```

Você pode ver que `\declarafixedfont` tem seis argumentos. O nome do comando a ser definido é seguido pelos cinco atributos de fonte nas classificações NFSS. Em vez de passar valores fixos (exceto o tamanho), os ganchos embutidos que descrevem a fonte principal de documentos são usados. Portanto, no exemplo acima `\scriptsizefont` ainda depende do layout geral do documento. No entanto, uma vez que a definição é executada, seu significado é congelado, portanto, as alterações posteriores nos padrões não alterarão a fonte `\scriptsizefont`.

## 5.3. Substituição automática de fontes

Quando uma solicitação de alteração de fonte não pode ser realizada porque a combinação não é conhecida pelo LATEX, ela tenta se recuperar usando uma fonte com atributos semelhantes. Aqui está o que acontece em detalhes: se a combinação de esquema de codificação, família, série e forma não for declarada, o LATEX tenta encontrar uma combinação conhecida primeiro alterando o atributo de forma para um padrão. Se a combinação resultante ainda for desconhecida, ela tentará alterar a série para um padrão. Como último recurso, ele muda a família para um valor padrão. Finalmente, ele procura a entrada interna da tabela para encontrar o tamanho solicitado. Por exemplo, se você solicitar `\ttfamily \ bfSeries \itshape` - uma fonte de máquina de escrever em uma série ousada e formato de itálico (que geralmente não existe) - então você receberá uma fonte de máquina de escrever em série média e uma forma vertical porque o Latex primeiro redefine a forma da forma antes da série. Nesse caso, se você preferir uma fonte de máquina de escrever com formato em itálico, deve anunciar suas preferências ao LaTeX usando a função `sub`, que é explicada no artigo [Como configurar novas fontes](/tex/{{lang.url-fragment}}java/latex-fonts-setup/).

O processo de substituição nunca altera o esquema de codificação porque qualquer alteração pode produzir caracteres incorretos na saída. Como você deve se lembrar, o esquema de codificação define como interpretar os caracteres de entrada, enquanto os outros atributos definem como a saída deve ser. Portanto, não seria apropriado se, por exemplo, um sinal de libra fosse substituído por um sinal de dólar em um contrato apenas porque o software tentasse ser inteligente.

Assim, todo esquema de codificação deve ter uma família, série e forma padrão, e pelo menos a combinação que consiste no esquema de codificação juntamente com os padrões correspondentes deve ter uma definição dentro do LaTeX.

## 5.4. Como usar comandos de baixo nível no documento

Os comandos de baixo nível descritos nas seções anteriores devem ser usados ​​nas definições de comandos de alto nível, na classe de documentos ou em arquivos de pacote ou no preâmbulo do documento.

Se você puder usar comandos de alto nível como `\textsf`, evite usar os comandos de baixo nível diretamente no documento sempre que possível. O motivo é que os comandos de baixo nível são instruções muito precisas para alternar para uma fonte específica, enquanto os comandos de alto nível podem ser personalizados usando pacotes ou declarações no preâmbulo. Suponha que você selecionou o computador moderno em seu documento usando `\fontfamily {cmss} \ selectFont`. Se você decidir mais tarde digitar todo o documento com fontes do pacote PSNFSS - digamos, os tempos - a aplicação de um pacote alteraria apenas as partes do documento que não contêm comandos explícitos `\fontfamily`.