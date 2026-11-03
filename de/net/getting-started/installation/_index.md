---
translation: true
template: /templates/_template-net.md
linktitle: Installation
title: Installation | Aspose.TeX für .NET
weight: 60
url: /net/installation/
description: Aspose.TeX Dokumentation für .NET finden Sie im heruntergeladenen ZIP-Paket oder können von der NuGet-Galerie heruntergeladen werden.
lastmod: "2026-11-02"
---

{{<section overview>}}

## Ein Paket wählen

Aspose.TeX für .NET ist als zwei NuGet-Pakete mit derselben API verfügbar:

- [Aspose.TeX](https://www.nuget.org/packages/Aspose.TeX) verwendet `System.Drawing.Common` und läuft unter Windows.
- [Aspose.TeX.Drawing](https://www.nuget.org/packages/Aspose.TeX.Drawing) verwendet das eingebettete Grafik-Backend Aspose.Drawing und läuft unter Windows, Linux und macOS, einschließlich Docker-Containern.

Binden Sie nur eines davon ein. Um ein Paket mit der .NET CLI zu installieren, führen Sie einen der folgenden Befehle im Ordner Ihres Projekts aus:

```bash
dotnet add package Aspose.TeX
```

```bash
dotnet add package Aspose.TeX.Drawing
```

Details zu `Aspose.TeX.Drawing` finden Sie unter [Linux, macOS und Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/). Der Rest dieser Seite beschreibt die Installation in Visual Studio; er gilt für beide Pakete.

## Installieren von Aspose.TeX für .NET über NuGet

NuGet ist ein kostenloses, entwicklerorientiertes Open-Source-Paketverwaltungssystem für die .NET-Plattform, das den Prozess der Integration von Bibliotheken von Drittanbietern in eine .NET-Anwendung während der Entwicklung vereinfachen soll. Es handelt sich um eine Visual Studio-Erweiterung, die das einfache Hinzufügen, Entfernen und Aktualisieren von Bibliotheken und Tools in Visual Studio-Projekten erleichtert, die das .NET Framework verwenden. Eine Bibliothek oder ein Tool kann problemlos mit anderen Entwicklern geteilt werden, indem ein NuGet-Paket erstellt und in einem NuGet-Repository gespeichert wird. Wenn Sie das Paket installieren, kopiert NuGet Dateien in Ihre Lösung und nimmt automatisch die erforderlichen Änderungen vor, z. B. das Hinzufügen von Verweisen und das Ändern Ihrer app.config- oder web.config-Dateien. Wenn Sie sich entscheiden, die Bibliothek zu entfernen, entfernt NuGet Dateien und macht alle an Ihrem Projekt vorgenommenen Änderungen rückgängig, sodass kein Durcheinander entsteht.

### Referenzierung von Aspose.TeX für .NET

Wir haben uns diese wunderbare Funktion zunutze gemacht, indem wir [Aspose.TeX für .NET](https://www.nuget.org/packages/Aspose.TeX)-Bibliotheken in einem NuGet-Paket gebündelt und in ein NuGet-Repository hochgeladen haben. Mit dieser Option profitieren Sie von der Nutzung von Aspose.TeX für .NET, ohne diese Komponente auf Ihrem System installieren zu müssen. NuGet läuft in Visual Studio 2010 und höheren Versionen, Visual Web Developer 2010 und Windows Phone Developer Tools 7.1. In unseren Tests haben wir es mit Visual Studio 2015 Ultimate getestet.

Um zu beginnen:

1. Öffnen Sie Ihre Lösung oder Ihr Projekt in Visual Studio.
2. Fügen Sie NuGet Package Manager als Visual Studio-Erweiterung hinzu:

   1. Wählen Sie das Menü **Extras** und anschließend **Erweiterungsmanager**.
   2. Wählen Sie **Online-Galerie**, um eine vollständige Liste der online verfügbaren Pakete zu erhalten.
   3. Wählen Sie **NuGet-Paketmanager**.
   4. Klicken Sie auf **Herunterladen**.
   5. Sobald der Paketmanager installiert ist, starten Sie Visual Studio neu, damit die Änderungen wirksam werden. 
   
      Wenn NuGet Package Manager installiert ist, können Sie Pakete im Fenster **NuGet-Pakete verwalten** oder mithilfe von PowerShell-Befehlszeilenbefehlen im dedizierten Visual Studio-Fenster **Package Manager Console** suchen, installieren, entfernen und aktualisieren . Sie finden beide Optionen, wenn Sie **Tools** und anschließend **Library Package Manager** auswählen.

### Installieren Sie das Paket mit der Package Manager-Konsole

So verweisen Sie mit der Paketmanager-Konsole auf die Komponente:

1. Öffnen Sie Ihre .NET-Anwendung in Visual Studio.
2. Wählen Sie im Menü **Extras** die Option **Library Package Manager** und dann **Package Manager Console**.
3. Geben Sie den Befehl „Install-Package Aspose.TeX“ ein, um die neueste Vollversion zu installieren, oder geben Sie den Befehl „Install-Package Aspose.TeX -prerelease“ ein, um die neueste Version einschließlich Hotfixes zu installieren.
4. Drücken Sie **Enter**.

### Aktualisieren Sie das Paket mit der Paket-Manager-Konsole

Wenn Sie bereits über NuGet auf die Komponente verwiesen haben, führen Sie die folgenden Schritte aus, um den Verweis auf die neueste Version zu aktualisieren:

1. Öffnen Sie Ihre .NET-Anwendung in Visual Studio.
2. Wählen Sie im Menü **Extras** die Option **Library Package Manager** und anschließend **Package Manager Console** aus, um die Package Manager-Konsole zu öffnen.
3. Geben Sie den Befehl „Update-Package Aspose.TeX“ ein, um auf die neueste Vollversion zu verweisen, oder geben Sie den Befehl „Update-Package Aspose.TeX -prerelease“ ein, um die neueste Version einschließlich Hotfixes zu installieren.
4. Drücken Sie **Enter**.

### Installieren Sie das Paket über die Paketmanager-GUI

Befolgen Sie diese Schritte, um über die Paketmanager-GUI auf die Komponente zu verweisen:

1. Öffnen Sie Ihre .NET-Anwendung in Visual Studio.
2. Wählen Sie im Menü **Extras** unter der Option **Lösung** die Optionen **Bibliothekspaket-Manager** und **NuGet-Pakete verwalten** aus. 

   Eine ähnliche Option erhalten Sie auch im Solution Explorer:
   1. Klicken Sie mit der rechten Maustaste auf den Projektnamen.
   2. Wählen Sie **NuGet-Pakete verwalten**.

3. Wählen Sie im linken Menü **Online**.
4. Geben Sie **Aspose.TeX** in das Suchfeld ein, um Aspose.TeX für .NET zu finden.
5. Klicken Sie neben der neuesten Version von Aspose.TeX für .NET auf **Installieren/Aktualisieren**

