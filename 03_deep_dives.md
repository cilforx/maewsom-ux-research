# 03. Deep Dive & Competitor Analysis

## Part 1: Transaction Lifecycle Deep Dives (10 Products)

เราวิเคราะห์ **Transaction Lifecycle** ของ 10 ผลิตภัณฑ์สำคัญ เพื่อดูว่าตั้งแต่ข้อมูลเข้าจนถึงเกิด Action ผู้ใช้ต้องออกแรง (Friction / Taps) มากแค่ไหน

### 1. MeowJot (เหมียวจด)
*   **Lifecycle:** Save Slip to Camera Roll (0 taps) → Background Detection (0) → OCR Extract (0) → Notification (1) → Open App (1) → Review Inbox (Swipe/Tap) (1-2) → Categorized (0) → View Stats (1).
*   **Total Taps to Value:** ~4 taps.
*   **Key Insight:** Flow ลื่นไหลมากเพราะขโมยพฤติกรรมเดิม (คนไทยชอบเซฟสลิป) มาเป็น Trigger AI ทำงานได้ดีระดับ 85% แต่ถ้า AI ผิด ผู้ใช้ต้องเข้าไปแก้ในแอป ซึ่งมีโอกาสหมักหมม

### 2. Nabtang (นับตังค์)
*   **Lifecycle:** Open App (1) → Tap '+' (1) → Enter Amount (3-4) → Select Category (1) → Save (1) → Dashboard updates.
*   **Total Taps to Value:** ~7-8 taps.
*   **Key Insight:** Manual 100% อาศัยวินัยสูงมาก ผู้ใช้ Churn rate สูงเมื่อผ่านไป 1-2 เดือน (จากรีวิว)

### 3. BooJot
*   **Lifecycle:** Open App (1) → View Goal (0) → Add saving (1) → Enter Amount (3) → Save (1).
*   **Total Taps to Value:** ~6 taps.
*   **Key Insight:** เน้น Visual Progress (หมูอ้วนขึ้น / หลอดเต็ม) เป็นการทำ Micro-transaction แบบ Manual

### 4. Piggipo
*   **Lifecycle (Credit Card):** Wait for Statement Email → Forward / Upload to App (2-3) → App Parses PDF (0) → Batch Review (1) → Visualizes total debt across cards (0).
*   **Total Taps to Value:** ~3-4 taps per month.
*   **Key Insight:** เปลี่ยนจากการทำ Daily Entry เป็น Monthly Batching ข้อดีคือลดภาระรายวัน ข้อเสียคือไม่เห็นภาพแบบ Real-time จนกว่าจะสิ้นเดือน

### 5. MAKE by KBank
*   **Lifecycle:** Open App (1) → FaceID (0) → View Cloud Pockets (0) → Tap Unassigned Pocket (1) → Drag to target pocket (1) → Release (1).
*   **Total Taps to Value:** ~4 taps (Highly Gamified).
*   **Key Insight:** การลากวาง (Drag & Drop) เปลี่ยนเรื่องเครียด (การจัดสรรเงิน) ให้เป็นเรื่องสนุก (Tactile Feedback)

### 6. LINE BK
*   **Lifecycle:** Open LINE (1) → Wallet Tab (1) → LINE BK (1) → PIN (3-6) → View Balance (0).
*   **Total Taps to Value:** ~6-9 taps.
*   **Key Insight:** แม้จะอยู่ใน LINE แต่ด้วยข้อจำกัดด้าน Security ทำให้ Flow การเข้าถึงบัญชีมีความเสียดทานเท่ากับแอปธนาคารปกติ

### 7. Cleo
*   **Lifecycle:** Open App/Messenger (1) → Type "How much left?" (text input) → AI parses (0) → AI answers + Roasts (0).
*   **Total Taps to Value:** 1 tap + Typing effort.
*   **Key Insight:** Chat UI ทำให้ผู้ใช้ไม่ต้องเรียนรู้วิธีการใช้แอป (No Navigational friction) แต่อาศัย Cognitive effort ในการคิดคำถามแทน

### 8. Rocket Money (with Rowan AI)
*   **Lifecycle:** Open App (1) → Bank Sync pulls data (0) → Notification of large transaction (1) → Tap to review (1) → Ask Rowan "Why is this high?" (Text/Voice) → AI Explains (0).
*   **Key Insight:** เป็น **Proactive AI** AI เป็นฝ่ายเริ่มทักผู้ใช้ก่อนเมื่อพบความผิดปกติ ทำให้ผู้ใช้รู้สึกมี Personal CFO

### 9. Copilot Money
*   **Lifecycle:** Open App (1) → Inbox shows 5 unreviewed synced transactions (0) → Swipe right to confirm, tap to edit (1 tap per tx).
*   **Total Taps to Value:** 1 tap per transaction.
*   **Key Insight:** UX/UI สวยที่สุดในตลาด (Tinder for Finance) ทำให้กระบวนการน่าเบื่ออย่างการ Review กลายเป็นเรื่องสนุกและเร็วมาก

### 10. Monarch Money
*   **Lifecycle:** Bank sync (0) → Auto-categorization based on custom rules (0) → Monthly Review Workflow (Multi-step guided UI).
*   **Key Insight:** เน้นทำ Workflow ให้เป็นระบบ เหมาะสำหรับ Household Finance มีระบบ Rule-engine ที่เก่งมาก

---

## Part 2: Special Analysis — MeowJot vs. MaewSom

> **โจทย์สำคัญ:** MaewSom ต้องแตกต่างจาก MeowJot ในระดับ Product Architecture อย่างไร เพื่อไม่ให้กลายเป็นแค่ “MeowJot บน LINE”

### 1. The Core Architecture Difference

*   **MeowJot Architecture:** Device-native + Background Process. ดักจับสลิปจากอัลบั้มรูปในมือถือ ข้อดีคือผู้ใช้ไม่ต้องทำอะไร (Zero-effort) ข้อเสียคือ **"ขาด Context"** ระบบรู้แค่ว่าโอนเงินให้ใคร แต่ไม่รู้ว่าซื้ออะไร (เว้นแต่จะใช้ AI วิเคราะห์จากชื่อบัญชีแม่ค้า)
*   **MaewSom Architecture:** LINE-native + Active Conversational Ingestion. ผู้ใช้ **ตั้งใจ** ส่งรูปสลิป, ข้อความ, หรือ Statement เข้ามาในแชท

### 2. Strategic Differentiations (การสร้างความแตกต่าง)

**A. Multi-Modal Contextual Capture (พิมพ์บอกบริบทได้ทันที)**
*   *MeowJot:* อ่านสลิป "โอนเงิน 500 บาท ให้ น.ส.สมศรี" → AI เดาหมวดหมู่ไม่ได้ อาจลงเป็น "อื่นๆ" หรือ "โอนเงิน"
*   *MaewSom:* ผู้ใช้ส่งสลิปพร้อมพิมพ์ต่อในแชทว่า "ค่าหารหมูกระทะ" → AI จับคู่สลิปกับ Text ถัดไปทันที ทำให้ Categories แม่นยำ 100% 

**B. Human-in-the-Loop via Quick Reply (ไม่ต้องเปิดแอปเพื่อแก้)**
*   *MeowJot:* ถ้าจัดหมวดผิด ผู้ใช้ต้องเปิดแอป → หา Transaction → กด Edit → เลือกหมวดใหม่ (High Friction)
*   *MaewSom:* เมื่อส่งสลิป บอทตอบทันที "บันทึก 500 บาท หมวดอาหาร (Food) ใช่ไหมเมี้ยว?" พร้อมปุ่ม **[ใช่] [ไม่ใช่, ค่าเดินทาง] [ไม่ใช่, อื่นๆ]** (1 Tap Resolution in Chat)

**C. Reconciliation as a Core Truth (กระทบยอดกับ Statement)**
*   *MeowJot:* นับเฉพาะสิ่งที่อยู่ในอัลบั้มรูป ถ้าโอนผ่านคอมพิวเตอร์ ตัดบัตรเครดิต หรือจ่ายเงินสด ระบบจะไม่รู้ ยอดรวมมักไม่ตรงกับความเป็นจริง (Broken Trust)
*   *MaewSom:* รับสลิปรายวันเพื่อ Track พฤติกรรม (Habit) แต่ **อนุญาตให้อัปโหลด e-Statement สิ้นเดือนเพื่อ Reconcile (กระทบยอด)** หาก Statement มีรายการที่ไม่ได้จด MaewSom จะดึงเข้ามาเติมอัตโนมัติ (Single Source of Truth)

**D. Relationship Scale (ไม่หวานเลี่ยนจนเกินไป)**
*   *MeowJot:* คุมโทนน่ารัก (Cute/Astrology) ตลอดเวลา
*   *MaewSom:* มี **Relationship & Emotional Context** แมวส้มจะขี้เล่นเมื่อเงินเหลือ แต่จะตัดเข้าสู่ "Serious Mode" (เปลี่ยนฟอนต์, สี, น้ำเสียง) ทันทีที่ผู้ใช้มีแนวโน้มช็อตหรือเป็นหนี้ (Builds true financial trust, not just a toy).

### บทสรุปการแข่งขันกับ MeowJot
MaewSom **ไม่ควรไปแข่งเรื่องการดึงรูปอัตโนมัติแบบลับหลัง (Background Sync)** เพราะมีข้อจำกัดทาง OS และเสียเปรียบแอป Native แต่ MaewSom ควร **ชนะด้วย Context, Conversation, และ Statement Reconciliation** อาศัยความได้เปรียบที่ผู้ใช้อยู่ในหน้าแชท LINE อยู่แล้ว สามารถพูดคุยเพื่อจัดหมวดหมู่ที่ซับซ้อนได้อย่างเป็นธรรมชาติ
