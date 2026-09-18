# 04. UX Pattern Library & Pain Point Matrix

## Part 1: Competitor Pain Point Matrix

จากการวิเคราะห์รีวิวเชิงลบ (Negative Reviews) ของแอปกลุ่ม Personal Finance / AI Finance เราพบกลุ่มปัญหาหลักเพื่อตั้งเป็น **Anti-Requirements (ข้อห้ามทำ)** สำหรับ MaewSom

| Pain Point Category | User Quote (Synthesized) | Competitor Examples | MaewSom Anti-Requirement (สิ่งที่ห้ามทำ) |
| :--- | :--- | :--- | :--- |
| **1. AI Inaccuracy Trust Drop** | "AI ทายหมวดผิดตลอด แล้วแก้ยากมาก ต้องลบลงใหม่" | Many AI-first apps | **ห้ามซ่อนปุ่ม Edit.** ต้องมี Undo / Edit แบบ 1-Tap เสมอ |
| **2. Duplicate Transactions** | "ลงสลิปไปแล้ว พอสิ้นเดือนอัป Statement ยอดเบิ้ลเฉยเลย ยอดรวมพังหมด" | Piggipo, YNAB (sometimes) | **ต้องมี Duplicate Detection** ที่ใช้ AI จับคู่ยอดที่ตรงกัน (Amount + Date) |
| **3. Too Much Manual Entry** | "ใช้ไป 2 อาทิตย์ก็เลิกละ ขี้เกียจพิมพ์ตอนต่อแถวจ่ายตังค์" | Nabtang, Money Diary | **ห้ามบังคับกรอกข้อมูลทั้งหมด.** อนุญาตให้บันทึกแค่ "ยอดเงิน" ข้อมูลอื่นค่อยให้ AI จัดการทีหลัง |
| **4. Inflexible Paywalls** | "กำลังจะดูว่าเดือนนี้เงินเหลือเท่าไหร่ โดนเด้งหน้าจ่ายเงินบังคับซื้อเลย" | Cleo, Monarch | **Paywall หลังเกิด Value (Post-Value Paywall).** อย่าล็อกฟีเจอร์พื้นฐาน (Balance) |
| **5. Lost in the App (IA Issue)** | "หาหน้าที่จะไปเพิ่มบัญชีใหม่ไม่เจอ เมนูซ้อนเมนู" | Banking apps | **LIFF IA ต้องแบน (Flat).** ไม่ควรมี Navigation ลึกเกิน 2 ชั้น |
| **6. The "Annoying" AI** | "บอทเตือนจุกจิกมาก พิมพ์เล่นมุกตลอดเวลา ตอนฉันกำลังเครียดเรื่องหนี้" | Cleo | **Context-Aware Tone.** หากเงินติดลบ ต้องเข้าสู่ Serious Mode |

---

## Part 2: UX Pattern Library

เราได้สกัด UX Patterns กว่า 20 รูปแบบที่พบใน 50 ผลิตภัณฑ์ แบ่งตามหมวดหมู่ดังนี้

### A. Patterns that consistently work (ใช้งานได้ดีเสมอ)

**1. Pattern: The Swipe-to-Review Inbox**
*   **Used by:** Copilot, Monarch
*   **Problem:** การยืนยัน Transaction จำนวนมากใช้เวลานาน
*   **How it works:** แสดงรายการที่ AI จัดหมวดแล้วเป็นแบบ Card ปัดขวาเพื่อยืนยัน (Confirm) ปัดซ้ายหรือแตะเพื่อแก้ไข
*   **Applicability to MaewSom:** High. นำมาใช้ในหน้า LIFF สำหรับตรวจ Statement ปลายเดือน

**2. Pattern: "Left to Spend" Visualizer**
*   **Used by:** Nabtang, YNAB, PocketGuard
*   **Problem:** ผู้ใช้ไม่อยากรู้ยอดรวมสุทธิ แต่อยากรู้ว่า "วันนี้ซื้อกาแฟได้ไหม"
*   **How it works:** แปลงยอด Budget หักลบค่าใช้จ่ายคงที่ (Fix cost) ออกมาเป็น "เงินที่ใช้ได้" (Safe to spend)
*   **Applicability to MaewSom:** High. เป็น Metric เดียวที่ควรโชว์ใน Home Dashboard

**3. Pattern: One-Tap Categorization from Context**
*   **Used by:** MeowJot
*   **How it works:** เดาหมวดหมู่จากชื่อบัญชีผู้รับโอน
*   **Applicability to MaewSom:** High.

### B. Patterns that cause friction (สร้างความลำบาก)

**4. Pattern: The Multi-Step Manual Form**
*   **Problem:** ต้องกรอก Date, Amount, Category, Note, Image
*   **Why it fails:** Cognitive load สูงเกินไป
*   **MaewSom Adaptation:** ห้ามใช้. ให้ผู้ใช้ส่งแค่สลิป หรือ พิมพ์ "ข้าว 50" แล้ว AI เติม Date/Category เอง

**5. Pattern: Deep Settings Menus**
*   **Problem:** ซ่อนการแก้ไข Budget ไว้ใน Settings > Account > Budget
*   **MaewSom Adaptation:** LIFF ควรกางทุกอย่างออกมาเป็น Card ในหน้าเดียว

### C. Emerging 2025–2026 patterns (เทรนด์ใหม่)

**6. Pattern: Generative Insight Summaries**
*   **Used by:** Origin, Copilot AI
*   **How it works:** แทนที่จะโชว์แค่กราฟแท่ง AI จะสรุปเป็น Text สั้นๆ เช่น "สัปดาห์นี้กินข้าวนอกบ้านเยอะกว่าปกติ 20% นะ"
*   **Applicability to MaewSom:** High (ใช้ส่งผ่าน LINE Chat ได้ดีเยี่ยม)

**7. Pattern: Chat as Search**
*   **Used by:** Rocket Money (Rowan)
*   **How it works:** พิมพ์ถาม "เดือนที่แล้วจ่ายค่าไฟเท่าไหร่" แทนที่จะไปนั่งเปิด Calendar
*   **Applicability to MaewSom:** High. (Core Feature ใน LINE)

**8. Pattern: Automated Subscription Tracking**
*   **How it works:** AI ตรวจจับยอดที่หักซ้ำๆ ทุกเดือนและตั้งเป็น Subscription ให้อัตโนมัติ

### D. Thai-Specific Patterns

**9. Pattern: E-Slip as Proof of Life**
*   **Used by:** MeowJot, Thai E-commerce
*   **How it works:** ใช้สลิปโอนเงินเป็น Trigger หลักในการบันทึกรายจ่าย
*   **Applicability to MaewSom:** Absolute High.

**10. Pattern: PromptPay / QR Parsing**
*   **How it works:** ดึงข้อมูลชื่อร้านค้าจากรหัส PromptPay
*   **Applicability to MaewSom:** High.

**11. Pattern: "วันหวยออก" Emotional Trigger**
*   **How it works:** วันที่ 1 และ 16 ของเดือน ผู้ใช้มีพฤติกรรมการเงินแปลกไป
*   **Applicability to MaewSom:** Medium. (ใช้เป็น Gimmick ในการทักทาย)

### E. LINE-Specific Patterns

**12. Pattern: Quick Reply Triage**
*   **Used by:** K PLUS (Fraud Alert)
*   **How it works:** ส่ง Notification พร้อมปุ่ม Quick Reply 2-3 ปุ่ม ให้จบงานในหน้าแชท
*   **Applicability to MaewSom:** High. ใช้สำหรับ "AI ไม่แน่ใจหมวดหมู่"

**13. Pattern: Flex Message Receipt**
*   **How it works:** สรุปรายการด้วยดีไซน์ใบเสร็จผ่าน Flex Message
*   **Applicability to MaewSom:** High. สร้างความรู้สึก Official & Trust.

**14. Pattern: Chat to LIFF Seamless Handoff**
*   **How it works:** กดปุ่ม "ดูรายละเอียด" ในแชท แล้วเปิด LIFF ตรงเข้าสู่หน้านั้นทันที (Deep Link) ไม่ใช่เปิดไปหน้า Home
*   **Applicability to MaewSom:** High. สำคัญมากต่อ UX

### F. AI-Specific Patterns

**15. Pattern: Confidence Indicators**
*   **Used by:** Copilot AI
*   **How it works:** แสดงไอคอนว่าข้อมูลนี้ AI มั่นใจกี่เปอร์เซ็นต์ (เช่น ไอคอนหุ่นยนต์สีส้ม = เดา, สีเขียว = มั่นใจ)
*   **Applicability to MaewSom:** High. ช่วย Manage Expectation

**16. Pattern: The "Explain Yourself" Button**
*   **How it works:** ผู้ใช้แตะถามได้ว่า "ทำไมถึงจัดยอดนี้อยู่ในหมวดนี้?"
*   **Applicability to MaewSom:** Medium.

**17. Pattern: Ambient AI Action**
*   **How it works:** AI ทำงานเบื้องหลัง และแจ้งเตือนเมื่อเสร็จ (เช่น "อ่าน Statement 100 รายการเสร็จแล้ว!")

### G. Financial Trust Patterns

**18. Pattern: Last Synced Timestamp**
*   **How it works:** บอกชัดเจนว่าตัวเลขนี้อัปเดตล่าสุดเมื่อไหร่ (เช่น "อัปเดตเมื่อ 2 นาทีที่แล้ว")
*   **Applicability to MaewSom:** High. ป้องกันผู้ใช้ตกใจถ้ายอดยังไม่เปลี่ยน

**19. Pattern: The "Pending" State**
*   **How it works:** แยกรายการที่เพิ่งบันทึก (แต่อาจจะมีการแก้ไข) ออกจากรายการที่ Verified แล้ว
*   **Applicability to MaewSom:** High.

**20. Pattern: Serious Mode UI Toggle**
*   **How it works:** ปรับ UI เป็นสีแดง/ดำ ลดแอนิเมชัน เมื่อเกิดสถานะการเงินวิกฤต (หนี้, ลบ)
*   **Applicability to MaewSom:** High.

### H. Monetization Patterns

**21. Pattern: The "Data Limit" Paywall**
*   **How it works:** ฟรี 50 transaction/เดือน ถ้าเกินต้องจ่าย
*   **Applicability to MaewSom:** Low (ทำให้ผู้ใช้เลิกใช้).

**22. Pattern: The "Advanced Automation" Paywall**
*   **Used by:** MeowJot (Premium)
*   **How it works:** ฟรีแบบ manual/slip เดี่ยวๆ, จ่ายเงินเพื่ออัปโหลด Statement ทีละ 20 หน้า
*   **Applicability to MaewSom:** High. ขาย "เวลาและความสะดวก" ไม่ใช่ขายพื้นที่เก็บข้อมูล
