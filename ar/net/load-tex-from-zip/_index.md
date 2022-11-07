---
translation: true
template: /_templates/_load-tex-from-zip-net.md
title: تحميل TeX من ZIP | NET API Solution
url: /net/load-tex-from-zip/
description: "NET API Solution للعمل مع TeX. تعلم من المثال كيفية تحميل ملف TeX من ZIP ببضعة أسطر من كود C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: قم بتحميل ملفات مصدر TeX من ZIP
h2: "NET API Solution لتحميل ملفات TeX من أرشيف ZIP"
---

{{<section overview>}}
---
p1: "تُعرف TeX باسم لغة التنضيد. هذا يعني أنك لا تقوم بتنسيق النص الخاص بك في المستند ، ولكن أدخل النص العادي مع الأوامر. كإخراج ، ستحصل على الملف المنسق بالتنسيق المطلوب (المحدد). للحصول على مزيد من الفهم لمدخلات ومخرجات TeX ، تعرف على [*TeX I / O*](https://docs.aspose.com/tex/net/tex-io/) للوثائق."
p2: "كما هو معروف ، فإن الغرض الرئيسي من TeX هو المساعدة في إنشاء كتابة نص رياضي أو تقني. ولكن قبل أي تلاعب ، يجب تحميل الملف أولاً. ستجد هنا مقتطفات من التعليمات البرمجية تشرح كيفية تحميل ملفات مصدر TeX من ZIP باستخدام أدلة ZIP للإدخال والإخراج ، والإخراج إلى جهاز PDF ، وكتابة الإخراج الطرفي إلى وحدة التحكم."
p3: "لتحميل ملفات .tex نحتاج:"
p4: "Aspose.TeX for .NET API وهي واجهة برمجة تطبيقات لمعالجة المستندات وتحويلها غنية بالميزات وقوية وسهلة الاستخدام لمنصة C#."
p5: "افتح مدير الحزم NuGet ، وابحث عن Aspose.TeX وقم بالتثبيت. يمكنك أيضًا استخدام الأمر التالي من Package Manager Console."
---

{{<section feature1>}}
---
title: "خطوات تحميل TeX من أرشيف ZIP C#:"
h3: "C# كود لتحميل TeX"
item1: "افتح الدفق في أرشيف ZIP لاستخدامه كدليل عمل الإدخال."
item2: "افتح الدفق في أرشيف ZIP لاستخدامه كدليل عمل الإخراج."
item3: "قم بإنشاء خيارات تحويل لتنسيق ObjectTeX الافتراضي عند امتداد محرك ObjectTeX باستخدام [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) طريقة [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) فئة."
item4: "حدد دليل عمل أرشيف ZIP للإدخال أو / وحدد مسارًا داخل الأرشيف. استخدم المُنشئين لفئة [*InputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/) لهذا الغرض."
item5: "حدد دليل عمل أرشيف ZIP للإخراج أو / وحدد مسارًا داخل الأرشيف. استخدم المُنشئين لفئة [*outputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/) لهذا الغرض."
item6: "حدد وحدة التحكم كمحطة إخراج باستخدام فئة [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)."
item7: "حدد خيارات الحفظ باستخدام فئة [*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/)."
item8: "قم بتشغيل الوظيفة [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) طريقة لـ [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item9: صقل الإخراج.
---