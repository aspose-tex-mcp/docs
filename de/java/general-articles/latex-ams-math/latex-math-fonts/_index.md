---
translation: true
template: /templates/_template-java.md
linktitle: Schriftarten in mathematischen Formeln
title: 8. Schriftarten in mathematischen Formeln | Mathematik für LaTeX-Schriftarten
weight: 80
url: /java/latex-math-fonts/
keywords: ams-latex, amsmath, amsfonts, amssymb, Latex-Math-Schriftarten, Latex-Math-Alphabete, Latex-BM-Paket, Latex-Schriftarten, Latex-Schriftarten Mathe
description: In diesem Artikel wird der Umgang mit mathematischen Schriftarten mithilfe von Standard-LaTeX sowie die Verwendung der Pakete amsmath und bm erläutert.
lastmod: "2024-09-26"
---

{{<section overview>}}

## Einführung in LaTeX-Schriftarten

Anders als bei Fließtext sind in der Regel keine automatischen Änderungen an den Schriftformen erforderlich. Verschiedene Formen haben in der Mathematik spezifische Bedeutungen. Für Vektoren können beispielsweise fette, aufrechte Buchstaben verwendet werden. Wenn sich die Zeichen in einer Formel aufgrund der Umgebungsbedingungen ändern würden, wäre das Ergebnis falsch. Aus diesem Grund unterscheidet sich der Umgang mit Schriftarten in mathematischen Formeln von dem in Texten.

Zeichen in einer Formel können in zwei Klassen unterteilt werden: Symbole und Buchstaben (einschließlich Ziffern). Tatsächlich befasst sich TeX intern mit acht Klassen, die geeignete Abstände definieren. Aber für die aktuelle Diskussion reicht die Einteilung in zwei Klassen völlig aus.

Einige Symbole, wie zum Beispiel „=“, können direkt über die Tastatur eingegeben werden. Ein Teil davon muss jedoch über einen Befehl eingegeben werden, z. B. `\leq` ergibt ein Kleiner-oder-Gleich-Zeichen. Die andere Hauptgruppe von Zeichen in einer Formel, die Buchstaben des Alphabets, werden direkt über die Tastatur eingegeben.

Im Standard-LaTeX sind mehr als 200 Symbole vordefiniert. Es ermöglicht dem Benutzer, nahezu jede gewünschte Formel zu setzen. Diese Symbole liegen in verschiedenen Schriftarten vor, können aber so aufgerufen werden, dass der Benutzer nicht wissen muss, wie sie intern dargestellt werden. Bei Bedarf können auf ähnliche Weise weitere Symbolschriften zugänglich gemacht werden.

Es gibt einen Unterschied zwischen Symbolen und Buchstaben des Alphabets, der für uns jetzt am wichtigsten ist: Symbole haben innerhalb einer Formel die gleiche grafische Darstellung, während der Benutzer das Erscheinungsbild der Buchstaben des Alphabets ändern kann. Die Befehle, die das Erscheinungsbild von Buchstaben in einer Formel ändern, werden als *Mathe-Alphabete-Bezeichner* bezeichnet, und die diesen Befehlen zugeordneten Schriftarten werden als *Mathe-Alphabete* bezeichnet. Eine Formel ändert sich nicht, wenn sie beispielsweise in einer Theoremumgebung platziert wird, in der der Text standardmäßig kursiv gesetzt ist, da die Alphabetkennungen unabhängig von umgebenden Schriftartbefehlen außerhalb der Formel sind. Dieses Verhalten ist sehr wichtig, da Zeichenformen Bedeutungen haben, die überall dort, wo die Formel in einem Dokument erscheint, unverändert bleiben müssen.

## 8.1. Bezeichner des mathematischen Alphabets

Ein Alphabet und eine große Anzahl von Symbolen reichen Wissenschaftlern nicht aus. Sie versuchen, jede verfügbare Schriftart zu verwenden, um spezielle Konzepte zu kennzeichnen. Neben fremden Alphabeten wie griechischen Buchstaben, auf die normalerweise als Symbole zugegriffen wird – `\alpha`, `\beta` usw. – finden wir serifenlose Buchstaben für Matrizen, fette Serifenbuchstaben für Vektoren, Fraktur-Schriftarten für Gruppen, Ideale oder Felder. Andere verwenden kalligrafische Formen, um Mengen zu bezeichnen. Die Anzahl der Konventionen ist unendlich und sie unterscheiden sich von Disziplin zu Disziplin. Und LaTeX berücksichtigt dies und ermöglicht es, neue Bezeichner für mathematische Alphabete zu deklarieren und sie jeder gewünschten Schriftformgruppe zuzuordnen, anstatt sich nur auf einen vordefinierten Satz zu verlassen, der nicht erweitert werden kann. Bei diesen Bezeichnern handelt es sich um spezielle Befehle zur Verwendung in einer Formel, die alle Buchstaben des Alphabets in ihrem Argument in einer bestimmten Schriftart setzen. Diese Bezeichner können in verschiedenen Formeln unterschiedliche Schriftarten verwenden, wie wir [später](/tex/{{lang.url-fragment}}java/latex-math-fonts/#3-math-formula-versions) sehen werden, aber innerhalb einer Formel wählen sie unabhängig von den Umgebungsbedingungen immer dieselbe Schriftart aus.

### Vordefinierte Alphabet-Bezeichner
LaTeX verfügt bereits über einige integrierte Alphabet-Bezeichner. Sie sind in der folgenden Tabelle aufgeführt. Die letzten beiden Zeilen zeigen, dass die in Formeln verwendeten Buchstaben dem Mathematikalphabet `\mathnormal` entnommen sind. Andererseits haben die von `\mathit` erzeugten Buchstaben unterschiedliche Abstände, was bedeutet, dass dieses Alphabet verwendet werden kann, um vollständige Wortvariablennamen bereitzustellen, die in einigen Disziplinen üblich sind.

| *Command* | *Example code* | *Result* |
|---|---|---|
| `\mathcal` | `$\mathcal{A}=a$` | !["Calligraphic A Equals a"](/tex/images/java/tutorial/latex-ams-math-8-1.png) |
| `\mathrm` | `$\mathrm{max}_i$`| !["Roman Max Subscript i"](/tex/images/java/tutorial/latex-ams-math-8-2.png) |
| `\mathbf` | `$\sum x = \mathbf{v}$`| !["Bold Sum x Equals v"](/tex/images/java/tutorial/latex-ams-math-8-3.png) |
| `\mathsf` | `$\mathsf{G}_1^2$`| !["Sans-serif G Subscript 1 Superscript 2"](/tex/images/java/tutorial/latex-ams-math-8-4.png) |
| `\mathtt` | `$\mathtt{W}(a)$`| !["Typewriter W of a"](/tex/images/java/tutorial/latex-ams-math-8-5.png) |
| `\mathnormal` | `$\mathnormal{abc}=abc$`| !["Normal abc Equals abc"](/tex/images/java/tutorial/latex-ams-math-8-6.png) |
| `\mathit` | `$differ\neq\mathit{differ}$`| !["Italic Differ Not Equal to Differ"](/tex/images/java/tutorial/latex-ams-math-8-7.png) |

In LaTeX2e sind mathematische Alphabetbezeichner Befehle mit einem Argument, einem einzelnen Buchstaben oder einem einzelnen Wort, die in einer speziellen Schriftart gesetzt werden müssen.


```tex
Therefore, $\mathsf{G}$ can be computed as
\begin{equation}
\mathsf{G} = \mathcal{A} +
             \sum_{i=1}^{n} \mathcal{B}_{i}
\end{equation}
```

![Vordefinierte mathematische Alphabet-Bezeichner](/tex/images/java/tutorial/latex-ams-math-8-8.png)

***Standard-Mathe-Alphabet***

Wenn Sie keinen Alphabetbezeichner explizit angeben, aus welchem ​​Alphabet werden die Alphabetzeichen ausgewählt? Mit anderen Worten: Was ist das Standard-Mathe-Alphabet? Die Antwort ist, dass es kein einheitliches Standardalphabet für Mathematik gibt. Das LaTeX-System kann so eingerichtet werden, dass alphabetische Zeichen aus verschiedenen Alphabeten abgerufen werden, es sei denn, der Benutzer fragt ausdrücklich nach einem bestimmten Zeichen. Dies ist normalerweise der Fall, wie das folgende Beispiel zeigt.

```tex
\begin{eqnarray}
x &=& 12345 \\
\mathrm{x} &=& \mathrm{12345} \\
\mathnormal{x} &=& \mathnormal{12345}
\end{eqnarray}
```

![Kein Standard-Mathe-Alphabet](/tex/images/java/tutorial/latex-ams-math-8-9.png)

Hier können Sie sehen, dass `\mathrm` die Ziffern und `\mathnormal` die Buchstaben nicht ändert, sodass die Standardeinstellung für Ziffern im normalen Setup das mit `\mathrm` und dem verknüpfte mathematische Alphabet ist Der Standardwert für Buchstaben ist der mit `\mathnormal` verknüpfte. Dieses Verhalten kann mit dem Befehl „\DeclareMathSymbol“ gesteuert werden.

### Welche Schriftart verwendet LaTeX für Mathematik?

In LaTeX ist die für den Mathematikmodus verwendete Standardschriftart normalerweise *Computer Modern*. Sie können jedoch auch andere Schriftarten verwenden, indem Sie diese mithilfe von Paketen in der Präambel Ihres LaTeX-Dokuments angeben.

### Benutzerdefinierte Alphabetkennungen

Sie können den Befehl `\DeclareMathAlphabet` verwenden, um eine neue Kennung für das mathematische Alphabet zu definieren. Nehmen wir an, Sie möchten eine schräge serifenlose Schriftart als Mathematikalphabet verfügbar machen. Zunächst entscheiden Sie sich für einen neuen Befehlsnamen, z. B. `\msfsl`, der als Alphabet-ID verwendet werden soll. Anschließend können Sie anhand der nachstehenden Schriftartenklassifizierungstabelle eine geeignete Schriftartengruppe finden, die Sie dieser Alphabetkennung zuweisen können.

![Klassifizierung der Computer Modern-Schriftfamilien](/tex/images/java/tutorial/latex-ams-math-8-10.png)

Sie werden feststellen, dass die **Computer Modern Sans**-Familie beispielsweise aus einer mittelgroßen Serie mit aufrechten und schrägen Formen besteht. Wenn Sie sich entscheiden, die schräge Form dieser Familie zu verwenden, teilen Sie dies LaTeX mit `\DeclareMathAlphabet` mit.

```text
\DeclareMathAlphabet{cmd}{encoding}{family}{series}{shape}
```

Die Deklaration enthält (neben dem Bezeichner selbst) vier Parameter: den Codierungsnamen, die Familie, die Serie und die Form der zu verwendenden Schriftart. Der im folgenden Beispiel definierte Alphabetbezeichner wechselt immer zu **Computer Modern Sans** mittel geneigt.

```tex
\DeclareMathAlphabet{\msfsl}{OT1}{cmss}{m}{sl}
% -------------------------------------------------------------------------------
We demonstrate this with the formula
\begin{equation}
\sum \msfsl{A}_{i} = a \tan \beta
\end{equation}
```

![Deklarieren einer benutzerdefinierten Mathe-Alphabet-ID](/tex/images/java/tutorial/latex-ams-math-8-11.png)

Sie können auch eine vorhandene Kennung des mathematischen Alphabets in einer Paketdatei oder in der Präambel Ihres Dokuments neu definieren. Zum Beispiel,

```tex
\DeclareMathAlphabet{\mathsf}{OT1}{pag}{m}{n}
```

überschreibt die Standardeinstellungen für die Alphabetkennung `\mathsf`. In Ihren Formeln wird auf **Adobe Avant Garde** umgestellt.

> Beachten Sie: Wenn das betreffende mathematische Alphabet Teil einer Symbolschriftart ist, die aus anderen Gründen bereits von LaTeX geladen wurde (z. B. `\mathcal`), ist es besser, `\DeclareSymbolFontAlphabet` zu verwenden, da hierdurch die eher begrenzten Ressourcen von TeX für Mathematik besser genutzt werden.

## Beste Mathe-Schriftarten

Neben der Standardschriftart *Computer Modern* bietet LaTeX sieben integrierte Schriftarten zum Setzen mathematischer Alphabete, sodass Benutzer ihre mathematischen Ausdrücke anpassen können, ohne zusätzliche Pakete in der Präambel zu benötigen. Und die beste Option für Sie ist die Verwendung einer dieser 8 Schriftarten.

| **Schriftart** | **Verwendung** | **Befehl** |
|---|---|---|
|Aufrecht Roman | Standard-Aufrecht-Schriftart|`\mathrm{}`|
|Kalligrafisch | Wird zum Setzen von normalen mathematischen Buchstaben verwendet.|`\mathnormal{}`|
|Kalligrafisch | Wird zum Setzen von Großbuchstaben mit einer speziellen kalligrafischen Schriftart verwendet.|`\mathcal{}`|
|Kursivschrift| Text kursiv formatieren|`\mathit{}`|
|Aufrecht [Sans Serif](/font/net/what-is-font/sans-serif-fonts/)| Legt aufrechte Sans-Serif-Buchstaben fest|`\mathsf{}`|
|Aufrecht Roman fett| Wird zum Setzen von aufrechten Roman-Fettbuchstaben verwendet|`\mathbf{}`|
|Schreibmaschinenschrift|Wird zum Setzen von aufrechten Schreibmaschinenbuchstaben verwendet.|`\mathtt{}`|


## 8.2. Textschriftbefehle in Mathematik

Obwohl Textschriftartdeklarationen wie `\rmfamily` in der Mathematik nicht verwendet werden können, können die Befehle zum Ändern der Schriftart – z. B. `\textrm` – sowohl in Text als auch in Mathematik verwendet werden. Mit diesen Befehlen können Sie vorübergehend vom mathematischen zum Textkontext wechseln und Text in die Mitte Ihrer Formel setzen, der logischerweise Teil des umgebenden Textes außerhalb der Formel ist. Die zum Setzen dieses Textes verwendete Schriftart hängt von den Umgebungsbedingungen ab, was bedeutet, dass sie die aktuelle Kodierung, Familie, Serie und Form erbt, wie im Beispiel unten.

```tex
\sffamily The result will be
\[ x = 10 \textbf{ and thus } y = 12 \]
```

![Textschriftbefehle in Mathematik](/tex/images/java/tutorial/latex-ams-math-8-12.png)

Hier sehen wir, dass die **Sans**-Familie beibehalten wurde und die Serie auf fett umgestellt wurde. Der Befehl [`\text`](/tex/{{lang.url-fragment}}java/latex-text-in-math-formula/#61-the-text-command) aus dem Paket „amstext“ (das auch von `amsmath` geladen wird) könnte sich als nützlicher erweisen. Es übernimmt die aktuellen Kodierungs-, Familien-, Serien- und Formwerte, ohne sie zu ändern.

## 8.3. Versionen mathematischer Formeln

Wir haben besprochen, wie man Teile einer Formel mithilfe mathematischer Alphabet-Bezeichner ändert. Mit LaTeX können Sie auch das Erscheinungsbild einer Formel als Ganzes ändern. Mathematische Formeln werden immer in einer bestimmten *mathematischen Version* gesetzt. Und Sie können außerhalb des Mathematikmodus zwischen Mathematikversionen wechseln, indem Sie den Befehl `\mathversion` verwenden, der das Gesamtlayout der folgenden Formeln ändert.

LaTeX verfügt standardmäßig über zwei Mathe-Versionen: *normal* und *bold*. Und spezielle Pakete stellen weitere Versionen bereit. Beispielsweise richtet das *mathtime*-Paket (für die kommerziellen **MathTime**-Schriftarten) eine Mathematikversion namens *heavy* ein, um Formeln mit extrem fetten Symbolen zu setzen, wie sie von den **MathTime**-Schriftarten bereitgestellt werden.

Offensichtlich ist die Standard-Mathe-Version `\mathversion{normal}`. Die fett gedruckte Version wiederum erzeugt fettere Buchstaben und Symbole, obwohl große Operatoren wie `\sum` standardmäßig nicht geändert werden. Das folgende Beispiel zeigt die gleiche Formel zunächst in der normalen und dann in der fettgedruckten mathematischen Version.

```tex
\begin{equation}
  \sum_{j=1}^{z} j = \frac{z(z+1)}{2}
\end{equation}
\mathversion{bold}
\begin{equation}
  \sum_{j=1}^{z} j = \frac{z(z+1)}{2}
\end{equation}
```

![Mathe-Versionen](/tex/images/java/tutorial/latex-ams-math-8-13.png)

Die Verwendung von `\mathversion` kann in bestimmten Situationen, beispielsweise in Überschriften, geeignet sein, Sie müssen jedoch bedenken, dass eine Änderung der Version eine Änderung des Erscheinungsbilds und möglicherweise der Bedeutung der gesamten Formel bedeutet. Wenn Sie nur einige Symbole oder Zeichen innerhalb einer Formel abdunkeln möchten, sollten Sie stattdessen die Alphabetkennung `\mathbf` für Zeichen und/oder den Befehl `\bm` verwenden, der vom Paket [`bm`](/tex/{{lang.url-fragment}}java/latex-math-fonts/#5-bold-face-in-formulas-the-bm-package) bereitgestellt wird Ändern Sie die `\mathversion`.

Wenn Sie die Mathematikversion ändern, sucht LaTeX in seinen internen Tabellen, um herauszufinden, wo sich alle Symbole für diese neue Mathematikversion befinden. Möglicherweise werden auch alle oder einige der Bezeichner des mathematischen Alphabets geändert und mit anderen Schriftformen in dieser Version verknüpft.

Aber was passiert mit benutzerdefinierten Alphabet-Bezeichnern wie `\msfsl`, die wir im [Beispiel](/tex/{{lang.url-fragment}}java/latex-math-fonts/#custom-alphabet-identifiers) definiert haben? Solange Sie sie mit `\DeclareMathAlphabet` deklariert haben, bleiben sie in allen Mathe-Versionen gleich.

Wenn der Mathe-Alphabet-Bezeichner eine andere Schriftart in einer speziellen Mathe-Version erzeugen soll, müssen Sie LaTeX dies mit dem Befehl `\SetMathAlphabet` mitteilen. Beispielsweise ist in der Standardeinstellung die Alphabetkennung `\mathsf` wie folgt definiert:

```tex
\DeclareMathAlphabet{\mathsf}{OT1}{cmss}{m}{n}
\SetMathAlphabet{\mathsf}{bold}{OT1}{cmss}{bx}{n}
```

Die erste Zeile legt das Medium **Computer Modern Sans** als Standard für `\mathsf` in allen Mathe-Versionen fest. Die zweite Zeile weist LaTeX an, **Computer Modern Sans** fett erweitert in der fetten Mathe-Version zu verwenden.

```tex
\SetMathAlphabet{cmd}{version}{encoding}{family}{series}{shape}
```

Wie Sie vielleicht anhand des vorherigen Beispiels erraten haben, benötigt `\SetMathAlphabet` sechs Argumente: die Kennung des mathematischen Alphabets, den Namen der mathematischen Version, für die Sie eine spezielle Einrichtung definieren, und vier Parameter zur Identifizierung der Schriftart, mit der Sie eine Verknüpfung herstellen Ihr Setup.
Wie bereits erwähnt, können Sie eine vorhandene Mathe-Alphabet-Kennung mithilfe von `\DeclareMathAlphabet` neu definieren. Wenn Sie dies tun, werden alle vorherigen `\SetMathAlphabet`-Deklarationen für diesen Bezeichner aus dem internen Speicher von LaTeX entfernt. Daher wird der Bezeichner in allen Mathe-Versionen gleich ausgegeben, es sei denn, Sie fügen neue `\SetMathAlphabet`-Deklarationen dafür hinzu.

## 8.4. Optimieren von Schriftarten in Formeln mit AMS-LATEX-Paketen

Das Paket *amsfonts* (und *amssymb*) definiert zwei mathematische Alphabete: das Euler-Fraktur-Alphabet (`\mathfrak`) und das Blackboard Bold-Alphabet (`\mathbb`). Siehe das Beispiel unten.

```tex
\usepackage{amsfonts}
% -------------------------------------------------------------------------------
$ \forall n \in \mathbb{N} : \mathfrak{M}_n \leq \mathfrak{A} $
```

![amsfonts Mathe-Alphabet-Bezeichner](/tex/images/java/tutorial/latex-ams-math-8-14.png)

## 5. Fetter Mathe-Schriftstil. Das „bm“-Paket

Nur für lateinische Buchstaben können Sie den Befehl `\mathbf` verwenden. Für alles andere gibt es das Paket „bm“. Laden Sie es einfach und verwenden Sie `\bm`, um jede Formel so fett und schön zu machen, wie es die verfügbaren Schriftarten zulassen.

Das folgende Beispiel zeigt viele Möglichkeiten, die Befehle `\bm` und `\mathbf` zu verwenden. Es zeigt auch eine Strategie zum Definieren von Kurznamen für häufig vorkommende Fettdrucksymbole unter Verwendung sowohl des standardmäßigen LaTeX-Standards `\newcommand` als auch `\bmdefine`, das vom „bm“-Paket bereitgestellt wird. Beachten Sie, dass `\mathbf{xy}` nicht identisch mit `\bm{xy}` ist. Ersteres erzeugt fettes römisches „**xy**“ und letzteres erzeugt „***xy***“ (fette Mathe-Kursivschrift).

```tex
\usepackage{amsmath,amssymb,bm}
\newcommand\bfB{\mathbf{B}} \newcommand\bfx{\mathbf{x}}
\bmdefine\bpi{\pi} \bmdefine\binfty{\infty}
% -------------------------------------------------------------------------------
\section{The bold equivalence
  $\sum_{j < B} \prod_\lambda : \bm{\sum_{x_j} \prod_\lambda}$}
\begin{gather}
  B_\infty + \pi B_1 \sim \bfB_{\binfty} \bm{+} \bpi \bfB_{\bm{1}}
    \bm {\sim B_\infty + \pi B_1}\\
  B_\binfty + \bpi B_{\bm{1}} \bm{\in} \bm{\biggl\lbrace}
    (\bfB, \bfx) : \frac {\partial \bfB}{\partial\bfx}
    \bm{\lnapprox} \bm{1} \bm{\biggr\rbrace}
\end{gather}
```

![Verwendung des bm-Pakets](/tex/images/java/tutorial/latex-ams-math-8-15.png)

In diesem Beispiel versucht „bm“ sein Bestes, die Wünsche nach fetten Versionen einzelner Symbole und Buchstaben zu erfüllen. Doch wer genau hinschaut, erkennt, dass die Ergebnisse nicht immer optimal sind. Beispielsweise werden die Summen- und Produktoperatoren mit einer Technik erstellt, die als „Poor Man's Bold“ bekannt ist und bei der das Symbol dreimal mit leichtem Versatz überdruckt wird. Außerdem werden die geschweiften Klammern überhaupt nicht fett dargestellt. Solche Nachteile lassen sich nicht vermeiden, da es für einige Symbole bei Verwendung der Mathe-Schriftarten **Computer Modern** einfach keine fette Variante gibt.

Welche genauen Regeln befolgt `\bm`, um die Symbole in seinem Argument fett darzustellen? Im Allgemeinen nutzt es die Tatsache, dass LaTeX eine **fette** Mathe-Version enthält (zugänglich über `\boldmath`), um eine ganze Formel fett zu setzen (vorausgesetzt, geeignete fette Schriftarten sind verfügbar und eingerichtet). Für jedes Symbol schaut sich der Befehl `\bm` diese mathematische Version an, um zu sehen, was in dieser Version getan würde. Wenn sich die für das Symbol ausgewählte Schriftart von der in der normalen Mathe-Version ausgewählten unterscheidet, wird das Symbol dann in dieser fetten Schriftart gesetzt, wodurch ein perfektes Ergebnis erzielt wird (vorausgesetzt, die fette Mathe-Version wurde ordnungsgemäß eingerichtet). Wenn die Schriftarten in beiden Versionen identisch sind, wird davon ausgegangen, dass keine fette Variante verfügbar ist, und es wird die Fettschrift des armen Mannes angewendet.

> Laden Sie das „bm“-Paket nach Paketen, die die vorhandene Mathematik-Schriftartkonfiguration ändern!

Noch komplexer ist die Situation bei Trennzeichen, wie im Beispiel `\biggl\lbrace`. TeX setzt normalerweise ein Trennzeichen durch ein Glyph, das so ausgewählt wird, dass es einer angeforderten Höhe aus einer Folge verschiedener Größen entspricht. Diese Glyphen können in unterschiedlichen Schriftarten vorliegen, und für eine bestimmte Größe können Fettvarianten vorhanden sein oder auch nicht. All dies zusammen macht es für `\bm` unmöglich, zuverlässig zu bestimmen, ob die Fettschrift des armen Mannes angewendet werden muss. Daher wird das Trennzeichen mit den Schriftarten gesetzt, die in der fetten Mathe-Version angeboten werden. Bei den Mathe-Schriftarten **Computer Modern** ist nur die kleinste Trennzeichengröße in Fettschrift verfügbar; Alle anderen Größen stammen von Schriftarten, die keine fetten Varianten haben.

```tex
\usepackage{bm}
% -------------------------------------------------------------------------------
$\bm{\Biggl\lbrace\biggl\lbrace\Bigl\lbrace\bigl \lbrace \lbrace
  \mathcal{Q}
  \rangle \bigr\rangle\Bigr\rangle\biggr\rangle
\Biggr\rangle}$
```

![Trennzeichen, die durch den \bm-Befehl fett gemacht (und nicht fett gemacht) wurden](/tex/images/java/tutorial/latex-ams-math-8-16.png)
Wenn ein Befehl, der selbst Argumente annimmt, normalerweise im Argument von `\bm` enthalten ist, muss dieser Befehl vollständig im Argument von `\bm` enthalten sein. Daher werden alle Teile des Satzmaterials fett gedruckt. Wenn Sie möchten, dass die Ausgabe eines Befehls mit Argumenten nur teilweise fett dargestellt wird, sollten Sie wie folgt vorgehen. Sie sollten die Symbole, die nicht fett dargestellt werden sollen, in eine `\mbox` einfügen und die mathematische Version innerhalb des Boxinhalts explizit mit `\unboldmath` zurücksetzen. TeX betrachtet eine `\mbox` als Symbol der Klasse *Ordinary*. Um den richtigen Abstand zu erhalten, müssen Sie es daher möglicherweise mit `\mathbin`, `\mathrel` oder `\mathop` umgeben.

```tex
\usepackage{amsmath,bm}
% -------------------------------------------------------------------------------
$ \bm{\sqrt[2]{x \times \alpha}} $ but
$ \bm{\sqrt[2]{x \mathbin{\mbox{\unboldmath$\times$}} \alpha}} $
or the similar
$ \bm{\sqrtsign}{\bm{x} \times \bm{\alpha}} $
```

![\bm mit Befehlen, die Argumente annehmen](/tex/images/java/tutorial/latex-ams-math-8-17.png)

Glücklicherweise sind solch komplexe Operationen selten erforderlich. In den meisten Fällen, in denen es um Befehle mit Argumenten geht, müssen nur Teile des Arguments fett dargestellt werden. Und dies kann durch die Verwendung des Befehls `\bm` innerhalb dieser Argumente erreicht werden. Wie bei `\sqrtsign` im vorherigen Beispiel ist `\bm` für den üblichen Fall fetter Akzente speziell so programmiert, dass das Argument des Akzents außerhalb seines eigenen Arguments stehen kann. Wenn Sie solche Akzente jedoch regelmäßig benötigen, definieren Sie am besten eigene Abkürzungen, wie im folgenden Beispiel.

***Verbesserung der Leistung***

Obwohl `\bmdefine\bpi{\pi}` einfach eine Abkürzung für `\newcommand\bpi{\bm{\pi}}` zu sein scheint, ist die Wahrheit fast das Gegenteil: `\bm` definiert ein neues verstecktes Temporär Befehl mit `\bmdefine` und verwendet dann sofort diesen temporären Befehl, um das fette Symbol zu erzeugen. Mit anderen Worten: `\bmdefine` erledigt die ganze harte Arbeit! Wenn Sie beispielsweise häufig etwas verwenden, das über `\bm{\alpha}` definiert ist, wird jedes Mal ein neues `\bmdefine` ausgeführt. Wenn Sie die `\bmdefine\balpha{\alpha}`-Definition in der Präambel angeben, dann erledigt `\bmdefine` seine zeitaufwändige Arbeit nur einmal, egal wie oft `\balpha` verwendet wird.

```tex
\usepackage{bm}
\bmdefine\bhat{\hat}
% -------------------------------------------------------------------------------
$\hat a \neq \bm{\hat a} \neq \bm\hat a = \bhat a\neq \bm\widehat a$
```

![Optimierte Darstellung von Akzenten in Fettschrift mit dem \bm-Befehl](/tex/images/java/tutorial/latex-ams-math-8-18.png)

Dieses Beispiel zeigt auch, dass die Akzente mit variabler Breite (z. B. `\widehat`) einen Nachteil mit den Trennzeichen haben: Im Mathematik-Setup **Computer Modern** stammen sie aus einer Schriftart, für die keine fette Variante verfügbar ist.