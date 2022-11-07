---
translation: true
template: /_templates/_customize-output-net.md
title: إنشاء مخرجات مخصصة TeX | NET API Solution
url: /net/customize-output/
description: "NET API Solution للعمل مع TeX. اقرأ مثال كيفية إنشاء إخراج مخصص لملف TeX ببضعة أسطر من كود C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: تخصيص الإخراج
h2: "NET API Solution لتخصيص إخراج ملفات TeX"
---

{{<section overview>}}
---
p1: "تُعرف TeX باسم لغة التنضيد. هذا يعني أنك لا تقوم بتنسيق النص الخاص بك في المستند ، ولكن أدخل النص العادي مع الأوامر."
p2: "تُعلمنا المقالة [*TeX I / O*](https://docs.aspose.com/tex/net/tex-io/) من التوثيق أن ملف TeX قد لا يحتوي على أي بيانات للطباعة ولكن فقط التحكم في التسلسلات . ومع ذلك ، فإنه عادة ما يحتوي على مثل هذه البيانات ، والملف بالتنسيق الهدف له نص منضدة. سيكون للملف أيضًا نفس اسم الملف المحدد كمدخل وهو ملف الإخراج الرئيسي. بالنسبة إلى TeX الأصلي ، يعد هذا ملفًا بتنسيق DVI. سنقوم باستدعاء اسم كل من ملفات الإدخال والإخراج دون تمديد اسم الوظيفة."
p3: "في هذه الصفحة ، ستجد مثالًا للتعليمات البرمجية يشرح إنشاء ملف تنسيق TeX مخصص حيث يمكنك معرفة كيفية تخصيص إخراج ملفات TeX. لتخصيص إخراج ملفات .tex نحتاج:"
p4: "Aspose.TeX for .NET API وهي واجهة برمجة تطبيقات لمعالجة المستندات وتحويلها غنية بالميزات وقوية وسهلة الاستخدام لمنصة C#."
p5: "افتح مدير الحزم NuGet ، وابحث عن Aspose.TeX وقم بالتثبيت. يمكنك أيضًا استخدام الأمر التالي من Package Manager Console."
---

{{<section feature1>}}
---
title: "خطوات تخصيص ناتج TeX C#:"
h3: "كود C# لتخصيص إخراج TeX"
item1: "بمساعدة [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) طريقة [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) فئة ، قم بإنشاء خيارات محرك TeX بدون تنسيق عند امتداد محرك ObjectTeX."
item2: "استخدم فئة [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) لتحديد دليل عمل نظام ملفات للإدخال."
item3: "استخدم فئة [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) لتحديد دليل عمل نظام الملفات للمخرجات."
item4: "لإنشاء التنسيق الجديد ، استخدم طريقة [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/)."
item5: صقل الإخراج.
---