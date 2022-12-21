---
translation: true
template: /_templates/_output-to-zip-net.md
title: टीएक्स टू जिप | .NET एपीआई समाधान
url: /net/output-to-zip/
description: ".NET API समाधान TeX के साथ काम करने के लिए। TeX से ZIP  कार्यक्षमता आपको अपनी TeX फ़ाइल को सबसे लोकप्रिय संग्रह के रूप में सहेजने देती है। C# उदाहरण।"
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: ज़िप को आउटपुट लिखें
h2: "TeX फ़ाइल रूपांतरण के परिणाम को C# .NET . के माध्यम से ज़िप के रूप में सहेजें"
---

{{<section overview>}}
---
p1: "TeX को डेटा मार्कअप भाषाओं में से एक के रूप में जाना जाता है। यह प्रकाशन सेट सिस्टम (कंप्यूटर टाइपसेटिंग) का मुख्य केंद्र है। [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) को एक फ़ाइल प्रारूप के रूप में मानना ​​संदिग्ध है, क्योंकि यह एक प्रोग्रामिंग भाषा है। और दूसरी ओर, यह एक दुभाषिया इंजन है जो इस भाषा को समझता है। वैसे भी, संक्षेप में, इसका मुख्य उद्देश्य गणितीय या तकनीकी पाठ लेखन के निर्माण में मदद करना है। लेकिन जब फ़ाइल पहले से ही बनाई जा चुकी हो और आप उस पर कोई और जोड़-तोड़ नहीं करना चाहते हैं, तो आप इसे एक अलग, अधिक लोकप्रिय, प्रारूप में बदलना चाह सकते हैं।"
p2: "विभिन्न अन्य विशेषताओं के बीच Aspose.TeX API समाधान TeX फ़ाइलों के रूपांतरण की अनुमति देता है और फिर परिणाम को ज़िप संग्रह के रूप में सहेजता है। यहां आपको टीएक्स को पीडीएफ में बदलने और परिणाम के आउटपुट को ज़िप में सहेजने के तरीके पर एक कोड स्निपेट मिलेगा। एपीआई कनवर्टर C# द्वारा समर्थित किसी भी भाषा का उपयोग कर टीएक्स को बदल देता है। आप यहां जो एपीआई देख रहे हैं, उसका उपयोग आपका स्वयं का क्रॉस-प्लेटफ़ॉर्म एप्लिकेशन बनाने या आपके .NET प्रोजेक्ट में एकीकृत करने के लिए भी किया जा सकता है। ऐसे [*क्रॉस-प्लेटफ़ॉर्म कन्वर्टर्स*](https://products.aspose.app/tex/conversion/tex) भी Aspose पारिस्थितिकी तंत्र में मौजूद हैं। लेकिन उदाहरणों को चलाने के लिए हमें चाहिए:"
p3: ".NET API के लिए Aspose.TeX जो C# प्लेटफॉर्म के लिए एक सुविधा संपन्न, शक्तिशाली और उपयोग में आसान दस्तावेज़ हेरफेर और रूपांतरण API है।"
p4: "NuGet पैकेज मैनेजर खोलें, और Aspose.TeX खोजें और इंस्टॉल करें। आप पैकेज मैनेजर कंसोल से निम्न कमांड का भी उपयोग कर सकते हैं।"
---

{{<section feature1>}}
---
title: आउटपुट TeX फ़ाइल C# के लिए ZIP निर्देशिकाओं का उपयोग करने के चरण।
h3: "C# आउटपुट के लिए ज़िप निर्देशिकाओं का उपयोग करने के लिए कोड"
item1: "[*TeXOptions Class*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) का उदाहरण बनाएं।"
item2: "[*OutputWorkingDirectory*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) प्रॉपर्टी का उपयोग करके आउटपुट के लिए एक ज़िप संग्रह कार्य निर्देशिका निर्दिष्ट करें।"
item3: "[*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/) क्लास का उपयोग करके कंसोल को आउटपुट टर्मिनल के रूप में निर्दिष्ट करें।"
item4: "[*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/) क्लास का उपयोग करके बचत के विकल्पों को परिभाषित करें।"
item5: "[*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) विधि का उपयोग करके [*PdfDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/)"
item6: आउटपुट को परिष्कृत करें।
item7: "आउटपुट ज़िप संग्रह को अंतिम रूप देने के लिए [*OutputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/) क्लास का उपयोग करें।"
---