---
translation: true
template: /_templates/_load-tex-from-disk-net.md
title: تحميل TeX من قرص | NET API Solution
url: /net/load-tex-from-disk/
description: "NET API Solution للعمل مع TeX. تعلم من المثال كيفية تحميل ملف TeX من القرص ببضعة أسطر من كود C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: قم بتحميل ملفات مصدر TeX من القرص
h2: "NET API Solution لتحميل ملفات TeX / LaTeX من القرص"
---

{{<section overview>}}
---
p1: "تُعرف TeX باسم لغة التنضيد. هذا يعني أنك لا تقوم بتنسيق النص الخاص بك في المستند ، ولكن أدخل النص العادي مع الأوامر. كإخراج ، ستحصل على الملف المنسق بالتنسيق المطلوب (المحدد). [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) هو النواة المركزية لنظام مجموعة النشر (تنضيد الكمبيوتر). يتم تشغيل مهمة TeX على ملف TeX محدد بشكل صريح. للحصول على مزيد من الفهم لمدخلات ومخرجات TeX ، تعرف على [*TeX I / O*](https://docs.aspose.com/tex/net/tex-io/) للوثائق."
p2: "كما هو معروف ، فإن الغرض الرئيسي من TeX هو المساعدة في إنشاء كتابة نص رياضي أو تقني. ولكن قبل أي تلاعب ، يجب تحميل الملف أولاً. ستجد هنا مقتطفات من التعليمات البرمجية تشرح كيفية تحميل ملفات مصدر TeX من القرص باستخدام دلائل نظام الملفات للإدخال والإخراج ، والإخراج إلى جهاز XPS ، وكتابة الإخراج الطرفي إلى وحدة التحكم."
p3: "لتشغيل الأمثلة التي نحتاجها:"
p4: "Aspose.TeX for .NET API وهي واجهة برمجة تطبيقات لمعالجة المستندات وتحويلها غنية بالميزات وقوية وسهلة الاستخدام لمنصة C#."
p5: "افتح مدير الحزم NuGet ، وابحث عن Aspose.TeX وقم بالتثبيت. يمكنك أيضًا استخدام الأمر التالي من Package Manager Console."
---

{{<section feature1>}}
---
title: 'خطوات تحميل TeX من القرص C#.'
h3: "C# كود لتحميل TeX"
item1: "أنشئ خيارات تحويل لتنسيق مخصص عند امتداد محرك ObjectTeX باستخدام [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) طريقة [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) فئة."
item2: "حدد دليل عمل نظام الملفات للإدخال. استخدم فئة [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) لهذا الغرض."
item3: "حدد دليل عمل نظام الملفات للمخرجات باستخدام فئة [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)."
item4: "حدد وحدة التحكم كمحطة إخراج باستخدام فئة [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)."
item5: "حدد محطة ذاكرة كمحطة إخراج إذا كنت بحاجة. لهذا الاستخدام [*OutputMemoryTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputmemoryterminal/) فئة."
item6: "قم بتشغيل الوظيفة [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) طريقة لـ [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item7: صقل الإخراج.
---