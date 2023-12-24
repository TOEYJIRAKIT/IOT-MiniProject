# ชื่อโครงการ: ระบบแจ้งเตือนการเข้า-ออกโรงเรียน (Attendance System)
## สมาชิกในกลุ่ม
- 64102080 จิรกิตติ์ เอียดเหตุ 
- 64110455 ภัครศักดิ์ ผลสนอง 
- 64125735 ธนวัฒน์ กองสีสังข์
## บทนำ
<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ยุคที่เรามีเทคโนโลยีที่เข้ามามีบทบาทในทุกๆ ด้านของชีวิต เทคโนโลยี IoT (Internet of Things) ไม่เพียงเป็นเพียงเครื่องมือที่ทำให้เรามีความสะดวกในการใช้ชีวิตประจำวัน แต่ยังเป็นแหล่งข้อมูลที่มีประโยชน์ในการพัฒนาและปรับปรุงสถานะต่างๆ ในสังคม ในที่นี้ เราจะพูดถึงระบบแจ้งเตือนการเข้า-ออกโรงเรียน (Attendance System) ที่ใช้เทคโนโลยี RFID ร่วมกับ Arduino ซึ่งเป็นตัวช่วยในการบันทึกและตรวจสอบข้อมูลของนักเรียนในโรงเรียนอย่างมีประสิทธิภาพ การรักษาความปลอดภัยและการจัดการนักเรียนในโรงเรียนเป็นเรื่องสำคัญที่ต้องใส่ใจอย่างยิ่ง เพื่อให้การเรียนการสอนเป็นไปอย่างมีประสิทธิภาพ ระบบแจ้งเตือนการเข้า-ออกที่ใช้ RFID จึงเข้ามาเป็นส่วนหนึ่งที่มีความสำคัญในการทำให้การบันทึกและติดตามข้อมูลของนักเรียนเป็นไปอย่างรวดเร็วและแม่นยำ
<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;การจัดการข้อมูลการเข้า-ออกของนักเรียนโดยใช้ระบบแบบดั้งเดิมมักพบปัญหาในเรื่องของความแม่นยำและความทันสมัย เช่น การใช้กระดาษที่สามารถสูญหายได้ง่าย หรือการทำงานที่ล่าช้า เพื่อแก้ไขปัญหานี้ ทางกลุ่มผู้จัดทำจึงมุ่งเน้นในการผลิตอุปกรณ์ IoT ที่สามารถเช็คสถานะการเข้า-ออกโรงเรียนของนักเรียน เพื่อช่วยในการจัดการและปรับปรุงกระบวนการทำงานของโรงเรียน
<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;โครงการนี้มุ่งเน้นในการพัฒนาระบบแจ้งเตือนการเข้า-ออกโรงเรียนที่ใช้เซนเซอร์ RFID ร่วมกับ Arduino เพื่อเพิ่มประสิทธิภาพในการบันทึกข้อมูลและสร้างระบบแจ้งเตือนที่ทันสมัย แสดงผลข้อมูลการเข้า-ออกต่างๆบนเว็บไซต์และมีการแจ้งเตือนผ่านระบบ LINE ไปยังผู้ปกครองโดยมีข้อมูลต่างๆ เช่น ชื่อ-สกุล, รหัสนักศึกษา เวลา สถานะเข้า-ออก เป็นต้น
<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;วัตถุประสงค์ของโครงการนี้มีดังต่อไปนี้ 1) สร้างตารางเก็บบันทึกข้อมูลการเข้า-ออกโรงเรียนของนักเรียนแสดงผลบนเว็บไซด์ได้ 2) สร้างระบบแจ้งเตือนการเข้า-ออกโรงเรียนของนักเรียนส่งไปยังผู้ปกครองผ่านระบบ LINE Notify ได้
## การออกแบบระบบ
### Data Stucture
โครงสร้างข้อมูลถูกเก็บด้วย JSON โดยประกอบด้วยข้อมูลดังนี้ uid , studentid , firstname , lastname , position , timestamp , status , id  ดังตัวอย่างตามลำดับ ที่ถูกจัดเก็บใน Module ชื่อ users 
#### โครงสร้างข้อมูล :
```json
{
  "users": [
    {
      "uid": "2",
      "studentid": "64125735",
      "firstname": "ธนวัฒน์",
      "lastname": "กองสีสังข์",
      "position": "นักศึกษา",
      "timestamp": "20:15:40",
      "status": "เข้า",
      "id": 1
    },
    {
      "uid": "2",
      "studentid": "64102080",
      "firstname": "จิรกิตติ์",
      "lastname": "เอียดเหตุ",
      "position": "นักศึกษา",
      "timestamp": "20:15:43",
      "status": "ออก",
      "id": 2
    }
  ]
}
```
### Data Dictionary
## การพัฒนาระบบ
## การทดสอบ
## สรุปผลการทดสอบ
