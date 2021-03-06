คู่มือการติดตั้งโปรแกรม RDX Gateway Client
================
## ติดตั้งโปรแกรม RDX Gateway Client 
1. ติดตั้ง Microsoft SQL Server ManageMent Studio
2. Copy Floder ECS_RD ไว้ Drive C:\
3. ติดตั้ง Database ECS_DATA_RD ติดตั้ง Database จาก ECS_DATA_RD.bak โดยวิธีการ Restore Files and File Groups 
     > Destination to restore ระบุ To database เป็น “ECS_DATA_RD” 
     > From Device เลือกไฟล์ ECS_DATA_RD.bak ที่อยู่ใน Folder C:\ECS_RD\DATA
 
 4. Config groupdb.ini
 
 >  ![image](image)

>C:\ECS_RD\DATA\groupdb.ini แก้ไขข้อมูลชื่อบริษัท , Member Code และ ConnectionString ตามรูป

## ติดตั้ง  Certificate
###  ติดตั้ง Cert ประเภท TOKEN จาก TDID

1.  ติดตั้ง Driver Safenet ติดตั้ง Driver Safenet ที่ C:\ECS_RD\Utility\SafeNetAuthenticationClient-x64-8.0-SP2.msi หรือดาวน์โหลดได้ที่  http://www.thaidigitalid.com/hardware/
	
	- 	ขั้นตอนการตั้งค่าเริ่มต้น (Initialization) ให้กับ Token
		1. เสียบ Token   กับคอมพิวเตอร์ และเปิดโปรแกรม SafeNet Authentication Client Tools
		2. คลิกที่ปุ่ม **“Advanced View”**
		3. คลิกขวาที่ชื่อของ Token แล้วเลือก **“Initialize”**
		4. ตั้งค่าโปรแกรม
			- ใส่ชื่อ Token Name
			- ตั้ง Password
			- ตั้ง Administrator Password เพื่อใช้ในการปลดล็อคเมื่อ Token ถูกล็อค
			- เลือกลบเครื่องหมายถูกออก Token Password must be changed on first logon
			- กดปุ่ม Start
			- กด OK เพื่อยืนยันทำ Initial

	- ขั้นตอนการนำ Cert ใส่ Token ผู้ที่ซื้อ Cert Token จาก TDID จะได้ Email มีข้อความดังด้านล่าง จากหน่วยงานรับลงทะเบียน TDID


```javascript
เรียน ท่านผู้ขอใบรับรองอิเล็กทรอนิกส์

ตามที่ท่านได้ยื่นใบคำขอใบรับรองอิเล็กทรอนิกส์ (หมายเลขตามที่ปรากฏในตารางด้านล่าง) มายังบริษัท ไทยดิจิทัล ไอดี จำกัด (TDID).
เพื่อออกใบรับรองอิเล็กทรอนิกส์ให้แก่ท่านนั้น

ขณะนี้บริษัทฯ ได้พิจารณาใบคำขอของท่านแล้วเสร็จเรียบร้อยแล้ว และยินดีออกใบรับรองฯให้แก่ท่านตามคำขอดังกล่าว
โดยท่านสามารถรับใบรับรองฯของท่านได้ โดยเริ่มจากการดาวน์โหลดไฟล์โปรแกรม TDID KeySuite ที่ goo.gl/W3crxp.
เมื่อเรียบร้อยแล้วให้ unzip ไฟล์แล้วเปิดโปรแกรมด้วยการดับเบิ้ลคลิกที่ TDID KeySuite.exe

หลังจาก Login เข้าโปรแกรม TDID KeySuite ด้วยหมายเลขใบคำขอใบรับรองอิเล็กทรอนิกส์ (ตามที่ปรากฏในตารางด้านล่าง).
แล้วให้ท่านดำเนินการตามขั้นตอนดังต่อไปนี้

1. สร้างคู่กุญแจในอุปกรณ์และไฟล์ CSR
กดปุ่มเมนู 1 เพื่อสร้างคู่กุญแจ (Public & Private Key) พร้อมกับไฟล์ CSR (Certificate Signing Request). 
และบันทึก (Save) ไฟล์ CSR(ไฟล์นามสกุล .csr) ลงบนเครื่องคอมพิวเตอร์เก็บไว้ เพื่อใช้ในขั้นตอนที่ 2 ต่อไป

2. รับไฟล์ใบรับรองอิเล็กทรอนิกส์
กดปุ่มเมนู 2 เพื่อเข้าสู่เวบไซต์รับใบรับรองฯ( Web Certificate Enrollment)โดย Login 
ด้วยหมายเลขใบคำขอใบรับรองฯ และรหัสอนุมัติ.
 (ตามที่ปรากฏในตารางด้านล่าง) จากนั้นป้อนไฟล์ CSR ที่ได้จากขั้นตอนที่ 1 เพื่อบันทึก (Save)ไฟล์ใบรับรองฯของท่าน 
 (ไฟล์นามสกุล .crt)  ลงบนเครื่องคอมพิวเตอร์ เก็บไว้ เพื่อใช้ในขั้นตอนที่ 3 ต่อไป 
 (ใบรับรองฯจะเริ่มนับอายุจากเวลาที่ท่านดำเนินการตามขั้นตอนที่ 2 เสร็จสิ้น)

3. ติดตั้งใบรับรองฯในอุปกรณ์
กดปุ่มเมนู 3 เพื่อป้อนไฟล์ใบรับรองฯ(ไฟล์นามสกุล .crt) ที่ได้จากขั้นตอนที่ 2 เข้าโปรแกรม TDID KeySuite 
สำหรับนำใบรับรองฯติดตั้งลงในอุปกรณ์

หมายเลขใบคำขอใบรับรองอิเล็กทรอนิกส์
(Application ID)  NEW-06-3910-1-1-17-0001294

รหัสอนุมัติ
(Authorization Code)  NpFQi0GAOFXNBMm6pm4NYf5q5TU

หมายเหตุ : รหัสอนุมัติ(Authorization Code)ที่ออกให้นี้มีอายุการใช้งาน 60 วัน 
สามารถใช้งานได้ในระหว่างวันที่ 2017/07/31 - 2017/09/29 เท่านั้น

จึงเรียนมาเพื่อโปรดดำเนินการ

หน่วยงานรับลงทะเบียน
THAI DIGITAL ID COMPANY LIMITED
142 ชั้น4 อาคารธนาคารกสิกรไทย ถนนสีลม เขตบางรัก กรุงเทพ 10500
ra@thaidigitalid.com
(ขออภัยหากท่านได้รับจดหมายฉบับนี้ ขณะที่ได้ดำเนินการตามขั้นตอนทั้งหมดไปเรียบร้อยแล้ว)
```

1. ดาวน์โหลดไฟล์โปรแกรม TDID KeySuite ที่ goo.gl/W3crxp เมื่อเรียบร้อยแล้วให้ unzip ไฟล์แล้วเปิดโปรแกรมด้วยการดับเบิ้ลคลิกที่ TDID KeySuite.exe  ตามใน Email หรือเอาจาก [C:/ECS_RD/Utility](C:/ECS_RD/Utility)
2. ระบุหมายเลขใบคำขอที่ได้จาก Email ระบุลงไปตามรูป แล้วกดปุ่ม Login
3. **สร้างคู่กุญแจในอุปกรณ์และไฟล์ CSR** กดปุ่มเมนู 1 เพื่อสร้างคู่กุญแจ (Public & Private Key) พร้อมกับไฟล์ CSR (Certificate Signing Request) และบันทึก (Save) ไฟล์ CSR(ไฟล์นามสกุล .csr) ลงบนเครื่องคอมพิวเตอร์เก็บไว้ เพื่อใช้ในขั้นตอนที่ 2 ต่อไป
4. **รับไฟล์ใบรับรองอิเล็กทรอนิกส์** กดปุ่มเมนู 2 เพื่อเข้าสู่เวบไซต์รับใบรับรองฯ( Web Certificate Enrollment)โดย Login ด้วยหมายเลขใบคำขอใบรับรองฯและรหัสอนุมัติ (ตามที่ปรากฏในตารางด้านล่าง) จากนั้นป้อนไฟล์ CSR ที่ได้จากขั้นตอนที่ 1 เพื่อบันทึก (Save)ไฟล์ใบรับรองฯของท่าน (ไฟล์นามสกุล .crt) ลงบนเครื่องคอมพิวเตอร์ เก็บไว้ เพื่อใช้ในขั้นตอนที่ 3 ต่อไป (ใบรับรองฯจะเริ่มนับอายุจากเวลาที่ท่านดำเนินการตามขั้นตอนที่ 2 เสร็จสิ้น)
5. **ติดตั้งใบรับรองฯในอุปกรณ์** กดปุ่มเมนู 3 เพื่อป้อนไฟล์ใบรับรองฯ(ไฟล์นามสกุล .crt) ที่ได้จากขั้นตอนที่ 2 เข้าโปรแกรม TDID KeySuite สำหรับนำใบรับรองฯติดตั้งลงในอุปกรณ์ 


### ติดตั้ง Cert ประเภท ไฟล์ P12

>เลือก Tab Config Setting > Tab Admin > Cer File Name > Cert Password > Save

## ติดตั้ง RDX Gateway WebService

1.  ติดตั้ง IIS

2.  Config  IIS เพิ่ม feature WCF Services (กรณีเครื่องที่ยังไม่มี)

>เข้าเมนู Control Panel > Programs > Turn Windows features on or off


3. Copy Floder AUTOSENDWCF ไว้ Drive C:\Inetpub\wwwroot
4. Config  Web.config แก้ไข CnnString ใน Web.config file
5. Config  WebService AUTOSENDWCF ใน IIS เข้าเมนู Control Panel > System and Security > Administrative Tools > Internet Information Service (IIS) Manager ได้ดังภาพ (Copy ShortCut IIS ไว้ที่หน้าจอ Desktop ด้วย)
6. Install SSL ลง IIS (https)

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyMTU3NjU1NTEsLTIwNzcyNzQzNzMsMT
MxOTM4MTMwOCwtMTY4NDMyNTEwMF19
-->