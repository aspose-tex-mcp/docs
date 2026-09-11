---
translation: true
template: /templates/_template-python-net.md
linktitle: Lizenzierung
title: Lizenzierung | Python über .NET
weight: 70
url: /python-net/licensing/
description: Wenn Sie die lizenzierte Version der Aspose.TeX-API-Lösung für Python verwenden, erfahren Sie hier, wie Sie die Lizenz anwenden.
lastmod: "2024-09-26"
---

{{<section overview>}}

## Bewerten Sie Aspose.TeX

Um Aspose.TeX für Python zu evaluieren, können Sie das Produkt einfach von der [Aspose.TeX für Python-Downloadseite](https://pypi.org/project/aspose-tex-net/) herunterladen. Die Testversion ist die gleiche wie die gekaufte Version. Durch das Hinzufügen einiger Codezeilen zum Anwenden der Lizenz wird die Testversion lizenziert. Die neueste Version finden Sie auf der Download-Seite.

### Einschränkungen der Evaluierungsversion

Die Testversion von Aspose.TeX bietet die volle Produktfunktionalität, mit der Ausnahme, dass im Ausgabedokument nur die ersten vier Seiten abgerufen werden können. Zusätzlich werden diese Seiten mit einem Bewertungsmodus-Wasserzeichen versehen.

Wenn Sie Aspose.TeX ohne diese Evaluierungseinschränkungen ausprobieren möchten, können Sie [eine 30-tägige temporäre Lizenz anfordern](https://purchase.aspose.com/temporary-license/), mit der Sie jeden Aspekt eines Produkts testen, bevor Sie es kaufen.

## Anwenden einer Lizenz

Nachdem Sie Ihre Evaluierung von Aspose.TeX für Python abgeschlossen haben und mit der Leistung zufrieden sind, können Sie über die Aspose-Website im [Kaufportal](https://purchase.aspose.com/pricing?) eine Lizenz erwerben. Es wird empfohlen, sich vor dem Kauf mit den verschiedenen verfügbaren Lizenztypen vertraut zu machen. Wenn Sie Fragen haben oder Hilfe benötigen, wenden Sie sich bitte an [das Aspose-Verkaufsteam](https://consulting.aspose.com/), das Ihnen gerne weiterhilft.

Jede Aspose-Lizenz beinhaltet ein einjähriges Abonnement, das Sie zu kostenlosen Upgrades auf alle neuen Versionen oder Fixes berechtigt, die in diesem Zeitraum veröffentlicht werden. Darüber hinaus bieten wir sowohl lizenzierten als auch Testbenutzern kostenlosen und unbegrenzten technischen Support.

Die Lizenz für Aspose ist eine reine XML-Textdatei, die Informationen wie den Produktnamen, die Anzahl der lizenzierten Entwickler und das Ablaufdatum des Abonnements enthält. Es ist wichtig, die Datei nicht zu ändern, da sie digital signiert ist und selbst das Hinzufügen eines zusätzlichen Zeilenumbruchs sie ungültig macht.

### Wann muss eine Lizenz beantragt werden?

Bitte befolgen Sie diese Richtlinien:

- Die Lizenz muss nur einmal pro Anwendungsdomäne festgelegt werden.
- Legen Sie die Lizenz fest, bevor Sie andere Aspose.TeX-Klassen verwenden.
- Der mehrmalige Aufruf von „SetLicense“ ist nicht schädlich, verschwendet jedoch Prozessorzeit.

#### Laden einer Lizenz aus einer Datei

Der folgende Codeausschnitt zeigt, wie eine in einer Datei gespeicherte Lizenz initialisiert wird.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-LoadLicenseFromFile.py" >}}

#### Laden einer Lizenz aus einem Stream-Objekt

Der nächste Code initialisiert die Lizenz aus einem Stream.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-LoadLicenseFromStream.py" >}}

### Gemessene Lizenz

Aspose.TeX bietet einen alternativen Lizenzierungsmechanismus namens *Metered Licensing*, der es Kunden ermöglicht, die Kosten auf der Grundlage ihrer Nutzung der API-Funktionen abzurechnen. Das Anwenden einer *Metered License* ist so einfach wie das Anwenden eines Paares kryptografischer Schlüssel. Weitere Informationen finden Sie im [FAQ-Abschnitt „Metered Licensing“](https://purchase.aspose.com/faqs/licensing/metered/).

Um die öffentlichen und privaten Schlüssel einer gemessenen Lizenz festzulegen, können Sie eine Instanz der Klasse [*Metered*](https://reference.aspose.com/tex/python-net/aspose.tex/metered/) verwenden, wie im folgenden Beispiel gezeigt:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-SetMeteredLicense.py" >}}