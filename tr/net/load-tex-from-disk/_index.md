---
translation: true
template: /_templates/_load-tex-from-disk-net.md
title: TeX'i bir diskten yükleme | .NET API Çözümü
url: /net/load-tex-from-disk/
description: "TeX ile çalışmak için .NET API Çözümü. Birkaç satır C# koduyla diskten bir TeX dosyasının nasıl yükleneceğini örnek üzerinde öğrenin."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: TeX kaynak dosyalarını diskten yükleyin
h2: "TeX/LaTeX dosyalarını diskten yüklemek için .NET API Çözümü"
---

{{<section overview>}}
---
p1: "TeX bir dizgi dili olarak bilinir. Bu, belgedeki metninizi biçimlendirmediğiniz, komutlarla birlikte düz metni girdiğiniz anlamına gelir. Çıktı olarak, gerekli (belirtilen) formatın formatlanmış dosyasını alacaksınız. [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) yayın seti sisteminin (bilgisayar dizgisi) merkezi çekirdeğidir. Bir TeX işi, açıkça belirtilen bir TeX dosyasında çalışır. TeX giriş ve çıkışını daha iyi anlamak için Dokümantasyonun [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) bölümünü öğrenin."
p2: "Bilindiği gibi TeX'in temel amacı matematiksel veya teknik metin yazımı oluşturmaya yardımcı olmaktır. Ancak herhangi bir manipülasyondan önce dosya ilk olarak yüklenmelidir. Burada, giriş ve çıkış için dosya sistemi dizinlerini kullanarak TeX kaynak dosyalarının diskten nasıl yükleneceğini, XPS cihazına çıktı alınmasını, terminal çıktısının konsola yazılmasını açıklayan kod parçacıkları bulacaksınız."
p3: "Örnekleri çalıştırmak için ihtiyacımız olan:"
p4: "C# platformu için zengin özelliklere sahip, güçlü ve kullanımı kolay bir belge işleme ve dönüştürme API'si olan Aspose.TeX for .NET API."
p5: "NuGet paket yöneticisini açın ve Aspose.TeX'i arayın ve kurun. Paket Yöneticisi Konsolundan aşağıdaki komutu da kullanabilirsiniz."
---

{{<section feature1>}}
---
title: TeX'i bir C# diskinden yükleme adımları.
h3: "TeX yüklemek için C# Kodu"
item1: "[*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) [*TeXOptions*](yönteminikullanarakObjectTeXmotoruzantısıüzerindeözelbirbiçimiçindönüştürmeseçeneklerioluşturun.https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Sınıf."
item2: "Giriş için bir dosya sistemi çalışma dizini belirtin. Bunun için [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) Sınıfını kullanın."
item3: "[*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) Sınıfını kullanarak çıktı için bir dosya sistemi çalışma dizini belirtin."
item4: "[*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/) Class'ı kullanarak konsolu çıkış terminali olarak belirtin."
item5: "Gerekirse, çıkış terminali olarak bir bellek terminali belirtin. Bunun için [*OutputMemoryTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputmemoryterminal/) Sınıfını kullanın."
item6: "İşi çalıştırın [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/)  yöntemi [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item7: Çıktıyı hassaslaştırın.
---