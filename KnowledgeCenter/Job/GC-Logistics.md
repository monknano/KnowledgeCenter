
บันทึกการขอแก้ไขโปรแกรมตามประชุมร่วม 21 ส.ค. 62
===
# Goods Control List
- Tranfer type ข้อ 2 และ 10 ต้องการแก้ไข format ชื่อไฟล์ที่ export จากระบบ
- เพิ่มการให้ช่วยหาช่องว่าง ๆ เพิ่มเติมสำหรับใส่ code ขนส่ง
- GC แจ้งว่า Port ปลายทางที่ระบุในใบขนสินค้า ไม่นำไปใช้เมื่อสร้างใบกำกับ
- หน่วยของ VGM + Authorized ต้องการให้มีค่า default เพื่อไม่ต้องมาใส่ทุกครั้ง ( คุณนุชแจ้งว่า หลักของ VGM ต้องบันทึกเป็น KGM เท่านั้น)
- ให้ ECS ช่วยตรวจสอบ และแก้ไขโปรแกรมเพื่อทดสอบว่า การเปิดโปรแกรมช้าเกี่ยวข้องการการ scale หน้าจอหรือไม่
- ให้มี report Counter Service ในส่วนของ Goods + Short

# Declaration
- ต้องการให้มีการระบุ Payment term ในโปรแกรมเพิ่มเติมได้ 
	- ECS แจ้งว่าจะดึงจากข้อมูลใบขนเก่า ๆ เมื่อ user แจ้งว่าไม่ขึ้น ทางโปรมเมอร์แจ้งให้ขอตัวอย่าง zip ไฟล์เพื่อตรวจสอบ
- เพิ่มรูปแบบ file text เพิ่มเติมจากที่มีอยู่ให้ import เข้าโปรแกรม ตรง create flat file เพื่อให้ได้ข้อมูลตรงส่วนของใบขนที่เดิมไม่ได้มีการ import (Declaration Header)

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5MDgxMjk3ODQsLTgwNDk1ODIzNCwxMz
g5NjQ5NDA4LDE0NDk0MzI2MjNdfQ==
-->