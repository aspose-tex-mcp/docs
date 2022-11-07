---
translation: true
template: /_templates/_output-to-zip-net.md
title: من TeX إلى ZIP | NET API Solution
url: /net/output-to-zip/
description: "NET API Solution للعمل مع TeX. تتيح لك وظيفة تحويل TeX إلى ZIP حفظ ملف TeX الخاص بك باعتباره الأرشيف الأكثر شيوعًا. C# أمثلة على هذه الوظيفة."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: اكتب الإخراج إلى ZIP
h2: "احفظ نتيجة تحويل ملف TeX بتنسيق ZIP عبر C# .NET"
---

{{<section overview>}}
---
p1: "تُعرف TeX بأنها إحدى لغات ترميز البيانات. إنه النواة الأساسية لنظام مجموعة النشر (تنضيد الكمبيوتر). من المشكوك فيه اعتبار [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) تنسيق ملف ، لأنه لغة برمجة. ومن ناحية أخرى ، فهو محرك مترجم يفهم هذه اللغة. على أي حال ، باختصار ، الغرض الرئيسي منه هو المساعدة في إنشاء كتابة نص رياضي أو تقني. ولكن عندما يكون الملف قد تم إنشاؤه بالفعل ولا تريد أي معالجات أخرى عليه ، فقد ترغب في تحويله إلى تنسيق مختلف أكثر شيوعًا."
p2: "يسمح حل Aspose.TeX API من بين الميزات الأخرى المختلفة بتحويل ملفات TeX ثم حفظ النتيجة كأرشيف ZIP. ستجد هنا مقتطفًا من التعليمات البرمجية حول كيفية تحويل TeX إلى PDF وحفظ ناتج النتيجة إلى zip. يقوم محول API بتحويل TeX باستخدام أي لغة تدعمها C#. يمكن أيضًا استخدام واجهة برمجة التطبيقات التي تراها هنا لإنشاء تطبيق خاص بك عبر الأنظمة الأساسية أو دمجها في مشروع .NET الخاص بك. هذه [*المحولات عبر الأنظمة الأساسية*](https://products.aspose.app/tex/conversion/tex) موجودة أيضًا في نظام Aspose البيئي. لكن لتشغيل الأمثلة نحتاج:"
p3: "Aspose.TeX for .NET API وهي واجهة برمجة تطبيقات لمعالجة المستندات وتحويلها غنية بالميزات وقوية وسهلة الاستخدام لمنصة C#."
p4: "افتح مدير الحزم NuGet ، وابحث عن Aspose.TeX وقم بالتثبيت. يمكنك أيضًا استخدام الأمر التالي من Package Manager Console."
---

{{<section feature1>}}
---
title: 'خطوات استخدام أدلة ZIP لملف الناتج TeX C#.'
h3: "كود C# لاستخدام أدلة ZIP للإخراج"
item1: "أنشئ مثيل [*TeXOptions Class*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/)."
item2: "حدد دليل عمل أرشيف ZIP للإخراج باستخدام خاصية [*OutputWorkingDirectory*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/)."
item3: "حدد وحدة التحكم كمحطة إخراج باستخدام فئة [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)."
item4: "حدد خيارات الحفظ باستخدام فئة [*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/)."
item5: "شغّل التحويل باستخدام طريقة [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) لـ [*PdfDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/)"
item6: صقل الإخراج.
item7: "لإنهاء أرشيف ZIP الناتج ، استخدم فئة [*OutputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/)."
---