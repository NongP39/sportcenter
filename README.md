# แผนที่กีฬา ลาดกระบัง

หน้าเว็บแผนที่ Google Maps แสดงสนามกีฬา ยิม และบริการเสริมรอบที่ดิน 14 ไร่ (ลาดกระบัง กรุงเทพฯ)
มีภาพดาวเทียมของ Google ช่องค้นหาสถานที่แบบ Google Maps มุมเอียง 3 มิติ Street View
ขอบเขตที่ดิน วงรัศมี 3/5/10/15/20 กม. และตัวกรองตามกีฬา ประเภท การคิดเงิน และระยะทาง

มีไฟล์เดียวคือ `index.html` (ข้อมูลสถานที่ 144 แห่งฝังอยู่ในไฟล์)

## ตั้งค่า Google Maps API key

1. เข้า https://console.cloud.google.com แล้วสร้างโปรเจกต์ใหม่
2. ผูกบัญชีชำระเงิน (Billing) กับโปรเจกต์ Google ให้โควตาฟรีรายเดือนตามประเภทบริการ ถ้าใช้เกินจะคิดเงิน ควรตั้ง Budget alert ไว้
3. เมนู APIs & Services > Library เปิดใช้ 2 ตัว: **Maps JavaScript API** และ **Places API (New)**
4. APIs & Services > Credentials > Create credentials > API key
5. กด Edit API key แล้วจำกัดการใช้งาน
   - Application restrictions: HTTP referrers ใส่ `https://<ชื่อผู้ใช้ GitHub>.github.io/*`
   - API restrictions: เลือกเฉพาะ 2 API ข้างบน
6. เปิด `index.html` แก้บรรทัดนี้ (อยู่ต้นสคริปต์) ให้ใส่คีย์
   `const GOOGLE_MAPS_API_KEY='คีย์ที่ได้';`

คีย์ฝั่งหน้าเว็บมองเห็นได้เสมอ การจำกัดโดเมนในข้อ 5 คือสิ่งที่กันคนอื่นเอาไปใช้

## เผยแพร่ด้วย GitHub Pages

Settings > Pages > Deploy from a branch > `main` / `(root)` > Save
ลิงก์จะเป็น `https://<ชื่อผู้ใช้>.github.io/<ชื่อ repo>/`

## ที่มาข้อมูล

ข้อมูลสถานที่: Google Places และเว็บไซต์ของสถานที่ ณ พ.ย. 2569
ระยะทางเป็นเส้นตรงจากที่ดิน ไม่ใช่ระยะขับรถ ประเภทสถานที่และกีฬาที่รองรับจัดจากชื่อและคำอธิบาย ไม่ได้ตรวจทีละแห่ง
