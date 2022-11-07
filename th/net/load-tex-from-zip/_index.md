---
translation: true
template: /_templates/_load-tex-from-zip-net.md
title: กำลังโหลด TeX จาก ZIP | .NET API โซลูชั่น
url: /net/load-tex-from-zip/
description: ".NET API โซลูชันเพื่อทำงานกับ TeX เรียนรู้เกี่ยวกับตัวอย่างวิธีโหลดไฟล์ TeX จาก ZIP ด้วยโค้ด C# สองสามบรรทัด"
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: โหลดไฟล์ต้นฉบับ TeX จาก ZIP
h2: ".NET API Solution เพื่อโหลดไฟล์ TeX จากไฟล์ ZIP"
---

{{<section overview>}}
---
p1: "TeX เรียกว่าภาษาเรียงพิมพ์ หมายความว่าคุณไม่ได้จัดรูปแบบข้อความของคุณในเอกสาร แต่ป้อนข้อความธรรมดาพร้อมกับคำสั่ง คุณจะได้รับไฟล์ที่จัดรูปแบบตามรูปแบบที่ต้องการ (ระบุ) เพื่อให้เข้าใจ TeX input และ output มากขึ้น ให้เรียนรู้ [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) ของเอกสารประกอบ"
p2: "อย่างที่ทราบกันดีว่าจุดประสงค์หลักของ TeX คือการช่วยสร้างการเขียนข้อความทางคณิตศาสตร์หรือทางเทคนิค แต่ก่อนที่จะทำการปรับเปลี่ยนใด ๆ ไฟล์ควรถูกโหลดก่อน ที่นี่คุณจะพบข้อมูลโค้ดที่อธิบายวิธีโหลดไฟล์ต้นฉบับ TeX จาก ZIP โดยใช้ไดเร็กทอรี ZIP สำหรับอินพุตและเอาต์พุต เอาต์พุตไปยังอุปกรณ์ PDF การเขียนเอาต์พุตเทอร์มินัลไปยังคอนโซล"
p3: "ในการโหลดไฟล์ .tex เราต้องการ:"
p4: "Aspose.TeX สำหรับ .NET API ซึ่งเป็น API การจัดการและการแปลงเอกสารที่มีคุณลักษณะหลากหลาย มีประสิทธิภาพ และใช้งานง่ายสำหรับแพลตฟอร์ม C#"
p5: "เปิดตัวจัดการแพ็คเกจ NuGet และค้นหา Aspose.TeX และติดตั้ง คุณสามารถใช้คำสั่งต่อไปนี้จาก Package Manager Console"
---

{{<section feature1>}}
---
title: "ขั้นตอนในการโหลด TeX จากไฟล์ ZIP C#:"
h3: "รหัส C# สำหรับการโหลด TeX"
item1: "เปิดสตรีมบนไฟล์ ZIP เพื่อใช้เป็นไดเร็กทอรีการทำงานของอินพุต"
item2: "เปิดสตรีมบนไฟล์ ZIP เพื่อใช้เป็นไดเร็กทอรีการทำงานของเอาต์พุต"
item3: "สร้างตัวเลือกการแปลงสำหรับรูปแบบ ObjectTeX เริ่มต้นตามส่วนขยายเอ็นจิน ObjectTeX โดยใช้ [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) วิธีการของ [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) คลาส"
item4: "ระบุไดเร็กทอรีการทำงานของไฟล์ ZIP สำหรับอินพุต หรือ/และระบุพาธภายในไฟล์เก็บถาวร ใช้ตัวสร้างของคลาส [*InputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/) สำหรับสิ่งนี้"
item5: "ระบุไดเร็กทอรีการทำงานของไฟล์ ZIP สำหรับเอาต์พุต หรือ/และระบุพาธภายในไฟล์เก็บถาวร ใช้ตัวสร้างของคลาส [*outputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/) สำหรับสิ่งนี้"
item6: "ระบุคอนโซลเป็นเทอร์มินัลเอาต์พุตโดยใช้คลาส [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)"
item7: "กำหนดตัวเลือกการบันทึกโดยใช้คลาส [*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/)"
item8: "เรียกใช้งาน [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) วิธีการสำหรับ [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)"
item9: ปรับแต่งผลลัพธ์
---