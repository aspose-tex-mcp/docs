---
translation: true
template: /_templates/_typeset-tex-files-net.md
title: TeX dizgi işlevi | .NET API'si
url: /net/typeset-tex-files/
description: "TeX ile çalışmak için .NET API Çözümü. Birkaç satır C# koduyla TeX dizgilerinin nasıl oluşturulacağını örnek üzerinde öğrenin."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Dizgi TeX dosyaları
h2: "Özel bir TeX biçimi C# .NET kullanarak bir TeX dosyası yazın"
---

{{<section overview>}}
---
p1: "TeX, aynı zamanda veri işaretleme dillerinden biri ve/veya dizgi dili olarak bilinir. Bu, belgedeki metninizi biçimlendirmediğiniz, komutlarla birlikte düz metni girdiğiniz anlamına gelir. Çıktı olarak, gerekli (belirtilen) formatın formatlanmış dosyasını alacaksınız. [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) yayın seti sisteminin (bilgisayar dizgisi) merkezi çekirdeğidir."
p2: "TeX dizgisini daha iyi anlamak için Belgelerin [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) bölümünü öğrenin. Ve bu sayfada, özel bir TeX formatı kullanarak bir TeX dosyasının nasıl dizileceğini açıklayan kod parçacıkları bulacaksınız."
p3: "Örnekleri çalıştırmak için ihtiyacımız olan:"
p4: "C# platformu için zengin özelliklere sahip, güçlü ve kullanımı kolay bir belge işleme ve dönüştürme API'si olan Aspose.TeX for .NET API."
p5: "NuGet paket yöneticisini açın ve Aspose.TeX'i arayın ve kurun. Paket Yöneticisi Konsolundan aşağıdaki komutu da kullanabilirsiniz."
---

{{<section feature1>}}
---
title: C# kullanarak TeX yazma adımları.
h3: "TeX dizgi için C# kodu"
item1: "[*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) Sınıfını kullanarak biçim sağlayıcıyı oluşturun."
item2: "[*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) [*TeXOptions*](yönteminikullanarakObjectTeXmotoruzantısıüzerindeözelbirbiçimiçindönüştürmeseçeneklerioluşturun.https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Sınıf."
item3: "Ana giriş bir akış olarak sağlanmadıysa giriş çalışma dizinini belirtin. Bunun için [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) Sınıfını kullanın."
item4: "Çıktı için bir dosya sistemi çalışma dizini belirtin. Bunun için [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) Sınıfını kullanın."
item5: "İşi çalıştırın [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/)  yöntemi [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item6: Çıktıyı hassaslaştırın.
---