---
translation: true
template: /_templates/_output-to-disk-net.md
title: TeX çıktısını diske yaz | .NET API Çözümü
url: /net/output-to-disk/
description: "TeX ile çalışmak için .NET API Çözümü. Birkaç satır C# koduyla TeX dosyası için özel çıktının nasıl oluşturulacağını örnek üzerinde öğrenin."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: TeX çıktısını diske yaz
h2: "TeX dosya dönüştürmenin sonucunu C# .NET aracılığıyla disk olarak kaydedin"
---

{{<section overview>}}
---
p1: "TeX, bir dizgi dili olarak bilinir; bu, metninizi belgede biçimlendirmediğiniz, komutlarla birlikte düz metni girdiğiniz anlamına gelir. Documentation'ın [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) makalesinden bilindiği gibi, TeX işi açıkça belirtilen bir TeX dosyası üzerinde çalışır. Orada ayrıca TeX etkileşim modları ve TeX giriş ve çıkışıyla ilgili temel öğeler hakkında bilgi bulabilirsiniz."
p2: "TeX'in ana kullanımı, matematiksel veya teknik metin yazımının oluşturulmasına yardımcı olmaktır. Ancak dosya zaten oluşturulduysa ve üzerinde daha fazla değişiklik yapmak istemiyorsanız, onu farklı, daha popüler bir biçime dönüştürmek isteyebilirsiniz."
p3: "Bu sayfada, girdi ve çıktı için dosya sistemi dizinlerini kullanmayı, XPS cihazına çıktı almayı, iş adını geçersiz kılmayı, terminal çıktısını diske yazmayı açıklayan bir kod örneği bulacaksınız. Basit bir deyişle, çıktının diske yazılmasıyla bir dönüşümdür. Böyle bir işlemi çalıştırmak için ihtiyacımız var:"
p4: "C# platformu için zengin özelliklere sahip, güçlü ve kullanımı kolay bir belge işleme ve dönüştürme API'si olan Aspose.TeX for .NET API."
p5: "NuGet paket yöneticisini açın ve Aspose.TeX'i arayın ve kurun. Paket Yöneticisi Konsolundan aşağıdaki komutu da kullanabilirsiniz."
---

{{<section feature1>}}
---
title: "Terminal çıktısını C# diskine yazma adımları:"
h3: "TeX'i dönüştürmek ve çıktıyı diske yazmak için C# Kodu"
item1: "[*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) [*TeXOptions*](https://aspose.com/tex/net/aspose.tex/texoptions/) yöntemini kullanarak ObjectTeX motor uzantısında dönüştürme seçenekleri oluşturun referans. Sınıf."
item2: "TeXJob yapıcısının ilk argümanının iş adı olarak alınmasını istemiyorsanız bir iş adı belirtin."
item3: "Giriş için bir dosya sistemi çalışma dizini belirtin. Bunun için [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) Sınıfını kullanın."
item4: "[*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) Sınıfının varlıklarının yardımıyla çıktı için bir dosya sistemi çalışma dizini belirtin."
item5: "Terminal çıktısının, çıktı çalışma dizinindeki bir dosyaya yazılması gerektiğini belirtin."
item6: "İşi çalıştırın [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/)  yöntemi [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
---