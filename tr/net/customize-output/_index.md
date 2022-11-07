---
translation: true
template: /_templates/_customize-output-net.md
title: Özel çıktı oluşturma TeX | .NET API
url: /net/customize-output/
description: "TeX ile çalışmak için .NET API Çözümü. Birkaç satır C# koduyla TeX dosyası için özel çıktı oluşturma örneğini okuyun."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Çıktıyı özelleştir
h2: "TeX dosyalarının çıktısını özelleştirmek için .NET API Çözümü"
---

{{<section overview>}}
---
p1: "TeX bir dizgi dili olarak bilinir. Bu, belgedeki metninizi biçimlendirmediğiniz, komutlarla birlikte düz metni girdiğiniz anlamına gelir."
p2: "Dokümantasyonun [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) makalesi bize bir TeX dosyasının dizilecek herhangi bir veri içermeyebileceğini, sadece kontrol dizilerini içerebileceğini öğretir. . Yine de genellikle bu tür verileri içerir ve hedef formattaki bir dosya dizgi metnine sahiptir. Dosya ayrıca girdi olarak belirtilen dosya ile aynı ada sahip olacaktır ve ana çıktı dosyasıdır. Orijinal TeX için bu, DVI formatında bir dosyadır. İş adını genişletmeden hem girdi hem de çıktı dosyalarının adını arayacağız."
p3: "Bu sayfada, TeX dosyalarının çıktısını nasıl özelleştireceğinizi görebileceğiniz özel bir TeX formatında dosya oluşturmayı açıklayan bir kod örneği bulacaksınız. .tex dosyalarının çıktısını özelleştirmek için ihtiyacımız olan:"
p4: "C# platformu için zengin özelliklere sahip, güçlü ve kullanımı kolay bir belge işleme ve dönüştürme API'si olan Aspose.TeX for .NET API."
p5: "NuGet paket yöneticisini açın ve Aspose.TeX'i arayın ve kurun. Paket Yöneticisi Konsolundan aşağıdaki komutu da kullanabilirsiniz."
---

{{<section feature1>}}
---
title: "TeX çıktısını C# özelleştirme adımları:"
h3: "TeX çıktı özelleştirmesi için C# Kodu"
item1: "[*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Yönteminin [*TeXOptions*](https://reference.aspose) yardımıyla .com/tex/net/aspose.tex/texoptions/) Sınıfı, ObjectTeX motor uzantısı üzerine formatsız TeX motor seçenekleri oluşturun."
item2: "Giriş için bir dosya sistemi çalışma dizini belirtmek üzere [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) Sınıfını kullanın."
item3: "Çıktı için bir dosya sistemi çalışma dizini belirtmek üzere [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) Sınıfını kullanın."
item4: "Yeni formatı oluşturmak için [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/) Yöntemini kullanın."
item5: Çıktıyı hassaslaştırın.
---