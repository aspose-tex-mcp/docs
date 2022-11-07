---
translation: true
template: /_templates/_load-tex-from-disk-net.md
title: กำลังโหลด TeX จากดิสก์ | .NET API โซลูชั่น
url: /net/load-tex-from-disk/
description: ".NET API โซลูชันเพื่อทำงานกับ TeX เรียนรู้เกี่ยวกับตัวอย่างวิธีโหลดไฟล์ TeX จากดิสก์ด้วยโค้ด C# สองสามบรรทัด"
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: โหลดไฟล์ต้นทาง TeX จากดิสก์
h2: ".NET API Solution เพื่อโหลดไฟล์ TeX/LaTeX จากดิสก์"
---

{{<section overview>}}
---
p1: "TeX เรียกว่าภาษาเรียงพิมพ์ หมายความว่าคุณไม่ได้จัดรูปแบบข้อความของคุณในเอกสาร แต่ป้อนข้อความธรรมดาพร้อมกับคำสั่ง คุณจะได้รับไฟล์ที่จัดรูปแบบตามรูปแบบที่ต้องการ (ระบุ) [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) เป็นแกนกลางของระบบชุดสิ่งพิมพ์ (การเรียงพิมพ์ด้วยคอมพิวเตอร์) งาน TeX ทำงานบนไฟล์ TeX ที่ระบุอย่างชัดเจน เพื่อให้เข้าใจ TeX input และ output มากขึ้น ให้เรียนรู้ [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) ของเอกสารประกอบ"
p2: "อย่างที่ทราบกันดีว่าจุดประสงค์หลักของ TeX คือการช่วยสร้างการเขียนข้อความทางคณิตศาสตร์หรือทางเทคนิค แต่ก่อนที่จะทำการปรับเปลี่ยนใด ๆ ไฟล์ควรถูกโหลดก่อน ที่นี่คุณจะพบข้อมูลโค้ดที่อธิบายวิธีโหลดไฟล์ต้นทาง TeX จากดิสก์โดยใช้ไดเร็กทอรีระบบไฟล์สำหรับอินพุตและเอาต์พุต เอาต์พุตไปยังอุปกรณ์ XPS การเขียนเอาต์พุตเทอร์มินัลไปยังคอนโซล"
p3: "ในการรันตัวอย่างเราต้องการ:"
p4: "Aspose.TeX สำหรับ .NET API ซึ่งเป็น API การจัดการและการแปลงเอกสารที่มีคุณลักษณะหลากหลาย มีประสิทธิภาพ และใช้งานง่ายสำหรับแพลตฟอร์ม C#"
p5: "เปิดตัวจัดการแพ็คเกจ NuGet และค้นหา Aspose.TeX และติดตั้ง คุณสามารถใช้คำสั่งต่อไปนี้จาก Package Manager Console"
---

{{<section feature1>}}
---
title: ขั้นตอนในการโหลด TeX จากดิสก์ C#
h3: "รหัส C# สำหรับการโหลด TeX"
item1: "สร้างตัวเลือกการแปลงสำหรับรูปแบบที่กำหนดเองตามส่วนขยายเอ็นจิน ObjectTeX โดยใช้ [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) วิธีการของ [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) คลาส"
item2: "ระบุไดเร็กทอรีการทำงานของระบบไฟล์สำหรับอินพุต ใช้คลาส [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) สำหรับสิ่งนี้"
item3: "ระบุไดเร็กทอรีการทำงานของระบบไฟล์สำหรับเอาต์พุตโดยใช้คลาส [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)"
item4: "ระบุคอนโซลเป็นเทอร์มินัลเอาต์พุตโดยใช้คลาส [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)"
item5: "ระบุเทอร์มินัลหน่วยความจำเป็นเทอร์มินัลเอาต์พุต หากคุณต้องการ สำหรับการใช้งานนี้ [*OutputMemoryTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputmemoryterminal/) คลาส"
item6: "เรียกใช้งาน [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) วิธีการสำหรับ [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)"
item7: ปรับแต่งผลลัพธ์
---