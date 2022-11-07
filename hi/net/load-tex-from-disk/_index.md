---
translation: true
template: /_templates/_load-tex-from-disk-net.md
title: डिस्क से टीएक्स लोड हो रहा है | .NET एपीआई समाधान
url: /net/load-tex-from-disk/
description: ".NET API समाधान TeX के साथ काम करने के लिए। सी# कोड की कुछ पंक्तियों के साथ डिस्क से टीएक्स फ़ाइल को लोड करने के उदाहरण के बारे में जानें।"
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: डिस्क से टीएक्स स्रोत फ़ाइलें लोड करें
h2: ".NET API समाधान डिस्क से TeX/LaTeX फ़ाइलें लोड करने के लिए"
---

{{<section overview>}}
---
p1: "टीएक्स को टाइपसेटिंग भाषा के रूप में जाना जाता है। इसका मतलब है कि आप दस्तावेज़ में अपने पाठ को प्रारूपित नहीं करते हैं, लेकिन आदेशों के साथ सादा पाठ दर्ज करें। आउटपुट के रूप में, आपको आवश्यक (निर्दिष्ट) प्रारूप की स्वरूपित फ़ाइल मिल जाएगी। [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) प्रकाशन सेट सिस्टम (कंप्यूटर टाइपसेटिंग) का केंद्रीय कोर है। एक टीएक्स जॉब स्पष्ट रूप से निर्दिष्ट टीएक्स फ़ाइल पर चलता है। TeX इनपुट और आउटपुट की अधिक समझ प्राप्त करने के लिए दस्तावेज़ीकरण का [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) सीखें।"
p2: "जैसा कि ज्ञात है, TeX का मुख्य उद्देश्य गणितीय या तकनीकी पाठ लेखन बनाने में मदद करना है। लेकिन किसी भी जोड़तोड़ से पहले, फ़ाइल को पहले लोड किया जाना चाहिए। यहां आपको इनपुट और आउटपुट के लिए फाइल सिस्टम निर्देशिकाओं का उपयोग करके डिस्क से टीएक्स स्रोत फ़ाइलों को लोड करने, एक्सपीएस डिवाइस पर आउटपुट करने, कंसोल पर टर्मिनल आउटपुट लिखने का तरीका बताते हुए कोड स्निपेट मिलेंगे।"
p3: "हमें जिन उदाहरणों की आवश्यकता है उन्हें चलाने के लिए:"
p4: ".NET API के लिए Aspose.TeX जो C# प्लेटफॉर्म के लिए एक सुविधा संपन्न, शक्तिशाली और उपयोग में आसान दस्तावेज़ हेरफेर और रूपांतरण API है।"
p5: "NuGet पैकेज मैनेजर खोलें, और Aspose.TeX खोजें और इंस्टॉल करें। आप पैकेज मैनेजर कंसोल से निम्न कमांड का भी उपयोग कर सकते हैं।"
---

{{<section feature1>}}
---
title: 'डिस्क C# से टीएक्स लोड करने के लिए कदम।'
h3: "टीएक्स लोड करने के लिए C# कोड"
item1: "[*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) कक्षा।"
item2: "इनपुट के लिए फ़ाइल सिस्टम कार्यशील निर्देशिका निर्दिष्ट करें। इसके लिए [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) क्लास का इस्तेमाल करें।"
item3: "[*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) क्लास का उपयोग करके आउटपुट के लिए फ़ाइल सिस्टम वर्किंग डायरेक्टरी निर्दिष्ट करें।"
item4: "[*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/) क्लास का उपयोग करके कंसोल को आउटपुट टर्मिनल के रूप में निर्दिष्ट करें।"
item5: "यदि आपको आवश्यकता हो तो एक मेमोरी टर्मिनल को आउटपुट टर्मिनल के रूप में निर्दिष्ट करें। इसके लिए [*OutputMemoryTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputmemoryterminal/) क्लास का इस्तेमाल करें।"
item6: "नौकरी चलाएँ [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) विधि के लिए  [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)।"
item7: आउटपुट को परिष्कृत करें।
---