---
translation: true
template: /templates/_template-net.md
title: Was ist TeX? Einführung in TeX
linktitle: Was ist TeX?
weight: 10
url: /net/what-is-tex/
keywords: was ist tex
description: Diese Seite beantwortet kurz die Frage „Was ist TeX?“ Gehört es zu den Programmiersprachen oder gilt es als Dokumentformat?
lastmod: "2026-04-22"
---

{{<section overview>}}

## Was TeX NICHT ist

TeX ist definitiv überhaupt kein Format.

## Was ist TeX?

Was ist TeX? Nun, das ist die Frage, wie Hamlet[^1] sagte. Versuchen wir es so einfach wie möglich zu beantworten.

Stellen Sie sich vor, wir hätten eine Programmiersprache, die aus zwei elementaren Befehlen (genannt *Steuersequenzen*) oder *Primitiven* besteht, `\a` und `\b`. Und in dieser Sprache können wir Programme für den Schriftsatz von Dokumenten (Bücher, Artikel usw.) schreiben. Nennen wir diese Sprache **(L1)**. Damit diese Programme auf eine bestimmte Art und Weise ausgeführt werden können, verfügen wir über eine bestimmte Engine, die die Befehle dieser Sprache interpretiert.

Nehmen wir nun an, dass wir beim Schreiben eines Satzprogramms für ein Dokument festgestellt haben, dass die Teilsequenz `\a \b \a` ziemlich häufig vorkommt. Und nehmen Sie außerdem an, dass es in unserer Sprache ein weiteres Primitiv „\def“ gibt, das es uns ermöglicht, Unterroutinen oder Makros zu definieren. Nennen wir diese Sprache **(L2)**. Unter diesen Umständen können wir das Makro `\def\c{\a \b \a}` am Anfang des Programms definieren und jedes Vorkommen der Teilsequenz durch `\c` ersetzen, sowohl zur besseren Lesbarkeit als auch zur Reduzierung.

Wenn wir nun ein anderes Dokument setzen wollen, in dessen Programm diese Unterfolge von Befehlen ebenfalls häufig vorkommt, müssen wir dieses Makro erneut definieren. Nehmen wir jedoch an, dass unsere Engine in der Lage ist, das `\c`-Makro in seinen internen Zustand zu laden und diesen Zustand dann als Binärdatei (ein *Dump*) zu speichern, die dann automatisch („über“) geladen wird **(L2)** Sprachbefehlssatz vor der Verarbeitung der Satzprogramme jedes Dokuments, in dem das Makro `\c` erforderlich ist. Wir werden den durch das `\c`-Makro erweiterten Satz von Grundelementen als *Format* bezeichnen. Somit ist unser Format eine *Makroerweiterung* der Low-Level-Primitivsprache **(L2)**.

Die Engine enthält außerdem eine Reihe interner Register oder *interne Parameter*, auf die über Steuersequenzen zugegriffen werden kann. Zusätzlich zu Makrodefinitionen kann ein Format Initialisierungsausdrücke für diese Parameter enthalten.

Es kam vor, dass <a href="https://en.wikipedia.org/wiki/Donald_Knuth" target=_blank rel="nofollow">Donald E. Knuth</a> eine Sprache ähnlich **(L2) definierte. **, aber mit einem viel größeren Satz an Grundelementen, die er TeX nannte. Er hat auch eine Engine entwickelt, die die TeX-Sprache versteht (und immer noch versteht). Er nannte es auch TeX.

Glücklicherweise waren dies nicht die einzigen Dinge, die er tat. Er schlug auch die Makroerweiterung oder das Makroformat vor, das er *Plain* TeX nannte und das das Schreiben von Programmen komfortabler machte. Der anfängliche Satz der Grundelemente von TeX wird manchmal VirTeX („Vir“ für „jungfräulich“) genannt und ist formal auch ein Format, wenn man es zusammen mit den Standardwerten interner Parameter betrachtet.

**Einerseits ist TeX also eine Programmiersprache. Und andererseits ist es eine Dolmetschermaschine, die diese Sprache versteht. Und drittens ist TeX ein allgemeineres Konzept, das ein Satzsystem als Ganzes bedeutet.**

Hier bleibt nur noch zu beachten, dass es sich bei den Zeichen des zu setzenden Textes tatsächlich auch um Befehle handelt, die die TeX-Engine dazu zwingen, entsprechende Zeichen (unter Berücksichtigung der aktuellen Eingabekodierung) unter Verwendung der aktuellen Schriftarteinstellungen (die z. wiederum sind durch Steuersequenzen steuerbar). Daher können wir bei der Definition von Makros auch Zeichen verwenden.

Wir hoffen, dass die Frage „Was ist TeX?“ von nun an beantwortet wird. existiert nicht mehr in deinem Kopf.
[^1]: Die Figur in W. Shakespeares "The Tragical Historie of Hamlet, Prince of Denmarke".