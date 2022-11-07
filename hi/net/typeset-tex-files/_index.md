---
translation: true
template: /_templates/_typeset-tex-files-net.md
title: टीएक्स टाइपसेटिंग कार्यक्षमता | .नेट एपीआई
url: /net/typeset-tex-files/
description: ".NET API समाधान TeX के साथ काम करने के लिए। उदाहरण के बारे में जानें कि C# कोड की कुछ पंक्तियों के साथ टीएक्स टाइपसेट कैसे बनाएं।"
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: टाइपसेट टीएक्स फाइलें
h2: "एक कस्टम टीएक्स प्रारूप C# .NET का उपयोग कर एक टीएक्स फ़ाइल टाइप करें"
---

{{<section overview>}}
---
p1: "TeX को एक ही समय में डेटा मार्कअप भाषाओं और/या टाइपसेटिंग भाषा में से एक के रूप में जाना जाता है। इसका मतलब है कि आप दस्तावेज़ में अपने पाठ को प्रारूपित नहीं करते हैं, लेकिन आदेशों के साथ सादा पाठ दर्ज करें। आउटपुट के रूप में, आपको आवश्यक (निर्दिष्ट) प्रारूप की स्वरूपित फ़ाइल मिल जाएगी। [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) प्रकाशन सेट सिस्टम (कंप्यूटर टाइपसेटिंग) का केंद्रीय कोर है।"
p2: "TeX टाइपसेटिंग की अधिक समझ प्राप्त करने के लिए दस्तावेज़ीकरण का [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) सीखें। और इस पेज पर आपको कस्टम टीएक्स प्रारूप का उपयोग करके एक टीएक्स फ़ाइल टाइप करने का तरीका बताते हुए कोड स्निपेट मिलेंगे।"
p3: "हमें जिन उदाहरणों की आवश्यकता है उन्हें चलाने के लिए:"
p4: ".NET API के लिए Aspose.TeX जो C# प्लेटफॉर्म के लिए एक सुविधा संपन्न, शक्तिशाली और उपयोग में आसान दस्तावेज़ हेरफेर और रूपांतरण API है।"
p5: "NuGet पैकेज मैनेजर खोलें, और Aspose.TeX खोजें और इंस्टॉल करें। आप पैकेज मैनेजर कंसोल से निम्न कमांड का भी उपयोग कर सकते हैं।"
---

{{<section feature1>}}
---
title: 'C# का उपयोग कर टीएक्स टाइप करने के लिए कदम।'
h3: "टीएक्स टाइप करने के लिए C# कोड"
item1: "[*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) क्लास का उपयोग करके प्रारूप प्रदाता बनाएं।"
item2: "[*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) कक्षा।"
item3: "यदि मुख्य इनपुट स्ट्रीम के रूप में प्रदान नहीं किया गया है तो इनपुट कार्यशील निर्देशिका निर्दिष्ट करें। इसके लिए [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) क्लास का इस्तेमाल करें।"
item4: "आउटपुट के लिए फ़ाइल सिस्टम कार्यशील निर्देशिका निर्दिष्ट करें। इसके लिए [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) क्लास का इस्तेमाल करें।"
item5: "नौकरी चलाएँ [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) विधि के लिए  [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)।"
item6: आउटपुट को परिष्कृत करें।
---