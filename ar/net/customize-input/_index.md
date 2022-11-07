---
translation: true
template: /_templates/_customize-input-net.md
title: إنشاء مدخلات مخصصة TeX | NET API Solution
url: /net/customize-input/
description: "NET API Solution للعمل مع TeX. تعلم في المثال كيفية إنشاء إدخال مخصص لملف TeX ببضعة أسطر من كود C#."
keywords: 'مدخلات مخصصة tex net api ، C# api لتخصيص tex'
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: تخصيص المدخلات
h2: "NET API Solution لتخصيص مدخلات ملفات TeX"
---

{{<section overview>}}
---
p1: "تُعرف TeX باسم لغة التنضيد. هذا يعني أنك لا تقوم بتنسيق النص الخاص بك في المستند ، ولكن أدخل النص العادي مع الأوامر. كما هو موضح في المقالة [*TeX I / O*](https://docs.aspose.com/tex/net/tex-io/) من التوثيق ، تعمل مهمة TeX على ملف TeX محدد بوضوح. لذلك ، نقوم بتضمين هذا الملف في مدخلات مهمة TeX معينة."
p2: "ستجد في هذه الصفحة مثالًا للرمز يشرح كيفية تخصيص مدخلات ملفات مصدر TeX مع الأخذ في الاعتبار أن الإدخال يجب أن يتبع بناء جملة TeX ، وبشكل مثالي ، يحتوي فقط على الأوامر المعروفة للمحرك."
p3: "لتخصيص إدخال ملفات .tex ، نحتاج إلى:"
p4: "Aspose.TeX for .NET API وهي واجهة برمجة تطبيقات لمعالجة المستندات وتحويلها غنية بالميزات وقوية وسهلة الاستخدام لمنصة C#."
p5: "افتح مدير الحزم NuGet ، وابحث عن Aspose.TeX وقم بالتثبيت. يمكنك أيضًا استخدام الأمر التالي من Package Manager Console."
---

{{<section feature1>}}
---
title: "خطوات تخصيص إدخال TeX C#:"
h3: "C# كود لتخصيص مدخلات TeX"
item1: "استخدام طريقة [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) لـ [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) الفئة ، أنشئ خيارات محرك TeX بدون تنسيق عند امتداد محرك ObjectTeX."
item2: "باستخدام فئة [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) ، حدد دليل عمل نظام الملفات للإدخال."
item3: "بمساعدة طريقة [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/) ، أنشئ التنسيق المخصص."
---