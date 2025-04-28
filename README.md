# ESP32 OLED I2C Day/Night Animation Display 🌞🌙

แสดง **Animation กลางวัน-กลางคืน** พร้อม **วัน/เดือน/ปี เวลา** บนจอ **OLED I2C** โดยดึงเวลาจากอินเทอร์เน็ต (NTP) ประเทศไทย 🇹🇭

---

## ✨ คุณสมบัติ

- แสดง Animation กลางวัน และ กลางคืน อัตโนมัติตามเวลาจริง
- แสดง วัน/เดือน/ปี และ เวลา แบบ Real-time
- อัปเดตเวลาโดยใช้ NTP Server (เวลาไทย UTC+7)
- รองรับขนาดภาพ 32x32, 64x64 หรือกำหนดเองได้
- ออกแบบเต็มจอ และแบ่งสัดส่วนสวยงาม (80% Animation / 20% เวลา)

---

## 🛠 ใช้อุปกรณ์อะไรบ้าง?

- **ESP32 Dev Board** (เช่น DOIT ESP32 DEVKIT V1)
- **OLED Display I2C** (SSD1306) ขนาด 128x64 พิกเซล
- สาย Jumper

---

## 🔌 การต่อสาย ESP32 ↔ OLED

| OLED Pin | ต่อกับ ESP32 Pin |
|:--------:|:----------------:|
| GND      | GND               |
| VCC      | 3V3 (หรือ 3.3V)   |
| SCL      | GPIO22 (SCL)       |
| SDA      | GPIO21 (SDA)       |

> 📌 หมายเหตุ: ถ้าใช้บอร์ดอื่น ดู Datasheet ว่า SCL/SDA อยู่ขาไหน

---

## 📚 ใช้ Library อะไรบ้าง?

ติดตั้งผ่าน **Library Manager** ของ Arduino IDE ได้เลย

- [`Adafruit_GFX`](https://github.com/adafruit/Adafruit-GFX-Library)
- [`Adafruit_SSD1306`](https://github.com/adafruit/Adafruit_SSD1306)
- [`NTPClient`](https://github.com/arduino-libraries/NTPClient)
- [`WiFi`](มากับ ESP32 โดยตรงแล้ว ไม่ต้องติดตั้งเพิ่ม)

---

## ⚙️ วิธีติดตั้งโปรเจกต์

1. เปิด **Arduino IDE**
2. ติดตั้ง Libraries ที่ระบุข้างบนให้ครบ
3. ไปที่ **Tools > Board > ESP32 Dev Module** (หรือรุ่นที่ใช้งาน)
4. กำหนด WiFi SSID และ Password ในโค้ด:
    ```cpp
    const char* ssid = "YOUR_WIFI_SSID";
    const char* password = "YOUR_WIFI_PASSWORD";
    ```
5. กำหนด Animation ไฟล์ (นำโค้ดจาก Wokwi Export มาวางใน `framesDay` และ `framesNight`)
6. อัปโหลดโค้ดไปยังบอร์ด ESP32

---

## 📸 ตัวอย่างหน้าจอ

> ![ESP32 Image](https://sumetee.pages.dev/Storage_web/esp32_N.png)

---

## ⚡️ ปัญหาที่อาจเจอ

- หากแสดง Animation เพี้ยน: ตรวจสอบให้แน่ใจว่า **FRAME_WIDTH/FRAME_HEIGHT ตรงกับขนาดรูปที่ Export**
- หากไม่เชื่อม WiFi: ตรวจสอบชื่อ WiFi และ Password
- หากขึ้น Upload error: กดปุ่ม "Boot" ที่ ESP32 ระหว่าง Upload

---

## 🧡 ขอบคุณ

- ภาพไอคอน: [icons8.com](https://icons8.com)
- เครื่องมือสร้าง Animation: [Wokwi Animator](https://wokwi.com/animator)

---
