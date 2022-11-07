---
translation: true
template: /_templates/_customize-input-net.md
title: Özel giriş TeX oluşturun | .NET API
url: /net/customize-input/
description: "TeX ile çalışmak için .NET API Çözümü. Birkaç satır C# koduyla TeX dosyası için nasıl özel girdi oluşturulacağını örnek üzerinde öğrenin."
keywords: özel giriş tex net api, tex'i özelleştirmek için C# api
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Girişi özelleştir
h2: "TeX dosyalarının girişini özelleştirmek için .NET API Çözümü"
---

{{<section overview>}}
---
p1: "TeX bir dizgi dili olarak bilinir. Bu, belgedeki metninizi biçimlendirmediğiniz, komutlarla birlikte düz metni girdiğiniz anlamına gelir. Dokümantasyonun [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) makalesinde açıklandığı gibi, TeX işi açıkça belirtilen bir TeX dosyası üzerinde çalışır. Yani, bu dosyayı belirli bir TeX işinin girişine dahil ediyoruz."
p2: "Bu sayfada, girişin TeX sözdizimini izlemesi gerektiğini ve ideal olarak yalnızca motor tarafından bilinen komutları içermesi gerektiğini dikkate alarak TeX kaynak dosyalarının girişinin nasıl özelleştirileceğini açıklayan bir kod örneği bulacaksınız."
p3: ".tex dosyaları girişini özelleştirmek için ihtiyacımız olan:"
p4: "C# platformu için zengin özelliklere sahip, güçlü ve kullanımı kolay bir belge işleme ve dönüştürme API'si olan Aspose.TeX for .NET API."
p5: "NuGet paket yöneticisini açın ve Aspose.TeX'i arayın ve kurun. Paket Yöneticisi Konsolundan aşağıdaki komutu da kullanabilirsiniz."
---

{{<section feature1>}}
---
title: "TeX C# girişini özelleştirme adımları:"
h3: "TeX giriş özelleştirmesi için C# Kodu"
item1: "[*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Yöntemini kullanma [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Sınıfı, ObjectTeX motor uzantısında formatsız TeX motor seçenekleri oluşturun."
item2: "[*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) Sınıfını kullanarak giriş için bir dosya sistemi çalışma dizini belirtin."
item3: "[*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/) Yönteminin yardımıyla özelleştirilmiş formatı oluşturun."
---