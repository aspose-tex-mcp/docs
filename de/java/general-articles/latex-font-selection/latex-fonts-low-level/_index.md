---
translation: true
template: /templates/_template-java.md
linktitle: 5. Low-Level-Schnittstelle
title: Die Low-Level-Schnittstelle | Aspose.TeX für Java
weight: 50
url: /java/latex-fonts-low-level/
keywords: Latex, Latex-Schriftarten, Latex-Schriftersatz, Latex-Schriftfamilien, Latex-Schriftserien, Latex-Schriftformen
description: Dieser Artikel behandelt die LaTeX-Low-Level-Schriftartschnittstelle, die hauptsächlich in Befehlsdefinitionen verwendet wird.
lastmod: "2024-09-26"
---

{{<section overview>}}

Im Gegensatz zu den High-Level-Schriftbefehlen, die für die Verwendung in einem Dokument gedacht sind, dienen die Low-Level-Befehle hauptsächlich der Definition neuer Befehle in Paketen oder in der Dokumentpräambel. Um solche Befehle optimal nutzen zu können, ist es hilfreich, die interne Organisation von Schriftarten im Schriftartenauswahlschema (NFSS) von LaTeX zu verstehen.

Einerseits besteht das Ziel des Schriftartenauswahlschemas von LaTeX darin, eine rationale Schriftartenauswahl mit Algorithmen zu ermöglichen, die sich an den Prinzipien des generischen Markups orientieren. Zu diesem Zweck wäre es wünschenswert, unabhängige Änderungen an möglichst vielen Schriftattributen zu ermöglichen. Andererseits enthalten Schriftfamilien im wirklichen Leben normalerweise nur eine Teilmenge der unzähligen vorstellbaren Kombinationen von Schriftattributen. Das Zulassen unabhängiger Änderungen an zu vielen Attributen führt daher zu zu vielen Kombinationen, für die keine echte externe Schriftart verfügbar ist und eine Standardschrift ersetzt werden muss.

Intern verfolgt LaTeX fünf unabhängige Schriftartattribute: die *aktuelle Kodierung*, die *aktuelle Familie*, die *aktuelle Serie*, die *aktuelle Form* und die *aktuelle Größe*. Das Codierungsattribut wurde in NFSS Release 2 eingeführt, als klar wurde, dass die Unterstützung mehrerer Sprachen nicht möglich wäre, ohne das Zeichencodierungsschema unabhängig von den anderen Schriftartattributen beizubehalten.

Die Werte dieser Attribute bestimmen die aktuell verwendete Schriftart. LaTeX verwaltet außerdem eine große Menge an Tabellen, die dazu dienen, Attributkombinationen mit externen Schriftarten zu verknüpfen (d. h. „.tfm“-Dateien, die die Daten enthalten, die LaTeX für seine Arbeit benötigt). Die Auswahl der Schriftart erfolgt dann in zwei Schritten:

1. Eine Reihe von Schriftartattributen werden mit den Low-Level-Befehlen „\fontencoding“, „\fontfamily“, „\fontseries“, „\fontshape“ und „\fontsize“ geändert.

2. Die Schriftart, die diesen neuen Attributeinstellungen entspricht, wird durch Aufrufen des Befehls „\selectfont“ ausgewählt.

Der zweite Schritt besteht aus mehreren Aktionen. Zunächst prüft LaTeX, ob die Schriftart, die den gewünschten Attributeinstellungen entspricht, dem System bekannt ist (d. h. die „.tfm“-Datei ist bereits geladen), und wenn ja, wird diese Schriftart ausgewählt. Andernfalls werden die internen Tabellen durchsucht, um den externen Schriftartnamen zu finden, der diesen Einstellungen zugeordnet ist. Wenn ein solcher Schriftartname gefunden wird, wird die entsprechende „.tfm“-Datei in den Speicher eingelesen und dann die Schriftart zum Setzen ausgewählt. Wenn der Schriftartname nicht gefunden wird, versucht LaTeX, eine alternative Schriftart zu finden, wie später in diesem Artikel erläutert.


## 5.1. Individuelle Schriftattribute festlegen

Für jedes Schriftartattribut gibt es einen Befehl, um seinen aktuellen Wert zu ändern. Alle diese Befehle akzeptieren mehr oder weniger jede beliebige Zeichenfolge als Argument, aber nur wenige Werte sind sinnvoll. Diese Werte sind nicht fest in NFSS verankert, sondern sind in den internen Tabellen festgelegte Konventionen. In den folgenden Abschnitten werden die Namenskonventionen vorgestellt, die im Standard-LaTeX-Setup verwendet werden. Jeder kann dieses Setup jedoch ändern, indem er neue Schriftartdeklarationen in den internen Tabellen hinzufügt. Normalerweise sollte jeder, der neue Schriftarten für die Verwendung mit LaTeX einrichtet, versuchen, diese Konventionen nach Möglichkeit einzuhalten, da nur eine konsistente Namenskonvention garantieren kann, dass in einem generisch markierten Dokument geeignete Schriftarten ausgewählt werden.

Wenn Sie über diese Schnittstelle eine bestimmte Schriftart auswählen möchten – zum Beispiel Computer Modern Dunhill Bold Condensed Italic 14pt – reicht die Kenntnis der Schnittstellenkonventionen allein nicht aus, da keine externe Schriftart für jede Kombination von Attributwerten existiert. Sie könnten versuchen, etwa Folgendes anzugeben:

```tex
\fontencoding{OT1}\fontfamily{cmdh}\fontseries{bc}\fontshape{it}%
\fontsize{14}{16pt}\selectfont
```

Dieser Code wäre gemäß den Namenskonventionen korrekt, wie wir weiter unten sehen werden. Da diese Attributkombination jedoch keiner echten Schriftart entspricht, müsste LaTeX sie durch eine andere Schriftart ersetzen. Der Ersetzungsmechanismus wählt möglicherweise eine Schriftart aus, die sich stark von der gewünschten unterscheidet. Sie sollten daher anhand der Schriftartentabellen prüfen, ob die gewünschte Kombination verfügbar ist. Hier finden Sie weitere Details zum [Schriftartersetzungsprozess](/tex/{{lang.url-fragment}}java/latex-fonts-low-level/#53-automatic-substitution-of-fonts).

### Auswahl der Schriftfamilie

Die Schriftfamilie wird mit dem Befehl „\fontfamily“ ausgewählt. Als Argument nimmt es eine Zeichenfolge an, die auf eine in den internen Tabellen deklarierte Schriftfamilie verweist. Die Zeichenfolge wurde bei der Einrichtung dieser Tabellen definiert und ist normalerweise eine kurze Buchstabenfolge – zum Beispiel „cmr“ für die Familie Computer Modern Roman. Die Familiennamen sollten nicht länger als fünf Buchstaben sein, da sie mit eventuell drei weiteren Buchstaben zu einem Dateinamen zusammengefasst werden, der auf manchen Systemen maximal acht Buchstaben haben darf.

### Auswahl der Schriftserie

Der Befehl „\fontseries“ ändert das Serienattribut. Die Serie kombiniert in ihrem Argument eine Gewichtung und eine Breite, was bedeutet, dass es unmöglich ist, die Breite der aktuellen Schriftart unabhängig von ihrer Gewichtung zu ändern. Dies ist akzeptabel, da es unwahrscheinlich ist, dass Gewicht oder Breite einzeln geändert werden müssen. Im Gegenteil: Eine Änderung des Gewichts geht in der Spezifikation des Designers oft mit einer Änderung der Breite einher. Dies ist keine große Überraschung, da Gewichtsänderungen das horizontale Erscheinungsbild der Buchstaben verändern und daher Anpassungen der Ausdehnung (Breite) erforderlich machen, um ein ausgewogenes Erscheinungsbild zu erzielen.

Die Bezeichnungen für das Gewicht und die Breite sind in den Seriennamen abgekürzt, so dass jede Kombination einzigartig ist. Diese Namenskonventionen sind in der folgenden Tabelle aufgeführt. Jedes Vorkommen von „m“ (steht für mittleres Gewicht oder Breite) wird weggelassen, es sei denn, Gewicht und Breite sind mittelgroß. In diesem Fall wird ein einzelnes „m“ verwendet. Beispielsweise wäre die fette Darstellung in erweiterter Darstellung „bx“, die mittlere Darstellung wäre „x“ und die fette Darstellung in mittlerer Darstellung wäre `b`.

![Benennungskonventionen für Schriftserien](/tex/images/java/tutorial/latex-font-selection-5-1.png)

### Auswahl der Schriftform

Der Befehl „\fontshape“ ändert das Formattribut. Für Standardformen werden Abkürzungen mit einem oder zwei Buchstaben verwendet. Diese Formen sind in der folgenden Tabelle aufgeführt:

![Benennungskonventionen für Schriftartformen](/tex/images/java/tutorial/latex-font-selection-5-2.png)

### Auswahl der Schriftgröße

Der Befehl „\fontsize{<size>}{<skip>}“ ändert die Schriftgröße. Es werden zwei Argumente benötigt: die „<Größe>“, zu der gewechselt werden soll, und die Grundlinie „<skip>“ (der Abstand zwischen den Grundlinien für diese Größe). Schriftgrößen werden normalerweise in Punkt gemessen, daher wird die Einheit vereinbarungsgemäß weggelassen. Das Gleiche gilt auch für das zweite Argument. Wenn der Grundliniensprung jedoch eine Gummilänge sein soll, müssen Sie eine Einheit angeben. Daher könnte eine gültige Größenänderung beantragt werden


```tex
\fontsize{14.4}{17}\selectfont
```

Selbst wenn eine solche Anfrage gültig ist, gibt es möglicherweise keine entsprechende externe Schriftart in dieser Größe. In einem solchen Fall versucht LaTeX, eine nahegelegene Größe zu finden, wenn seine internen Tabellen eine Größenkorrektur zulassen, oder meldet andernfalls einen Fehler.

Wenn Sie Schriftarten verwenden, die in beliebigen Größen vorliegen, können Sie natürlich jede gewünschte Größe auswählen:


```tex
\fontsize{1in}{1.2in}\selectfont A text in an arbitrary font size
```

### Auswahl der Kodierung

Der Befehl „\fontencoding“ wird verwendet, um die Kodierung zu ändern. Das Argument ist der interne Name für die gewünschte Kodierung. Dieser Name muss LaTeX bekannt sein, entweder als eine der vordefinierten Kodierungen (vom Kernel geladen) oder wie mit dem Befehl „\DeclareFontEncoding“ deklariert. Hier finden Sie weitere Informationen zum [Deklarieren von Schriftartenkodierungen](/tex/{{lang.url-fragment}}java/latex-fonts-setup/#64-how-to-declare-a-new-font-encoding-scheme). Die Namen der Standardschriftartkodierungen sind in der folgenden Tabelle aufgeführt:

![Standardschriftartkodierungsnamen](/tex/images/java/tutorial/latex-font-selection-5-3.png)
NFSS basiert auf der Annahme, dass die meisten (oder besser alle) Schriftarten für den Text in derselben Kodierung verfügbar sind, solange sie zum Satz in derselben Sprache verwendet werden. Mit anderen Worten: Codierungsänderungen sollten nur dann notwendig sein, wenn Sie von einer Sprache in eine andere wechseln. In diesem Fall sollen normalerweise die Sprachunterstützungspakete (z. B. aus dem „babel“-System) hinter den Kulissen für die Kodierung sorgen.

Im folgenden Beispiel ändern wir die Kodierung manuell, indem wir eine Umgebung „Cyr“ für den Satz in Kyrillisch definieren. In dieser Umgebung werden sowohl die Schriftartenkodierung als auch die Eingabekodierung lokal geändert. Für eine ordnungsgemäße Sprachunterstützung wären natürlich zusätzliche Arbeiten erforderlich, beispielsweise die Änderung der Silbentrennungsregeln. Die Kodierungen werden LaTeX deklariert, indem sie mit dem Paket „fontenc“ geladen werden. „T2A“ gibt eine der standardmäßigen kyrillischen Kodierungen an. „T1“ wird seit dem letzten Laden zur Standardkodierung.

![Encondings Beispiel-Quellcode](/tex/images/java/tutorial/latex-font-selection-5-4.png)

![Encondings Beispielausgabe](/tex/images/java/tutorial/latex-font-selection-5-5.png)

Leider kann „T1“ für die meisten PostScript-Schriftarten nicht vollständig implementiert werden. Fünf Zeichen im folgenden Beispiel werden wahrscheinlich als Tintenkleckse angezeigt, was auf fehlende Glyphen in der Schriftart hinweist. Beachten Sie, dass die Symbole „pro Tausend“ und „pro Zehntausend“ tatsächlich durch die Verbindung eines Prozentzeichens und einer oder zwei zusätzlichen kleinen Nullen gebildet werden; nur die letztere Glyphe fehlt.


```tex
\usepackage[T1]{fontenc}
-----------------------------------------
\fontfamily{cmr}\selectfont
\j{} \ng{} \NG{} \textperthousand{}\textpertenthousand \par
\fontfamily{ptm}\selectfont
\j{} \ng{} \NG{} \textperthousand{}\textpertenthousand{}

```

![T1 für PostScript-Schriftarten](/tex/images/java/tutorial/latex-font-selection-5-5.png)

## 5.2. Festlegen mehrerer Schriftartattribute

Beim Entwerfen von Seitenstilen oder Layout-orientierten Befehlen möchten Sie häufig eine bestimmte Schriftart auswählen – das heißt, Sie müssen Werte für alle Attribute angeben. Hierzu stellt LaTeX den Befehl „\usefont“ zur Verfügung, der vier Argumente benötigt: die Kodierung, Familie, Serie und Form. Der Befehl aktualisiert diese Attribute und ruft dann „\selectfont“ auf. Wenn Sie auch die Größe und den Grundliniensprung angeben möchten, geben Sie vor „\usefont“ den Befehl „\fontsize“ ein. Zum Beispiel,


```tex
\fontsize{14}{16pt}\usefont{OT1}{cmdh}{bc}{it}
```

würde zum gleichen Ergebnis führen wie die folgenden Befehle:


```tex
\fontencoding{OT1}\fontfamily{cmdh}\fontseries{bc}\fontshape{it}%
\fontsize{14}{16pt}\selectfont
```

LaTeX bietet außerdem die Deklaration „\DeclareFixedFont“, mit der sich neue Befehle definieren lassen, die auf eine vollständig feste Schriftart umschalten. Solche Befehle sind sehr schnell, da sie keine internen Tabellen nachschlagen müssen. Daher sind sie in Befehlsdefinitionen, die zwischen Schriftarten hin und her wechseln müssen, sehr nützlich. Wenn wir beispielsweise einen Befehl zum Setzen eines bestimmten Textes in Skriptgröße deklarieren möchten, können wir dies wie folgt tun:


```tex
\DeclareFixedFont\ScriptSizeFont{\encodingdefault}{\familydefault}
    {\seriesdefault}{\shapedefault}{7pt}
\newcommand\theScript[1]{{\ScriptSizeFont #1}}
```

Sie können sehen, dass „\DeclareFixedFont“ sechs Argumente hat. Auf den Namen des zu definierenden Befehls folgen die fünf Schriftartattribute in den NFSS-Klassifizierungen. Anstatt feste Werte (außer der Größe) zu übergeben, werden die integrierten Hooks verwendet, die die Hauptschriftart des Dokuments beschreiben. Daher hängt „\ScriptSizeFont“ im obigen Beispiel immer noch vom Gesamtlayout des Dokuments ab. Sobald die Definition jedoch ausgeführt wird, wird ihre Bedeutung eingefroren, sodass spätere Änderungen an den Standardeinstellungen die Schriftart „\ScriptSizeFont“ nicht ändern.

## 5.3. Automatische Ersetzung von Schriftarten

Wenn eine Schriftartänderungsanforderung nicht ausgeführt werden kann, weil die Kombination LaTeX nicht bekannt ist, versucht LaTeX, die Schriftart mithilfe einer Schriftart mit ähnlichen Attributen wiederherzustellen. Im Einzelnen passiert Folgendes: Wenn die Kombination aus Kodierungsschema, Familie, Serie und Form nicht deklariert ist, versucht LaTeX, eine bekannte Kombination zu finden, indem es zunächst das Formattribut auf einen Standardwert ändert. Wenn die resultierende Kombination noch unbekannt ist, wird versucht, die Serie auf einen Standardwert zu ändern. Als letzten Ausweg wird die Familie auf einen Standardwert geändert. Schließlich sucht es im internen Tabelleneintrag nach der angeforderten Größe. Wenn Sie beispielsweise nach „\ttfamily\bfseries\itshape“ fragen – einer Schreibmaschinenschrift in fetter Reihe und kursiver Form (die es normalerweise nicht gibt) – dann erhalten Sie eine Schreibmaschinenschrift in mittlerer Reihe und aufrechter Form, weil LaTeX zuerst Setzt die Form zurück, bevor die Serie zurückgesetzt wird. Wenn Sie in einem solchen Fall eine Schreibmaschinenschrift mit kursiver Form bevorzugen, müssen Sie LaTeX Ihre Präferenzen mit der „sub“-Funktion mitteilen, die im Artikel [So richten Sie neue Schriftarten ein](/tex/{{lang.url-fragment}}java/latex-fonts-setup/) erläutert wird.

Der Ersetzungsprozess ändert niemals das Codierungsschema, da jede Änderung zu falschen Zeichen in der Ausgabe führen kann. Wie Sie sich vielleicht erinnern, definiert das Codierungsschema, wie die Eingabezeichen interpretiert werden, während die anderen Attribute definieren, wie die Ausgabe aussehen soll. Daher wäre es nicht angemessen, wenn beispielsweise in einem Vertrag ein Pfund-Zeichen durch ein Dollar-Zeichen ersetzt würde, nur weil die Software versucht, clever zu sein.

Daher muss jedes Codierungsschema eine Standardfamilie, -serie und -form haben, und zumindest die Kombination aus dem Codierungsschema und den entsprechenden Standardeinstellungen muss in LaTeX definiert sein.

## 5.4. So verwenden Sie Befehle auf niedriger Ebene im Dokument

Die in den vorherigen Abschnitten beschriebenen Low-Level-Befehle sollen in den Definitionen von High-Level-Befehlen verwendet werden, entweder in Dokumentklassen- oder Paketdateien oder in der Dokumentpräambel.

Wenn Sie High-Level-Befehle wie „\textsf“ verwenden können, sollten Sie nach Möglichkeit vermeiden, die Low-Level-Befehle direkt im Dokument zu verwenden. Der Grund dafür ist, dass es sich bei den Low-Level-Befehlen um sehr präzise Anweisungen zum Wechseln zu einer bestimmten Schriftart handelt, während High-Level-Befehle mithilfe von Paketen oder Deklarationen in der Präambel angepasst werden können. Angenommen, Sie haben in Ihrem Dokument „Computer Modern Sans“ mit „\fontfamily{cmss}\selectfont“ ausgewählt. Wenn Sie sich später dafür entscheiden, das gesamte Dokument mit Schriftarten aus dem PSNFSS-Bundle zu setzen, beispielsweise Times, würde die Anwendung eines Pakets nur die Teile des Dokuments ändern, die keine expliziten „\fontfamily“-Befehle enthalten.