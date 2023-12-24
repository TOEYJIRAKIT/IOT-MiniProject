# ชื่อโครงการ: ระบบแจ้งเตือนการเข้า-ออกโรงเรียน (Attendance System)
## Link to youtube
[ระบบแจ้งเตือนการเข้า-ออกโรงเรียน (Attendance System)]()
## สมาชิกในกลุ่ม
- 64102080 จิรกิตติ์ เอียดเหตุ 
- 64110455 ภัครศักดิ์ ผลสนอง 
- 64125735 ธนวัฒน์ กองสีสังข์
## บทนำ
<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ยุคที่เรามีเทคโนโลยีที่เข้ามามีบทบาทในทุกๆ ด้านของชีวิต เทคโนโลยี IoT (Internet of Things) ไม่เพียงเป็นเพียงเครื่องมือที่ทำให้เรามีความสะดวกในการใช้ชีวิตประจำวัน แต่ยังเป็นแหล่งข้อมูลที่มีประโยชน์ในการพัฒนาและปรับปรุงสถานะต่างๆ ในสังคม ในที่นี้ เราจะพูดถึงระบบแจ้งเตือนการเข้า-ออกโรงเรียน (Attendance System) ที่ใช้เทคโนโลยี RFID ร่วมกับ Arduino ซึ่งเป็นตัวช่วยในการบันทึกและตรวจสอบข้อมูลของนักเรียนในโรงเรียนอย่างมีประสิทธิภาพ การรักษาความปลอดภัยและการจัดการนักเรียนในโรงเรียนเป็นเรื่องสำคัญที่ต้องใส่ใจอย่างยิ่ง เพื่อให้การเรียนการสอนเป็นไปอย่างมีประสิทธิภาพ ระบบแจ้งเตือนการเข้า-ออกที่ใช้ RFID จึงเข้ามาเป็นส่วนหนึ่งที่มีความสำคัญในการทำให้การบันทึกและติดตามข้อมูลของนักเรียนเป็นไปอย่างรวดเร็วและแม่นยำ
<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;การจัดการข้อมูลการเข้า-ออกของนักเรียนโดยใช้ระบบแบบดั้งเดิมมักพบปัญหาในเรื่องของความแม่นยำและความทันสมัย เช่น การใช้กระดาษที่สามารถสูญหายได้ง่าย ปัญหาผู้ปกครองไม่ทราบว่าลูกหลานมาเรียนจริงหรือไม่ หรือการทำงานที่ล่าช้าของระบบแบบเก่า เพื่อแก้ไขปัญหานี้ ทางกลุ่มผู้จัดทำจึงมุ่งเน้นในการผลิตอุปกรณ์ IoT ที่สามารถเช็คสถานะการเข้า-ออกโรงเรียนของนักเรียน เพื่อช่วยในการจัดการและปรับปรุงกระบวนการทำงานของโรงเรียน
<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;โครงการนี้มุ่งเน้นในการพัฒนาระบบแจ้งเตือนการเข้า-ออกโรงเรียนที่ใช้เซนเซอร์ RFID ร่วมกับ Arduino เพื่อเพิ่มประสิทธิภาพในการบันทึกข้อมูลและสร้างระบบแจ้งเตือนที่ทันสมัย แสดงผลข้อมูลการเข้า-ออกต่างๆบนเว็บไซต์และมีการแจ้งเตือนผ่านระบบ LINE ไปยังผู้ปกครองโดยมีข้อมูลต่างๆ เช่น ชื่อ-สกุล, รหัสนักศึกษา เวลา สถานะเข้า-ออก เป็นต้น
<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;วัตถุประสงค์ของโครงการนี้มีดังต่อไปนี้ 1) สร้างตารางเก็บบันทึกข้อมูลการเข้า-ออกโรงเรียนของนักเรียนแสดงผลบนเว็บไซด์ได้ 2) สร้างระบบแจ้งเตือนการเข้า-ออกโรงเรียนของนักเรียนส่งไปยังผู้ปกครองผ่านระบบ LINE Notify ได้
## การออกแบบระบบ

แสดงสถาปัตยกรรระบบ (Systems Architecture)
![image](https://github.com/TOEYJIRAKIT/IOT-MiniProject/assets/110581279/7c9e642d-8419-4730-a407-67cfb7a40a49)


แสดงสถาปัตยกรรมซอฟต์แวร์ (Software Architecture)
![image](https://github.com/TOEYJIRAKIT/IOT-MiniProject/assets/110581279/da251ea8-d665-45d7-be86-467cf74235ce)


### Data Stucture
โครงสร้างข้อมูลถูกเก็บด้วย JSON โดยประกอบด้วยข้อมูลดังนี้ uid , studentid , firstname , lastname , position , timestamp , status, id ดังตัวอย่างตามลำดับ ที่ถูกจัดเก็บใน Module ชื่อ users 
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
      "uid": "3",
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
| Attribute | Description | Data Type | Example |
|--------------------|--------------------|--------------------|--------------------|
| uid  |  รหัสประจำผู้ใช้งาน  | String   | 2   |
| studentid  |รหัสนักเรียน  | String   | 64125735 |   
| firstname  | ชื่อ  | String   | ธนวัฒน์   |
| lastname  |  นามสกุล  | String   | กองสีสังข์   |
| position  |ตำแหน่ง  | String   | นักศึกษา   |
| timestamp  | เวลา  | String   | 20:15:43   |
| status  | สถานะ  | String   | เข้า   |
| id  | รหัสลำดับผู้ใช้  | int   | 1   |
## การพัฒนาระบบ
### เครื่องมือ
- Arduino UNO+WiFi R3 ATmega328P+ESP8266 Web Server Wifi ใช้สำหรับอ่านค่า Sensor และติดตั้งอุปกรณ์ 
- RFID Sensor ทำหน้าที่เป็นตัวอ่านบัตรที่สแกนเข้ามา 
- OLED Display ใช้สำหรับแสดงข้อมูลส่วนตัวของผู้สแกนบัตร
- Jumper Wire สายไฟใช้สำหรับเชื่อมต่อ Sensor เข้ากับตัวบอร์ด
- Key Tag สำหรับแสกนเพื่อส่งข้อมูลบัตรไปยัง Sensor แสกน
### ภาษาโปรแกรม 
- ภาษา C ใช้สำหรับเขียนคำสั่งลงไปยังบอร์ดเพื่อที่จะสามารถรับค่าและส่งค่าข้อมูลได้
- Json ทำหน้าที่เป็น Json Server เพื่อเก็บข้อมูลและส่งข้อมูลไปยังหน้าเว็บ 
- JavaScript ทำหน้าเป็นตัวดึงข้อมูลจาก Json Server เพื่อแสดงข้อมูลที่มีการเก็บบน Json Server มาแสดงบนหน้าเว็บ
- HTML ใช้สำหรับการพัฒนาหน้าเว็บ และเพื่อตบแต่งความสวยงานของหน้าเว็บและแสดงข้อมูลที่มีการดึงมาโดย JavaScript
### ไลบรารี
- SPI.h: ไลบรารีสำหรับการสื่อสารผ่าน Serial Peripheral Interface (SPI) ซึ่งใช้ในการเชื่อมต่อกับอุปกรณ์อื่น ๆ ที่รองรับ SPI เช่น จอ OLED
- Wire.h: ไลบรารีสำหรับการสื่อสารผ่าน I2C (Inter-Integrated Circuit) ซึ่งใช้ในการเชื่อมต่อกับอุปกรณ์ I2C อื่น ๆ เช่น ม็อดูล RFID
- Adafruit_GFX.h: ไลบรารีนี้เป็นไลบรารีที่สร้างขึ้นมาเพื่อให้การเขียนกราฟิกบนจอ LCD หรือ OLED ง่ายขึ้น โดยมีคลาสพื้นฐานสำหรับการวาดรูปแบบต่าง ๆ บนจอ
- Adafruit_SSD1306.h: ไลบรารีนี้เป็นไลบรารีสำหรับจอ OLED ที่ใช้ควบคุมด้วยชิพ SSD1306 ซึ่งจะทำให้คุณสามารถสร้างและแสดงข้อมูลต่าง ๆ บนจอ OLED
- MFRC522.h: ไลบรารีสำหรับการใช้งาน RFID (Radio-Frequency Identification) โดยใช้ชิพ MFRC522 ซึ่งสามารถอ่านข้อมูลจาก RFID card หรือ tag
- ESP8266WiFi.h: ไลบรารีสำหรับการเชื่อมต่อ WiFi ใน ESP8266
- NTPClient.h: ไลบรารีสำหรับการซิงค์เวลาจาก NTP (Network Time Protocol) server
- WiFiUdp.h: ไลบรารีสำหรับการใช้งาน UDP ในการเชื่อมต่อ WiFi
- PubSubClient.h: ไลบรารีสำหรับการเข้ารหัสและส่งข้อมูลผ่าน MQTT (Message Queuing Telemetry Transport) protocol
- TridentTD_LineNotify.h: ไลบรารีสำหรับการส่งข้อความผ่าน Line Notify API
## การทดสอบ
### สถานการณ์ 1 ทดสอบการสแกนบัตรผ่าน RFID ด้วยบัตรที่มีข้อมูลในระบบ 
- ตัวแปรต้น: บัตรที่เคยมีการบันทึกข้อมูลผู้ใช้
- ตัวแปรตาม: ผลลัพธ์การอ่านค่าและการแสดงผลข้อมูล
- ตัวแปรควบคุม: โค้ดสำหรับการอ่านบัตรผ่าน RFID Sensor, OLED Display, Key tag
- ผลการทดลอง: ![411950731_1278126119679940_1025604557624947419_n](https://github.com/TOEYJIRAKIT/IOT-MiniProject/assets/110581279/937fa408-c1ff-4490-8df2-835b1f327a6c)

### สถานการณ์ 2 ทดสอบการสแกนบัตรผ่าน RFID ด้วยบัตรที่ไม่มีข้อมูลในระบบ 
- ตัวแปรต้น: บัตรที่ไม่เคยมีการบันทึกข้อมูลผู้ใช้
- ตัวแปรตาม: ผลลัพธ์การอ่านค่าและการแสดงผลข้อมูล
- ตัวแปรควบคุม: โค้ดสำหรับการอ่านบัตรผ่าน RFID Sensor, OLED Display, Key tag
- ผลการทดลอง: ![409711670_725107342563807_3125771315398492763_n](https://github.com/TOEYJIRAKIT/IOT-MiniProject/assets/110581279/c837699d-fabb-4724-983b-86ad8e897e8e)


## สรุปผลการทดสอบ
สรุปได้ว่าโครงงานนี้สามารถตอบโจทย์วัตถุประสงค์ได้ คือ 1) สามารถสร้างตารางเก็บบันทึกข้อมูลการเข้า-ออกโรงเรียนของนักเรียนแสดงผลบนเว็บไซด์ได้ 2) สามารถสร้างระบบแจ้งเตือนการเข้า-ออกโรงเรียนของนักเรียนส่งไปยังผู้ปกครองผ่านระบบ LINE Notify ได้ตามจุดมุ่งหมายที่วางไว้
