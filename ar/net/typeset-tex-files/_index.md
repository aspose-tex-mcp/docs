---
translation: true
template: /_templates/_typeset-tex-files-net.md
title: وظيفة تنضيد TeX | .NET API المحلول 
url: /net/typeset-tex-files/
description: "NET API Solution للعمل مع TeX. تعلم من المثال كيفية إنشاء مجموعات طباعية TeX ببضعة أسطر من كود C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: تنضيد ملفات TeX
h2: "اضبط ملف TeX على تنسيق TeX مخصص C# .NET"
---

{{<section overview>}}
---
p1: "تُعرف TeX بأنها إحدى لغات ترميز البيانات و / أو لغة التنضيد في نفس الوقت. هذا يعني أنك لا تقوم بتنسيق النص الخاص بك في المستند ، ولكن أدخل النص العادي مع الأوامر. كإخراج ، ستحصل على الملف المنسق بالتنسيق المطلوب (المحدد). [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) هو النواة المركزية لنظام مجموعة النشر (تنضيد الكمبيوتر)."
p2: "للحصول على مزيد من الفهم لتنضيد TeX ، تعرف على [*TeX I / O*](https://docs.aspose.com/tex/net/tex-io/) للوثائق. وستجد في هذه الصفحة مقتطفات من التعليمات البرمجية تشرح كيفية تنضيد ملف TeX باستخدام تنسيق TeX مخصص."
p3: "لتشغيل الأمثلة التي نحتاجها:"
p4: "Aspose.TeX for .NET API وهي واجهة برمجة تطبيقات لمعالجة المستندات وتحويلها غنية بالميزات وقوية وسهلة الاستخدام لمنصة C#."
p5: "افتح مدير الحزم NuGet ، وابحث عن Aspose.TeX وقم بالتثبيت. يمكنك أيضًا استخدام الأمر التالي من Package Manager Console."
---

{{<section feature1>}}
---
title: 'خطوات لتنضيد TeX باستخدام C#.'
h3: "C# كود لتنضيد TeX"
item1: "أنشئ موفر التنسيق باستخدام فئة [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/)."
item2: "أنشئ خيارات تحويل لتنسيق مخصص عند امتداد محرك ObjectTeX باستخدام [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) طريقة [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) فئة."
item3: "حدد دليل عمل الإدخال إذا لم يتم توفير الإدخال الرئيسي كتدفق. استخدم فئة [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) لهذا الغرض."
item4: "حدد دليل عمل نظام الملفات للمخرجات. استخدم فئة [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) لهذا الغرض."
item5: "قم بتشغيل الوظيفة [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) طريقة لـ [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item6: صقل الإخراج.
---