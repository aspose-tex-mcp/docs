---
translation: true
template: /templates/_template-net.md
linktitle: Lizenzierung
title: Lizenzierung – Aspose.TeX für .NET
weight: 70
url: /net/licensing/
description: Wenn Sie sich für die lizenzierte Version der Aspose.TeX-API-Lösung für .NET entschieden haben, erfahren Sie hier, wie Sie die Lizenz anwenden.
lastmod: "2024-09-26"
---

{{<section overview>}}

## Bewerten Sie Aspose.TeX

Sie können das Produkt Aspose.TeX für .NET zu Evaluierungszwecken einfach herunterladen. Die neueste Version finden Sie auf der [Aspose.TeX for .NET-Downloadseite](https://www.nuget.org/packages/Aspose.TeX/). Der Test-Download ist derselbe wie der gekaufte Download. Die Testversion wird einfach lizenziert, wenn Sie ein paar Codezeilen hinzufügen, um die Lizenz anzuwenden.

### Einschränkungen der Evaluierungsversion

Die Testversion von Aspose.TeX (ohne Angabe einer Lizenz) bietet die volle Produktfunktionalität, außer dass im Ausgabedokument nur bis zu vier erste Seiten abgerufen werden können. Außerdem werden diese Seiten mit einem Wasserzeichen für den Bewertungsmodus versehen.

Wenn Sie Aspose.TeX ohne Evaluierungseinschränkungen ausprobieren möchten, fordern Sie eine 30-tägige temporäre Lizenz an. Weitere Informationen finden Sie unter [Wie bekomme ich eine temporäre Lizenz?](https://purchase.aspose.com/temporary-license/).

## Anwenden einer Lizenz

Wenn Sie mit Ihrer Evaluierung von Aspose.TeX für .NET zufrieden sind, kaufen Sie eine Lizenz auf der Aspose-Website: [Purchase Portal](http://www.aspose.com/purchase/default.aspx). Machen Sie sich mit den verschiedenen verfügbaren Lizenztypen vertraut. Wenn Sie Fragen haben, [kontaktieren Sie das Aspose-Verkaufsteam](http://www.aspose.com/corporate/contact/default.aspx) und es hilft Ihnen gerne weiter.

Zu jeder Aspose-Lizenz gehört ein einjähriges Abonnement für kostenlose Upgrades auf alle neuen Versionen oder Fixes, die in diesem Zeitraum herauskommen. Wir bieten sowohl lizenzierten als auch Testbenutzern kostenlosen und unbegrenzten technischen Support.

Die Lizenz ist eine reine Text-XML-Datei, die Details wie den Produktnamen, die Anzahl der lizenzierten Entwickler, das Ablaufdatum des Abonnements usw. enthält. Die Datei ist digital signiert. Ändern Sie sie daher nicht: Selbst das Hinzufügen eines zusätzlichen Zeilenumbruchs zur Datei macht sie ungültig.

### Wann muss eine Lizenz beantragt werden?

Befolgen Sie diese einfachen Regeln:

- Die Lizenz muss nur einmal pro Anwendungsdomäne festgelegt werden.
- Sie müssen die Lizenz festlegen, bevor Sie andere Aspose.TeX-Klassen verwenden.
- Das mehrmalige Aufrufen von SetLicense ist nicht schädlich, verschwendet jedoch Prozessorzeit.
- Wenn Sie eine Windows Forms- oder Konsolenanwendung entwickeln, rufen Sie SetLicense im Startcode auf, bevor Sie Aspose.TeX-Klassen verwenden.
- Rufen Sie beim Entwickeln einer ASP.NET-Anwendung SetLicense aus der Datei Global.asax.cs in der geschützten Methode Aplication_Start auf. Der Aufruf erfolgt einmalig beim Start der Anwendung.
- Rufen Sie SetLicense nicht innerhalb der Page_Load-Methoden auf, da dies bedeutet, dass die Lizenz jedes Mal geladen wird, wenn eine Webseite geladen wird.
- Wenn Sie eine Klassenbibliothek entwickeln, können Sie SetLicense von einem statischen Konstruktor der Klasse aufrufen, die Aspose.TeX verwendet. Der statische Konstruktor wird ausgeführt, bevor eine Instanz Ihrer Klasse erstellt wird, um sicherzustellen, dass die Aspose.TeX-Lizenz richtig eingestellt ist.

### Wenden Sie die Lizenz mithilfe einer Datei oder eines Stream-Objekts an

Verwenden Sie die Methode [License.SetLicense](https://reference.aspose.com/tex/net/aspose.tex/license/), um die Komponente zu lizenzieren. Der einfachste Weg, eine Lizenz festzulegen, besteht darin, die Lizenzdatei im selben Ordner wie die *Aspose.TeX.dll* abzulegen und den Dateinamen ohne Pfad anzugeben, wie unten gezeigt.

#### Laden einer Lizenz aus einer Datei

Dieser Codeausschnitt initialisiert eine Lizenz, die in einer Datei oder einer eingebetteten Ressource gespeichert ist.

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-LoadLicenseFromFile.cs" >}}

#### Laden einer Lizenz aus einem Stream-Objekt

Diese Codeausschnitte initialisieren die Lizenz aus dem Stream.

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-LoadLicenseFromStream.cs" >}}

### Gemessene Lizenz

Aspose.TeX verfügt über einen alternativen Lizenzierungsmechanismus. Kunden, die eine Abrechnung auf Basis der Nutzung der API-Funktionen wünschen, können *Metered Licensing* nutzen. Das Anwenden einer *Metered License* ist eigentlich so einfach wie das Anwenden eines Paares kryptografischer Schlüssel. Weitere Einzelheiten finden Sie im Abschnitt „FAQ zur zählerbasierten Lizenzierung“ (6).

Die öffentlichen und privaten Schlüssel einer gemessenen Lizenz werden mithilfe einer Instanz der Klasse [*Metered*](https://reference.aspose.com/tex/net/aspose.tex/metered/) festgelegt, wie im folgenden Beispiel gezeigt: 

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-SetMeteredLicense.cs" >}}