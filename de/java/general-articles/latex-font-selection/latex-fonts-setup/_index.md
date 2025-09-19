---
translation: true
template: /templates/_template-java.md
title: 6. So richten Sie neue Schriftarten ein
linktitle: So richten Sie neue Schriftarten ein
weight: 60
url: /java/latex-fonts-setup/
keywords: Latex, Latex-Schriftarten, Ersetzung von Latex-Schriftarten, Einrichtung von Latex-Schriftarten
description: Dieser Artikel behandelt das Einrichten neuer Schriftarten für die Verwendung mit LaTeX und enthält außerdem ein Beispiel für eine Schriftartendefinition.
lastmod: "2024-09-26"
---

{{<section overview>}}

Um neue Schriftarten für die Verwendung mit LaTeX einzurichten, müssen Sie grundsätzlich die internen Schriftartenauswahltabellen mit Informationen füllen, die für die spätere Verknüpfung einer Schriftartanforderung in einem Dokument mit der externen „.tfm“-Datei erforderlich sind, die von LaTeX verwendete Zeicheninformationen enthält. Daher sind die Tabellen dafür verantwortlich, die externe Datei „cmdunh10.tfm“ mit der folgenden Anfrage zu verknüpfen:

```tex
\fontencoding{OT1}\fontfamily{cmdh}\fontseries{m}\fontshape{n}%
\fontsize{10}{12pt}\selectfont
```

Um neue Schriftarten hinzuzufügen, müssen Sie den Vorgang umkehren. Für jede neue externe Schriftart müssen Sie fünf Fragen beantworten:

1. Was ist die Schriftartenkodierung, d. h. welche Zeichen befinden sich an welchen Positionen?
2. Wie lautet sein Familienname?
3. Welche Serie hat es (Gewicht und Breite)?
4. Welche Form hat es?
5. Wie groß ist es?


Die Antworten auf diese Fragen liefern die notwendigen Informationen zur Klassifizierung Ihrer externen Schriftarten gemäß den LaTeX-Konventionen. In den nächsten Abschnitten besprechen wir, wie man neue Schriftarten in die NFSS-Tabellen einträgt, damit sie im Haupttext verwendet werden können. Normalerweise benötigen Sie diese Informationen, wenn Sie neue Schriftarten verwenden möchten, beispielsweise um eine kurze Paketdatei für den Zugriff auf eine neue Schriftartenfamilie zu erstellen. In späteren Abschnitten werden wir auf kompliziertere Konzepte eingehen, die wichtig sind, wenn Sie beispielsweise spezielle Schriftarten für Mathematik anstelle der Standardschriftarten verwenden möchten.

## 6.1. Die Namenskonvention für externe Schriftarten

Ein De-facto-Standardschema zur Benennung von Schriftarten in der TeX-Welt klassifiziert alle Dateinamen von Schriftarten mithilfe von acht alphanumerischen Zeichen, wobei die Groß- und Kleinschreibung keine Rolle spielt. Diese Beschränkung auf acht Zeichen garantiert, dass auf allen Computerplattformen dieselben Dateinamen verwendet werden können. Das Prinzip des Schemas ist in der folgenden Tabelle beschrieben, wobei die Teile in Klammern weggelassen werden können, wenn sie einer Vorgabe entsprechen. Eine Designgröße wird beispielsweise nur dann angegeben, wenn die Schriftart nicht linear skaliert ist.

![Die Namenskonvention für externe Schriftarten](/tex/images/java/tutorial/latex-font-selection-6-1.png)

Nachfolgend finden Sie die Klassifizierung der 35 „grundlegenden“ PostScript-Schriftarten entsprechend der Schriftartenschnittstelle von LaTeX. Für jede Schriftart wird der vollständige Adobe-Name und der entsprechende kurze Dateiname (in der derzeit diskutierten Klassifizierung) angegeben. Für „OT1“, „T1“ oder „TS1“ müsste man „7t“, „8t“ bzw. „8c“ anhängen, um den vollständigen Dateinamen zu erhalten. Zum Beispiel „putr8t“ für Utopia Regular in „T1“-Codierung.  Dies wird für die weitere Diskussion nützlich sein.

![PostScript-Schriftartenklassifizierung](/tex/images/java/tutorial/latex-font-selection-6-2.png)

Die Namenskonvention umfasst interne TeX-Namen für Schriftarten (d. h. diejenigen, die in „\DeclareFontShape“-Deklarationen verwendet werden, wie im nächsten Abschnitt beschrieben), Namen für virtuelle Schriftarten und ihre Komponenten (z. B. bestimmte Neucodierungen physischer Schriftarten) sowie die Namen physischer Schriftarten Schriftarten. Bei PostScript-Schriftarten unterscheiden sich die physischen Schriftartnamen oft von denen, die TeX intern verwendet.
Im letzteren Fall müssen interne Schriftartnamen den entsprechenden externen Schriftarten zugeordnet werden, wenn das Ergebnis eines LaTeX-Laufs angezeigt oder gedruckt wird. Beispielsweise verwendet der PostScript-Treiber „dvips“ Zuordnungsdateien (Standarderweiterung „.map“), die Zeilen wie enthalten


```
putr8r Utopia-Regular "TeXBase1Encoding ReEncodeFont " <8r.enc <putr8a.pfb
```

Sagen Sie ihm, dass die Schriftart „putr8r“ von der externen Schriftart „putr8a.pfb“ abgerufen werden kann, indem Sie sie über einen speziellen Codierungsvektor („8r.enc“) neu codieren. Allerdings finden Sie keinen Verweis auf diesen „putr8r“ in der Datei „t1put.fd“, die die „\DeclareFontShape“-Deklarationen für die Utopia-Familie in der „T1“-Kodierung enthält. Der Grund dafür ist, dass „putr8t“ eine virtuelle Schriftart ist (erstellt mit Hilfe des Dienstprogramms „fontinst“), die auf „putr8r“ verweist. Letzterer Link ist nur in den Quellen der virtuellen Schriftarten zu finden.

## 6.2. So deklarieren Sie neue Schriftfamilien und Schriftformgruppen

Jede Familie/Kodierungskombination muss mit Hilfe des Befehls „\DeclareFontFamily“, der drei Argumente benötigt, in LaTeX eingeführt werden. Die ersten beiden sind das Kodierungsschema und der Familienname. Der dritte ist normalerweise leer, enthält jedoch möglicherweise spezielle Optionen zum Laden von Schriftarten und wird in diesem Artikel näher erläutert. Wenn Sie also eine neue Familie deklarieren möchten – beispielsweise Computer Modern Dunhill mit der alten TeX-Kodierung –, würden Sie schreiben

```tex
\DeclareFontFamily{OT1}{cmdh}{}
```

Normalerweise gibt es in einer Schriftfamilie viele einzelne Schriftarten. Um die Anzahl der Deklarationen zu reduzieren, müssen Sie Schriftarten, die sich nur in der Größe unterscheiden, zusammenfassen und als Gruppe deklarieren, anstatt jedes Familienmitglied einzeln anzukündigen.

Eine solche Gruppe wird mit dem Befehl „\DeclareFontShape“, der sechs Argumente benötigt, in die internen Tabellen von LaTeX eingetragen. Die ersten vier Argumente sind das Kodierungsschema, der Familienname, der Serienname und der Formname, unter dem Sie auf diese Schriftarten zugreifen möchten. Das fünfte Argument ist eine Liste von Größen und externen Schriftartnamen, die in einem speziellen Format angegeben wird, das weiter unten erläutert wird. Das sechste Argument ist normalerweise leer und seine Verwendung wird in diesem Artikel näher erläutert.

Beispielsweise könnte ein NFSS-Tabelleneintrag für Computer Modern Dunhill Medium Upright im alten TeX-Kodierungsschema als eingegeben werden

```tex
\DeclareFontShape{OT1}{cmdh}{m}{n}{ <10> cmdunh10 }{}
```

vorausgesetzt, dass nur eine externe Schriftart für die Größe 10pt verfügbar ist. Wenn Sie diese Schriftart auch in 12pt (skaliert von 10pt) zur Verfügung haben, wäre die Deklaration

```tex
\DeclareFontShape{OT1}{cmdh}{m}{n}{ <10> <12>cmdunh10 }{}
```

Wenn die externe Datei in allen möglichen Größen verfügbar ist, wird die Deklaration sehr einfach. Dies ist der Fall bei Typ-1-PostScript-Schriftarten (Outline-Schriftarten) oder wenn das Treiberprogramm in der Lage ist, Schriftarten bei Bedarf durch Aufruf von METAFONT zu generieren.

Beispielsweise könnte Times Roman im Hochformat „Times Roman“ im LaTeX-Kodierungsschema „T1“ wie folgt eingeführt werden

```tex
\DeclareFontShape{T1}{ptm}{b}{n}{ <-> ptm8t }{}
```

In diesem Beispiel wird ein Größenbereich mit zwei offenen Enden deklariert. Dadurch wird für alle Größen die gleiche externe Datei „ptmb8t.tfm“ verwendet und auf die gewünschte Größe skaliert. Wenn Sie mehr als eine „.tfm“-Datei für eine Schriftart haben – zum Beispiel „emtt10“ für Textgrößen und „emtt12“ für Anzeigegrößen (European Modern Typewriter) – könnte die Deklaration lauten

```tex
\DeclareFontShape{T1}{emtt}{m}{n}{<-12> emtt10 <12-> emtt12}{}
```

In diesem Fall würde die Datei „emtt10.tfm“ für Größen kleiner als 12pt und „emtt12.tfm“ für alle Größen größer oder gleich 12pt verwendet werden.

Die obigen Beispiele zeigen, dass das fünfte Argument des Befehls „\DeclareFontShape“ aus Größenangaben in spitzen Klammern besteht, vermischt mit Ladeinformationen für die einzelnen Größen (z. B. Schriftartnamen). Der Teil innerhalb der spitzen Klammern wird als *Größeninformation* bezeichnet, und der Teil nach der schließenden spitzen Klammer wird als *Schriftartinformation* bezeichnet.  Die Schriftartinformationen sind weiter in eine *Größenfunktion* (oft leer) und ihre Argumente strukturiert. Innerhalb der Argumente von „\DeclareFontShape“ werden Leerzeichen ignoriert, um die Lesbarkeit der Einträge zu verbessern. Unter ungewöhnlichen Umständen, wenn ein echtes Leerzeichen eingegeben werden muss, können Sie den Befehl „\space“ verwenden.

### Einfache Größen und Größenbereiche

Die Größenangaben können in *einfache Größen* und *Größenbereiche* unterteilt werden. Eine einfache Größe wird durch eine einzelne (Dezimal-)Zahl wie „<10>“ oder „<17,28>“ angegeben und kann jeden positiven Wert haben. Sie werden jedoch wahrscheinlich keine Werte unter 4 oder über 120 finden, da die Zahl eine in Punkt gemessene Schriftgröße darstellt. Ein Größenbereich wird durch zwei einfache Größen angegeben, die durch einen Bindestrich getrennt sind, um einen Bereich von Schriftgrößen anzugeben, die dieselben Schriftinformationen aufweisen. Die untere Grenze ist im Bereich enthalten, während die obere Grenze ausgeschlossen ist. „<5-10>“ steht beispielsweise für Größen größer oder gleich 5pt und kleiner als 10pt. Es ist möglich, die Zahl bei beiden Größen des Bindestrichs in einem Größenbereich wegzulassen: „<->“ steht für alle möglichen Größen, „<-10>“ steht für alle Größen unter 10 pt und „<12->“. steht für alle Größen größer oder gleich 12pt.
Mehrere einfache Größen haben oft die gleichen Schriftartinformationen. In diesem Fall besteht eine bequeme Abkürzung darin, alle bis auf die letzte Information wegzulassen:

```tex
\DeclareFontShape{OT1}{panr}{m}{n}{ <5> <6> <7> <8> <9> <10>
    <10.95> <12> <14.4> <17.28> <20.74> <24.88> pan10 }{}
```

Damit wird erklärt, dass die Schriftart Pandora medium Roman in mehreren Größen verfügbar ist, die alle durch Skalierung aus der gleichen Designgröße hergestellt werden.

### Größenfunktionen

Wie oben erwähnt, sind die Schriftartinformationen weiter in eine Größenfunktion und ihr Argument strukturiert. Wenn in der Schriftart-Infozeichenfolge ein „*“ erscheint, bildet alles links davon den Funktionsnamen und alles rechts davon das Argument. Wenn kein Sternchen vorhanden ist, wie in allen bisherigen Beispielen, wird die gesamte Zeichenfolge als Argument betrachtet und der Funktionsname ist *leer*.

Größenfunktionen erzeugen die Spezifikation, die LaTeX benötigt, um die externe Schriftart zu finden und sie in der gewünschten Größe zu laden. Dieser Vorgang basiert auf der vom Benutzer angeforderten Größe und den Informationen im Befehl „\DeclareFontShape“. Größenfunktionen sind auch dafür verantwortlich, den Benutzer über besondere Ereignisse zu informieren. Einige Funktionen unterscheiden sich beispielsweise nur darin, ob sie Warnungen ausgeben. Diese Funktion ermöglicht es dem Systembetreuer, LaTeX so einzurichten, wie es für die jeweilige Site am besten geeignet ist.

Der Name einer Größenfunktion besteht aus null oder mehr Buchstaben. Einige der Größenfunktionen können zwei Argumente annehmen: ein optionales und ein obligatorisches. Ein optionaler Parameter muss in eckige Klammern eingeschlossen werden. Die folgende Spezifikation würde beispielsweise für alle möglichen Größen die Größenfunktion „s“ mit dem optionalen Argument „0,9“ und dem obligatorischen Argument „cmfbi10“ auswählen:


```tex
<-> s * [0.9] cmfib8
```

Die Größenangaben in „\DeclareFontShape“ werden in der Reihenfolge überprüft, in der sie angegeben sind. Wenn eine Größeninformation mit der angeforderten Größe übereinstimmt, wird die entsprechende Größenfunktion ausgeführt. Wenn dieser Vorgang eine gültige Schriftart ergibt, werden keine weiteren Einträge überprüft. Andernfalls wird die Suche mit dem nächsten Eintrag fortgesetzt. Die Standardgrößenfunktionen sind unten aufgeführt.

**Die Funktion „leer“** Die Funktion „leer“ lädt die Schriftartinformationen genau in der angeforderten Größe, wenn es sich um eine einfache Größe handelt. Wenn ein Größenbereich vorhanden ist und die vom Benutzer angeforderte Größe innerhalb dieses Bereichs liegt, wird die Schriftart genau in der Benutzergröße geladen.
Wenn der Benutzer beispielsweise „14.4“ angefordert hat, dann die Spezifikation

```tex
<-> panr10
```

würde die Datei „panr10.tfm“ mit 14,4pt laden. Alle Werte in der „.tfm“-Datei sind um 1,44 skaliert, da diese Schriftart für 10pt konzipiert wurde.

Manchmal möchten Sie möglicherweise eine Schriftart in einer etwas anderen Größe laden als vom Benutzer gewünscht. Eine solche Anpassung kann erforderlich sein, wenn Schriftarten einer Familie im Vergleich zu Schriftarten anderer Familien, die im selben Dokument verwendet werden, zu groß erscheinen. Zu diesem Zweck ermöglicht die leere Größenfunktion ein optionales Argument zur Angabe eines Skalierungsfaktors, der mit der angeforderten Größe multipliziert wird, um die tatsächlich zu ladende Größe zu erhalten.

Daher, 

```tex
<-> [0.95] phvr8t
```

würde die Datei „phvr8t.tfm“ (Helvetica in der Kodierung „T1“) immer mit 95 % der angeforderten Größe laden. Wenn das optionale Argument verwendet wird, gibt die Funktion „Leere Größe“ eine Warnung aus, um den Benutzer darüber zu informieren, dass die Schriftart nicht in der beabsichtigten Größe geladen wird.

**Die „s“-Funktion** Die „s“-Funktion macht dasselbe wie die leere Funktion, außer dass auf dem Terminal keine Nachricht generiert wird. Nachrichten werden weiterhin in die Transkriptdatei geschrieben, sodass Sie herausfinden können, welche Schriftarten verwendet wurden, falls etwas schief geht.

**Die „gen“-Funktion** Externe Schriftartnamen werden oft erstellt, indem die Schriftgröße an eine Zeichenfolge angehängt wird, die die Schriftart darstellt. Beispielsweise sind „cmtt8“, „cmtt9“ und „cmtt10“ die externen Namen für die Schriftarten Computer Modern Typewriter mit 8, 9 bzw. 10 pt. Bei nach einem solchen Schema organisierten Schriftnamen können Sie den Eintrag mit der Funktion „gen“ kürzen. Diese Funktion kombiniert die Schriftartinformationen und die angeforderte Größe, um die externen Schriftartnamen zu generieren. Also, wenn Sie schreiben

```tex
<8> <9> <10> gen * cmtt
```

das wäre eine Abkürzung für
```tex
<8> cmtt8 <9> cmtt9 <10> cmtt10
```

Dadurch werden acht Zeichen in den internen NFSS-Tabellen eingespart. Diese Funktion kombiniert beide Teile wörtlich, daher sollten Sie sie nicht mit Dezimalgrößen wie „14,4“ verwenden. Sie müssen außerdem sicherstellen, dass die Ziffern im externen Schriftartnamen tatsächlich die Designgröße darstellen (z. B. „cmr17“ ist tatsächlich Computer Modern Roman mit 17,28 pt).

Im Übrigen verhält sich die Funktion „gen“ wie die leere Funktion. Das heißt, das optionale Argument stellt, sofern angegeben, einen Skalierungsfaktor dar und generiert bei Verwendung eine Informationsmeldung.

**Die „sgen“-Funktion** Die „sgen“-Funktion ist die stille Version der gen-Funktion. Es schreibt jede Nachricht nur in die Transkriptdatei.

**Die Funktion „genb“** Diese Größenfunktion ähnelt gen, ist jedoch für Schriftarten gedacht, bei denen die Größe im Schriftartnamen in Zentipunkten codiert ist, wie z. B. die EC-Schriftarten. Infolgedessen kann eine Zeile wie z 

```tex
<9> <10> <10.95> <12> genb * ecrm
```

fungiert als Kurzschrift

```tex
<9> ecrm0900 <10> ecrm1000 <10.95> ecrm1095 <12> ecrm1200
```

Ein optionales Argument hat, sofern vorhanden, die gleiche Wirkung wie die leere Funktion.

**Die Funktion „sgenb“** Die Funktion „sgenb“ ist die stille Version der Funktion „genb“. Es schreibt jede Nachricht nur in die Transkriptdatei.

**Die Funktion „sub“** Die Funktion „sub“ wird verwendet, um eine andere Schriftartengruppe zu ersetzen, wenn für die aktuelle Schriftartengruppe keine externe Schriftart vorhanden ist. In diesem Fall ist das Argument kein externer Schriftname, sondern eine durch Schrägstriche getrennte Kombination aus einer anderen Familie, Serie und Form. Beispielsweise hat die Computer Modern Sans keine kursive Form, sondern nur eine schräge Form. Daher ist es sinnvoll, die schräge Form als Ersatz für die kursive zu deklarieren:

```tex
\DeclareFontShape{OT1}{cmss}{m}{it}{ <-> sub * cmss/m/sl }{}
```

Ohne diese Deklaration würde der automatische Ersetzungsmechanismus von LaTeX die Standardform Computer Modern Sans aufrecht ersetzen.

Es gibt andere gute Verwendungsmöglichkeiten für die Funktion „sub“. Schauen Sie sich den folgenden Code an:

```tex
\DeclareFontShape{OT1}{cmss}{m}{sl}{ <-8> sub * cmss/m/n
   <8> cmssi8 <9> cmssi9 <10><10.95> cmssi10 <12><14.4> cmssi12
   <17.28><20.74><24.88> cmssi17 }{}
```

Diese Deklaration besagt, dass LaTeX bei Größen kleiner als 8pt in der Deklaration der Schriftartform nach „OT1/cmss/m/n“ suchen sollte. Solche Ersetzungen können verkettet werden. Beispielsweise gibt es keine Computer Modern Sans-Schriftart, die kleiner als 8pt ist, sodass die Gruppe der ersetzten Schriftarten wahrscheinlich einen anderen Ersetzungseintrag enthalten wird. Die Verwendung dieser Methode hat jedoch den Vorteil, dass Sie beim Erwerb einer zusätzlichen Schriftart nur eine Deklaration der Schriftartformgruppe ändern müssen – andere Deklarationen, die diese Schriftart verwenden, profitieren automatisch davon.

**Die Funktion „ssub“** Die Funktion „ssub“ hat die gleiche Funktionalität wie die Funktion „sub“, erzeugt jedoch keine Warnungen auf dem Bildschirm (das erste „s“ bedeutet „stumm“).

**Die Funktion „subf“** Die Funktion „subf“ lädt Schriftarten auf die gleiche Weise wie die leere Funktion, erzeugt jedoch eine Warnung, dass dieser Vorgang als Ersatz durchgeführt wurde, da die angeforderte Schriftartform nicht verfügbar ist. Diese Funktion kann verwendet werden, um einige externe Schriftarten zu ersetzen, ohne dass dafür eine separate Schriftartengruppe deklariert werden muss, wie im Fall der Funktion „sub“. Zum Beispiel, 

```tex
\DeclareFontShape{OT1}{ptm}{bx}{n}{ <-> subf * ptmb7t }{}
```

würde den Benutzer warnen, dass die angeforderte Kombination nicht verfügbar ist und daher stattdessen die Schriftart „ptmb7t“ geladen wurde. Da dies weniger informativ ist als die Verwendung der „sub“-Funktion, sollte letztere bevorzugt werden.

**Die Funktion „ssubf“** Die stille Version von „subf“. Diese Funktion schreibt ihre Nachrichten nur in die Transkriptdatei.

**Die „feste“ Funktion** Diese Funktion ignoriert die angeforderte Größe und lädt stattdessen die als Argument angegebene externe Schriftart. Falls vorhanden, gibt das optionale Argument die Größe (in Punkt) an, mit der die Schriftart geladen wird. Somit können Sie mit dieser Funktion Größenbereiche angeben, für die eine Schriftart in einer bestimmten festen Größe geladen wird.

**Die „sfixed“-Funktion** Die stille Version von „fixed“. Diese Funktion wird beispielsweise verwendet, um die Schriftart mit den großen mathematischen Symbolen zu laden, die oft nur in einer Größe verfügbar ist.

### Optionen zum Laden von Schriftarten

Wie oben erwähnt, muss jede Schriftfamilie mit dem Befehl „\DeclareFontFamily“ deklariert werden. Das Argument dieses Befehls sowie das sechste Argument von „\DeclareFontShape“ können verwendet werden, um spezielle Vorgänge anzugeben, die beim Laden einer Schriftart ausgeführt werden. Auf diese Weise können Sie Parameter ändern, die einer Schriftart als Ganzes zugeordnet sind.

Neben den Informationen zu jedem Zeichen verwaltet TeX für jede externe Schriftart einen Satz globaler Dimensionen und anderer mit der Schriftart verknüpfter Werte. Beispielsweise hat jede Schriftart ihr eigenes „Bindestrichzeichen“, das Zeichen, das eingefügt wird, wenn TeX ein Wort trennt. Ein weiteres Beispiel ist die normale Breite und Dehnbarkeit von Leerzeichen zwischen Wörtern; Für jede Schriftart wird ein Wert beibehalten und jedes Mal geändert, wenn TeX zu einer neuen Schriftart wechselt. Durch Ändern dieser Werte beim Laden der Schriftart können besondere Effekte erzielt werden.

Normalerweise betreffen Änderungen eine ganze Familie; Beispielsweise möchten Sie möglicherweise die Silbentrennung für alle in der Schreibmaschinenfamilie gesetzten Wörter verbieten. In diesem Fall sollte das dritte Argument von „\DeclareFontFamily“ verwendet werden. Wenn die Änderungen nur für eine bestimmte Schriftformgruppe gelten sollen, müssen Sie das sechste Argument von „\DeclareFontShape“ verwenden. Mit anderen Worten: Wenn eine Schriftart geladen wird, wendet NFSS zuerst das Argument von „\DeclareFontFamily“ und dann das sechste Argument von „\DeclareFontShape“ an, sodass es bei Bedarf die für die gesamte Familie angegebenen Ladeoptionen überschreiben kann.

Mit „\hyphenchar\font=<Nummer>“ gibt TeX das für die Silbentrennung verwendete Zeichen an. Die „<Nummer>“ stellt die Position dieses Zeichens innerhalb des Codierungsschemas dar. Der Standardwert ist der Wert von „\defaulthyphenchar“, der „45“ ist und die Position des „-“-Zeichens in den meisten Kodierungsschemata darstellt. Wenn Sie diese Zahl auf „-1“ setzen, wird die Silbentrennung unterdrückt. Daher durch Erklärung

```tex
\DeclareFontFamily{0T1}{cmtt}{\hyphenchar\font=-1}
```

Sie können die Silbentrennung für alle Schriftarten der „cmtt“-Familie mit dem Kodierungsschema „OT1“ unterdrücken. Schriftarten mit der Kodierung „T1“ haben an Position 127 einen alternativen Bindestrich, sodass Sie beispielsweise festlegen können,

```tex
\DeclareFontFamily{T1}{cmr}{\hyphenchar\font=127}
```

Dadurch unterscheidet sich der Bindestrich vom zusammengesetzten Bindestrich, der in Wörtern wie „sogenannte“ eingegeben wird. TeX trennt keine Wörter, die bereits explizite Bindestriche enthalten (außer direkt nach dem Bindestrich), was in Sprachen, in denen die durchschnittliche Wortlänge viel größer ist als im Englischen, ein Problem darstellen kann. Mit den oben genannten Einstellungen kann dieses Problem gelöst werden.

Jeder TeX-Schriftart ist ein Satz von Dimensionen zugeordnet, die durch Zuweisungen der Form „\fontdimen<Nummer>\font=<Dimen>“ geändert werden, wobei „<Nummer>“ die Referenznummer für die Dimension und „<Dimen>“ ist ` ist der zuzuweisende Wert. Die Standardwerte werden beim Laden der Schriftart aus der „.tfm“-Datei abgerufen. Jede Schriftart hat mindestens sieben solcher Dimensionen:* `\fontdimen1` Gibt die Neigung pro Punkt der Zeichen an. Wenn der Wert Null ist, ist die Schriftart aufrecht.

* `\fontdimen2` Gibt die normale Breite eines Leerraums zwischen Wörtern an (Wortzwischenraum).

* `\fontdimen3` Gibt die zusätzliche Dehnbarkeit des Zwischenwortraums an, d. h. die zusätzliche Menge an Leerraum, die TeX dem Raum zwischen Wörtern hinzufügen darf, um gerechtfertigte Zeilen in einem Absatz zu erzeugen. Im Notfall fügt TeX möglicherweise mehr Speicherplatz hinzu als dieser zulässige Wert; in diesem Fall wird ein *nicht vollständig gefülltes Feld* gemeldet.

* `\fontdimen4` Gibt die zulässige Verkleinerung des Wortzwischenraums an, d. h. die Menge an Platz, die TeX vom normalen Wortzwischenraum (\fontdimen2) abziehen darf, um ausgerichtete Zeilen in einem Absatz zu erzeugen. TeX wird den Zwischenwortraum niemals auf weniger als dieses Minimum verkleinern.

* `\fontdimen5` Gibt die *x-Höhe* an. Es definiert die schriftartorientierte Dimension „1ex“.

* `\fontdimen6` Gibt die *Quad*-Breite an. Es definiert die schriftorientierte Dimension „1em“.

* „\fontdimen7“ Gibt den Betrag an, der als zusätzlicher Leerraum vorgesehen ist, der nach bestimmten Satzende-Interpunktionszeichen hinzugefügt werden soll, wenn „\nonfrenchspacing“ in Kraft ist. Es wird immer ignoriert bzw. durch den Wert „\xspaceskip“ ersetzt, wenn dieser Wert ungleich Null ist.

Wenn Sie den einer Schriftart zugeordneten Wortabstand ändern, können Sie keinen absoluten Wert verwenden, da ein solcher Wert für alle Größen innerhalb einer Formengruppe verwendbar sein muss. Daher müssen Sie den Wert mithilfe eines anderen Parameters definieren, der von der Schriftart abhängt. Man könnte zum Beispiel sagen:


```tex
\DeclareFontShape{0T1}{cmr}{m}{n}{...}
   {\fontdimen2\font=.7\fontdimen2\font}
```

Diese Deklaration reduziert den normalen Zwischenwortraum auf 70 % seines ursprünglichen Wertes. Ebenso könnte die Dehnbarkeit und Schrumpfbarkeit verändert werden.

Einige Schriftarten in Formeln benötigen mehr als sieben Schriftgrößen. Nämlich die Symbolschriftarten namens „symbols“ und „largesymbols“. TeX kann keine Formel setzen, wenn diese Schriftarten weniger als 22 bzw. 13 „\fontdimen“-Parameter haben. Die Werte dieser Parameter werden verwendet, um die Zeichen in einer mathematischen Formel zu positionieren.

Es gibt eine unglückliche Optimierung im TeX-System: TeX lädt jede „.tfm“-Datei nur einmal für eine bestimmte Größe. Daher ist es unmöglich, eine Schriftformgruppe (mit dem Befehl „\DeclareFontShape“) zu definieren, um eine externe Schriftart zu laden – sagen wir „cmtt10“ – und diesmal einen anderen Befehl „\DeclareFontShape“ zu verwenden, um dieselbe externe Schriftart zu laden Ändern einiger der „\fontdimen“-Parameter oder anderer mit der Schriftart verknüpfter Parameter. Ein Versuch, dies zu tun, ändert die Werte für beide Schriftformgruppen.

Angenommen, Sie versuchen, eine Schriftform mit engen Abständen zu definieren, indem Sie den Abstand zwischen Wörtern verkleinern:

```tex
\DeclareFontShape{T1}{ptm}{m}{n}{ <-> ptmr8t }{}
\DeclareFontShape{T1}{ptm}{c}{n}{ <-> ptmr8t }
                     {\fontdimen2\font=.7\fontdimen2\font}
```

Diese Erklärung wird nicht funktionieren. Der Wortabstand für die mittlere Form ändert sich, wenn die enge Form auf die dort angegebenen Werte geladen wird, und das ist nicht das, was erwartet wird. Der beste Weg, mit dieser Situation umzugehen, besteht darin, eine virtuelle Schriftart zu definieren, die dieselben Zeichen wie die Originalschriftart enthält, sich jedoch in den Einstellungen der Schriftgrößen unterscheidet. Eine andere mögliche Lösung besteht darin, die Schriftart in einer etwas anderen Größe zu laden, wie in der folgenden Deklaration:

```tex
\DeclareFontShape{T1}{ptm}{c}{n}{ <-> [0.9999] ptmr8t }
                 {\fontdimen2\font=.7\fontdimen2\font}
```

Diese Methode macht sie zu unterschiedlichen Schriftarten für TeX mit separaten „\fontdimen“-Parametern. Alternativ können Sie in diesem speziellen Fall den Abstand zwischen Wörtern steuern, indem Sie „\spaceskip“ festlegen und so die Schriftartwerte überschreiben.

## 6.3. So ändern Sie Schriftfamilien und Schriftformgruppen

Wenn für ein bestimmtes Dokument eine nicht standardmäßige Schriftartformdeklaration benötigt wird, sollte diese private Deklaration in ein Paket oder in die Präambel des Dokuments eingefügt werden. Dadurch wird jede vorhandene Deklaration für die Schriftart-Form-Kombination überschrieben. Es ist jedoch wichtig, dass die Verwendung von „\DeclareFontFamily“ ein späteres Laden der entsprechenden „.fd“-Datei verhindert (wird später in diesem Artikel besprochen). Außerdem hat diese neue Deklaration keine Auswirkungen auf bereits geladene Schriftarten.

## 6.4. So deklarieren Sie ein neues Schriftartenkodierungsschema

Schriftartänderungen, die Änderungen im Codierungsschema mit sich bringen, erfordern bestimmte Vorsichtsmaßnahmen. In der „T1“-Kodierung haben beispielsweise die meisten akzentuierten Buchstaben ihre eigenen Glyphen, während in der traditionellen TeX-Textkodierung („OT1“) akzentuierte Buchstaben aus Buchstaben und Akzenten mithilfe des Grundelements „\accent“ generiert werden müssen. Wenn die beiden Ansätze gemischt werden müssen, beispielsweise weil eine Schriftart nur in einer der Kodierungen verfügbar ist, muss sich die Definition eines Befehls wie „\““ je nach aktueller Schriftartenkodierung unterschiedlich verhalten.

Aus diesem Grund muss jede Schriftartenkodierung formal mit einem „\DeclareFontEcnoding“-Befehl in LaTeX eingeführt werden, der drei Argumente benötigt. Das erste Argument ist der Name der Kodierung, der später verwendet wird, um mit dem Befehl „\fontencoding“ auf die Kodierung zuzugreifen. Die Liste der [Standardkodierungsschemata](/tex/{{lang.url-fragment}}java/latex-fonts-low-level/#choosing-the-encoding) und ihrer internen Namen finden Sie in der Tabelle in Abschnitt 5.1.

Das zweite Argument enthält beliebigen Code (z. B. Definitionen), der immer dann ausgeführt werden soll, wenn LaTeX mit dem Befehl „\fontencoding“ von einer Kodierung zur anderen wechselt. Das letzte Argument enthält Code, der jedes Mal verwendet werden soll, wenn auf die Schriftart als mathematisches Alphabet zugegriffen wird. Somit können diese drei Argumente verwendet werden, um Befehle neu zu definieren, die von den Positionen der Zeichen in der Kodierung abhängen.

Das LaTeX3e-Projekt behält sich die Verwendung von Kodierungen vor, die mit den folgenden Buchstaben beginnen:

* `t` – Standard-Textkodierungen mit 256 Zeichen.
* „TS“ – Symbole zur Erweiterung der entsprechenden `t`-Kodierung.
* „X“ – Textkodierungen, die nicht den strengen Anforderungen für `t`-Kodierungen entsprechen.
* „M“ – standardmäßige mathematische Kodierungen mit 256 Zeichen.
* „S“ – andere Symbolkodierungen.
* „A“ – andere Spezialanwendungen.
* „OT“ – Standard-Textkodierungen mit 128 Zeichen.
* „OM“ – Standard-Mathe-Kodierungen mit 128 Zeichen.

Der Buchstabe `o` betont, dass die 128-Zeichen-Kodierungen alt und *veraltet* sind. Idealerweise werden diese Kodierungen durch von der TeX-Benutzergruppe definierte Standards ersetzt, so dass in Zukunft eine Änderung der Kodierung nur noch beim Wechsel von einer Sprache in eine andere erforderlich sein wird.

Wenn Sie Ihre eigenen privaten Kodierungen deklarieren, sollten Sie Namen wählen, die mit `l` für „lokal“ oder „E“ für „experimentell“ beginnen. Kodierungen, die mit „U“ beginnen, gelten für „Unbekannte“ oder „Nicht klassifizierte“ Kodierungen, also für Schriftarten, die keinem gemeinsamen Kodierungsmuster entsprechen. Die eingeführte Namenskonvention garantiert, dass Dateien, die offizielle Kodierungen verwenden, portierbar sind.

Der Befehl „\DeclareFontEncoding“ speichert den Namen der neu deklarierten Kodierung im Befehl „\LastDeclaredEncoding“. Dies ist manchmal nützlich, wenn Sie andere verwandte Kodierungsinformationen deklarieren und wird beispielsweise in den Kodierungsdeklarationsdateien für die kyrillischen Sprachen verwendet.

Außerdem müssen, wie wir in der Erörterung der Schriftartersetzung im vorherigen Artikel erwähnt haben, die Standardwerte für Familie, Serie und Form möglicherweise für verschiedene Kodierungen unterschiedlich sein. Für einen solchen Fall stellt NFSS den Befehl „\DeclareFontSubstitution“ bereit, der die Kodierung als erstes Argument übernimmt. Die nächsten drei Argumente sind die Standardwerte (im Zusammenhang mit dieser Codierung) für die Familie, die Serie und die Form zur Verwendung im automatischen Ersetzungsprozess. Es ist wichtig, dass diese drei Argumente eine gültige Schriftform bilden müssen. Mit anderen Worten: Für sie existiert eine „\DeclareFontShape“-Deklaration. Andernfalls wird eine Fehlermeldung ausgegeben, wenn NFSS seine internen Tabellen unter `\begin{document}` überprüft.

## 6.5. Interne Dateiorganisation

Schriftfamilien können beim Generieren einer Formatdatei deklariert, in der Dokumentpräambel deklariert oder bei Bedarf geladen werden, wenn ein Befehl zum Ändern der Schriftart im Dokument eine Kombination anfordert, die noch nicht verwendet wurde. Der erste Weg führt dazu, dass bei jedem LaTeX-Lauf interner Speicher verbraucht wird, auch wenn die Schriftart nicht verwendet wird. Die letzten beiden Optionen nehmen bei der Dokumentformatierung etwas mehr Zeit in Anspruch, da die Schriftartdefinitionen zur Laufzeit gelesen werden müssen. Dennoch sind die letztgenannten Lösungen für die meisten Formengruppen vorzuziehen, da sie es Ihnen ermöglichen, eine Vielzahl von Dokumenten mit einem einzigen LaTeX-Format zu setzen.

Wenn die Formatdatei generiert wird, liest LaTeX eine Datei mit dem Namen „fonttext.ltx“, die den Standardsatz von Schriftartenfamiliendefinitionen und einige andere Deklarationen im Zusammenhang mit Textschriftarten enthält.

Alle anderen Schriftartenfamiliendefinitionen sollten in externen Dateien deklariert werden, die bei Bedarf geladen werden: entweder Paketdateien oder Schriftartendefinitionsdateien („.fd“).  Wenn Schriftfamiliendefinitionen in einer Paketdatei abgelegt werden, müssen Sie dieses Paket explizit nach dem Befehl `\documentclass` laden. Es gibt jedoch eine dritte Möglichkeit: Immer wenn NFSS eine Anfrage für eine Schriftfamilie „foo“ in einem Kodierungsschema „BAR“ erhält und nichts über diese Kombination weiß, versucht es, eine Datei namens „barfoo.fd“ zu laden. Wenn diese Datei vorhanden ist, soll sie Definitionen von Schriftartformgruppen für die Familie „foo“ im Codierungsschema „BAR“ enthalten – also Deklarationen der Form

```tex
\DeclareFontFamily{BAR}{foo}{...}
\DeclareFontShape{BAR}{foo}{...}{...}{...}{...}
...
\endinput
```

Auf diese Weise wird es möglich, eine große Anzahl von Schriftfamilien für LaTeX zu deklarieren, ohne wertvollen Speicher mit Informationen zu füllen, die wahrscheinlich fast nie verwendet werden.

Jede „.fd“-Datei sollte alle Schriftartdefinitionen für eine Schriftartfamilie in einem Kodierungsschema enthalten. In der Datei müssen eine oder mehrere „\DeclareFontShape“-Deklarationen und genau eine „\DeclareFontFamily“-Deklaration vorhanden sein. In der Datei sollten keine anderen Definitionen erscheinen, außer vielleicht einer „\ProvidesFile“-Deklaration oder einigen „\typeout“-Anweisungen, die den Benutzer über das Laden der Schriftart informieren. Anstelle des Befehls „\typeout“ können Sie den einfachen TeX-Befehl „\wlog“ verwenden, der sein Argument nur in die Transkriptdatei schreibt. Detaillierte Informationen in der Transkriptdatei sollten von allen „.fd“-Dateien generiert werden, die in der Produktion verwendet werden, da die Betrachtung dieses Transkripts dabei hilft, Fehler zu erkennen, indem es Informationen über die Dateien und ihre Versionen bereitstellt, die in einem bestimmten Auftrag verwendet werden. Wenn „\typeout“- oder „\wlog“-Befehle verwendet werden, ist es wichtig zu bedenken, dass Leerzeichen und Leerzeilen in einer „.fd“-Datei ignoriert werden. Daher ist es notwendig, den Befehl „\space“ im Argument für „\typeout“ oder „\wlog“ zu verwenden, um ein Leerzeichen auf dem Bildschirm und in der Transkriptdatei zu erhalten.

Neue Kodierungsschemata können nicht über den „.fd“-Mechanismus eingeführt werden. NFSS lehnt jede Anfrage zum Wechsel zu einem Kodierungsschema ab, das nicht explizit im LaTeX-Format (d. h. „fonttext.ltx“), in einer Paketdatei oder in der Präambel des Dokuments deklariert wurde.

## 6.6. So deklarieren Sie neue Schriftarten für die Verwendung in Mathematik

### So geben Sie Schriftgrößen an

Für jede Textgröße verwaltet NFSS [drei Größen, die zum Setzen mathematischer Formeln verwendet werden](/tex/{{lang.url-fragment}}java/latex-math-fractions-binomial-styles/): die Größe, in der die meisten Symbole gesetzt werden sollen (ausgewählt durch `\textstyle` oder `\displaystyle`); die Größe für tiefgestellte und hochgestellte Zeichen erster Ordnung (`\scriptstyle`); und die Größe für tiefgestellte und hochgestellte Zeichen höherer Ordnung (`\scriptscriptstyle`). Wenn Sie zu einer neuen Textgröße wechseln, für die die entsprechenden mathematischen Größen noch nicht bekannt sind, versucht NFSS, diese als Bruchteile der Textgröße zu berechnen. Wenn Sie nicht möchten, dass NFSS diese Größen berechnet, können Sie die korrekten Werte selbst über „\DeclareMathSizes“ angeben. Diese Deklaration benötigt vier Argumente: die äußere Textgröße und die drei mathematischen Größen für diese Textgröße. Die folgende Deklaration definiert beispielsweise die mathematischen Größen für die 14pt-Größe (Überschrift) auf 14pt, 10pt bzw. 7pt:

```tex
\DeclareMathSizes{14}{14}{10}{7}
```

Eine weitere Erklärung unten (für Überschriften einer höheren Ebene) informiert NFSS darüber, dass für eine Textgröße von 36pt keine mathematischen Größen erforderlich sind. Dies kann dazu beitragen, das unnötige Laden vieler Schriftarten zu vermeiden.

```tex
\DeclareMathSizes{36}{}{}{}
```

### So fügen Sie neue Symbole hinzu

Wir haben bereits besprochen, wie man [mathematische Alphabetbefehle](/tex/{{lang.url-fragment}}java/latex-math-fonts/#81-math-alphabet-identifiers) verwendet, um Buchstaben mit besonderen Formen in einer Formel zu erzeugen. Hier zeigen wir, wie man Schriftarten hinzufügt, die spezielle Symbole enthalten, sogenannte *Symbolschriftarten*, und wie man solche Symbole in Formeln zugänglich macht.

Das Hinzufügen neuer Symbolschriftarten ähnelt der Deklaration einer neuen mathematischen Alphabetkennung: „\DeclareSymbolFont“ definiert die Standardeinstellungen für alle Mathematikversionen, „\SetSymbolFont“ überschreibt die Standardeinstellungen für eine bestimmte Version.

Die mathematischen Symbolschriftarten sind über einen symbolischen Namen zugänglich. Wenn Sie beispielsweise die AMS-Schriftart „msbm10“ installieren möchten (siehe Glyphendiagramm unten), müssen Sie die Schriftart zunächst mithilfe der in den vorherigen Abschnitten beschriebenen Deklarationen NFSS bekannt machen.

![msbm10-Glyphendiagramm](/tex/images/java/tutorial/latex-font-selection-6-3.png)

Diese Anweisungen würden so aussehen

```tex
\DeclareFontFamily{U}{msb}{}
\DeclareFontShape{U}{msb}{m}{n}{ <5> <6> <7> <8> <9> gen * msbm
        <10> <10.95> <12> <14.4> <17.28> <20.74> <24.88> msbm10}{}
```

und werden normalerweise in einer „.fd“-Datei abgelegt. Anschließend müssen Sie diese Symbolschriftart für alle Mathematikversionen mit dem folgenden Befehl deklarieren:

```tex
\DeclareSymbolFont{AMSb}{U}{msb}{m}{n}
```

Es stellt die Schriftformengruppe „U/msb/m/n“ als Symbolschrift unter dem Namen „AMSb“ zur Verfügung. Wenn es in dieser Schriftfamilie eine fette Serie gäbe (tatsächlich ist sie nicht vorhanden), könnten Sie die Einrichtung für die fette Mathe-Version nachträglich ändern, indem Sie Folgendes sagen:

```tex
\SetSymbolFont{AMSb}{bold}{U}{msb}{b}{n}
```

Nachdem Sie sich um die Schriftartdeklarationen gekümmert haben, können Sie diese Symbolschrift im Mathematikmodus verwenden. Aber wie kann man NFSS mitteilen, dass beispielsweise der Befehl „\lessdot“ im Mathematikmodus das entsprechende Symbol in der Ausgabe erzeugen soll? Dazu müssen Sie Ihre eigenen Symbolnamen in NFSS einführen, indem Sie „\DeclareMathSymbol“ verwenden:

```tex
\DeclareMathSymbol{cmd}{type}{symbol-font}{slot}
```

Das erste Argument ist der von Ihnen gewählte Befehlsname. Das zweite Argument ist einer der in der folgenden Tabelle aufgeführten Befehle und bestimmt die Art des Symbols, die wiederum den Platz bestimmt, den LaTeX um das Symbol herum einfügt, wenn es in einer Formel vorkommt.

![Math-Objekttypen](/tex/images/java/tutorial/latex-font-selection-6-4.png)

Mit Ausnahme von `\mathalpha` können diese Befehle übrigens in mathematischen Formeln als Funktionen mit einem Argument verwendet werden. In diesem Fall platzieren sie ihr (möglicherweise komplexes) Argument so, als ob es vom entsprechenden Typ wäre.

Das dritte Argument identifiziert die Symbolschriftart, aus der das Symbol abgerufen werden soll – also den symbolischen Namen, der durch den Befehl „\DeclareSymbolFont“ definiert wird. Das vierte Argument gibt die Position des Symbols in der Schriftartkodierung an, entweder als Dezimal-, Oktal- oder Hexadezimalwert. Die Positionen aller Glyphen dieser Schriftart können Sie ganz einfach aus der Glyphentabelle oben ermitteln. Beispielsweise kann „\lessdot“ als deklariert werden

```tex
\DeclareMathSymbol{\lessdot}{\mathbin}{AMSb}{"6c}
```

Anstelle eines Befehlsnamens können Sie auch ein einzelnes Zeichen als erstes Argument verwenden. Beispielsweise verfügt das Paket „eulervm“ über mehrere Deklarationen der Form

```tex
\DeclareMathSymbol{0}{\mathalpha}{letters}{"30}
```

um anzugeben, woher die Ziffern abgerufen werden sollen.

Der Befehl „\DeclareMathSymbol“ gibt eine Position in einer Symbolschriftart an. Daher ist es wichtig, dass alle externen Schriftarten, die über die Befehle „\DeclareSymbolFont“ und „\SetSymbolFont“ mit dieser Symbolschrift verknüpft sind, an dieser Position dasselbe Zeichen haben. Der einfachste Weg, dies sicherzustellen, besteht darin, nur Schriftarten mit derselben Kodierung zu verwenden (es sei denn, es handelt sich um die „U“- oder unbekannte Kodierung, da zwei Schriftarten in dieser Kodierung nicht dieselben Zeichen enthalten müssen).

Im obigen Glyphendiagramm finden Sie auch „Tafelfett“-Buchstaben (ABC... beginnend mit der Position „101“). Wenn Sie diese Buchstaben als Mathe-Alphabet verwenden möchten, können Sie sie mit `\DeclareMathAlphabet` definieren. Wenn diese Symbolschrift jedoch bereits geladen ist, ist es besser, eine Verknüpfung zu verwenden, um auf einzelne Symbole zuzugreifen:

```tex
\DeclareSymbolFontAlphabet{\mathbb}{AMSb}
```

Das heißt, Sie geben den Namen Ihrer mathematischen Alphabetkennung und den symbolischen Namen der zuvor deklarierten Symbolschriftart an.
Ein wichtiger Grund dafür, Schriftarten nicht unnötig zweimal zu laden, besteht darin, dass es in TeX eine Obergrenze von 16 mathematischen Schriftarten gibt, die zu einem bestimmten Zeitpunkt aktiv sein können. Bei der Berechnung dieser Grenze zählt jede Symbolschrift; Mathe-Alphabete zählen nur, wenn sie tatsächlich im Dokument verwendet werden, und sie zählen lokal in jeder Mathe-Version. Wenn also acht Symbolschriftarten deklariert sind, können Sie in jeder Version höchstens acht (möglicherweise unterschiedliche) Mathe-Alphabet-Bezeichner verwenden.

Als kurze Zusammenfassung: Um neue Symbolschriftarten einzuführen, müssen Sie eine kleine Anzahl von „\DeclareSymbolFont“- und „\SetSymbolFont“-Deklarationen und möglicherweise eine große Anzahl von „\DeclareMathSymbol“-Deklarationen ausgeben. Daher erfolgt das Hinzufügen solcher Schriftarten am besten in einer Paketdatei.

### So führen Sie neue Mathe-Versionen ein

Wir haben bereits [erwähnt](/tex/{{lang.url-fragment}}java/latex-math-fonts/#83-math-formula-versions), dass die Standardkonfiguration automatisch zwei mathematische Versionen deklariert: normal und fett. Um zusätzliche Versionen einzuführen, können Sie die Deklaration „\DeclareMathVersion“ verwenden, die ein Argument benötigt – den Namen der neuen Mathematikversion. Alle zuvor deklarierten Symbolschriftarten und Mathematikalphabete sind in dieser Mathematikversion automatisch verfügbar. Ihnen werden die Standardschriftarten zugewiesen – also die Schriftarten, die Sie mit `\DeclareMathAlphabet` oder „\DeclareSymbolFont“ angegeben haben.

Sie können dann die Einrichtung für Ihre neue Version ändern, indem Sie die entsprechenden Befehle `\SetMathAlphabet` und „\SetSymbolFont“ für die fett gedruckte Mathe-Version ausgeben, wie weiter oben in diesem Abschnitt und im Artikel über [Schriftarten in Mathe](/tex/{{lang.url-fragment}}java/latex-math-fonts/) gezeigt. . Auch hier erfolgt die Einführung einer neuen Mathematikversion normalerweise in einer Paketdatei.


### So ändern Sie die Symbolschriftart-Einstellung

Wir haben gesehen, wie man neue Symbolschriftarten hinzufügt, um auf mehr Symbole zuzugreifen. Dieselben Befehle können zum Ändern eines vorhandenen Setups verwendet werden. Diese Funktion könnte interessant sein, wenn Sie sich für die Verwendung spezieller Schriftarten in einigen oder allen Mathe-Versionen entscheiden.

Nachfolgend finden Sie die Standardeinstellungen für LaTeX:

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

In der Standardkonfiguration werden von Operatoren wie „\log“ und „\max“ erzeugte Ziffern und Texte aus der Symbolschrift „Operatoren“ übernommen. Um dies so zu ändern, dass diese Elemente gut mit der Haupttextschrift harmonieren – beispielsweise Computer Modern Sans statt Computer Modern Roman –, können Sie die folgenden Befehle eingeben:

```tex
\SetSymbolFont{operators}{normal}{0T1}{cmss}{m} {n}
\SetSymbolFont{operators}{bold} {0T1}{cmss}{bx}{n}
```

Symbolschriftarten mit den Namen „symbols“ und „largesymbols“ spielen in TeX eine einzigartige Rolle. Aus diesem Grund benötigen sie eine spezielle Anzahl von „\fontdimen“-Parametern, die ihnen zugeordnet sind. Daher können als diese beiden Symbolschriftarten nur speziell vorbereitete Schriftarten verwendet werden. Im Prinzip kann man solche Parameter beim Laden zu jeder Schriftart hinzufügen, indem man den dritten Parameter von „\DeclareFontFamily“ oder den sechsten Parameter von „\DeclareFontShape“ verwendet.

## 6.7. So definieren Sie Ihre eigene „.fd“-Datei (Beispiel)

Wenn Sie (PostScript-)Schriftarten einrichten und die erforderliche „.fd“-Datei erstellen möchten, sollten Sie die oben in diesem Artikel beschriebene Vorgehensweise befolgen. Wenn „fontinst“ zum Generieren der erforderlichen Schriftartmetrikdateien verwendet wird, werden automatisch auch die entsprechenden „.fd“-Dateien generiert. Es ist jedoch einfach, eine „.fd“-Datei für eine einzelne Schriftfamilie von Hand zu schreiben, vorausgesetzt, Sie wissen, welche Schriftkodierung verwendet wird. Schauen wir uns als Beispiel die Deklarationsdatei „t1bch.fd“ für *Bitstream Charter* in der Kodierung „T1“ an:

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

Die erste Zeile ist eine *Identifikationszeile*. Anschließend erfolgt die Deklaration der Schriftfamilie und Kodierung („bch“ und „T1“) mittels „\DeclareFontFamily“. Das Argument dieses Befehls sollte dem Namen der „.fd“-Datei entsprechen, mit der Ausnahme, dass die Kodierung im Dateinamen Kleinbuchstaben ist. Als nächstes wird jede Kombination aus Serie und Form dem Namen einer „.tfm“-Datei zugeordnet. Diese Schriftarten werden auf jede gewünschte Größe skaliert (beachten Sie „<->“). Der zweite Teil der Datei richtet einige Ersetzungen für Kombinationen ein, für die keine Schriftart verfügbar ist (d. h. das Ersetzen der fetten erweiterten Serie durch die fette Serie).
Vorausgesetzt, Sie verfügen über die zusätzlichen *Charter*-Schriftarten (Schwarz und BlackItalic), möchten Sie möglicherweise die entsprechenden Definitionen zur „.fd“-Datei hinzufügen. Um den „T1“-Zeichensatz zu emulieren, müssen Sie natürlich zunächst die entsprechenden virtuellen Schriftarten bereitstellen. Glücklicherweise können viele Schriftarten aus dem Internet heruntergeladen werden.

Ein weiterer möglicher Grund, eigene „.fd“-Dateien zu erstellen, könnte in der Notwendigkeit liegen, Schriftarten aus verschiedenen Familien zu kombinieren und sie als eine einzige neue Schriftartenfamilie in LaTeX einzuführen. Beispielsweise gibt es die Schriftfamilie *Aldus*, die als Ergänzung zur Schriftart *Palatino* (die ursprünglich als Anzeigeschrift konzipiert war) konzipiert wurde. Da es für Aldus keine fett gedruckte Serie gibt, ist Palatino eine natürliche Wahl als fetter Ersatz. Im folgenden Beispiel kombinieren wir Aldus in seiner mittleren Serie mit Palatino Bold und nennen die zusammengesetzte Schriftfamilie „zasj“. Es wird nur ein Fragment einer vollständigen „.fd“-Datei präsentiert, was ausreicht, um die Idee zu veranschaulichen.

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

Um auf diese „Pseudofamilie“ zuzugreifen, müssen wir „zasj“ in der „T1“-Kodierung auswählen. Wir müssen auch sicherstellen, dass „\textbf“ auf Fett und nicht auf Fett erweitert umschaltet, da unsere „.fd“-Datei keine Ersetzungen bereitstellt. All dies kann automatisch durch ein kleines Paket wie dieses bereitgestellt werden:

```tex
\ProvidesPackage{fontmix}[2003/10/12 T1 Aldus/Palatino mix.]
\RequirePackage[T1]{fontenc}
\renewcommand\rmdefault{zasj} \renewcommand\bfdefault{b}
```

Wenn wir also das Paket „fontmix“ laden, erhalten wir Aldus und Palatino Bold für Schlagzeilen. Ein solcher Schriftartenmix wertet Ihren Text möglicherweise nicht oft auf, daher wird in diesem Beispiel nicht empfohlen, zufällige Kombinationen zu erstellen.

## 6.8. Die Reihenfolge der Erklärungen

NFSS verlangt, dass Sie alle Erklärungen in einer bestimmten Reihenfolge abgeben, damit überprüft werden kann, ob Sie alle erforderlichen Informationen angegeben haben. Wenn Sie Objekte in der falschen Reihenfolge deklarieren, wird eine Beschwerde eingereicht. Hier sind die Abhängigkeiten, die Sie berücksichtigen müssen:

* „\DeclareFontFamily“ prüft, ob das Kodierungsschema zuvor mit „\DeclareFontEncoding“ deklariert wurde.
* „\DeclareFontShape“ prüft, ob die Schriftfamilie in der angeforderten Kodierung als verfügbar deklariert wurde („\DeclareFontFamily“).
* „\DeclareSymbolFont“ stellt sicher, dass das Codierungsschema gültig ist.
* „\SetSymbolFont“ stellt zusätzlich sicher, dass die angeforderte Mathematikversion deklariert wurde (`\DeclareMathVersion`) und dass die angeforderte Symbolschriftart deklariert wurde (`\DeclareSymbolFont`).
* `\DeclareSymbolFontAlphabet` prüft, ob der Befehlsname für die Alphabetkennung verwendet werden kann und ob die Symbolschriftart deklariert wurde.
* `\DeclareMathAlphabet` prüft, ob der gewählte Befehlsname verwendet werden kann und ob das Kodierungsschema deklariert wurde.
* `\SetMathAlphabet` prüft, ob der Alphabetbezeichner zuvor mit `\DeclareMathAlphabet` oder `\DeclareSymbolFontAlphabet` deklariert wurde und ob die Mathematikversion und das Kodierungsschema bekannt sind.
* „\DeclareMathSymbol“ stellt sicher, dass der Befehlsname verwendet werden kann (d. h. undefiniert ist oder zuvor als mathematisches Symbol deklariert wurde) und dass die Symbolschriftart zuvor deklariert wurde.
* Wenn der Befehl `\begin{document}` erreicht wird, führt NFSS einige zusätzliche Prüfungen durch. Beispielsweise wird überprüft, ob die Ersetzungsvorgaben für jedes Codierungsschema auf bekannte Deklarationen von Schriftartformgruppen verweisen.

