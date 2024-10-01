---
translation: true
template: /templates/_template-java.md
title: Andere TeX-Konvertierungsausgabeformate | Java
linktitle: Andere TeX-Formate
weight: 18
url: /java/other-tex-formats/
description: Die Konvertierungsfunktion der Aspose.TeX-API-Lösung für Java ermöglicht die Konvertierung von LaTeX-Dateien und Ihren eigenen benutzerdefinierten TeX-Dateien. Hier sind einige Codebeispiele.
lastmod: "2024-09-26"
---

{{<section overview>}}

Es ist höchst unwahrscheinlich, dass Sie derzeit eine TeX-Datei konvertieren möchten, die in einem anderen Format als LaTeX geschrieben ist. Dies ist jedoch aus irgendeinem Grund möglich, wenn Sie die TeX-Sprache und/oder Interna studieren. Wie auch immer, **Aspose.TeX für Java** ermöglicht Ihnen die Konvertierung von Dateien, die im einfachen TeX-Format geschrieben wurden. Sie können damit auch benutzerdefinierte Formate erstellen und in diesen Formaten gestaltete Dokumente setzen.

Wir beginnen mit der Erstellung eines benutzerdefinierten Formats.

## Erstellen eines benutzerdefinierten Formats

Denken Sie daran, dass die Formatdatei ein binärer Speicherauszug des internen Zustands der TeX-Engine ist.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-CreateCustomTeXFormatFile.java" >}}

Wie Sie sehen, ähnelt der Code dem Code zum Konvertieren einer TeX-Datei. Aber es gibt ein paar Unterschiede.

Zunächst verwenden wir hier die Jobkonfiguration [TeXConfig.objectIniTeX()](https://reference.aspose.com/tex/java/com.aspose.tex/TeXConfig#objectIniTeX--). Dies ist eine spezielle Konfiguration, die den Zustand der Engine „unberührt“ belässt, d. h. die internen Parameter haben ihre Standardwerte und der Satz von Steuersequenzen stimmt mit dem Satz von Grundelementen überein. In unserem Beispiel wird die Menge der Grundelemente in dem [hier](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) erwähnten Sinne erweitert.

Als nächstes richten wir wie gewohnt die Eingabe- und Ausgabearbeitsverzeichnisse ein. Das Eingabearbeitsverzeichnis muss die Hauptformatquelldatei und alle ihre Abhängigkeiten enthalten.

Und der zweite wesentliche Unterschied ist die Art und Weise, wie wir den Job ausführen. Dieses Mal verwenden wir die statische Methode [createFormat()](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob#createFormat-java.lang.String-com.aspose.tex.TeXOptions-), die zusammen mit den Optionen den Namen der Hauptquelldatei übernimmt, der mit dem Formatnamen identisch sein muss.

## Textsatz einer TeX-Datei in Ihrem benutzerdefinierten Format

Da wir nun über unser eigenes TeX-Format verfügen, möchten wir eine in diesem Format geschriebene TeX-Datei setzen. Hier ist der Code:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-TypesetWithCustomTeXFormat.java" >}}

Natürlich müssen wir das Format irgendwie festlegen. Zunächst müssen wir eine Instanz der Klasse [FormatProvider](https://reference.aspose.com/tex/java/com.aspose.tex/FormatProvider) erstellen. Dann verwenden wir im Optionskonstruktor die Konfiguration [TeXConfig.objectTeX()](https://reference.aspose.com/tex/java/com.aspose.tex/TeXConfig#objectTeX--), die unseren Formatanbieter als Argument verwendet und das Format über den „jungfräulichen“ Zustand der Engine lädt.

Der Rest des Codes sollte Ihnen bekannt sein. Es nutzt die zuvor in diesem [Leitfaden](/tex/{{lang.url-fragment}}java/conversion/) besprochenen Funktionen.

## Textsatz einer TeX-Datei im Plain-TeX-Format

Wenn wir den Formatanbieter aus dem gerade gezeigten Code weglassen, lädt die Engine das Standardformat, das im vierten Sinne [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/) ist. Wenn Sie also eine TeX-Datei im einfachen TeX-Format geschrieben haben, können Sie sie auf diese Weise in jedes unterstützte Zielformat konvertieren.