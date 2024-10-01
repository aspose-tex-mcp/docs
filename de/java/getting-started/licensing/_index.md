---
translation: true
template: /templates/_template-java.md
linktitle: Lizenzierung
title: Lizenzierung - Aspose.TeX für Java
weight: 70
url: /java/licensing/
description: Wenn Sie sich für die lizenzierte Version der Aspose.TeX-API-Lösung für Java entschieden haben, erfahren Sie hier, wie Sie die Lizenz anwenden.
lastmod: "2024-09-26"
---

{{<section overview>}}


### Einschränkungen der Evaluierungsversion

Die Testversion von Aspose.TeX (ohne Angabe einer Lizenz) bietet die volle Produktfunktionalität, außer dass im Ausgabedokument nur bis zu vier erste Seiten abgerufen werden können. Außerdem werden diese Seiten mit einem Wasserzeichen für den Bewertungsmodus versehen.

Wenn Sie Aspose.TeX ohne Evaluierungseinschränkungen ausprobieren möchten, fordern Sie eine 30-tägige temporäre Lizenz an. Weitere Informationen finden Sie unter [Wie bekomme ich eine temporäre Lizenz?](https://purchase.aspose.com/temporary-license/).

### Wenden Sie die Lizenz mithilfe einer Datei oder eines Stream-Objekts an

Verwenden Sie die Methode [License.setLicense](https://reference.aspose.com/tex/java/com.aspose.tex/License#setLicense-java.lang.String-), um die Komponente zu lizenzieren. Der einfachste Weg, eine Lizenz festzulegen, besteht darin, die Lizenzdatei im selben Ordner wie *aspose.tex.jar* abzulegen und den Dateinamen ohne Pfad anzugeben, wie unten gezeigt.

#### Laden einer Lizenz aus einer Datei

Dieser Codeausschnitt initialisiert eine Lizenz, die in einer Datei oder einer eingebetteten Ressource gespeichert ist.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-LoadLicenseFromFile.java" >}}

#### Laden einer Lizenz aus einem Stream-Objekt

Diese Codeausschnitte initialisieren die Lizenz aus dem Stream.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-LoadLicenseFromStream.java" >}}

### Gemessene Lizenz

Aspose.TeX verfügt über einen alternativen Lizenzierungsmechanismus namens *Metered Licensing*. Wenn ein Kunde eine Abrechnung basierend auf der Nutzung der API-Funktionen wünscht, kann er eine *Metered License* anwenden, was eigentlich so einfach ist wie die Anwendung eines kryptografischen Schlüsselpaars. Weitere Einzelheiten finden Sie im [FAQ-Abschnitt „Metered Licensing“](https://purchase.aspose.com/faqs/licensing/metered/).

Die öffentlichen und privaten Schlüssel einer gemessenen Lizenz können mithilfe einer Instanz der Klasse [*Metered*](https://reference.aspose.com/tex/net/aspose.tex/metered/) festgelegt werden, wie unten gezeigt: 

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-SetMeteredLicense.java" >}}