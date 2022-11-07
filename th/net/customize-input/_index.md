---
translation: true
template: /_templates/_customize-input-net.md
title: สร้างอินพุตแบบกำหนดเอง TeX | .NET API โซลูชั่น
url: /net/customize-input/
description: ".NET API โซลูชันเพื่อทำงานกับ TeX เรียนรู้เกี่ยวกับตัวอย่างวิธีสร้างอินพุตแบบกำหนดเองสำหรับไฟล์ TeX ด้วยโค้ด C# สองสามบรรทัด"
keywords: 'อินพุตที่กำหนดเอง tex net api, C# api เพื่อปรับแต่ง tex'
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: ปรับแต่งอินพุต
h2: ".NET API Solution เพื่อปรับแต่งอินพุตของไฟล์ TeX"
---

{{<section overview>}}
---
p1: "TeX เรียกว่าภาษาเรียงพิมพ์ หมายความว่าคุณไม่ได้จัดรูปแบบข้อความของคุณในเอกสาร แต่ป้อนข้อความธรรมดาพร้อมกับคำสั่ง ตามที่อธิบายไว้ในบทความ [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) ของเอกสารประกอบ งาน TeX จะทำงานบนไฟล์ TeX ที่ระบุอย่างชัดเจน ดังนั้นเราจึงรวมไฟล์นี้ไว้ในอินพุตของงาน TeX บางงาน"
p2: "ในหน้านี้ คุณจะพบตัวอย่างโค้ดที่อธิบายวิธีปรับแต่งอินพุตของไฟล์ต้นทาง TeX โดยคำนึงถึงว่าอินพุตควรเป็นไปตามไวยากรณ์ TeX และควรมีเฉพาะคำสั่งที่กลไกรู้จักเท่านั้น"
p3: "ในการปรับแต่งอินพุตไฟล์ .tex เราต้องการ:"
p4: "Aspose.TeX สำหรับ .NET API ซึ่งเป็น API การจัดการและการแปลงเอกสารที่มีคุณลักษณะหลากหลาย มีประสิทธิภาพ และใช้งานง่ายสำหรับแพลตฟอร์ม C#"
p5: "เปิดตัวจัดการแพ็คเกจ NuGet และค้นหา Aspose.TeX และติดตั้ง คุณสามารถใช้คำสั่งต่อไปนี้จาก Package Manager Console"
---

{{<section feature1>}}
---
title: "ขั้นตอนในการปรับแต่งอินพุต TeX C#:"
h3: "รหัส C# สำหรับการปรับแต่งอินพุต TeX"
item1: "การใช้ [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) วิธีการของ [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) คลาส สร้างตัวเลือกเอ็นจิน TeX สำหรับไม่มีรูปแบบตามส่วนขยายเอ็นจิ้น ObjectTeX"
item2: "ใช้ [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) คลาส ระบุไดเร็กทอรีการทำงานของระบบไฟล์สำหรับอินพุต"
item3: "ด้วยความช่วยเหลือของเมธอด [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/) ให้สร้างรูปแบบที่กำหนดเอง"
---