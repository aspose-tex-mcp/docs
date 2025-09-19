---
translation: true
template: /templates/_template-net.md
title: TeX-Ausgabe/Eingabeformat
linktitle: TeX-E/A
weight: 12
url: /net/tex-io/
description: Grundlagen der Arbeit mit TeX als Ausgabe- oder Eingabeformat innerhalb der Aspose.TeX-API. Der TeX-Job wird für eine explizit angegebene Datei ausgeführt.
lastmod: "2024-09-26"
---

{{<section overview>}}

## TeX-Datei

Technisch gesehen kann jede Datei eine TeX-Datei sein. Es muss nicht einmal die Erweiterung *.tex* vorhanden sein. Eine TeX-Engine liest die Eingabe Byte für Byte und versucht, ihr bekannte Befehle (d. h. solche, die sich in ihrem internen Zustand befinden) zu erkennen. Es meldet lediglich Fehler über nicht erkannte Befehle und/oder fordert Korrekturen auf dem Terminal an (sofern es in einem [interaktiven Modus](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes) läuft). Wenn Sie jedoch ein gut gesetztes Dokument erwarten, sollte die Eingabe der TeX-Syntax folgen und im Idealfall nur Befehle enthalten, die der Engine bekannt sind.

## TeX-Eingabe

Ein TeX-Job wird auf einer explizit angegebenen TeX-Datei ausgeführt. Daher schließen wir diese Datei in die Eingabe eines bestimmten TeX-Jobs ein. Darüber hinaus verfügt TeX über vier Grundelemente im Zusammenhang mit der Hilfseingabe:

* `\input<Dateiname>` erfordert einen Dateinamen und beginnt mit der Verarbeitung dieser Datei, sobald die Verarbeitung der enthaltenden Datei den Befehl `\closeout` erreicht. Sobald das Ende der Hilfsdatei erreicht ist, kehrt die Verarbeitung zu der Datei zurück, die den Befehl `\closeout` enthält.
* `\openin<4-bit-number>=<Dateiname>` erfordert ebenfalls einen Dateinamen, öffnet aber lediglich eine Datei und ordnet sie einer Zahl von 0 bis 15 zu.
* `\read<Nummer> zu <Kontrollsequenz>` erfordert die Nummer, der eine Datei zugeordnet ist, und liest jeweils eine Zeile daraus, sodass `<Kontrollsequenz>` der Liste der gelesenen Token entspricht.
* `\closein<4-bit-number>` schließt die der Nummer zugeordnete Datei.

Die Dateien, deren Namen an die Befehle `\closeout` und `\openin` übergeben werden, sind ebenfalls in der TeX-Eingabe enthalten, und wir nennen sie *Hilfseingabedateien* oder *Abhängigkeiten*, während wir die für den Job angegebene Datei aufrufen die *Haupteingabe*-Datei.

Die vier Befehle können entweder in der Haupteingabedatei oder in einer Hilfseingabedatei auftreten. Aber Vorsicht vor zirkulären Abhängigkeiten.

Im [interaktiven Modus](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes) fordert die TeX-Engine im Falle eines Fehlers eine Korrektur auf dem Terminal an. An dieser Stelle möchten Sie möglicherweise den fehlerhaften Befehl durch einen neuen ersetzen. Und dies wird eine weitere und letzte Möglichkeit sein, Eingaben für TeX bereitzustellen, die wir als *Terminaleingabe* bezeichnen.

## TeX-Ausgabe

Wie wir [oben](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) erwähnt haben, wird ein TeX-Job für eine explizit angegebene Datei ausgeführt. Die Datei darf keine zu setzenden Daten enthalten. Möglicherweise gibt es nur Steuersequenzen, die keine einzugebenden Zeichen erzeugen. Aber normalerweise wird es solche Daten enthalten, sodass wir eine Datei im Zielformat erhalten, die unseren gesetzten Text enthalten sollte (oder was auch immer die Engine und das Format sonst noch zulassen, wenn sie um zusätzliche Funktionen eines bestimmten Zielformats erweitert werden). . Die Datei hat denselben Namen wie die als Eingabe angegebene Datei. Wir nennen diese Datei die *Hauptausgabedatei*. Wie wir [oben](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) erwähnt haben, handelt es sich für das Original-TeX um eine Datei im DVI-Format. Wir nennen den Namen der Eingabe- und Ausgabedateien ohne Erweiterung *Jobname*.

Darüber hinaus verfügt TeX über drei Grundelemente im Zusammenhang mit der Hilfsausgabe:

* `\openout<4-bit-number>=<Dateiname>` erfordert einen Dateinamen, öffnet eine Datei und ordnet sie einer Zahl von 0 bis 15 zu.
* `\write<Nummer>{Token-Liste}` erfordert die Nummer, der eine Datei zugeordnet ist, und schreibt die „Token-Liste“ in die Datei.
* `\closeout<4-bit-number>` schließt die der Nummer zugeordnete Datei.


 
Die Dateien, deren Namen an die `\openout`-Befehle übergeben werden, sind auch in der TeX-Ausgabe enthalten, und wir nennen sie *Hilfsausgabedateien*.

Während die TeX-Engine die Eingabe durchläuft, gibt sie möglicherweise einige Debug-Informationen in die *log*- oder *trascript*-Datei aus. Wir werden diese Datei in die TeX-Ausgabe einbinden.
Gleichzeitig mit dem Schreiben in die Protokolldatei gibt die TeX-Engine möglicherweise weniger detaillierte Informationen an das Terminal aus. Und dies ist die letzte Art und Weise, wie die TeX-Engine die Ausgabe schreibt, die wir als *Terminalausgabe* bezeichnen.

## TeX-Interaktionsmodi

Ein TeX-Job kann jederzeit in einem von vier Interaktionsmodi ausgeführt werden. Diese Modi werden durch die folgenden TeX-Grundelemente umgeschaltet:

* `\batchmode`. Die Engine verzichtet auf alle Stopps und die Terminalausgabe und benötigt daher das Terminal weder für die Eingabe noch für die Ausgabe.
* `\nonstopmode`. Der Motor verzichtet auf alle Stopps und benötigt das Terminal somit nur zur Ausgabe.
* `\scrollmode`. Die Engine verzichtet auf Fehlerstopps und benötigt das Terminal sowohl für die Eingabe als auch für die Ausgabe.
* `\errorstopmode`. Der Motor stoppt bei jeder Gelegenheit zur Interaktion.

Aspose.TeX ermöglicht es uns, den Interaktionsmodus als TeX-Joboption anzugeben, wenn sein Objekt erstellt wird. Dieser Modus wird im internen Zustand der Engine unmittelbar nach dem Laden des TeX-Formats eingestellt (sofern überhaupt ein Format geladen werden soll) und in einen anderen Modus umgeschaltet, sobald die Engine auf einen der vier Befehle trifft. Der Standardwert dieser Option behält den durch das TeX-Format definierten Interaktionsmodus bei. Wenn kein Format geladen ist, ist der Interaktionsmodus derselbe, der durch den Befehl „\errorstopmode“ festgelegt wurde.