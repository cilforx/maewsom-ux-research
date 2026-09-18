# 06. MaewSom Design Strategy & LIFF IA

## 1. Design Principles for MaewSom LIFF

สกัดจากงานวิจัย นี่คือ 8 หลักการออกแบบ (Design Principles) สำหรับ MaewSom

**Principle 1: Don't Build a Desktop App in LIFF**
*   *Evidence:* แอป E-commerce บน LIFF ที่โหลดช้า มี Navigation ซับซ้อน ทำให้ผู้ใช้บ่นและเลิกใช้
*   *Insight:* ผู้ใช้เปิด LIFF เพราะต้องการจบงานเฉพาะกิจ ไม่ได้ต้องการนั่งแช่นานๆ
*   *Implication:* LIFF ต้องแบน (Flat IA) ห้ามมีหน้าจอย่อยซ้อนกันเกิน 2 ระดับ
*   *MaewSom Requirement:* ใช้ Bottom Sheet หรือ Modal สำหรับ Action ย่อย แทนการเปิดหน้าใหม่

**Principle 2: The Inbox is the Core Workflow**
*   *Evidence:* Copilot และ Monarch ประสบความสำเร็จอย่างสูงด้วยระบบ "Review Inbox" 
*   *Insight:* AI ไม่มีวันแม่น 100% ผู้ใช้ต้องการควบคุมข้อมูลก่อนที่มันจะเข้าไปปนกับยอดรวม
*   *Implication:* สิ่งแรกที่ผู้ใช้เห็นเมื่อเปิด LIFF ควรเป็นรายการที่รอการยืนยัน
*   *MaewSom Requirement:* สร้างหน้า "Review Inbox" ที่ใช้ Swipe gesture (ปัดขวาเพื่ออนุมัติ) ให้เคลียร์รายการได้รวดเร็ว

**Principle 3: One Metric to Rule Them All**
*   *Evidence:* ผู้ใช้เลิกใช้ YNAB เพราะเรียนรู้ยาก แต่รัก PocketGuard เพราะบอกแค่ตัวเลขเดียว "In My Pocket"
*   *Insight:* คนส่วนใหญ่ไม่อยากวิเคราะห์กราฟแท่ง แต่อยากรู้แค่ว่า "ใช้เงินได้อีกเท่าไหร่"
*   *Implication:* แดชบอร์ดต้องโชว์ตัวเลขที่นำไปตัดสินใจได้ทันที
*   *MaewSom Requirement:* หน้า Home ของ LIFF ต้องเด่นที่ตัวเลข "เงินคงเหลือที่ใช้ได้ (Safe to Spend)" เป็นอันดับแรก

**Principle 4: Statement Reconciliation as the Anchor**
*   *Evidence:* MeowJot มีปัญหาเรื่องยอดเงินไม่ตรงกับบัญชีจริง เพราะสลิปหล่นหาย
*   *Insight:* ถ้าตัวเลขรวม (Balance) ไม่ตรงกับในแอปธนาคาร ผู้ใช้จะหมดความเชื่อมั่น
*   *Implication:* ต้องมีฟีเจอร์กระทบยอดเพื่อปรับตัวเลขให้ตรงความจริง
*   *MaewSom Requirement:* มีหน้า "กระทบยอดรายเดือน" (Reconcile) ให้ผู้ใช้อัปโหลด Statement เพื่อให้ AI ตรวจสอบรายการที่ตกหล่น

**Principle 5: Dynamic Persona Context**
*   *Evidence:* Cleo ถูกรีวิวแย่เมื่อผู้ใช้อยู่ในภาวะหนี้สินแต่บอทยังเล่นมุก Piggipo เปลี่ยนหน้าร้องไห้เมื่อหนี้บาน
*   *Insight:* อารมณ์ขันทางการเงินมีขอบเขต
*   *Implication:* UI ต้องรู้บริบททางการเงินของผู้ใช้
*   *MaewSom Requirement:* สร้าง "Serious Mode" ใน LIFF (เปลี่ยนสีกราฟเป็นแดง/ดำ ปิดแอนิเมชันน่ารัก) เมื่อใช้เกินงบ หรือมีหนี้

**Principle 6: Frictionless Edit**
*   *Evidence:* การแก้หมวดหมู่ในแอปแบบดั้งเดิมใช้ 3-4 แตะ
*   *Insight:* ถ้าแก้ไขยาก ผู้ใช้จะปล่อยผ่าน และข้อมูลขยะจะเต็มระบบ
*   *Implication:* การแก้ไขต้องทำได้ใน 1 แตะจากหน้าแรก
*   *MaewSom Requirement:* แตะที่ไอคอนหมวดหมู่ใน List ย่อยเพื่อแสดง Modal เลือกหมวดใหม่ได้ทันที

**Principle 7: Trust Badges**
*   *Evidence:* ผู้ใช้ไม่แน่ใจว่ารายการไหนมาจากไหน (ทำเอง หรือ AI เดา)
*   *Insight:* Provenance (ที่มา) คือสิ่งสำคัญ
*   *Implication:* UI ต้องระบุแหล่งที่มาของข้อมูลเสมอ
*   *MaewSom Requirement:* ใส่ Badge เล็กๆ ท้าย Transaction เช่น `[e-Slip]` `[Statement]` `[Auto-recurring]`

**Principle 8: Design for the Blank Canvas**
*   *Evidence:* หน้าจอว่างเปล่า (Empty State) ตอนเริ่มใช้แอปการเงินทำให้คนไปต่อไม่ถูก
*   *Insight:* ผู้ใช้ใหม่ต้องถูก Onboard ด้วย Action ไม่ใช่หน้าจอดำๆ
*   *Implication:* Empty State ต้องเป็น Call-to-action ที่ทำผ่าน LINE ได้
*   *MaewSom Requirement:* หน้า Home ตอนแรกต้องมีปุ่ม "ลองส่งสลิปแรกลงในแชทสิ" (Deep link กลับไปที่แชท)

---

## 2. Proposed Research-Based Information Architecture (LIFF)

**Rich Menu Mapping (ทางเข้าจาก Chat):**
1. 🏠 **ภาพรวม (Dashboard)** -> เปิด LIFF หน้า Home
2. 📝 **รอตรวจ (Inbox)** -> เปิด LIFF หน้า Review Inbox
3. ⚙️ **ตั้งค่า (Settings)** -> เปิด LIFF หน้า Account/Budget
4. 🤖 **คุยกับแมวส้ม** -> เรียก Quick Reply เมนูช่วยเหลือในแชท

**LIFF Navigation (Bottom Tab):**

1. **Tab 1: Inbox (รอตรวจ)**
   *   รายการที่ AI ทายจากสลิปแต่ไม่มั่นใจ
   *   รายการที่ดึงจาก Statement แต่ไม่มีสลิปคู่
   *   *Action:* Swipe Right (Confirm), Tap (Edit)
2. **Tab 2: Home (Dashboard)**
   *   Hero: "Safe to Spend" (เงินที่ใช้ได้)
   *   Card: Weekly recap graph
   *   List: Recent Transactions (ที่อนุมัติแล้ว)
3. **Tab 3: Accounts & Reconcile (บัญชี)**
   *   List of Wallets/Banks
   *   ปุ่ม "อัปโหลด Statement กระทบยอด"
4. **Tab 4: Settings (ตั้งค่า)**
   *   กำหนด Budget
   *   Manage Subscription (Premium)

---

## 3. What This Means for MaewSom LIFF (Feature Recommendations)

| Feature / Area | Observed Pattern & Evidence | Recommendation | Confidence |
| :--- | :--- | :--- | :--- |
| **Home** | ผู้ใช้เมิน Dashboard ที่ซับซ้อน (Wallet by BB) | ใช้ "Left to Spend" widget เป็นจุดศูนย์กลาง | High |
| **Navigation** | เมนูลึกทำให้หลง (Banking apps) | ใช้ Bottom Nav แค่ 4 Tabs ซ่อน Action ใน Bottom Sheet | High |
| **Review Inbox** | Batch review ได้ผลดีสุด (Copilot) | สร้าง Inbox เป็นหน้าแรกสุด (Default tab) ถ้ามีรายการค้าง | High |
| **Transaction Detail** | ต้องการ Context (MeowJot) | แสดงภาพ e-Slip ต้นฉบับแนบไว้ในหน้ารายละเอียดเสมอ | High |
| **Statement** | Duplicate problem | มีระบบ AI Match หาคู่ (e-Slip + Statement) เพื่อป้องกันยอดเบิ้ล | High |
| **Persona** | สนุกตอนแรก รำคาญตอนหลัง (Cleo) | ใช้ "Serious Mode" (ลดโทนตัวละครลง) เมื่อยอดเงินติดลบ | Medium |
| **Notification** | แจ้งเตือนเยอะไปคนรำคาญ | ให้ Push alert ในแชท เฉพาะเวลาใช้เงินก้อนใหญ่ หรือ งบใกล้หมด | High |
| **Premium** | Paywall ก่อนใช้งานทำให้ Churn | ล็อกฟีเจอร์ Reconcile Statement แทนที่จะล็อกจำนวน e-Slip | Medium |
| **Error State** | AI เดาผิดบ่อย (General trend) | มีปุ่ม "แจ้งแมวส้มว่าผิด" เพื่อส่ง Feedback loop | High |

---

## 4. Open Questions (สิ่งที่ควรทำ Usability Testing ต่อ)

สิ่งที่ Research เบื้องต้นยังตอบไม่ได้ และต้องทำ Prototype ไปทดสอบกับผู้ใช้ชาวไทย:

1. **Swipe Gesture Recognition:** ผู้ใช้ไทยคุ้นเคยกับการปัดขวาเพื่อ Confirm (แบบ Tinder/Copilot) ในบริบทแอปการเงินหรือไม่? หรือชอบแตะปุ่ม [Confirm] ชัดๆ มากกว่า?
2. **Trust in Statement Reconciliation:** เมื่อ AI หักลบกลบหนี้ระหว่างสลิปที่จดกับ Statement ที่อัปโหลด ผู้ใช้จะเชื่อตัวเลขสุทธิของ AI หรือจะรู้สึกสับสน? (ต้องการทดสอบ "Explainability UI")
3. **The "Serious Mode" Transition:** การเปลี่ยนหน้าตาแอปและคำพูดกะทันหันเมื่อเงินติดลบ จะทำให้ผู้ใช้รู้สึกขอบคุณ หรือรู้สึกถูกต่อว่า/ตัดสิน?
