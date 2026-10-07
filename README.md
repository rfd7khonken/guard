📅 คู่มือการติดตั้งและใช้งานระบบจัดตารางเวรอัตโนมัติ (Fair Duty Rota & LINE Notify)

ระบบจัดการและจัดตารางเวรอัตโนมัติรูปแบบ Single Page Application (SPA) สำหรับสมาชิก 7 คน พร้อมระบบแจ้งเตือนผ่าน LINE Messaging API และซิงค์ข้อมูลกับ Google Sheets Database

🌟 คุณสมบัติเด่นของระบบ

🚫 กฎเหล็กไม่ซ้ำวันในสัปดาห์ (Weekly Uniqueness Constraint):

ใน 1 สัปดาห์ (อาทิตย์ - เสาร์) สมาชิกแต่ละคนจะได้รับเวร ไม่เกิน 1 ครั้ง (1 คนต่อ 1 วันในสัปดาห์นั้น)

กระจายเวรให้อัตโนมัติเท่ากันทุกเดือน (Equal Distribution 100%)

ป้องกันการเข้าเวรติดกัน 2 วันข้ามสัปดาห์หรือข้ามเดือน

📱 Pop-up (Modal) เวรประจำวัน:

คลิกวันใดก็ได้ในปฏิทินเพื่อเปิด Pop-up รายละเอียดเวรประจำวัน

สามารถสลับเปลี่ยนตัวผู้เข้าเวรเฉพาะวันนั้นๆ ได้ทันที (Manual Override)

มีปุ่ม "ส่งเตือนวันเข้าเวรนี้เข้า LINE" ใน Pop-up

📲 LINE Messaging API Integration:

ส่งการแจ้งเตือนตารางเวรประจำวันและสรุปเวรทั้งเดือนเข้า LINE Official Account / LINE Group ในรูปแบบ Flex Message สวยงาม

💾 Dual Storage:

ทำงานได้ทันทีแบบ Off-line ผ่าน LocalStorage

ซิงค์ข้อมูลขึ้น Google Sheets Database ผ่าน Google Apps Script

🚀 ขั้นตอนการนำขึ้น GitHub Pages

สร้าง GitHub Repository:

ไปที่ GitHub ➔ กดสร้าง Repository ใหม่ (ตั้งชื่อเช่น duty-rota-app)

อัปโหลดไฟล์:

นำไฟล์ index.html และ README.md อัปโหลดขึ้นสู่ Repository

เปิดใช้งาน GitHub Pages:

ไปที่เมนู Settings ➔ Pages

ตรงหัวข้อ Source เลือก Branch เป็น main (หรือ master) แล้วกด Save

รอระบบ Build ประมาณ 1-2 นาที จะได้ URL เช่น https://your-username.github.io/duty-rota-app/

🔌 ขั้นตอนติดตั้ง Google Apps Script (GAS) API & LINE Automate

สร้าง Google Sheet:

เปิด Google Sheets สร้างชีตใหม่

เปิดหน้าเขียนโค้ด:

ไปที่เมนู ส่วนขยาย (Extensions) ➔ Apps Script

วางโค้ด GAS:

เปิดหน้าเว็บระบบตารางเวร ➔ ไปที่แท็บ ตั้งค่า & LINE / GAS ➔ กดปุ่ม "คัดลอกโค้ด Google Apps Script (GAS)"

นำโค้ดไปวางในหน้า Apps Script

ตั้งค่า LINE Token ใน Apps Script:

แก้ไขตัวแปร LINE_TOKEN และ TARGET_ID ด้านบนสุดของโค้ด GAS

Deploy เป็น Web App:

กด Deploy (การทำให้ใช้งานได้) ➔ New Deployment (การทำให้ใช้งานได้ใหม่)

เลือกประเภทเป็น Web App

Execute as: Me (ฉัน)

Who has access: Anyone (ทุกคน)

กด Deploy แล้วคัดลอก Web App URL มาใส่ในหน้าตั้งค่าของเว็บ

ตั้งเวลาแจ้งเตือนอัตโนมัติ 06:00 น. ทุกเช้า:

ในหน้า Apps Script คลิกไอคอน นาฬิกา (Triggers / ตัวกระตุ้น) ทางซ้ายมือ

กด Add Trigger (เพิ่มตัวกระตุ้น)

เลือกฟังก์ชั่น sendDailyLineNotification

เลือกแหล่งเหตุการณ์: Time-driven (ตามเวลา) ➔ Day timer (ตัวนับเวลาวัน) ➔ เลือกช่วงเวลา 06:00 - 07:00 น. แล้วกด
