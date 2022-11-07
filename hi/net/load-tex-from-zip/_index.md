---
translation: true
template: /_templates/_load-tex-from-zip-net.md
title: ज़िप से टीएक्स लोड हो रहा है | .NET एपीआई समाधान
url: /net/load-tex-from-zip/
description: ".NET API समाधान TeX के साथ काम करने के लिए। C# कोड की कुछ पंक्तियों के साथ ज़िप से एक टीएक्स फ़ाइल लोड करने के उदाहरण के बारे में जानें।"
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: ज़िप से टीएक्स स्रोत फ़ाइलें लोड करें
h2: "ज़िप संग्रह से TeX फ़ाइलों को लोड करने के लिए .NET API समाधान"
---

{{<section overview>}}
---
p1: "टीएक्स को टाइपसेटिंग भाषा के रूप में जाना जाता है। इसका मतलब है कि आप दस्तावेज़ में अपने पाठ को प्रारूपित नहीं करते हैं, लेकिन आदेशों के साथ सादा पाठ दर्ज करें। आउटपुट के रूप में, आपको आवश्यक (निर्दिष्ट) प्रारूप की स्वरूपित फ़ाइल मिल जाएगी। TeX इनपुट और आउटपुट की अधिक समझ प्राप्त करने के लिए दस्तावेज़ीकरण का [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) सीखें।"
p2: "जैसा कि ज्ञात है, TeX का मुख्य उद्देश्य गणितीय या तकनीकी पाठ लेखन बनाने में मदद करना है। लेकिन किसी भी जोड़तोड़ से पहले, फ़ाइल को पहले लोड किया जाना चाहिए। यहां आपको कोड स्निपेट मिलेंगे जो बताते हैं कि कैसे इनपुट और आउटपुट के लिए ज़िप निर्देशिकाओं का उपयोग करके ज़िप से टीएक्स स्रोत फ़ाइलों को लोड करना है, पीडीएफ डिवाइस पर आउटपुट करना, कंसोल पर टर्मिनल आउटपुट लिखना।"
p3: ".tex फ़ाइलों को लोड करने के लिए हमें चाहिए:"
p4: ".NET API के लिए Aspose.TeX जो C# प्लेटफॉर्म के लिए एक सुविधा संपन्न, शक्तिशाली और उपयोग में आसान दस्तावेज़ हेरफेर और रूपांतरण API है।"
p5: "NuGet पैकेज मैनेजर खोलें, और Aspose.TeX खोजें और इंस्टॉल करें। आप पैकेज मैनेजर कंसोल से निम्न कमांड का भी उपयोग कर सकते हैं।"
---

{{<section feature1>}}
---
title: "एक ज़िप संग्रह C# से टीएक्स लोड करने के लिए कदम:"
h3: "टीएक्स लोड करने के लिए C# कोड"
item1: "इनपुट कार्यशील निर्देशिका के रूप में उपयोग करने के लिए ज़िप संग्रह पर स्ट्रीम खोलें।"
item2: "आउटपुट कार्यशील निर्देशिका के रूप में उपयोग करने के लिए ज़िप संग्रह पर स्ट्रीम खोलें।"
item3: "[*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) कक्षा।"
item4: "इनपुट के लिए एक ज़िप संग्रह कार्यशील निर्देशिका निर्दिष्ट करें या/और संग्रह के अंदर एक पथ निर्दिष्ट करें। इसके लिए [*InputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/) क्लास के कंस्ट्रक्टर्स का इस्तेमाल करें।"
item5: "आउटपुट के लिए एक ज़िप संग्रह कार्यशील निर्देशिका निर्दिष्ट करें या/और संग्रह के अंदर एक पथ निर्दिष्ट करें। इसके लिए [*outputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/) क्लास के कंस्ट्रक्टर्स का इस्तेमाल करें।"
item6: "[*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/) क्लास का उपयोग करके कंसोल को आउटपुट टर्मिनल के रूप में निर्दिष्ट करें।"
item7: "[*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/) क्लास का उपयोग करके बचत विकल्पों को परिभाषित करें।"
item8: "नौकरी चलाएँ [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) विधि के लिए  [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)।"
item9: आउटपुट को परिष्कृत करें।
---