---
title: แก้ปัญหา WordPress module imagick not installed

date: 2022-06-12
tags: 
  - Wordpress

---

ในขณะที่ไล่เช็คความเรียบร้อยของเว็บดูอยู่นั้น ก็เห็นว่าตัว site health มันแจ้งมาว่า `imagick, is not installed, or has been disabled.` ก็เลยลองไปไล่หาวิธีแก้ โชคดีที่ว่าตอนนี้ใช้โฮส VPS กับ DigitalOcean อยู่ แล้วเค้ามีบอร์ดถามตอบเรื่องนี้อยู่พอดี สรุปได้คำตอบมาว่า…

```
sudo apt install php8.0-imagick
sudo service apache2 restart
```

รันคำสั่งปุ้บ หายปั้บ เรียบร้อยแจ่มแมว