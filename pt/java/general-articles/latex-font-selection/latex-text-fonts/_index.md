---
translation: true
template: /templates/_template-java.md
linktitle: Fontes de texto de LaTeX
title: 3. Como usar fontes de LaTeX no texto
weight: 30
url: /java/latex-text-fonts/
keywords: LATEX, fontes de LaTeX, comandos de fontes de texto LaTeX, LaTeX grande, tamanho da fonte de LaTeX
description: Este artigo aborda os comandos da fonte do LATEX que alteram independentemente diferentes atributos de fonte para uso no texto normal.
lastmod: "2025-06-16"
---

{{<section overview>}}

Ao escrever um documento de LaTeX, as tags de marcação usadas para estruturar o documento escolhem automaticamente as fontes apropriadas. Por exemplo, para um título de seção, atributos de fonte como tamanho grande e peso em negrito são definidos pela classe de documentos e aplicados quando um comando `\seção` for usado. Portanto, você raramente precisa especificar atributos de fonte diretamente.

Mas às vezes é necessário. Por exemplo, você pode escolher uma família de fontes diferente (ou outro atributo geral de fonte) para o texto principal. Essa alteração geralmente pode ser feita como simplesmente especificando um pacote apropriado.

Outro caso é quando você deseja marcar certos fragmentos do documento como especial - por exemplo, para denotar acrônimos, exemplos ou nomes de empresas. Se você optar por usar, digamos, uma fonte sem serifa para esses fragmentos, poderá fazê -lo com nomes de empresas ao redor com `\textsf {...}`. Mas a melhor prática é definir um novo comando (digamos, `\ Company`) para esse fim. Definir comandos individuais para coisas logicamente diferentes facilita a alteração da formatação posteriormente de maneira consistente.

Você também pode querer digitar uma tabela em um tamanho menor para ajustá -la em uma página. Como as classes de documentos podem formatar documentos automaticamente apenas até certo ponto, esse desejo é legítimo. Segue -se que a formatação manualmente, como a inserção de quebras de página, é frequentemente necessária para criar uma versão final. Infelizmente, a formatação explícita torna difícil o uso do documento e propenso a erros. Portanto, o uso direto dos comandos de mudança de fonte em um documento deve ser minimizado. Isso também é verdade para todos os comandos de formatação visual.


## 3.1. Como usar comandos de fontes no LaTeX padrão

A fonte usada para o texto principal de um documento é chamada de fonte *principal*, *fonte do corpo* ou *fonte normal*. Ele é selecionado automaticamente no início do documento e em certas construções, como notas de rodapé e figuras. Cabeças de seção e outras tags de marcação lógica alternam automaticamente para um tipo de letra ou tamanho diferente, dependendo da classe de documentos. Portanto, a introdução da marcação lógica correta é a única ação necessária do autor. No entanto, às vezes pode ser desejável destacar manualmente certas partes do texto escolhendo um tipo de letra apropriado. Isso é feito com os comandos discutidos abaixo.

Existem duas formas para a maioria dos comandos de mudança de fonte: um comando com um argumento, como `\textbf {...}` e uma declaração, como `\bfSeries`. A forma declarativa não assume argumentos, mas instrui o Latex que a partir de agora (até o final do atual grupo de aparelhos ou ambientes) deve se comportar de uma maneira especial. Isso significa que você não deve escrever algo como `\bfSeries {...}`, porque isso tornaria tudo ousado a partir deste ponto até o final do ambiente atual.

É melhor fazer uso dos comandos da fonte com um argumento para alterar as fontes para palavras individuais ou frases curtas em seu documento. Para fragmentos mais longos, você deve usar a forma do ambiente da declaração, como mostrado no exemplo abaixo:

```tex
Some words in this sentence are \begin{bfseries}typeset in bold letters.
The bold typeface\end{bfseries} continues here. 
```

![A forma ambiental de \ bfSeries](/tex/images/java/tutorial/latex-font-selection-3-1.png)

As próprias formas declarativas geralmente são melhores na definição de novos ambientes ou comandos.

> É também importante que os comandos de fonte com um argumento não permitam quebras de parágrafo nos seus argumentos.

### A fonte principal do documento

Usando o comando `\textNormal` ou a declaração`\normalfont`, você pode alternar para a fonte principal do documento. Eles normalmente ocorrem apenas nas definições de comandos ou ambientes quando é importante definir uma maneira de sempre digitar a mesma fonte, independentemente das condições circundantes. Por exemplo, o comando para os nomes de comando de LaTeX de Typeset pareceria o seguinte:

```tex
\newcommand\Lcs[1]{{\normalfont\ttfamily\textbackslash#1}%}
```

O uso de `\NormalFont` impede os nomes de comando lançados em itálico, mesmo dentro do texto em itálico.

### Famílias de fonte padrão

Por padrão, o LATEX mantém três famílias de fontes: uma fonte de texto serificado, acessada com o comando `\textrm`; uma fonte de texto sem serif, acessada por `\textsf`; e uma fonte de máquinas de escrever (monoespactada), acessada por `\texttt`. As formas de declaração desses comandos são `\rmfamily` ,`\sffamily` e `\ttfamily`, respectivamente.

Os nomes exatos das famílias de fontes externas acessados ​​por esses comandos dependem da classe de documentos, mas podem ser alterados no preâmbulo ou por pacotes. Como padrão de instalação, a família de fontes serifinada é **Computer Modern Roman**, a família Sans serif é **Computer Modern Sans**, e a família da máquina de escrever é **Modern Typewriter Modern**. Se você usar uma configuração diferente, deve ter cuidado para definir essas famílias de fontes padrão para que as fontes possam ser misturadas sem confrontos visuais. Também é importante garantir que as fontes externas estejam disponíveis na resolução correta para o dispositivo de saída direcionado.

A maioria das classes de documentos define a fonte serifinada, acessada por `\textrm`, como a fonte principal do documento; portanto, o comando `\textrm` não é usado com frequência. Mas se um designer de documentos escolheu uma fonte sem serifa como o principal tipo de letra, o `\textrm` seria a família alternativa de fontes serifinados.

### Série de fontes padrão

No LATEX, a série * é uma combinação de dois atributos: largura e peso (ousadia). O LATEX permite alterar a série com dois comandos: `\textMd` e `\textbf`. As declarações correspondentes são `\mdSseries` e `\bfSeries`, respectivamente. O primeiro comando seleciona uma fonte com valores médios para a largura e o peso, enquanto o último muda para uma série mais ousada. Novamente, os valores reais dependem da classe de documentos e de suas opções ou pacotes subsequentes. Em uma configuração padrão, `\textbf` muda para uma versão em negrito do tipo de letra atual, enquanto `\textMd` retorna à versão de largura média e média do tipo de letra atual.

### Formas de fonte padrão

A forma * do tipo de letra atual é o terceiro atributo de fonte que pode ser alterado independentemente dos outros. A forma padrão para a maioria dos documentos é a forma vertical, que pode ser acessada com o comando `\textup` ou a declaração `\upshape`, se necessário.

Os comandos mais usados ​​parecem ser `\textit` e `\textsc`, que mudam para uma forma de fonte itálica ou pequena, respectivamente. As declarações correspondentes são `\itshape` e `\scshape`.

O comando `\textSl` (seu formulário de declaração é` \ slshape`) muda para a forma inclinada. Uma família de fontes geralmente contém apenas uma forma itálica ou inclinada, embora o computador Roman Modern contenha os dois.

No ponto em que se muda de inclinado para vertical, os personagens geralmente se aproximam demais, especialmente se o último personagem inclinado tiver um ascendente. A quantidade adequada de espaço extra que deve ser adicionada nesse limite é chamada de correção **itálica**. A largura exata deste espaço depende do caractere individual e é armazenada no arquivo `.tfm`. Os comandos da fonte com argumentos adicionam automaticamente a correção em itálico, mas quando as declarações são empregadas, ela deve ser inserida manualmente usando `\/`. Para uma fonte vertical, a correção itálica dos personagens geralmente é zero ou muito pequena, embora existam algumas exceções. O próximo exemplo mostra como usar corretamente as declarações de mudança de forma que mudam para formas inclinadas.

```tex
\raggedright
When switching back from {\itshape italic\/} or {\slshape slanted\/} shapes to an upright font one
should add the {\itshape italic correction}, except when a small punctuation character follows.
```

![A correção em itálico](/tex/images/java/tutorial/latex-font-selection-3-2.png)

Às vezes, pequenas tampas são usadas em títulos ou para formatar nomes. Para este último caso, você pode, por exemplo, definir o comando `\name` da seguinte maneira:

```tex
\newcommand\name[1]{\textsc{#1}}
```

Como alternativa, você pode usar duas declarações:

```tex
\newcommand\name[1]{{\normalfont\scshape #1}}
```

O primeiro comando simplesmente muda para a forma de pequenas capas, enquanto o segundo formulário redefine inicialmente todos os atributos de fonte para seus padrões. Qual opção escolher depende das fontes disponíveis e do tipo de documento. Com o computador moderno, apenas as famílias romanas e de máquinas de escrever contêm formas de pequenas capas, portanto a segunda definição pode ser preferida em determinadas aplicações, pois usará pequenas capas (embora serifitas), mesmo em um contexto de `\sffamily`. O primeiro comando solicitaria uma série média, pequenas capas, fontes em forma na família Modern Sans Modern. Essa fonte não está disponível, então o LATEX tentaria encontrar um substituto alterando primeiro o atributo de forma para o seu padrão. Como resultado, você não receberia pequenos bonés.

Outro comando de forma especial do LATEX é o comando `\ \ ênf`, que enfatiza fragmentos no texto normal. Sua forma declarativa é `\em`. Como tradição, as palavras enfatizadas no texto são definidas em itálico; Mas se a ênfase é desejada em um fragmento já em itálico do texto, geralmente se alterna para a fonte vertical. O comando `\ \ ênf` suporta esta convenção, mudando para a forma` \itshape` se a fonte atual estiver na vertical e para a forma `\upshape` se a fonte atual já estiver inclinada (ou seja, a forma for` \itshape` ou `\slshape`). Portanto, o usuário não precisa se preocupar com o estado atual do texto ao usar o comando `\ \ ênf` ou a declaração`\em '.

```tex
{\em Nevertheless, one has to be careful about the\/ {\em proper\/} use of italic corrections
on both ends of the emphasized text}. It is therefore better to use the \verb=\emph= command,
which \emph{automatically} takes care of the italic correction on both sides.
```

![Enfatizando fragmentos de texto](/tex/images/java/tutorial/latex-font-selection-3-3.png)

### Tamanhos de fonte padrão

Existem 10 comandos de mudança de tamanho no LaTeX. Esses comandos não possuem formulários de comando correspondentes com um argumento, pois as alterações no tamanho da fonte são normalmente usadas apenas nas definições de comandos.

![Tamanhos de fonte padrão](/tex/images/java/tutorial/latex-font-selection-3-4.png)

O tamanho selecionado por esses comandos depende das configurações na classe de documentos e possivelmente das opções (por exemplo, `11pt`) especificadas com ele. Em geral, `\normalsize` corresponde ao tamanho principal do documento, e os comandos de mudança de tamanho formam uma sequência ordenada, começando com `\ tiny` como o menor e subindo para `\enorme` como o maior tamanho. Pode acontecer que mais de um comando se refere ao mesmo tamanho. Por exemplo, quando um grande `\normalsize` é escolhido,`\enorme` pode ser o mesmo que `\enorme`. Mas a ordem é sempre homenageada.

Os comandos de mudança de tamanho para os tamanhos de texto principais (ou seja, `\normalsize`, ` \ small` e `\ Footnotesize`) geralmente afetam o espaçamento nas listas e exibições. Portanto, para alterar seu comportamento, não se deve simplesmente substituir sua definição por uma chamada para `\fontsize`, mas, em vez disso, inicie a definição original, conforme documentado em` classes.dtx`.

## 3.2. Como combinar comandos de fonte padrão

Como já mostrado, os comandos e declarações padrão de mudança de fonte podem ser combinados, resultando na seleção de um tipo de letra que corresponda à combinação de atributos de fonte. Veja o exemplo abaixo:

```tex
One can typeset a text {\sffamily\bfseries\large in a large sans serif
bold typeface} but note the unchanged leading! \LaTeX{} uses the value
in force at the \emph{end} of the paragraph!
```

![Comandos de fontes de LaTeX combinações](/tex/images/java/tutorial/latex-font-selection-3-5.png)

Internamente, o comando `\sffamily` muda para a família sem serif, então `\bfSeries` muda para a série Bold padrão nesta família e, finalmente `\ grande`, seleciona um tamanho grande, mas deixa todos os outros atributos inalterados. A liderança parece permanecer inalterada porque o escopo de `\ grande` termina antes do final do parágrafo. Os arquivos métricos de fonte são carregados para todos os tipos de letra intermediários, mesmo que essas fontes nunca sejam usadas. No exemplo acima, eles seriam "sem serif médio 10pt" após o `\sffamily`, então" sem serifa ousada estendida 10pt "após o `\bfSeries` e, finalmente, “Sans serif ousado estendido 14pt”, que é a fonte que é realmente usada. Portanto, esses comandos de alto nível podem forçar a seleção de fontes do LATEX a carregar desnecessariamente fontes que nunca são usadas. Há apenas uma pequena perda de velocidade de processamento quando uma determinada combinação é usada pela primeira vez. Mas se você tiver muitas combinações diferentes desse tipo, considere melhor defini-las em termos de [declarações primitivas de mudança de fonte](/tex/{{lang.url-fragment}}java/latex-fonts-low-level/).

## 3.3. Comandos e declarações de fontes comparação

Todos os comandos alterando a fonte com argumentos começam com `\text ...` (exceto `\ ênf`) para enfatizar que eles são destinados ao uso no texto normal. O uso desses comandos em vez dos formulários declarativos tem a vantagem de manter a consistência com outras construções de LaTeX. Eles são destinados a digitar peças curtas de texto em uma família, série ou forma específicas. A tabela a seguir mostra o efeito desses comandos.

![Comandos e declarações](/tex/images/java/tutorial/latex-font-selection-3-6.png)

Outra vantagem desses comandos é que eles inserem automaticamente qualquer correção em itálico necessária em ambos os lados de seu argumento. Portanto, você não precisa se preocupar em perder as correções em itálico ao alterar fontes.

A correção em itálico inserida automaticamente está errada em muito poucas situações. Geralmente, é recomendável omitir a correção em itálico se um pequeno caráter de pontuação (uma vírgula ou período) seguir diretamente a alteração da fonte. Você pode definir em quais casos a correção em itálico deve ser suprimida. Isso é feito especificando os caracteres que devem cancelar uma correção em itálico anterior na lista `\nocorrlist`. A definição padrão para este comando é

```tex
\newcommand{\nocorrlist}{,.}
```

Também é possível suprimir a correção itálica em instâncias individuais. Para esse fim, o comando `\nocorr` é fornecido. Observe que você deve colocar `\nocorr` na extremidade esquerda ou direita dentro do argumento dos comandos`\text ... `, dependendo de qual lado do fragmento precisa da supressão da correção em itálico.

```tex
\emph{When using the \LaTeX{} high-level font commands, the \emph{proper} use of
italic corrections is automatically taken care of}. Only \emph{sometimes} one has
to help \LaTeX{} by adding a \verb=\nocorr= command.
```

![A correção em itálico](/tex/images/java/tutorial/latex-font-selection-3-7.png)

Por outro lado, as formas de declaração geralmente são mais adequadas para definir seus próprios comandos ou ambientes.

```tex
% Part of the preamble
\newenvironment{bfitemize}{\begin{itemize}%
  \normalfont\bfseries\raggedright}{\end{itemize}}
-----------------------------------------------
\begin{bfitemize}
\item This environment produces boldface items.
\item It is defined in terms of \LaTeX's
\texttt{itemize} environment and NFSS declarations.
\end{bfitemize}
```

![A lista com itens em negrito](/tex/images/java/tutorial/latex-font-selection-3-8.png)

## 3.4. Como acessar todos os personagens de uma fonte

Mesmo que exista um personagem em uma fonte, às vezes é impossível inseri -lo no teclado. Muitos caracteres úteis são acessíveis por comandos como `\ss` ou` \ ae`. Alguns caracteres podem ser gerados implicitamente a partir de sequências de cartas como `ffi`, que produz a ligadura" FFI "e` --- `, que produz o longo traço nas fontes Tex padrão.

Além disso, o comando `\símbolo` permite acessar qualquer caractere em uma fonte, fornecendo seu número no esquema de codificação atual como decimal, octal (precedido por` '`) ou número hexadecimal (precedido por` "`).

```tex
\fontencoding{T1}\selectfont
-----------------------------------------------
In the font encoding (\texttt{T1}), characters like \symbol{"DE},
symbol{'237}, and \symbol{32} are included and can be accessed with
the \verb=\symbol= command.
```

![O comando \ símbolo](/tex/images/java/tutorial/latex-font-selection-3-9.png)

## 3.5. Como alterar as fontes de texto padrão

Se você deseja modificar facilmente a aparência geral de um documento, pode usar os ganchos internos do LateX que modificam o comportamento dos comandos de mudança de fonte de alto nível discutidos anteriormente. Os valores desses ganchos podem ser definidos em arquivos de pacotes ou no preâmbulo de um documento usando `\renewCommand`. Aqui está a lista dos ganchos:

![Os ganchos para a fonte de alto nível muda](/tex/images/java/tutorial/latex-font-selection-3-10.png)

Por exemplo, se você escrever no preâmbulo
```tex
\renewcommand\familydefault{cmss}
```

Um documento inteiro apareceria no computador moderno, porque essa redefinição altera a família de fontes para a fonte principal usada pelo LATEX. Em detalhes, a fonte principal do documento é determinada pelos valores de `\codingDefault`, ` \ FamilyDefault`, `\SeriesDefault` e `\ShapeDefault`. Isso significa que você deve garantir que esses comandos sejam definidos de tal maneira que a combinação deles aponte para uma forma de fonte existente nas tabelas internas do LaTeX.

O valor padrão de `\codingDefault` (` ot1`) serve realmente compatibilidade. Isso significa que o LATEX assume que a maioria das fontes usa a codificação original. Na maioria das circunstâncias, é melhor usar a codificação `T1`, porque contém muitos glifos adicionais que não estão disponíveis com` ot1` e permite a hifenização adequada para palavras com caracteres acentuados. Atualmente, algumas fontes não suportam `ot1`, pois são projetadas para uso com` T1`.

É importante lembrar que nem toda fonte pode ser usada como padrão de codificação de documentos. Um pré -requisito é que a codificação deve incluir a maioria das letras ASCII visíveis em suas posições padrão. O `\codingDefault` pode ser alterado carregando o pacote` FONTENC` com uma ou mais opções.

A configuração inicial de `\familydefault` significa que a alteração` \ rmdefault` mudará implicitamente `\familydefault` para o novo valor, desde que nenhuma configuração especial para` \ FamilyDefault` seja definida. Mas se `\familydefault` for alterado,` \ rmdefault` não será afetado.