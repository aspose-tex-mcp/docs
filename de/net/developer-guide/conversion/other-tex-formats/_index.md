---
translation: true
template: /templates/_template-net.md
title: Andere TeX-Konvertierungsausgabeformate | .NET
linktitle: Andere TeX-Formate
weight: 18
url: /net/other-tex-formats/
description: Die Konvertierungsfunktion der Aspose.TeX-Lösung für .NET ermöglicht die Konvertierung von LaTeX-Dateien und Ihren eigenen benutzerdefinierten TeX-Dateien.
lastmod: "2026-04-22"
---

{{<section overview>}}

Es ist höchst unwahrscheinlich, dass Sie derzeit eine TeX-Datei konvertieren möchten, die in einem anderen Format als LaTeX geschrieben ist. Dies ist jedoch aus irgendeinem Grund möglich, wenn Sie die TeX-Sprache und/oder Interna studieren. Wie auch immer, **Aspose.TeX für .NET** ermöglicht Ihnen die Konvertierung von Dateien, die im einfachen TeX-Format geschrieben wurden. Sie können damit auch benutzerdefinierte Formate erstellen und in diesen Formaten gestaltete Dokumente setzen.

Wir beginnen mit der Erstellung eines benutzerdefinierten Formats.

## Erstellen eines benutzerdefinierten Formats

Denken Sie daran, dass die Formatdatei ein binärer Speicherauszug des internen Zustands der TeX-Engine ist.

{{< gist "aspose-com-gists" "c0eb6cbcfb001b7e6355cafa4611afed" "Example-CreateCustomFormat.cs" >}}

Wie Sie sehen, ähnelt der Code dem Code zum Konvertieren einer TeX-Datei. Aber es gibt ein paar Unterschiede.

Zunächst verwenden wir hier die Jobkonfiguration [TeXConfig.ObjectIniTeX](https://reference.aspose.com/tex/net/aspose.tex/texconfig/objectinitex/). Dies ist eine spezielle Konfiguration, die den Zustand der Engine „unberührt“ belässt, d. h. die internen Parameter haben ihre Standardwerte und der Satz von Steuersequenzen stimmt mit dem Satz von Grundelementen überein. In unserem Beispiel wird die Menge der Grundelemente in dem [hier](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) erwähnten Sinne erweitert.

Als nächstes richten wir wie gewohnt die Eingabe- und Ausgabearbeitsverzeichnisse ein. Das Eingabearbeitsverzeichnis muss die Hauptformatquelldatei und alle ihre Abhängigkeiten enthalten.

Und der zweite wesentliche Unterschied ist die Art und Weise, wie wir den Job ausführen. Dieses Mal verwenden wir die statische Methode [CreateFormat()](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/), die zusammen mit den Optionen den Namen der Hauptquelldatei übernimmt, der mit dem Formatnamen identisch sein muss.

## Textsatz einer TeX-Datei in Ihrem benutzerdefinierten Format

Da wir nun über unser eigenes TeX-Format verfügen, möchten wir eine in diesem Format geschriebene TeX-Datei setzen. Hier ist der Code:

{{< gist "aspose-com-gists" "c0eb6cbcfb001b7e6355cafa4611afed" "Example-TypesetWithCustomFormat.cs" >}}

Natürlich müssen wir das Format irgendwie festlegen. Zunächst müssen wir eine Instanz der Klasse [FormatProvider](https://reference.aspose.com/tex/net/aspose.tex.resourceproviders/formatprovider/) erstellen. Dann verwenden wir im Optionskonstruktor die Konfiguration [TeXConfig.ObjectTeX()](https://reference.aspose.com/tex/net/aspose.tex/texconfig/objecttex/), die unseren Formatanbieter als Argument verwendet und das Format über den „jungfräulichen“ Zustand der Engine lädt.

Der Rest des Codes sollte Ihnen bekannt sein. Es nutzt die zuvor in diesem [Leitfaden](/tex/{{lang.url-fragment}}net/conversion/) besprochenen Funktionen.

## Textsatz einer TeX-Datei im Plain-TeX-Format

Wenn wir den Formatanbieter aus dem gerade gezeigten Code weglassen, lädt die Engine das Standardformat, das im vierten Sinne [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/) ist. Wenn Sie also eine TeX-Datei im einfachen TeX-Format geschrieben haben, können Sie sie auf diese Weise in jedes unterstützte Zielformat konvertieren.
