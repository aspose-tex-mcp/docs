---
translation: true
template: /templates/_template-java.md
linktitle: Lizenzierung
title: Lizenzierung | Aspose.TeX für Java
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

Verwenden Sie die Methode [License.setLicense](https://reference.aspose.com/tex/java/com.aspose.tex/license/#setLicense-java.lang.String-), um die Komponente zu lizenzieren. Setzen Sie in den folgenden Beispielen `licenseFilePath` auf den vollständigen Pfad zu Ihrer Lizenzdatei. Die aufrufende Methode muss `Exception` behandeln oder deklarieren.

#### Laden einer Lizenz aus einer Datei

Dieser Codeausschnitt wendet eine in einer Datei gespeicherte Lizenz an.

{{< gist "aspose-com-gists" "2a6bdc66eff2968d36c7580d02721b14" "Example-SetLicenseFromFile.java" >}}

#### Laden einer Lizenz aus einem Stream-Objekt

Diese Codeausschnitte initialisieren die Lizenz aus dem Stream.

{{< gist "aspose-com-gists" "2a6bdc66eff2968d36c7580d02721b14" "Example-SetLicenseFromStream.java" >}}

### Gemessene Lizenz

Aspose.TeX verfügt über einen alternativen Lizenzierungsmechanismus namens *Metered Licensing*. Wenn ein Kunde eine Abrechnung basierend auf der Nutzung der API-Funktionen wünscht, kann er eine *Metered License* anwenden, was eigentlich so einfach ist wie die Anwendung eines kryptografischen Schlüsselpaars. Weitere Einzelheiten finden Sie im [FAQ-Abschnitt „Metered Licensing“](https://purchase.aspose.com/faqs/licensing/metered/).

Die öffentlichen und privaten Schlüssel einer gemessenen Lizenz können mithilfe einer Instanz der Klasse [*Metered*](https://reference.aspose.com/tex/java/com.aspose.tex/metered/) festgelegt werden, wie unten gezeigt:

{{< gist "aspose-com-gists" "2a6bdc66eff2968d36c7580d02721b14" "Example-SetMeteredLicense.java" >}}