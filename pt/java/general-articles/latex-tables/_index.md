---
translation: true
template: /templates/_template-java.md
linktitle: Tabelas de LaTeX
title: Tabelas no LaTeX 
weight: 50
url: /java/latex-tables/
keywords: Tabelas de LaTeX, ambiente tabular, design de tabela de LaTeX, formatação de tabela em LaTeX, tabelas de composição em LaTeX, layout da tabela de LaTeX, espaçamento de mesa de LaTeX, personalização de tabelas de LaTeX, alinhamento de tabela de LaTeX, multirrow e multicolumn em tabelas de LaTeX
description: Este artigo é um guia rápido para a criação de tabelas funcionais, amigáveis ​​para leitores, visualmente impulsionadas e profissionais no LaTeX.
lastmod: "2025-06-16"
---

{{<section overview>}}

## 1. Introdução

As tabelas desempenham um papel importante no aprimoramento da clareza, organização e apelo visual de documentos acadêmicos e profissionais. Eles servem como uma maneira poderosa de apresentar dados, comparações e relacionamentos complexos em um formato estruturado e facilmente digerível. Aqui está uma breve visão geral de sua importância:

1. **Resumo de dados**: As tabelas fornecem uma representação condensada de informações que, de outra forma, poderiam exigir vários parágrafos para explicar. Eles permitem que os autores apresentem grandes quantidades de dados concisamente, facilitando a compreensão dos pontos -chave dos leitores.

2. **Visualização clara**: dados complexos, como figuras estatísticas, resultados da pesquisa e descobertas experimentais, podem ser apresentadas com mais eficiência usando tabelas. O formato tabular ajuda os leitores a identificar tendências, padrões e outliers muito mais fáceis.

3. **Análise comparativa**: As tabelas permitem comparações lado a lado de diferentes conjuntos de dados. Seja comparando as especificações do produto, o desempenho financeiro ou as variáveis ​​de pesquisa, as tabelas ajudam os leitores a tirar conclusões significativas de relance.

4. **Organização lógica**: As tabelas fornecem uma estrutura lógica que segrega dados em linhas e colunas. Essa organização facilita a apresentação de dados que possuem categorias distintas, permitindo que os leitores naveguem facilmente e encontrem informações específicas.

5. **Integridade dos dados**: Nos contextos acadêmicos e profissionais, a precisão dos dados é fundamental. As tabelas permitem que os autores apresentem dados brutos, eliminando o risco de má interpretação que pode surgir quando os dados são transmitidos em forma narrativa.

6. **Referências e citações**: Quando as tabelas são bem marcadas e devidamente referenciadas, elas se tornam valiosas pontos de referência em um documento. Os autores podem se referir a tabelas específicas ao discutir as descobertas, facilitando os leitores a seguir o argumento.

7. **Engajamento visual**: As tabelas bem projetadas quebram a monotonia do conteúdo textual, envolvem visualmente os leitores e ajudam a mantê-los interessados. Eles contribuem para a estética geral e o profissionalismo de um documento.

8. **Eficiência na comunicação**: Profissionais e pesquisadores ocupados geralmente precisam extrair informações rapidamente. As tabelas permitem visualizar dados e encontrar detalhes específicos sem ter que ler parágrafos de texto.

9. **Padronização**: Na pesquisa acadêmica, as tabelas padronizadas são frequentemente usadas para apresentar metodologias experimentais, resultados e análises estatísticas. Isso garante consistência entre publicações e ajuda na reprodutibilidade da pesquisa.

Em essência, as tabelas servem como cubos de informação, apresentando com eficiência insights orientados a dados, mantendo um formato estruturado e amigável ao leitor. Seu papel na transmissão de detalhes intrincados, garantindo clareza e acessibilidade, os torna uma ferramenta indispensável na comunicação acadêmica e profissional.

Vamos agora recorrer ao LaTeX como um poderoso sistema de composição que permite que os autores transformem suas idéias em documentos lindamente criados. O LaTeX transcende as limitações dos processadores de texto tradicionais, oferecendo um campo de precisão, elegância e versatilidade que é muito perceptível ao processar estruturas tabulares.
Na sua essência, o LATEX é mais do que apenas uma ferramenta de preparação de documentos; É uma forma de arte que combina tipografia com tecnologia. Esteja você criando trabalhos acadêmicos, relatórios, apresentações ou até livros, o LaTeX se destaca na produção de documentos que não são apenas esteticamente agradáveis, mas também transmitem informações com a máxima clareza. Seu domínio reside, entre outras coisas, em sua integração perfeita de estruturas tabulares complexas, que são a espinha dorsal da representação de dados em vários campos.

Com o LATEX, o arranjo de informações nas tabelas vai além de uma simples grade de linhas e colunas. Em vez disso, é uma sinfonia cuidadosamente orquestrada, onde o alinhamento, o espaçamento e o estilo de harmonizar para fornecer uma apresentação refinada de dados. As estruturas tabulares no LaTeX tornam -se narrativas visuais, transmitindo conjuntos de dados, relacionamentos e comparações complexos com elegância e precisão.

Ao oferecer muitas ferramentas e pacotes adaptados ao design tabular, o LaTeX transforma dados em narrativa visual. Desde o controle da largura das colunas até o ajuste das bordas e sombreamento de células, o nível de personalização do LateX garante que cada tabela alinhe perfeitamente com o objetivo do seu documento. Para aqueles que trabalham com conteúdo matemático, técnico ou científico, a inclusão contínua do LATEX de equações e símbolos nas células da tabela eleva a comunicação de idéias complexas.

No entanto, o poder do LaTeX se estende além da mera estética. Introduz a eficiência por meio de mecanismos de referência cruzada, tornando os marcos de navegação de tabelas dentro do seu documento. Além disso, os pacotes do LATEX permitem a criação de layouts complexos que abrangem várias linhas ou colunas, acomodando as apresentações de dados mais exigentes.

Quanto mais você se aprofundar no mundo do LaTeX, mais as características mais sutis você explora; Os recursos que fazem do LaTeX uma ferramenta indispensável para cientistas, profissionais e pesquisadores. Você mergulha na arte de projetar tabelas que capturam atenção, apresenta informações de forma persuasiva e contribuem para o impacto geral do seu documento.


## 2. Noções básicas de tabelas em LaTeX

O conceito fundamental de tabelas no LaTeX gira em torno do ambiente `Tabular ', onde você define colunas, linhas e seu conteúdo para organizar e apresentar dados em um formato estruturado e visualmente agradável.

A estrutura básica de uma tabela no LaTeX envolve os seguintes componentes:

1. **Comece o ambiente `Tabular`**: Para criar uma tabela, você inclui o conteúdo da tabela em um ambiente` tabular`. Este ambiente especifica o layout e a estrutura da tabela.

2. Especificação da coluna: Dentro do ambiente `Tabular`, você define o número de colunas e seu alinhamento usando especificadores de coluna. Os especificadores comuns incluem `l` para alinhado à esquerda,` c` para centradas e `r` para colunas alinhadas à direita. Você também pode especificar quais colunas o LaTeX deve se separar com linhas verticais e quais bordas externas verticais devem ser desenhadas.

3. **Conteúdo da linha**: Cada linha da tabela é criada especificando o conteúdo de cada célula dentro da linha. As células são separadas pelo símbolo `&` e cada linha é encerrada com o comando `\\`.

4. Isso aprimora a estrutura visual da tabela.

### Exemplos simples

Aqui está um exemplo básico de uma tabela de LaTeX:

```tex
\begin{tabular}{|c|c|c|}                             \hline
    Header 1 & Header 2 & Header 3 \\                \hline
    Row 1, Cell 1 & Row 1, Cell 2 & Row 1, Cell 3 \\ \hline
    Row 2, Cell 1 & Row 2, Cell 2 & Row 2, Cell 3 \\ \hline
\end{tabular}

```

Neste exemplo, o ambiente `tabular` é usado para criar uma tabela com três colunas, cada uma (`c`). O resultado da composição é mostrado abaixo:

<a href="/tex/images/java/tutorial/latex-tables-1.jpg" style="display:inline-block;width:100%;">![Exemplo de saída](/tex/images/java/tutorial/latex-tables-1.jpg)</a>

O exemplo a seguir mostra como criar uma tabela com colunas alinhadas esquerda e direita.

```tex
\begin{tabular}{|l r||}
  \hline
  Company & Income \\            \hline \hline
  Pinapple Computer & \$150M \\
  Megasoft & \$210M \\
  General Waters Ltd. & \$98M \\
  Alphamet & \$2117M \\           \hline
\end{tabular}
```

A borda externa direita é feita dupla, o cabeçalho também é separado da tabela por uma linha dupla, não há linha vertical que separe as colunas.

<a href="/tex/images/java/tutorial/latex-tables-2.jpg" style="display:inline-block;width:100%;">![Exemplo de saída](/tex/images/java/tutorial/latex-tables-2.jpg)</a>

Você também pode desenhar linhas horizontais que não abrangem a tabela inteira da esquerda para a direita.

```tex
\begin{tabular}{|r|l|}         \hline
  9D5 & hexadecimal \\
  4725 & octal \\              \cline{2-2}
  1001 1101 0101 & binary \\   \hline \hline
  2517 & decimal \\            \hline
\end{tabular}
```

Aqui, o comando `\ CLINE {i-j}` diz ao LATEX para desenhar uma linha da coluna i <pup> th </pup> para a coluna J <pup> th </pup>.

<a href="/tex/java/latex-tables/latex-tables-3.jpg" style="display:inline-block;width:100%;">![Exemplo de saída](latex-tables-3.jpg)</a>

As colunas em uma tabela podem ter uma largura fixa, caso em que são chamadas de colunas * parágrafos *. Para criar essas colunas, você usa o especificador `p` seguido pela largura da coluna no aparelho. Considere o seguinte exemplo:

```tex
\begin{tabular}{|p{3cm}|p{2cm}|}            \hline
  A short text. & A very very long text. \\ \hline
  A very very long text. \newline And some more text in a new line. & A short text. \\ \hline
\end{tabular}
```

Observe o uso do comando `\newline`.

<a href="/tex/java/latex-tables/latex-tables-4.jpg" style="display:inline-block;width:100%;">![Exemplo de saída](/tex/images/java/tutorial/latex-tables-4.jpg)</a>

Com o pacote `Array` incluído, mais duas opções estão disponíveis para colunas de largura fixa:` m {width} ` - o mesmo que` p {width} `, mas alinhe verticalmente o teor de células no meio;
`b {width}` - o mesmo que `p {width}`, mas alinha verticalmente o conteúdo de células na parte inferior.

No caso raro de que uma tabela precisa ser incluída no texto de um parágrafo, você pode especificar a posição da tabela em relação à linha de base da linha de texto anexante. Para esse fim, você usa a opção `t`, ` c` (padrão) ou `b` para alinhar a linha de base ao topo, centro ou inferior da tabela. Por exemplo,

```tex
This is the text of the paragraph
\begin{tabular}[t]{|r|l|}     \hline
  9D5 & hexadecimal \\
  4725 & octal \\             \cline{2-2}
  1001 1101 0101 & binary \\  \hline \hline
  2517 & decimal \\           \hline
\end{tabular}
that include a table.
```

Aqui dizemos ao LATEX que a linha de base deve se alinhar ao fundo da tabela.

<a href="/tex/java/latex-tables/latex-tables-5.jpg" style="display:inline-block;width:100%;">![Exemplo de saída](/tex/images/java/tutorial/latex-tables-5.jpg)</a>

### Definindo várias colunas

Quando a sua tabela contém colunas alinhadas de forma idêntica, você pode definir todas elas em outras usando o `*{num} {format}` sintaxe. Isso é especialmente útil quando sua tabela possui muitas colunas.

```tex
\begin{tabular}{l*{7}{c}r}
  Employee   & Sun & Mon & Tue & Wed & Thu & Fri & Sat & Total \\ \hline
  John Doe   &     &  x  &     &     &     &  x  &     &   2   \\
  Dean Jones &  x  &     &  x  &     &  x  &     &     &   3   \\
  Chris Cross&     &     &     &  x  &     &     &     &   1   \\
  Pete Brad  &     &     &     &     &     &     &  x  &   1
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-6.jpg" style="display:inline-block;width:100%;">![Exemplo de saída](/tex/images/java/tutorial/latex-tables-6.jpg)</a>

### Especificação da coluna usando `> {\ commmand}` e `<{\ comando}`

Outra maneira de especificar colunas é usar `> {\ comando}` para comandos executados direito *antes de* cada elemento da coluna e `<{\ comando}` para comandos executados direito *após* cada elemento da coluna. Isso está disponível quando você possui o pacote `Array` incluído no preâmbulo do documento. No exemplo a seguir, usamos essa sintaxe para centralizar cada uma das duas colunas e digitar a primeira em ousada face.

```tex
\begin{tabular}{>{\centering\textbf\bgroup}p{3.5cm}<{\egroup}>|{\centering}p{3.5cm} }
  History & Geometry
  \tabularnewline \hline
  Ancient & Elementary
  \tabularnewline
  Medieval & Affine 
  \tabularnewline
  Modern & Analytic
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-7.jpg" style="display:inline-block;width:100%;">![Exemplo de saída](/tex/images/java/tutorial/latex-tables-7.jpg)</a>

## 3. Personalização do layout da tabela

Nas tabelas de LaTeX, o ajuste do espaçamento é crucial para garantir que a tabela pareça bem estruturada e visualmente atraente. O espaçamento adequado aumenta a legibilidade e evita a aglomeração do conteúdo. Aqui estão alguns aspectos -chave do ajuste de espaçamento nas tabelas de LaTeX:

### Espaçamento entre colunas

O LATEX adiciona automaticamente algum espaço entre as colunas. Para ajustar o espaço entre colunas, você pode usar o comando `\setLength {\ TabColsep} {value}`antes do ambiente tabular. Aumentar o valor aumenta o espaço entre as colunas. O valor padrão é `6pt`.

### Espaçamento entre filos

Para aumentar o espaço entre as linhas, você pode usar o comando `\renewCommand {\ Arraystretch} {value}`antes do ambiente `tabular`. Aumentar o valor estende as linhas, aumentando o espaçamento vertical da mesa. O valor padrão é `1.0`.

Você também pode especificar o salto após uma linha explicitamente usando cola após o terminador da linha.

```tex
\begin{tabular}{cl} \hline
  Level & Complexity \\ [1cm]
  1 & Simple \\
  2 & Intermediate \\
  3 & Complex \\ \hline
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-8.jpg" style="display:inline-block;width:100%;">![Exemplo de saída](/tex/images/java/tutorial/latex-tables-8.jpg)</a>

### Usando `@` e `!` Expressões

Tendo o pacote `Array` incluído no preâmbulo do documento, você pode especificar separadores de colunas com o `@{...} `ou`! {...} `construções.

Eles normalmente tomam algum texto como argumento e, quando anexados a uma coluna, inserem automaticamente esse texto em cada célula nessa coluna antes e/ou após os dados reais para essa célula. O comando `@{...}` substitui o espaço entre colunas pelo conteúdo especificado como o argumento. Ao deixar o argumento vazio, você pode suprimir os espaços entre colunas.

Vamos pegar uma tabela básica especificada pelo seguinte código:

```tex
\begin{tabular}{|l|l|}
  \hline
  1.1 & 1.2 \\ \hline
  2.1 & 2.2 \\
  \hline
\end{tabular}
```

Ao variar a descrição da coluna, obtemos os seguintes resultados:

<a href="/tex/java/latex-tables/latex-tables-9.jpg" style="display:inline-block;width:100%;">![Exemplo de saída](/tex/images/java/tutorial/latex-tables-9.jpg)</a>

Para preservar o espaçamento inicial, você pode usar `! {...}`.

<a href="/tex/java/latex-tables/latex-tables-10.jpg" style="display:inline-block;width:100%;">![Exemplo de saída](/tex/images/java/tutorial/latex-tables-10.jpg)</a>

E aqui está um exemplo de uma coluna de números de ponto flutuante alinhados ao ponto decimal:

```tex
\begin{tabular}{r@{.}l}
  3 & 14159 \\
  16 & 2 \\
  123 & 456 \\
\end{tabular}

```

<a href="/tex/java/latex-tables/latex-tables-11.jpg" style="display:inline-block;width:100%;">![Exemplo de saída](/tex/images/java/tutorial/latex-tables-11.jpg)</a>

### Usando o pacote `dcolumn`

É possível centralizar uma coluna no separador decimal usando o pacote `dcolumn`, que fornece um novo especificador de coluna para números de ponto flutuante. A maneira simples de usar este pacote é demonstrada no exemplo a seguir:

```tex
\usepackage{dcolumn}
................................................
\newcolumntype{d}[1]{D{.}{\cdot}{#1} } %the argument for d specifies the maximum number of decimal places
\begin{tabular}{l r c d{1} }
  Left&Right&Center&\mathrm{Decimal}\\
  1&2&3&4\\
  11&22&33&44\\
  1.1&2.2&3.3&4.4\\
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-12.jpg" style="display:inline-block;width:100%;">![Exemplo de saída](/tex/images/java/tutorial/latex-tables-12.jpg)</a>

Observe que uma coluna alinhada por decimal é compensada no modo matemática, daí o uso de `\mathrm` para o cabeçalho da coluna no exemplo acima. Além disso, o texto em uma coluna alinhada decimal (por exemplo, o cabeçalho) será alinhada à direita antes do separador decimal (supondo que não haja separador decimal no texto). Embora isso possa ser bom para texto muito curto ou títulos de colunas numéricas, ele parece complicado no exemplo acima. Uma solução para isso é usar o comando `\multicolumn` descrito abaixo, especificando uma única coluna e seu alinhamento. Por exemplo, para centralizar o cabeçalho * decimal * sobre sua coluna no exemplo acima, a primeira linha da própria tabela seria `esquerda e direita e centro & \ multicolumn {1} {c} {decimal} \\`.

## 4. Mesclagem de células

Uma tabela um pouco mais complexa pode ser obtida pela fusão de células horizontal e/ou verticalmente.

### Células abrangendo várias colunas

A forma geral do comando que faz uma extensão celular sobre várias colunas é: `\multicolumn {num_cols} {alinhamento} {contents}`. Aqui, `num_cols` é o número de colunas para mesclar; `alinhamento` é` l`, `c`, ` r`, ou, para ter um texto de texto, `p {width}`. E `conteúdo `são os dados que você deseja colocar nessa célula.

Aqui está o exemplo simples:

```tex
\begin{tabular}{|l|l|}
  \hline
  \multicolumn{2}{|c|}{Available currencies} \\
  \hline
  CNY & Chinese Yuan \\
  JPY & Japanese Yen \\
  GBP & Great Britain Pound \\
  USD & US Dollar \\
  CAD & Canadian Dollar \\
  EUR & Euro \\
  \hline
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-13.jpg" style="display:inline-block;width:100%;">![Exemplo de saída](/tex/images/java/tutorial/latex-tables-13.jpg)</a>

### Células que abrangem várias linhas

Para fazer várias linhas de extensão de células, você precisará incluir o pacote `multirrow`. O pacote fornece o seguinte comando: `\multirow {num_rows} {width} {contents}`.

Aqui, `num_rows` é o número de linhas para mesclar; `width` é a largura da célula (`*`para a largura natural do conteúdo) e` conteúdo 'é os dados reais a serem digitados na célula.

```tex
\begin{tabular}{|l|l|l|}
  \hline
  \multicolumn{3}{ |c| }{Available currencies} \\
  \hline
  South America & BRL & Brazilian Real \\ \hline
  \multirow{3}{*}{Asia} & CNY & Chinese Yuan \\
   & JPY & Japanese Yen \\
   & HKD & Hong Kong Dollar \\ \hline
  \multirow{3}{*}{Europe} & EUR & Euro \\
   & GBP & Great Britain Pound \\
   & CHF & Swiss Franc \\ \hline
  Oceania & AUD & Australian Dollar \\ \hline
  \multirow{2}{*}{North America} & USD & US Dollar \\
   & CAD & Canadian Dollar \\
  \hline
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-14.jpg" style="display:inline-block;width:100%;">![Exemplo de saída](/tex/images/java/tutorial/latex-tables-14.jpg)</a>

Você precisa se lembrar que, ao usar o comando `\multirow`, você deve inserir uma entrada em branco para cada célula apropriada em cada linha subsequente a ser abrangente.

### Abrangendo células em ambas as direções

O exemplo a seguir demonstra como abranger células em ambas as direções simultaneamente e obter as fronteiras desenhadas corretamente:

```tex
\begin{tabular}{cc|c|c|c|c|l}
  \cline{3-6}
  & & \multicolumn{4}{ c| }{Primes} \\ \cline{3-6}
  & & 2 & 3 & 5 & 7 \\ \cline{1-6}
  \multicolumn{1}{ |c }{\multirow{2}{*}{Powers} } &
    \multicolumn{1}{ |c| }{504} & 3 & 2 & 0 & 1 & \\ \cline{2-6}
  \multicolumn{1}{ |c }{} &
    \multicolumn{1}{ |c| }{540} & 2 & 3 & 1 & 0 & \\ \cline{1-6}
  \multicolumn{1}{ |c }{\multirow{2}{*}{Powers} } &
    \multicolumn{1}{ |c| }{gcd} & 2 & 2 & 0 & 0 & min \\ \cline{2-6}
  \multicolumn{1}{ |c }{} &
    \multicolumn{1}{ |c| }{lcm} & 3 & 3 & 1 & 1 & max \\ \cline{1-6}
\end{tabular}
```

O comando `\multicolumn {1} {` é usado para desenhar as fronteiras verticais esquerda e direita. Embora seja combinado com `\multirow {2} {*} {...}`, ainda desenha bordas verticais que abrangem apenas a primeira linha. Para compensar isso, adicionamos `\multicolumn {1} {` nas seguintes linhas abrangidas pelo `mutltirow`.

<a href="/tex/java/latex-tables/latex-tables-15.jpg" style="display:inline-block;width:100%;">![Exemplo de saída](/tex/images/java/tutorial/latex-tables-15.jpg)</a>

## 5. Tamanho da tabela

O pacote `graphicx` fornece o comando` \ redemexbox {width} {altura} {objeto} `que pode ser usado com o ambiente` tabular` para esticar ou encolher uma tabela para uma largura e altura especificadas. No exemplo a seguir, redimensionamos a tabela para largura de 12 cm, mantendo a proporção.

```tex
\resizebox{12cm}{!} {
  \begin{tabular}{|c|c|c|}                           \hline
    Header 1 & Header 2 & Header 3 \\                \hline
    Row 1, Cell 1 & Row 1, Cell 2 & Row 1, Cell 3 \\ \hline
    Row 2, Cell 1 & Row 2, Cell 2 & Row 2, Cell 3 \\ \hline
  \end{tabular}
}
```

<a href="/tex/java/latex-tables/latex-tables-16.jpg" style="display:inline-block;width:100%;">![Exemplo de saída](/tex/images/java/tutorial/latex-tables-16.jpg)</a>

Você também pode usar `\scalebox {ratio} {objeto}` da mesma maneira, mas com proporções em vez de tamanho fixo:

```tex
\scalebox{0.7}{
  \begin{tabular}...
  \end{tabular}
}
```

## 6. Tabelas de posicionamento

Você pode posicionar facilmente uma tabela em uma página se colocá -la dentro de um ambiente `tabela`.

```tex
\begin{table}[positioning_option]
  \centering
  \begin{tabular}{...}
    ...
  \end{tabular}
\end{table}
```

As opções de posicionamento disponíveis são:

`h` - colocará a tabela *aqui* aproximadamente.

`T` - posiciona a tabela na *TOP* da página.

`b` - posiciona a tabela na *parte inferior* da página.

`p` - coloque a tabela em uma página especial (apenas para tabelas).

`!` - Substituir parâmetros internos de LaTeX.

`H` - coloque a mesa neste local preciso (praticamente como` h! `).

Para centralizar uma tabela horizontalmente, você pode preceder o ambiente `tabular` com o comando `\centring` em um ambiente `tabela`.

## 7. legendas, rótulos e referências

Você pode legendar uma tabela com algum texto. Na saída, o texto será prefixado com *Tabela N.*, onde *n* é o número da tabela apropriado rastreado automaticamente pelo LATEX. Para fazer isso, use o comando `\legend`. Também é possível atribuir um rótulo a uma tabela para que a tabela possa ser referenciada em qualquer lugar do documento. O par de comandos correspondente é `\ Label` e `\ref`. Considere o seguinte exemplo:

```tex
Table \ref{table:1} is an example of a referenced \LaTeX{} element.

\begin{table}[h!]
  \centering
  \begin{tabular}{|c|c|c|} \hline
    Header 1 & Header 2 & Header 3 \\                \hline
    Row 1, Cell 1 & Row 1, Cell 2 & Row 1, Cell 3 \\ \hline
    Row 2, Cell 1 & Row 2, Cell 2 & Row 2, Cell 3 \\ \hline
  \end{tabular}
  \caption{A caption for the table.}
  \label{table:1}
\end{table}
```

Aqui, a referência na primeira linha será substituída automaticamente pelo número definido pelo comando `\Label`.

<a href="/tex/java/latex-tables/latex-tables-17.jpg" style="display:inline-block;width:100%;">![Exemplo de saída](/tex/images/java/tutorial/latex-tables-17.jpg)</a>

## 8. Tabelas para colorir

### Alterando cores em linhas de mesa

O pacote `xcolor` fornece os comandos necessários para produzir mesas com cores alternativas de linha. O pacote deve ser carregado com a opção Tabela: `\usepackage {tabela] {xcolor}`.
O comando `\rowcolors {starting_row} {ODD_COLOR} {Even_Color}` deve ocorrer antes do início do ambiente `Tabular`.

```tex
\begin{center}
  \rowcolors{2}{green}{pink}

  \begin{tabular}{lll}
    \multicolumn{3}{c}{The header} \\
    odd & odd & odd \\
    even & even & even\\
    \hiderowcolors odd & odd & odd \\
    \showrowcolors even & even & even\\
     even & even & even\\
  \end{tabular}
\end{center}
```

O comando `\hiderowcolors`, fornecido pelo pacote` xcolor`, desativando destacando a partir da linha que ocorre até o final da tabela. Para reativar o destaque, use o comando `\ShowRowColors`.

<a href="/tex/java/latex-tables/latex-tables-18.jpg" style="display:inline-block;width:100%;">![Exemplo de saída](/tex/images/java/tutorial/latex-tables-18.jpg)</a>

### Colorir células individuais

Com o pacote `xcolor`, você também pode especificar a cor de uma célula específica.

```tex
\begin{tabular}{|l|l|l|}
  \multicolumn{3}{c}{The header} \\
  \hline
  \cellcolor{red} odd & odd & odd \\
  \hline
  even & \cellcolor{red} even & even\\
  \hline
  odd & odd & \cellcolor{red} odd \\
  \hline
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-19.jpg" style="display:inline-block;width:100%;">![Exemplo de saída](/tex/images/java/tutorial/latex-tables-19.jpg)</a>

### Usando o pacote `colortbl`

O pacote `colortbl` fornece o comando `\columnColor` para especificar a cor da coluna no preâmbulo de um ambiente tabular dentro do construto `> {...}`. Isso significa que você também deve ter o pacote `Array` incluído. (Não se esqueça de incluir também o pacote `xcolor`.)

```tex
\begin{tabular}{|>{\columncolor{green}}l|>{\color{white}\columncolor{red}}c|}
  one & two\\
  three & four
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-20.jpg" style="display:inline-block;width:100%;">![Exemplo de saída](/tex/images/java/tutorial/latex-tables-20.jpg)</a>

O comando `\rowcolor` pode ser usado para especificar as cores da linha. Deve ser usado no início da linha. O comando tem a mesma sintaxe que `\columnColor`.

```tex
\begin{tabular}{l|c|}
  \rowcolor{green} one & two\\
  \rowcolor{red} three & four
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-21.jpg" style="display:inline-block;width:100%;">![Exemplo de saída](/tex/images/java/tutorial/latex-tables-21.jpg)</a>

Você também pode colorir regras verticais. Por exemplo, 

```tex
\setlength{\arrayrulewidth}{2pt}
\begin{tabular}{!{\color{blue}\vline} l !{\color{blue}\vline} l !{\color{blue}\vline}
    l !{\color{blue}\vline}}
  \multicolumn{3}{c}{The header} \\
  odd & odd & odd \\
  even & even & even\\
  odd & odd & odd \\
\end{tabular}
```

resultará em

<a href="/tex/java/latex-tables/latex-tables-22.jpg" style="display:inline-block;width:100%;">![Exemplo de saída](/tex/images/java/tutorial/latex-tables-22.jpg)</a>

Observe o uso de `\setLength {\ ArrayRulewidth} {2pt}` para alterar a espessura da regra.

No entanto, colorir `\hline` e `\CLINE` é um pouco mais complicado e está disponível com comandos extras (que também se aplicam às regras verticais). O comando `\arrayruleColor` pode ser usado globalmente ou dentro de uma tabela. Nos dois casos, afeta todas as regras subsequentes. Portanto, se você deseja uma cor diferente para as regras verticais, deve especificá -la no preâmbulo da tabela. Por exemplo,

```tex
\setlength\arrayrulewidth{2pt}
%\arrayrulecolor{blue} % to set the color for all rules
\begin{tabular}{|l!{\color{green}\vline}l|l|}
  \multicolumn{3}{c}{The header} \\
  \hline
  odd & odd & odd \\
  \arrayrulecolor{blue} \hline
  even & even & even\\
  \hline
  odd & odd & odd \\ \arrayrulecolor{red}
  \hline
\end{tabular}
```

resultará em

<a href="/tex/java/latex-tables/latex-tables-23.jpg" style="display:inline-block;width:100%;">![Exemplo de saída](/tex/images/java/tutorial/latex-tables-23.jpg)</a>

## 9. Construindo mesas longas

O ambiente `tabular` tem uma desvantagem significativa. Produz tabelas que não podem ser divididas entre as páginas com o algoritmo de quebra de página interno do Tex. Assim, se a sua tabela for longa, ela se espalhará abaixo da parte inferior da página.

Felizmente, existe o pacote `LongTable`, hoje em dia fornecido na maioria das distribuições, que define o ambiente' LongTable 'para lidar com tabelas tão longas. Na maioria dos aspectos, esse ambiente funciona da mesma maneira que o ambiente `tabular '. Existem algumas diferenças, no entanto.

Demonstraremos a maioria dos recursos do `LongTable` no exemplo a seguir, onde você também pode encontrar notas e diferenças de uso do ambiente` Tabular`. (O exemplo também usa o pacote `literal` para alguma formatação de texto, por isso deve ser incluído também.)

```tex
\begin{longtable}{|r||p{1in}|}
  \caption[An optional table caption ...]{A long table\label{long}}\\
  \hline\hline
  \multicolumn{2}{|c|}{This part appears at the top of the table}\\
  \textsc{First}&\textsc{Second}\\
  \hline\hline
  \endfirsthead % Everything above this command will appear at the beginning of the table, in the first page.

  \caption[]{(continued)}\\
  \hline\hline
  \multicolumn{2}{|c|}{This part appears at the top of every other page}\\
  \textbf{First}&\textbf{Second}\\
  \hline\hline
  \endhead % Whatever you put before this command and below \endfirsthead will be displayed at the top of the table in every page except the first one.

  \hline
  This goes at the&bottom.\\
  \hline
  \endfoot % What you put after \endhead and before this command will appear at the bottom of the table in every page except the last one.

  \hline
  These lines will&appear\\
  in place of the & usual foot\\
  at the end& of the table\\
  \hline
  \endlastfoot % The elements after \endfoot and before this command will be displayed at the bottom of the table but only in the last page where the table appears.

  \texttt{longtable} columns are specified& in the \\
  same way as in the \texttt{tabular}& environment.\\
  \verb!|r||p{1in}|! & inthis case. \\
  Each row ends with a & \verb|\\| command. \\
  The \verb|\\| command has an & optional \\
  argument, just as in & the \\
  \texttt{tabular} & environment. \\ [10pt]
  See the effect of \verb|\\[10pt]| & ? \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Also \verb|\hline| may be used, & as in \texttt{tabular}. \\
  \hline
  That was a \verb|\hline| & . \\
  \hline\hline
  That was a \verb|\hline\hline| & . \\
  \multicolumn{2}{||c||}
    {This is a \texttt{\textbackslash multicolumn\{2\}\{||c||\}}} \\
  If a page break occurs at a \verb|\hline| then & a line is drawn \\
  at the bottom of one page and at the & top of the next. \\
  \hline
  The \texttt{[t] [b] [c]} argument of \texttt{tabular} & cannot be used. \\
  The optional argument may be one of & \texttt{[l] [r] [c]} \\
  to specify whether the table should be & adjusted \\
  to the left, right, & or centrally. \\
  \hline\hline
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Some lines may take up a lot of space, like this: &
  \raggedleft This last column is a ``p'' column so this ``row'' of the table can take
  up several lines. Note however that \TeX will never break a page within such a row.
  Page breaks only occur between rows of the table or at \verb|\hline| commands.
  \tabularnewline
  Lots of lines & like this.\\
  Lots of lines & like this.\\
  Lots of lines & like this.\\
  Lots of lines & like this.\\
  Lots of lines & like this.\\
  Lots of lines & like this.\\
  \hline
  Lots of lines& like this.\\
  Lots of lines& like this.\\
\end{longtable}
```

Isso resultará em duas páginas:

<a href="/tex/java/latex-tables/latex-tables-24.jpg" style="display:inline-block;width:49%;">![Exemplo de saída](/tex/images/java/tutorial/latex-tables-24.jpg)</a>
<a href="/tex/java/latex-tables/latex-tables-25.jpg" style="display:inline-block;width:49%;">![Exemplo de saída](/tex/images/java/tutorial/latex-tables-25.jpg)</a>

Não se confunda se você não obtiver o mesmo resultado após a primeira corrida do Tex. Devido às limitações técnicas do TEX, pode levar algumas corridas para obter a mesa que você vê nas imagens.

## 10. Um exemplo de tabela complexa

Forneceremos um exemplo mais complexo de uma tabela que combina muitos dos recursos acima.

```tex
\documentclass{article}
  \usepackage{dcolumn}
  \usepackage{verbatim}
  \usepackage{colortbl}
  \usepackage[table]{xcolor}
  \usepackage{longtable}
\begin{document}
  \hbox{}\vspace{100pt} % To make the table break between pages

  \newcolumntype{A}{>{\color{white}\columncolor{red}[.5\tabcolsep]\raggedright}
    p{2cm}}
  \newcolumntype{B}{>{\columncolor{blue}[.5\tabcolsep]\color{yellow}\raggedright}
    p{3cm}}
  \newcolumntype{C}{>{\columncolor{yellow}[.5\tabcolsep]}D{.}{\cdot}{-1}}
  \newcolumntype{E}{>{\large\bfseries \columncolor{cyan}[.5\tabcolsep]}c}
  \newcolumntype{F}{>{\color{white} \columncolor{magenta}[.5\tabcolsep]}c}
  \newcolumntype{G}{>{\columncolor[gray]{0.8}[.5\tabcolsep][\tabcolsep]}l}
  \newcolumntype{H}{>{\columncolor[gray]{0.8}}l}
  \newcolumntype{I}{>{\columncolor[gray]{0.8}[\tabcolsep][.5\tabcolsep]}D{.}{\cdot}
    {-1}}
  \setlength\minrowclearance{2pt} %Before starting give a little space

  \begin{longtable}{ABC}
    \multicolumn{3}{E}{A long table example} \\
    \multicolumn{2}{F}{First two columns} & \multicolumn{1}{F}{Third column} \\
    \multicolumn{2}{F}{p-type} & \multicolumn{1}{F}{D-type (\textsf{dcolumn})}
    \endfirsthead

    \multicolumn{3}{E}{A long table example (continued)} \\
    \multicolumn{2}{F}{First two columns} & \multicolumn{1}{F}{Third column} \\
    \multicolumn{2}{F}{p-type} & \multicolumn{1}{F}{D-type (\textsf{dcolumn})}
    \endhead

    \multicolumn{3}{E}{Continued\ldots}
    \endfoot

    \multicolumn{3}{E}{The End}
    \endlastfoot

    P-column & and another one & 12.34 \\
    \multicolumn{1}{G}{Total} & \multicolumn{1}{H}{(wrong)} &
      \multicolumn{1}{I}{100.6}\\
    Some long text in the first column & bbb & 1.2 \\
    aaa & and some long text in the second column & 1.345 \\
    \multicolumn{1}{G}{Total} & \multicolumn{1}{H}{(wrong)} &
      \multicolumn{1}{I}{100.6} \\
    aaa&bbb & 1.345 \\
    Note that the colored rules in all columns stretch to accommodate large entries
      In one column. & bbb & 1.345 \\
    aaa & bbb & 100 \\
    aaa & Depending on your driver you may get unsightly gaps or lines
      where the `screens' used to produce different shapes interact
      badly. You may want to cause adjacent panels of the same color by
      specifying a larger overhang or by adding some negative space (in a
      \verb|\noalign| between rows. & 12.4 \\
    aaa & bbb & 45.3 \\
  \end{longtable}
\end{document}
```

Antes do ambiente `LongTable`, definimos tipos de colunas com o comando`\newColumnType` fornecido pelo pacote `dcolumn`. Dentro dos argumentos, usamos a notação `> {...}` para definir formatos de coluna. As definições da coluna, por sua vez, usam comandos especificando cores, alinhamento, fontes e larguras da coluna. O próprio ambiente "longTable" é outro recurso empregado. Dentro do ambiente, usamos o comando `\multicolumn` para mesclar células horizontalmente junto com os tipos de coluna previamente definidos.

O resultado de todos os esforços está abaixo:

<a href="/tex/java/latex-tables/latex-tables-26.jpg" style="display:inline-block;width:49%;">![Exemplo de saída](/tex/images/java/tutorial/latex-tables-26.jpg)</a>
<a href="/tex/java/latex-tables/latex-tables-27.jpg" style="display:inline-block;width:49%;">![Exemplo de saída](/tex/images/java/tutorial/latex-tables-27.jpg)</a>

## 11. Melhores práticas e dicas

As tabelas de composição no LaTeX podem ser uma tarefa diferenciada, mas seguir as melhores práticas e dicas podem ajudá-lo a criar tabelas claras, esteticamente agradáveis ​​e de aparência profissional. Aqui estão algumas melhores práticas e dicas valiosas para tabelas de composição no LaTeX:

1. **Use cabeçalhos de coluna significativos:**
   - Forneça cabeçalhos claros e descritivos para cada coluna, de modo a orientar os leitores na compreensão do conteúdo.
   
2. **Alinhar dados numéricos no ponto decimal:**
   - Ao apresentar dados numéricos, alinhe os números na vírgula decimal para facilitar a leitura. Pode utilizar o pacote `dcolumn` para esta finalidade.
   
3. **Evite videiras verticais**:
   - Em publicações profissionais, é geralmente recomendado evitar o uso de linhas verticais para separar colunas. Utilize linhas horizontais com moderação para maior clareza.

4. **Mantenha a consistência:**
   - Mantenha uma formatação consistente em todo o documento, incluindo tipos de letra, tamanhos de letra e alinhamento dentro das tabelas.
   
5. **Minimize o conteúdo da célula:**
   - Evite sobrecarregar as células com conteúdo excessivo. Se uma célula contiver muito texto, considere dividi-la em várias linhas ou colunas.
   
6. **Adicione legendas e rótulos:**
   - Inclua legendas informativas acima ou abaixo das suas tabelas e utilize o comando `\label` para ativar as referências cruzadas dentro do seu documento.

7. **Empregue `multirrow` e` multicolumn` "com moderação:**
    - Embora `multirow` e `multicolumn` sejam úteis para a fusão de células, evite o uso excessivo, pois pode tornar as tabelas complexas e mais difíceis de ler.

8. **Evite tabelas excessivamente complexas:**
    - Se os seus dados forem demasiado complexos para uma única tabela, considere dividi-los em várias tabelas mais pequenas ou utilizar outros recursos visuais, como gráficos ou tabelas.
    
9. **Use o espaço horizontal, pensativo:**
    - Ajuste o espaço entre colunas utilizando `\setlength{\tabcolsep}{value}` e o espaço entre linhas utilizando `\renewcommand{\arraystretch}{value}` para otimizar o layout da tabela.

10. **Revise suas tabelas:**
    - Reveja cuidadosamente e verifique se existem erros nas suas tabelas, incluindo a precisão dos dados, a formatação e o alinhamento.
    
Ao implementar essas melhores práticas e dicas, você pode criar tabelas de LaTeX que não apenas comunicam efetivamente seus dados, mas também aprimoram a qualidade geral e o profissionalismo de seus documentos.

## 12. Conclusão

Viajamos pelo intrincado mundo das estruturas de tabela no LaTeX, descobrindo a notável versatilidade e precisão que esse sistema de digitação oferece. A capacidade do LATEX de integrar perfeitamente as tabelas em documentos capacita os usuários a comunicar dados, comparações e relacionamentos complexos com graça e clareza.

Desde os conceitos fundamentais do ambiente `Tabular` até as técnicas avançadas envolvendo pacotes` multirrow` e `longTable', exploramos as ferramentas e estratégias que fazem do LaTeX uma potência para a criação de tabelas. Aprendemos como o LaTeX não apenas embeleza nossas tabelas, mas também simplifica a apresentação dos dados, ajudando em comunicação eficaz. 

Enfatizamos a importância das melhores práticas: cabeçalhos de colunas significativos, alinhamento, espaçamento adequado e consistência. Essas práticas nos permitem criar tabelas que não sejam apenas funcionais, mas visualmente atraentes e profissionais.

Enquanto você continua a explorar o LaTex, lembre -se de que dominar as estruturas da mesa é uma arte tanto quanto é uma ciência. É uma habilidade que pode aumentar significativamente o impacto de seus trabalhos, relatórios e apresentações acadêmicos. 

Portanto, armado com o conhecimento das capacidades da tabela do LaTeX, leve seus documentos para o próximo nível. Experimente, refina e inove no campo das estruturas de tabela e deixe que o LaTeX seja seu companheiro de confiança na elaboração de documentos que transmitem informações de maneira eficaz, lindamente e profissionalmente.