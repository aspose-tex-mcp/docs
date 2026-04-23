---
translation: true
template: /templates/_template-java.md
linktitle: Schrifteigenschaften
title: 2. Schrifteigenschaften
weight: 20
url: /java/latex-font-attributes/
keywords: Latex, Latex-Schriftarten, Latex-Schriftkodierungen, NFSS
description: Lernen Sie LaTeX-Schriftklassifizierungen im Hinblick auf verschiedene Schriftmerkmale behandelt und das Konzept der LaTeX-Schriftkodierungen.
lastmod: "2024-09-26"
---

{{<section overview>}}

Schriftarten können aufgrund verschiedener Merkmale in einzelne überlappende Klassen eingeteilt werden. Es erweist sich oft als nützlich, diese Eigenschaften zu kennen, wenn wir entscheiden müssen, welche Schriftfamilie in einem bestimmten Kontext verwendet werden soll. Siehe auch den Dokumentationsartikel von [Aspose.Font](https://products.aspose.com/font/) zu [verschiedenen Schriftarten](/font/net/what-is-font/font-types/).

## 2.1. Proportionale und monospaced Schriftarten

Schriftarten können entweder proportional oder monospaced sein. In einer Proportionalschrift haben Glyphen je nach Form unterschiedliche Breiten.  Gleichzeitig haben in einer monospaced Schriftart alle Glyphen die gleiche Breite. Die zusätzlichen Leerzeichen um Glyphen von monospaced Schriftarten erschweren das Erkennen von Wortgrenzen und machen in solchen Schriftarten eingegebenen Text somit weniger lesbar. Im Gegensatz dazu ermöglichen proportionale (oder *typografische*) Schriftarten in der Regel die Platzierung von mehr Wörtern auf einer Seite und sind besser lesbar als monospaced Schriftarten. Siehe die Abbildung unten:

![Proportionale und monospaced Schriftarten](/tex/images/java/tutorial/latex-font-selection-2-1.png)
 
Obwohl Monospace-Schriftarten weniger lesbar erscheinen, haben sie dennoch ihren Nutzen. Ein Beispiel sind Tabellen oder Programmauflistungen, bei denen es auf die richtige Ausrichtung des Inhalts ankommt. Seit diesem Buch werden Sie auf jedem Computer immer Computerprogramme finden, die in einer monospaced-Schriftart angezeigt werden. Dadurch lassen sich Programme leicht vom umgebenden Text unterscheiden.

Sie können sogar eine Monospace-Schriftart als Basisschriftart für ein vollständiges Dokument auswählen, da eine solche Schriftart bei Verwendung mit unbündigen Absätzen wie von Hand erstellt aussieht und ihr den Eindruck einer Schreibmaschine verleiht.

## 2.2. Serifen- und serifenlose Schriftarten

In einigen Schriftarten haben Glyphen *Serifen*, in anderen hingegen nicht. Diese Tatsache führt uns zu einer weiteren nützlichen Klassifizierung. Serifen sind winzige horizontale Striche an den Enden von Glyphen. Ursprünglich wurden sie mit dem Meißel hergestellt, als römische Kapitelle in Stein gemeißelt wurden. Aus diesem Grund werden Schriftarten mit Serifen oft als *romanische* Schriftarten bezeichnet.

![Schriftarten mit und ohne Serifen](/tex/images/java/tutorial/latex-font-selection-2-2.png)
 
Serifenschriften galten lange Zeit als besser lesbar, da sie dem Auge mehr Hinweise zur Identifizierung geben. Spezielle Untersuchungen haben jedoch gezeigt, dass die Lesegeschwindigkeit durch das Fehlen von Serifen nicht wesentlich beeinträchtigt wird.

## 2.3. Schriftfamilien und ihre Attribute

Abgesehen von den oben besprochenen groben Klassifizierungen werden Schriftarten in Schriftfamilien gruppiert. Mitglieder einer Schriftfamilie haben gemeinsame Gestaltungsprinzipien und unterscheiden sich durch Variationen in Größe, Stärke, Breite und Form.

### Schriftformen

Fast jede Schriftfamilie hat eine Form, die sogenannte *aufrechte* Form. Die Schriftart, die Sie gerade lesen, ist in aufrechter Form. Diese Schriftform wird normalerweise zum Schreiben von normalem Text verwendet.

Eine weitere wichtige Form, die in den meisten Familien enthalten ist, ist die *kursive* Form, die aussieht

![Text in Kursivschrift](/tex/images/java/tutorial/latex-font-selection-2-3.png)
 
Kursive Glyphen sind nach rechts geneigt und Buchstaben werden anders gezeichnet als ihre aufrechten Gegenstücke, wie in der folgenden Abbildung dargestellt:

![Vergleich von aufrechten, kursiven aufrechten und kursiven Formen](/tex/images/java/tutorial/latex-font-selection-2-4.png)
 
Die erste Zeile zeigt Buchstaben der Computer Modern Serif-Familie in aufrechter Form und die dritte Zeile zeigt dieselben Buchstaben in kursiver Form. Um den zeichnerischen Unterschied deutlicher hervorzuheben, sind in der zweiten Zeile die kursiven Buchstaben ohne die übliche Schräge dargestellt. Mit anderen Worten, das sind kursive Buchstaben in aufrechter Position.

San-Serif-Schriftfamilien haben oft keine richtige Kursivschrift; Stattdessen haben sie eine *schräge* Form, bei der die regulären aufrechten Zeichen nach rechts geneigt sind. Solche Schriftarten werden oft auch *oblique* oder *sloped* genannt.
Eine weitere gängige Schriftform ist die *Kapitälchen*-Form, bei der die Kleinbuchstaben als Großbuchstaben mit reduzierter Höhe dargestellt werden. Wenn die Form der Kapitälchen für eine bestimmte Schriftart nicht verfügbar ist, verwenden Typografen manchmal aufrechte Großbuchstaben in kleineren Größen, die jedoch nicht die gleiche Qualität wie eine gut gestaltete Kapitälchenschrift erzielen. Echte Kapitälchen haben eine andere Breite und Stärke als Großbuchstaben derselben Schriftart, die auf die Höhe von gestalteten Kapitälchen reduziert wurden. In der Abbildung unten können Sie sehen, dass die Striche in den falschen Großbuchstaben viel zu dünn sind.

![Vergleich von echten und gefälschten Kapitälchen](/tex/images/java/tutorial/latex-font-selection-2-5.png) 

### Gewicht und Breite

Schriftarten einer bestimmten Form innerhalb einer Familie können sich in der *Stärke* unterscheiden. Diese Eigenschaft hängt mit der Dicke der Striche zusammen, mit denen die einzelnen Formen gezeichnet werden. Einige Schriftartenhersteller bezeichnen die für normalen Text vorgesehenen Schriftstärken als „Book“, während andere sie als „Medium“ bezeichnen. Für dünne Striche ist die Bezeichnung *hell* gebräuchlich, während dickere Striche meist als *fett* bezeichnet werden. In größeren Schriftfamilien finden wir manchmal einen Bereich, der mit *ultra light* beginnt, über *extra light*, *light*, *semi light* usw. geht und am anderen Ende mit *ultra Bold* endet. Doch oft stehen in manchen Familien nur wenige Gewichte zur Verfügung. Die Computer Modern Roman-Familie hat beispielsweise nur mittlere und fette Strichstärken.

Die *Breite* der Schriftart ist ein weiteres wichtiges Attribut. Es bezieht sich auf das Ausmaß der Ausdehnung oder Kontraktion im Vergleich zur normalen oder mittleren Breite in der Familie. Computer Modern Roman verfügt über fette Schriftarten in *mittlerer Breite* und *erweiterter Breite*. Komprimierte Schriftarten werden häufig in Titeln und Überschriften verwendet, wobei Schriftarten mittlerer Breite in großen Größen zu viel Platz beanspruchen würden.

### Schriftgrößen

Die Maßeinheit für Schriftgrößen ist ein Druckerpunkt (pt). Ein Zoll hat 72,27 Punkte. Die Schriftgröße bezieht sich nicht auf ein bestimmtes Merkmal, sondern ist vielmehr ein vom Schriftdesigner gewählter Wert, der dem Benutzer Orientierung geben soll. Beispielsweise sind in einer 10pt-Schriftart die Buchstaben des Alphabets normalerweise weniger als 10pt hoch und nur Zeichen wie Klammern haben ungefähr diese Höhe.

Das Erscheinungsbild einer Schriftart hängt von vielen Faktoren ab, wie z. B. der Höhe der Kleinbuchstaben (die *x-Höhe*), der Strichstärke und der Tiefe der Unterlängen (der Teil der Buchstaben unterhalb der Grundlinie, wie in der). Buchstabe 'q'. Aus diesem Grund kann es sein, dass zwei Schriftarten derselben Größe nicht gut miteinander harmonieren.

In der LaTeX-Welt sind Schriftarten oft in Größen verfügbar, die Potenzen von 1,2 haben, was bedeutet, dass sie einem geometrischen Verlauf folgen. Diese Anordnung erleichtert die Erstellung einer vergrößerten Masterkopie, die später fotografisch verkleinert werden kann, wodurch die endgültige Ausgabeauflösung effektiv erhöht wird. Heutzutage sind Schriftarten meist vektorisiert und können somit beliebig skaliert werden. Aus diesem Grund werden viele kommerzielle Schriftfamilien nur in einer einzigen Designgröße angeboten.

Die Verwendung skalierter Schriftarten anstelle von Schriftarten, die für eine bestimmte Größe konzipiert sind, führt häufig zu weniger zufriedenstellenden Ergebnissen. Dies liegt daran, dass sich Schriftarten nicht linear an das menschliche Auge anpassen. Sie können den Unterschied in der folgenden Abbildung sehen:

![Eine echte 10pt- und eine vergrößerte 5pt-Schriftart](/tex/images/java/tutorial/latex-font-selection-2-6.png)
 
Die Glyphen in handgefertigten Schriftarten größerer Größe sind normalerweise schmaler als vergrößerte Schriftarten einer kleineren Größe derselben Familie. Wann immer möglich, sollten Schriftarten verwendet werden, die für die gewünschte Größe ausgelegt sind. Bei Bedarf ist es jedoch akzeptabel, Schriftarten innerhalb eines kleinen Größenbereichs zu skalieren.

## 2.4. Schriftartenkodierungen

Wie wir in der Einleitung erwähnt haben, bezieht sich TeX auf die Glyphen einer Schriftart, indem es sie über Codes anspricht. Eine solche Zuordnung wird als *Schriftartkodierung* bezeichnet. In LaTeX sollen zwei Schriftarten mit derselben Schriftartenkodierung in dem Sinne austauschbar sein, dass sie bei gleicher Eingabe die „gleichen“ Glyphen auf der gedruckten Seite erzeugen.
Durch die Klassifizierung von Schriftarten anhand ihrer Schriftartenkodierungen ist es möglich, andere Merkmale, wie z. B. Schriftartenfamilien oder Schriftartenserien, zu ändern und dennoch sicherzustellen, dass das Satzergebnis verständlich bleibt.

Ursprünglich enthielten TeX-Distributionen Schriftarten, die nur 128 Glyphen pro Schriftart enthielten. Daher enthalten diese Schriftarten keine Akzentzeichen als einzelne Glyphen. Alle diese Glyphen mussten mit dem Grundelement `\accent` von TeX oder mit ähnlichen Methoden erstellt werden. Daher können Wörter, die diakritische Zeichen enthalten, von LaTeX nicht automatisch getrennt werden, und Kerning (Korrektur des Abstands zwischen bestimmten Buchstaben in der Schriftart) kann nicht automatisch angewendet werden. Die Kodierung dieser Schriftarten wird `OT1` genannt. Obwohl es die Standardkodierung für LaTeX bleibt, ist es nicht ratsam, `OT1` für andere Sprachen als Englisch zu verwenden.

Die TeX-Benutzergemeinschaft hat eine 256-Zeichen-Kodierung namens `.fd` definiert, die es TeX ermöglicht, in mehr als 30 Sprachen basierend auf dem lateinischen Alphabet korrekt zu setzen. Daher wird die Verwendung der `.fd`-Kodierung dringend empfohlen, da heutzutage fast alle mit LaTeX verwendbaren Schriftfamilien in dieser Kodierung verfügbar sind. Tatsächlich sind einige *nur* in der `.fd`-Codierung verfügbar. Durch die Angabe von `\usepackage[T1]{fontenc}` nach dem Befehl `\documentclass` wird `.fd` zur Standardkodierung innerhalb eines Dokuments.