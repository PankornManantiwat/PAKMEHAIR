# PAKMEHAIR — ร้านค้าออนไลน์ตัวอย่าง

เว็บไซต์ร้านขายแชมพูสำหรับงานเรียน มีสินค้า 3 SKUs, ตะกร้าสินค้า, ฟอร์มข้อมูลผู้รับ, สรุปคำสั่งซื้อ และพิมพ์ใบจัดสินค้า/ใบปะหน้าพัสดุ

## โครงสร้างไฟล์
- `index.html` หน้าเว็บไซต์
- `styles.css` รูปแบบและการแสดงผลมือถือ
- `app.js` ข้อมูลสินค้า ตะกร้า Checkout และใบจัดสินค้า
- `products.csv` แม่แบบข้อมูลสำหรับ Google Sheets
- `assets/products/` โฟลเดอร์รูปสินค้าแยกต่างหาก

## ทดลองใช้งาน
เปิด `index.html` ในเบราว์เซอร์ หรือเปิดโฟลเดอร์นี้ด้วย VS Code แล้วใช้ Live Server

## เชื่อม Google Sheets
1. สร้าง Google Sheets แล้วนำข้อมูลจาก `products.csv` ไปวาง
2. ใช้หัวคอลัมน์ตามนี้: `sku,name,type,description,price,stock,image`
3. ใน Google Sheets เลือก File > Share > Publish to web
4. เลือกชีตที่เก็บสินค้า และรูปแบบ Comma-separated values (.csv) แล้ว Publish
5. คัดลอก URL CSV
6. เปิด `app.js` แล้วใส่ URL ในบรรทัด `const GOOGLE_SHEET_CSV_URL = "";`
7. บันทึกและอัปโหลดไฟล์ขึ้น GitHub ใหม่

หมายเหตุ: หากตั้งค่าเป็น Anyone with the link หรือ Publish to web ข้อมูลในชีตจะถูกเปิดเผยต่อสาธารณะ ห้ามใส่ข้อมูลลูกค้าหรือข้อมูลลับในชีตนี้

## อัปโหลด GitHub
1. เข้า https://github.com แล้วสร้าง New repository เช่น `botane-shampoo-store`
2. ตั้งเป็น Public (สะดวกต่อการส่งงาน) แล้ว Create repository
3. กด Add file > Upload files
4. อัปโหลดไฟล์และโฟลเดอร์ทั้งหมดในโปรเจกต์นี้ โดยคงโครงสร้างเดิม
5. กด Commit changes

## Deploy ด้วย Vercel
1. เข้า https://vercel.com แล้ว Sign up / Log in ด้วย GitHub
2. กด Add New > Project
3. Import repository `botane-shampoo-store`
4. Framework Preset เลือก Other
5. Build Command และ Output Directory ปล่อยว่างได้ (เป็นเว็บ Static)
6. กด Deploy แล้วรอจนเสร็จ
7. เปิดโดเมน `.vercel.app` ที่ Vercel แสดงให้

## ข้อจำกัดของเดโมนี้
- คำสั่งซื้อและตะกร้าถูกเก็บในเบราว์เซอร์ของผู้ใช้เท่านั้น ไม่ได้ส่งเข้า Google Sheets หรือระบบหลังบ้าน
- ไม่มีระบบตัดเงินจริง/ชำระเงินออนไลน์ และไม่มีการสร้างเลข Tracking จากบริษัทขนส่ง
- ใบจัดสินค้า/ใบปะหน้าพัสดุเป็นเอกสารตัวอย่าง กรอกข้อมูลผู้รับจากฟอร์มและสั่งพิมพ์ได้
- การตัดสต็อกจริงและบันทึกออเดอร์หลายผู้ใช้ต้องเพิ่ม Backend/API และฐานข้อมูลที่ปลอดภัย
