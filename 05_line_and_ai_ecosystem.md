# 05. LINE Ecosystem & AI Financial Trust

## 1. Chat vs. LIFF Responsibility (การแบ่งหน้าที่)

ปัญหาที่พบบ่อยที่สุดในการออกแบบแอปบน LINE คือ **"พยายามยัดทุกอย่างไว้ในแชท"** หรือ **"พยายามสร้างแอปใหม่ทั้งก้อนใน LIFF"** 

จากการศึกษา 10 เคสที่ดีที่สุดใน ecosystem (เช่น Starbucks, Major Cineplex, PTT, SCB Connect) พบกฎทองคำคือ:

> **Chat is for Time-bound Triage. LIFF is for Space-bound Exploration.**
> (แชทเหมาะกับงานที่อิงกับเวลาและการตัดสินใจด่วน LIFF เหมาะกับงานที่ใช้พื้นที่และต้องการภาพรวม)

### สิ่งที่ควรทำใน LINE Chat (Messaging API)
*   **Data Ingestion:** ส่งรูปสลิป, พิมพ์ตัวเลข, อัปโหลดไฟล์ Statement
*   **Quick Confirmation:** "ยอด 500 บาท คือค่าอาหารใช่ไหม?" (ใช้ Quick Reply)
*   **Proactive Alerts:** "คุณกำลังจะใช้เงินเกินงบเดือนนี้แล้ว"
*   **Contextual Queries:** "เดือนนี้จ่ายค่าไฟไปหรือยัง?"

### สิ่งที่ควรทำใน LIFF
*   **Dashboard & Overview:** ดูกราฟวงกลม, ยอดเงินคงเหลือ, Cash flow
*   **Batch Operations:** หน้า Review Inbox เพื่อกด Confirm ทีละ 20 รายการ
*   **Complex Settings:** ตั้งค่า Budget, เพิ่มบัญชี
*   **Reconciliation:** หน้าจอเปรียบเทียบ Statement ธนาคาร กับ รายการที่จดไว้
*   **Historical Search:** เลื่อนดู Transaction ของเดือนที่แล้ว

---

## 2. LINE Interaction Responsibility Matrix

เพื่อนำไปออกแบบ MaewSom เราได้สร้าง Matrix แบ่งหน้าที่ของเครื่องมือแต่ละชิ้นใน LINE

| User Job (งานของผู้ใช้) | Chat | Quick Reply | Flex Message | Rich Menu | LIFF | เหตุผล (Why) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **บันทึกรายจ่ายด่วน** | **Primary** | - | - | - | - | เร็วที่สุด แค่พิมพ์หรือโยนสลิปลงไป |
| **ยืนยันหมวดหมู่ที่ AI สงสัย** | - | **Primary** | - | - | - | 1-Tap ไม่เปลืองพื้นที่แชท เมื่อกดแล้วหายไป |
| **ดูสรุปยอดหลังบันทึกเสร็จ** | - | - | **Primary** | - | - | สวยงาม ดูเป็นทางการ (Receipt format) และ Share ต่อได้ |
| **เปิดดู Dashboard รวม** | - | - | - | **Primary** | - | แตะปุ่มเดียวบนคีย์บอร์ดเพื่อเปิดทางเข้า |
| **แก้ไขรายการที่ผิด (หลายๆ รายการ)**| - | - | - | - | **Primary** | ต้องใช้พื้นที่หน้าจอ และต้องการ UI แบบ List/Swipe |
| **กระทบยอด Statement ปลายเดือน** | - | - | - | - | **Primary** | ซับซ้อนเกินกว่าจะทำใน Chat (ต้องเทียบทีละบรรทัด) |
| **แจ้งเตือนงบจะหมด** | **Primary** | - | - | - | - | เป็น Push Notification ที่ทรงพลังที่สุด |

---

## 3. Financial Trust UX Model for AI

AI จะถูกผู้ใช้เกลียดทันทีที่ตัวเลข "เงิน" ไม่ตรงกับความเป็นจริง เพื่อรักษาความน่าเชื่อถือ (Trust) MaewSom ต้องใช้ **Financial Trust UX Model**

### The 4 Pillars of AI Trust in MaewSom:

1. **Clear Provenance (รู้ที่มา):** 
   *   Transaction ทุกอันต้องมี Tag บอกที่มา: `[จากสลิป]` `[จาก Statement]` หรือ `[ผู้ใช้พิมพ์เอง]`
2. **Confidence Signage (บอกระดับความมั่นใจ):**
   *   หมวดหมู่ที่ AI มั่นใจ (เช่น ค่าโทรศัพท์จากบิล AIS) → **Auto-approve** ลงบัญชีเลย แจ้งเตือนเงียบๆ
   *   หมวดหมู่ที่ AI ไม่มั่นใจ (เช่น โอนเงินเข้าบัญชีนาย ก.) → **Pending status** + เด้ง Quick Reply ถาม
3. **Graceful Degradation (พร้อมถอย):**
   *   ถ้า AI อ่านสลิปไม่ออก (ภาพเบลอ) อย่าพยายามเดามั่ว ให้บอทตอบว่า *"สลิปเบลอจัง แมวส้มอ่านไม่ออก พิมพ์บอกหน่อยได้ไหมเมี้ยว?"*
4. **Reversible Actions (แก้ได้เสมอ):**
   *   ถ้า Auto-approve ไปแล้ว ต้องมีปุ่ม Edit/Undo อยู่ใน Flex Message เสมอ เพื่อให้แก้ได้ทันทีโดยไม่ต้องเข้า LIFF
