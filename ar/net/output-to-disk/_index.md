---
translation: true
template: /_templates/_output-to-disk-net.md
title: كتابة إخراج TeX على القرص | NET API
url: /net/output-to-disk/
description: "NET API Solution للعمل مع TeX. تعرف على المثال حول كيفية إنشاء إخراج مخصص لملف TeX ببضعة أسطر من كود C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: اكتب إخراج TeX على القرص
h2: "احفظ نتيجة تحويل ملف TeX كقرص عبر C# .NET"
---

{{<section overview>}}
---
p1: "تُعرف TeX باسم لغة التنضيد مما يعني أنك لا تقوم بتنسيق النص الخاص بك في المستند ، ولكن تقوم بإدخال النص العادي مع الأوامر. كما هو معروف من المقالة [*TeX I / O*](https://docs.aspose.com/tex/net/tex-io/) من التوثيق ، تعمل مهمة TeX على ملف TeX محدد بوضوح. هناك يمكنك أيضًا العثور على معلومات حول أوضاع تفاعل TeX والأولويات المتعلقة بإدخال وإخراج TeX."
p2: "الاستخدام الرئيسي لـ TeX هو المساعدة في إنشاء كتابة نص رياضي أو تقني. ولكن عندما يكون الملف قد تم إنشاؤه بالفعل ولا تريد أي معالجات أخرى عليه ، فقد ترغب في تحويله إلى تنسيق مختلف أكثر شيوعًا."
p3: "في هذه الصفحة ، ستجد مثالًا للرمز يشرح استخدام دلائل نظام الملفات للإدخال والإخراج ، والإخراج إلى جهاز XPS ، وتجاوز اسم المهمة ، وكتابة الإخراج الطرفي على القرص. بكلمات بسيطة ، إنه تحويل مع كتابة الإخراج إلى القرص. لتشغيل هذه العملية ، نحتاج إلى:"
p4: "Aspose.TeX for .NET API وهي واجهة برمجة تطبيقات لمعالجة المستندات وتحويلها غنية بالميزات وقوية وسهلة الاستخدام لمنصة C#."
p5: "افتح مدير الحزم NuGet ، وابحث عن Aspose.TeX وقم بالتثبيت. يمكنك أيضًا استخدام الأمر التالي من Package Manager Console."
---

{{<section feature1>}}
---
title: "خطوات كتابة الإخراج الطرفي إلى القرص C#:"
h3: "C# كود لتحويل TeX وكتابة الإخراج على القرص"
item1: "أنشئ خيارات تحويل عند امتداد محرك ObjectTeX باستخدام [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) طريقة [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) الفئة."
item2: "حدد اسمًا لوظيفة إذا كنت لا تريد استخدام الوسيطة الأولى لمنشئ TeXJob كاسم وظيفة."
item3: "حدد دليل عمل نظام الملفات للإدخال. استخدم فئة [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) لهذا الغرض."
item4: "حدد دليل عمل نظام الملفات للمخرجات بمساعدة كيانات فئة [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)."
item5: "حدد أنه يجب كتابة الإخراج الطرفي في ملف في دليل عمل الإخراج."
item6: "قم بتشغيل الوظيفة [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) طريقة لـ [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
---