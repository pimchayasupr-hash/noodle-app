# ฮุ้ง ก๋วยเตี๋ยวกากหมูต้มยำ 🍜

## ไฟล์ที่มี
| ไฟล์ | ใช้งาน |
|------|--------|
| `index.html` | หน้าลูกค้าสั่งอาหาร |
| `seller.html` | หน้าเจ้าของร้าน (รับออเดอร์/ตรวจสลิป) |

---

## วิธี Push ขึ้น GitHub Pages (มีลิงก์เปิดบน iPhone/iPad ได้เลย)

### ขั้นตอนที่ 1 — สร้าง Repository บน GitHub
1. ไปที่ **github.com** → Login
2. กด **"New repository"** (ปุ่มเขียว)
3. ตั้งชื่อ: `hung-noodle` (หรืออะไรก็ได้)
4. เลือก **Public**
5. กด **"Create repository"**

### ขั้นตอนที่ 2 — อัปโหลดไฟล์
1. ในหน้า repository ที่เพิ่งสร้าง → กด **"uploading an existing file"**
2. ลาก `index.html` และ `seller.html` เข้าไป
3. กด **"Commit changes"**

### ขั้นตอนที่ 3 — เปิด GitHub Pages
1. ไปที่ **Settings** (แถบบนของ repo)
2. เมนูซ้าย → **Pages**
3. Source → เลือก **"Deploy from a branch"**
4. Branch → เลือก **main** → folder **/ (root)**
5. กด **Save**
6. รอ 1-2 นาที → จะได้ลิงก์แบบนี้:

```
https://[username].github.io/hung-noodle/
```

### ขั้นตอนที่ 4 — แชร์ลิงก์
| หน้า | ลิงก์ |
|------|-------|
| 📱 ลูกค้า | `https://[username].github.io/hung-noodle/index.html` |
| 🧑‍🍳 ร้าน | `https://[username].github.io/hung-noodle/seller.html` |

---

## Firebase Rules (ตั้งหลังทดสอบ)
ไปที่ Firebase Console → Realtime Database → Rules → เปลี่ยนเป็น:
```json
{
  "rules": {
    "orders": {
      ".read": true,
      ".write": true
    }
  }
}
```

---

## หมายเหตุ
- ร้านเปิด **08:00 – 14:00 น.** (ปรับได้ในไฟล์ index.html บรรทัด `const CLOSE_HOUR = 14`)
- สลิปเก็บใน localStorage ของลูกค้า (ไม่ขึ้น Firebase เพราะขนาดใหญ่)
- ถ้าลูกค้าและร้านอยู่คนละเครื่อง ร้านจะเห็นปุ่ม "ยืนยันโอนแล้ว" ให้กดเองได้

