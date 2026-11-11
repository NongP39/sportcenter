# แผนที่กีฬา ลาดกระบัง

หน้าเว็บแผนที่อินเทอร์แอคทีฟแสดงสนามกีฬา ยิม และบริการเสริมรอบที่ดิน 14 ไร่ (ลาดกระบัง กรุงเทพฯ)

| ไฟล์ | คืออะไร | ต้องใช้คีย์ |
|---|---|---|
| `index.html` | แผนที่ภาพดาวเทียม Esri ที่ฝังไว้ในโฟลเดอร์ `sat/` ใช้ได้ทันที | ไม่ต้อง |
| `google.html` | แผนที่ Google Maps จริง: ภาพดาวเทียม Google, ช่องค้นหาสถานที่แบบ Google Maps, มุมเอียง 3 มิติ, Street View | ต้องมี Google Maps API key |

## วิธีเปิดใช้ google.html

1. เข้า https://console.cloud.google.com แล้วสร้างโปรเจกต์ใหม่
2. ผูกบัญชีชำระเงิน (Billing) กับโปรเจกต์ Google ให้โควตาใช้ฟรีรายเดือนตามประเภทบริการ ถ้าใช้เกินจะคิดเงิน ควรตั้ง Budget alert ไว้
3. เมนู APIs & Services > Library เปิดใช้ 2 ตัว: **Maps JavaScript API** และ **Places API (New)**
4. APIs & Services > Credentials > Create credentials > API key
5. กด Edit API key แล้วจำกัดการใช้งาน:
   - Application restrictions: HTTP referrers ใส่ `https://<ชื่อผู้ใช้ GitHub>.github.io/*`
   - API restrictions: เลือกเฉพาะ 2 API ข้างบน
6. เปิดไฟล์ `google.html` แก้บรรทัดแรกของสคริปต์ให้เป็น
   `const GOOGLE_MAPS_API_KEY='คีย์ที่ได้';`
7. Commit แล้วเปิด `https://<ชื่อผู้ใช้>.github.io/<ชื่อ repo>/google.html`

คีย์ฝั่งหน้าเว็บมองเห็นได้เสมอ การจำกัดโดเมนในข้อ 5 คือสิ่งที่กันคนอื่นเอาไปใช้

## เผยแพร่ด้วย GitHub Pages

Settings > Pages > Deploy from a branch > `main` / `(root)` > Save

## เครดิต

- ภาพดาวเทียมใน `sat/`: Esri World Imagery (Maxar, Earthstar Geographics, ผู้ร่วมจัดทำ)
- ข้อมูลสถานที่: Google Places และเว็บไซต์ของสถานที่ ณ พ.ย. 2569
- เส้นเขตอำเภอ: chingchai/OpenGISData-Thailand
