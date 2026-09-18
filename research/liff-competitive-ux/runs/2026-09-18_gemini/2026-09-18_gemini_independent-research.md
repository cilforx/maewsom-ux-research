---
topic: liff-competitive-ux
date: 2026-09-18
researcher: Gemini
model: Gemini 3.1 Pro (High)
status: raw
research_type: independent-pass
canonical: false
---

# 01. Executive Summary & Market Strategy

## 1. Executive Summary: The State of Personal Finance (2025–2026)

จากการศึกษา 50 ผลิตภัณฑ์ทางการเงินทั้งในไทยและระดับโลก ตลอดจนแอปพลิเคชันที่มี AI และ ecosystem ของ LINE ทิศทางของตลาด Personal Finance Assistant ชี้ไปที่ **"Proactive, Zero-Data Entry, and Conversational"** 

ผู้ใช้เริ่มปฏิเสธแอปที่ต้องใช้ความพยายามสูง (High Friction) ในการกรอกข้อมูลด้วยตนเอง (Manual Entry) การเปลี่ยนผ่านจาก Dashboard-heavy apps สู่ Chat-centric interfaces (นำโดย Cleo, Monarch AI, และในไทยคือ MeowJot) พิสูจน์ให้เห็นว่าผู้ใช้ยอมแลกความละเอียดของข้อมูล (Granularity) กับความสะดวกสบาย (Convenience) 

### ทิศทางของตลาด (Market Direction)
- **Zero-Entry as a Baseline:** การนำเข้าข้อมูลอัตโนมัติ (Bank Sync, e-Slip OCR, Statement Reading) ไม่ใช่ Killer Feature อีกต่อไป แต่เป็น "Baseline" ที่ผู้ใช้คาดหวัง
- **AI-Driven Categorization:** ความแม่นยำของ AI ในการแยกหมวดหมู่สูงขึ้นมาก (85-95%) แต่ปัญหาใหม่ที่เกิดคือ "Trust" (ผู้ใช้ไม่แน่ใจว่า AI จัดถูกไหม และแก้ไขยาก)
- **Conversational UI is for Triage, not Analytics:** แชทเหมาะสำหรับการนำเข้าข้อมูล, แจ้งเตือน, และรับคำสั่งสั้นๆ (Triage) แต่ **ล้มเหลว** อย่างหนักเมื่อพยายามใช้แสดงผลข้อมูลทางการเงินที่ซับซ้อน (เช่น Cash flow forecast หรือ Month-over-month comparison)
- **Relationship as Retention:** ผลิตภัณฑ์ที่ใช้ Persona (เช่น Cleo, MeowJot) มี Retention rate สูงกว่าแอปแนว Utility ล้วนๆ แต่มีความเสี่ยงเมื่อผู้ใช้อยู่ในภาวะเครียดทางการเงิน (Serious/High-Stakes State)

### ความเสี่ยงหลักของ MaewSom (Key Risks)
1. **The "MeowJot" Overlap:** หาก MaewSom เป็นเพียง "แมวที่อ่านสลิปได้บน LINE" จะชนกับ MeowJot โดยตรงซึ่งมีฐานผู้ใช้แข็งแกร่งและแบรนด์ที่คล้ายคลึงกัน (Cat Persona + Finance)
2. **LINE Ecosystem Limitations:** การสลับไปมาระหว่าง Chat และ LIFF อาจทำให้เกิด Friction หาก Context ไม่เชื่อมกัน (เช่น ถามคำถามในแชท แต่ถูกเตะไปหน้าแรกของ LIFF แทนที่จะเป็นหน้า Detail)
3. **Trust & Data Provenance Erosion:** ถ้า AI จัดการ Transaction ผิดพลาดบ่อย และผู้ใช้ไม่รู้ว่าตัวเลขคำนวณมาจากไหน (เช่น Statement ยอดไม่ตรงกับที่ AI สรุป) ผู้ใช้จะเลิกใช้ทันที (Churn)

### โอกาสหลัก (Key Opportunity)
**"The Reconciled Conversational Co-Pilot"** 
ช่องว่างที่ยังไม่มีใครทำได้ดีในไทยคือ การผสาน **ความง่ายของ Chat (LINE)** เข้ากับ **ความน่าเชื่อถือของ Accounting (Statement Reconciliation)** โดยมี **Human-in-the-loop (Review Inbox)** ที่โปร่งใส MaewSom สามารถจับกลุ่มผู้ใช้ที่ต้องการความสะดวกแบบ MeowJot แต่ต้องการความชัวร์ระดับ YNAB ผ่าน Interface ของ LINE

---

## 2. Competitive Maps

เพื่อหาจุดยืนของ MaewSom เราได้จัดวาง 50 คู่แข่งบนแกนพฤติกรรมหลัก 4 แกน:

### Map 1: Input Effort vs. Interface Paradigm
**Manual ←→ Automated** | **Dashboard ←→ Conversational**

*   **Top-Left (Manual & Dashboard):** YNAB, รับจ่ายจด, Money Diary *(High intent, High friction)*
*   **Top-Right (Automated & Dashboard):** K PLUS, MAKE by KBank, Monarch Money, Copilot *(Low intent input, High analytical capability)*
*   **Bottom-Left (Manual & Conversational):** (Blank Space) *(ไม่มีใครทำเพราะไม่สมเหตุสมผล)*
*   **Bottom-Right (Automated & Conversational):** Cleo, Erica, **MeowJot (moving here)**

> **MaewSom Positioning:** ขวาล่างสุด (Highly Automated + Conversational) แต่ต้องมี **LIFF เป็น Dashboard-bridge** เพื่อดึงข้อดีของ Top-Right มาใช้เมื่อผู้ใช้ต้องการวิเคราะห์ลึกๆ

### Map 2: Emotional Connection vs. Proactivity
**Utility ←→ Relationship** | **Reactive ←→ Proactive**

*   **Top-Left (Utility & Reactive):** Bank Apps (SCB, KTB), Standard Budgeting Apps *(เครื่องมือที่รอคำสั่ง)*
*   **Top-Right (Utility & Proactive):** Rocket Money, Monarch AI *(เครื่องมือที่เตือนเมื่อมีสิ่งผิดปกติ)*
*   **Bottom-Left (Relationship & Reactive):** (Rare)
*   **Bottom-Right (Relationship & Proactive):** Cleo, **MeowJot (with MeowDoo)**

> **MaewSom Positioning:** ขวาล่าง (Proactive Relationship) ต้องสร้างความผูกพันผ่านตัวละคร แต่ต้อง **Adaptive** (ลดความขี้เล่นลงทันทีเมื่อเตือนเรื่องหนี้ หรือเงินติดลบ)

---

## 3. White Space / Opportunity Areas

จากการวิเคราะห์ 50 ผลิตภัณฑ์ พบ **ช่องว่าง (White Space)** ที่ยังไม่มีการแก้ปัญหาที่สมบูรณ์ โดยเฉพาะในจุดตัดของ LINE-native, AI, และ Trust:

### 1. The "Statement-to-Slip" Reconciliation Gap
*   **ปัญหา:** แอปส่วนใหญ่อ่าน e-Slip (รายวัน) หรืออ่าน Statement (รายเดือน) อย่างใดอย่างหนึ่ง เมื่อทำทั้งสองอย่าง มักเกิด Transaction ซ้ำซ้อน (Duplicate) และผู้ใช้ไม่รู้ว่าตัวเลขไหนคือ "Source of Truth"
*   **โอกาส (White Space):** MaewSom สามารถใช้ AI เป็นตัวกลางนำ e-Slip ที่ผู้ใช้ส่งรายวันใน LINE ไป **Reconcile (กระทบยอด)** กับ Statement ที่อัปโหลดตอนสิ้นเดือน หากตรงกัน AI จะ "Verified" หากไม่ตรง จะส่ง "Correction Request" ไปที่ LIFF Review Inbox 

### 2. The "Micro-Review" via LINE Quick Reply
*   **ปัญหา:** ผู้ใช้ขี้เกียจเปิดแอปเข้าไป Review Inbox ที่มีรายการค้าง 50 รายการ
*   **โอกาส (White Space):** ทยอยส่ง Micro-review ผ่าน LINE Push Message (เช่น "วันนี้มี 3 รายการที่ไม่แน่ใจว่าใช่ค่ากินไหม") พร้อม Quick Reply [ใช่] [ไม่ใช่, คือ...] เพื่อให้เกิด Zero-friction human-in-the-loop

### 3. Progressive Persona Adaptation (Context-Aware Tone)
*   **ปัญหา:** Cleo หยาบคาย (Roast) ซึ่งสนุกในตอนแรก แต่สร้างความรำคาญเมื่อผู้ใช้เครียดจริง MeowJot น่ารักเสมอ แต่อาจดูไม่น่าเชื่อถือเมื่อตัวเลขผิด
*   **โอกาส (White Space):** MaewSom มีระบบ "Serious Mode" หากตรวจพบว่า Cash flow ติดลบ, หนี้บัตรเครดิตเกิน, หรือระบบประมวลผล Statement ผิดพลาด ตัวละครแมวส้มจะเปลี่ยน Tone-of-voice เป็น Professional ทันที ตัดภาพ Animation ที่รุงรังออก เพื่อส่งสัญญาณ "Trust & Focus"

### 4. Shared Finance on LINE (Multiplayer Mode)
*   **ปัญหา:** แอปทำบัญชีคู่รัก/เพื่อนแชร์ค่าห้อง (Honeydue) มักต้องโหลดแอปใหม่ ทำให้ Adoption rate ต่ำ
*   **โอกาส (White Space):** LINE เป็นพื้นที่ Social อยู่แล้ว MaewSom สามารถสร้าง "Shared Wallet / Split Bill View" ใน LIFF และแชร์ผลลัพธ์ลง LINE Group ได้โดยตรง โดยผู้ใช้คนอื่นสามารถกดยืนยันผ่าน Flex Message ได้ทันทีโดยไม่ต้องโหลดแอปแยก
# 02. 50-Product Research Matrix

> [!NOTE]
> เนื่องจากการแสดงผล 22 dimensions × 50 products ในตารางเดียวจะอ่านไม่ได้บนหน้าจอปกติ เราจึงยุบรวม (Aggregate) Dimensions เป็น 7 เสาหลักทางการออกแบบ เพื่อให้เห็น Pattern ชัดเจน และวิเคราะห์ความเชื่อมโยงได้

## Dimension Grouping:
1. **Positioning & Entry:** Positioning, Entry Point, Onboarding, Monetization
2. **Input & UX/UI:** Transaction Capture, Navigation, Home Screen, Empty State
3. **AI & Review:** AI Capability, Transaction Review, Financial Semantics, Error/Failure State
4. **Data & Trust:** Trust & Data Provenance, Serious State
5. **Engagement:** Notification, Character/Personality, Retention, Insights
6. **UX Analysis:** Strengths, Weaknesses, What to Learn, What NOT to Copy

---

## Group A: Thai Direct Personal Finance Competitors

| Product | Positioning & Entry | Input & UX/UI | AI & Review | Data & Trust | Engagement | MaewSom Takeaways |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **1. MeowJot** | **Pos:** Auto e-Slip tracker with cat persona.<br>**Entry:** App Icon, Share Extension.<br>**Monetize:** Premium for Statement/Deeper AI. | **Input:** OCR e-Slip (Background/Manual).<br>**Nav:** Bottom Tab (Home, Stats, Profile).<br>**Home:** Daily Timeline + Balance. | **AI:** Extracts amount, date, receiver. Auto-categorizes via merchant DB.<br>**Review:** Swipe to approve/edit pending slips. | **Trust:** High trust on amount, medium on category. Shows "Extracted from slip". | **Engage:** Cute Cat UI, "MeowDoo" (fortune), Push notifications. | **Learn:** Zero-entry is king.<br>**Avoid:** Forcing app downloads when LINE is enough. |
| **2. Nabtang** | **Pos:** Simple, clean budget tracker.<br>**Entry:** App Icon.<br>**Monetize:** Freemium. | **Input:** 100% Manual.<br>**Nav:** Bottom Tab.<br>**Home:** Budget remaining circle. | **AI:** None.<br>**Review:** Immediate manual input. | **Trust:** Source of truth is the user. | **Engage:** Clean aesthetic, minimal friction for manual input. | **Learn:** Visual clarity on "Left to spend".<br>**Avoid:** Manual entry dependency. |
| **3. รับจ่ายจด** | **Pos:** Traditional ledger for Thai market.<br>**Entry:** App Icon.<br>**Monetize:** Ads / Premium to remove ads. | **Input:** Manual.<br>**Home:** List of transactions. | **AI:** None. | **Trust:** Basic calculator level. | **Engage:** None. Pure utility. | **Avoid:** Outdated, spreadsheet-like UI. |
| **4. BooJot** | **Pos:** Piggy bank tracker / savings goal.<br>**Entry:** App Icon.<br>**Monetize:** Ads. | **Input:** Manual goal tracking.<br>**Home:** Visual goals. | **AI:** None. | **Trust:** User input. | **Engage:** Visual progress bars for saving. | **Learn:** Visualizing goals (e.g., buying a new phone). |
| **5. Save Money** | **Pos:** No-frills expense tracker.<br>**Entry:** App Icon. | **Input:** Manual. | **AI:** None. | **Trust:** Local storage. | **Engage:** Utility. | **Avoid:** Bland UI. |
| **6. Piggipo** | **Pos:** Credit card manager / Debt visualizer.<br>**Entry:** App Icon.<br>**Monetize:** Premium. | **Input:** Statement import / Manual.<br>**Home:** Cute pig characters indicating debt health. | **AI:** Basic OCR/parsing of statements.<br>**Review:** Batch review of CC statements. | **Trust:** High, but breaks if bank statement format changes. | **Engage:** Pig emotions change based on debt level (Happy = paid, Crying = over limit). | **Learn:** Emotional mapping to financial health (Serious State handling). |
| **7. Money Diary** | **Pos:** Diary-style tracker.<br>**Entry:** App Icon. | **Input:** Manual + Photo attach. | **AI:** None. | **Trust:** User-driven. | **Engage:** Journaling aspect. | **Learn:** Attaching context (photos) to expenses. |
| **8. Money Note+** | **Pos:** Simple spreadsheet alternative. | **Input:** Manual. | **AI:** None. | **Trust:** Basic. | **Engage:** Utility. | **Avoid:** Clunky UI. |
| **9. Lumpsum** | **Pos:** Holistic financial planner.<br>**Entry:** App Icon. | **Input:** Manual / Complex onboarding. | **AI:** Basic forecasting. | **Trust:** Very high (Financial Advisor positioning). | **Engage:** Serious, professional tone. | **Learn:** Long-term wealth overview.<br>**Avoid:** High onboarding friction. |
| **10. MeKinMeChai** | **Pos:** Niche Thai tracker. | **Input:** Manual. | **AI:** None. | **Trust:** Basic. | **Engage:** Thai localization. | **Avoid:** Lack of automation. |

---

## Group B: Thai Banking / Fintech (Internal Context)

| Product | Positioning & Entry | Input & UX/UI | AI & Review | Data & Trust | Engagement | MaewSom Takeaways |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **11. SCB EASY** | **Pos:** Full-service banking.<br>**Entry:** App, Deep link. | **Input:** Auto (from bank TX).<br>**Home:** Accounts & Actions. | **AI:** "Just for You" insights.<br>**Review:** Auto-categorized in "My Expenses". | **Trust:** Absolute (Source of Truth). | **Engage:** Utility, personalized banners. | **Learn:** Absolute trust mapping.<br>**Avoid:** Cluttered action menus. |
| **12. K PLUS** | **Pos:** Lifestyle & Banking.<br>**Entry:** App. | **Input:** Auto.<br>**Home:** Balance & K Point. | **AI:** Basic categorization.<br>**Review:** Can edit category, but buried. | **Trust:** Absolute. | **Engage:** K Point gamification. | **Learn:** Reward loops. |
| **13. MAKE by KBank** | **Pos:** Cloud pocket budgeting (Gen Z).<br>**Entry:** App. | **Input:** Bank transfer via Cloud Pockets.<br>**Home:** Visual Pockets (Drag & Drop). | **AI:** Auto-sort (basic).<br>**Review:** Inbox for unassigned money. | **Trust:** High (KBank backend). | **Engage:** Pop-art UI, high gamification, drag-to-transfer. | **Learn:** Physical metaphor (Drag & Drop) for budgeting. |
| **14. Krungthai** | **Pos:** Mass market banking. | **Input:** Auto. | **AI:** Minimal. | **Trust:** Absolute. | **Engage:** Government scheme integration. | **Avoid:** Sluggish UI. |
| **15. Paotang** | **Pos:** E-wallet / Gov gateway. | **Input:** Top-up. | **AI:** None. | **Trust:** High. | **Engage:** Utility only. | **Avoid:** Fragmented IA. |
| **16. ttb touch** | **Pos:** Financial well-being app. | **Input:** Auto. | **AI:** Comprehensive "Smart Dashboard" (predicts bills). | **Trust:** Very High. | **Engage:** Dashboard warns about upcoming liquidity issues. | **Learn:** Predictive insights (Proactive). |
| **17. Krungsri** | **Pos:** Retail banking. | **Input:** Auto. | **AI:** Kepthemed insights. | **Trust:** High. | **Engage:** Simple utility. | **Avoid:** Generic graphs. |
| **18. Bualuang** | **Pos:** Traditional banking. | **Input:** Auto. | **AI:** Minimal. | **Trust:** High. | **Engage:** Basic. | **Avoid:** Outdated UI. |
| **19. TrueMoney** | **Pos:** Everyday Super App e-Wallet. | **Input:** Payment/Top-up.<br>**Home:** Services grid. | **AI:** Promo targeting. | **Trust:** Medium (E-wallet). | **Engage:** Heavy gamification, loyalty. | **Learn:** Micro-transaction handling. |
| **20. LINE BK** | **Pos:** Social banking in LINE.<br>**Entry:** LINE Wallet tab. | **Input:** Auto.<br>**Home:** Balance & Credit line. | **AI:** Credit scoring.<br>**Review:** N/A. | **Trust:** High (KBank partner). | **Engage:** Seamless chat-to-transfer. | **Learn:** Perfect LINE native integration.<br>**Avoid:** Burying entry point in Wallet tab. |

---

## Group C: Global Personal Finance / Budgeting

| Product | Positioning & Entry | Input & UX/UI | AI & Review | Data & Trust | Engagement | MaewSom Takeaways |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **21. YNAB** | **Pos:** Zero-based budgeting cult.<br>**Monetize:** High Subscription. | **Input:** Bank Sync / Manual.<br>**Home:** "Ready to Assign". | **AI:** Learns categorization from user.<br>**Review:** Must manually approve every synced TX. | **Trust:** Extreme (Reconciliation feature is core). | **Engage:** Rule-based (4 Rules), high retention via ideology. | **Learn:** "Review & Reconcile" workflow.<br>**Avoid:** Too steep learning curve. |
| **22. Monarch** | **Pos:** Premium household finance.<br>**Monetize:** Subscription. | **Input:** Plaid/Finicity.<br>**Home:** Beautiful dashboard. | **AI:** Auto-categorization, custom rules.<br>**Review:** Bulk review inbox. | **Trust:** Very High (Status indicators). | **Engage:** Customizable dashboard. | **Learn:** Collaborative (Multiplayer) finance view. |
| **23. Copilot** | **Pos:** AI-first, design-centric tracker (iOS). | **Input:** Bank Sync.<br>**Home:** Dynamic widgets. | **AI:** Highly accurate ML categorization.<br>**Review:** Tinder-style swipe to review. | **Trust:** AI Confidence scores displayed. | **Engage:** Gorgeous UI, dark mode, smooth animations. | **Learn:** Swipe-to-review UX.<br>**Avoid:** iOS only logic. |
| **24. Rocket** | **Pos:** Subscription cancellation / Bill negotiator. | **Input:** Bank Sync. | **AI:** Identifies recurring charges. | **Trust:** High. | **Engage:** Push alerts for fee increases. | **Learn:** "Upcoming Bills" view. |
| **25. Simplifi** | **Pos:** Quick, easy tracking by Quicken. | **Input:** Sync. | **AI:** Cash flow projection. | **Trust:** High. | **Engage:** "Left to Spend". | **Learn:** Spending plan simplicity. |
| **26. PocketGuard**| **Pos:** "In my pocket" limit tracker. | **Input:** Sync. | **AI:** "In My Pocket" algorithm. | **Trust:** High. | **Engage:** Clear single metric focus. | **Learn:** Boil down to one actionable number. |
| **27. Wallet** | **Pos:** Global multi-currency tracker. | **Input:** Sync / Manual. | **AI:** Basic rules. | **Trust:** Medium. | **Engage:** Extensive charts. | **Avoid:** Overwhelming chart options. |
| **28. Spendee** | **Pos:** Shared wallets, beautiful UI. | **Input:** Sync / Manual. | **AI:** Basic. | **Trust:** Medium. | **Engage:** Shared tracking. | **Learn:** Shared expense UI. |
| **29. Emma** | **Pos:** Gen Z finance, gamified. | **Input:** Open Banking. | **AI:** Chatbot/Insights. | **Trust:** Medium. | **Engage:** Gummy bear mascot, quests. | **Learn:** Gamified saving. |
| **30. Honeydue** | **Pos:** Couples finance. | **Input:** Sync. | **AI:** Shared categorization. | **Trust:** High. | **Engage:** Comment on partner's TX. | **Learn:** Contextual chat inside a transaction. |

---

## Group D: AI / Conversational Finance

| Product | Positioning & Entry | Input & UX/UI | AI & Review | Data & Trust | Engagement | MaewSom Takeaways |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **31. Cleo** | **Pos:** AI that roasts you (Gen Z/Alpha). | **Input:** Chat / Sync.<br>**Home:** Chat Interface. | **AI:** Natural language query, proactive roasting.<br>**Review:** Chatbot asks. | **Trust:** Medium (Focus is on behavior, not exact accounting). | **Engage:** Extreme persona, humor, streaks. | **Learn:** Conversational ingestion.<br>**Avoid:** Being too aggressive; Thais prefer polite/cute. |
| **32. Albert** | **Pos:** Human + AI advisor. | **Input:** Sync.<br>**Home:** Action cards. | **AI:** "Genius" (Auto-savings). | **Trust:** High (Backed by real humans). | **Engage:** SMS/App chat. | **Learn:** Hybrid AI-Human fallback. |
| **33. Origin** | **Pos:** Comprehensive AI Wealth. | **Input:** Sync.<br>**Home:** Dashboard. | **AI:** AI answers complex tax/investment questions. | **Trust:** Very High. | **Engage:** Proactive planning. | **Learn:** AI for deeper advice. |
| **34. Rowan** | **Pos:** AI in Rocket Money. | **Input:** Sync. | **AI:** Chat to query "How much did I spend on Amazon?". | **Trust:** High. | **Engage:** Search via chat. | **Learn:** Chat as a search interface. |
| **35. Monarch AI**| **Pos:** Assistant in Monarch. | **Input:** Sync. | **AI:** Generative answers on dashboard data. | **Trust:** High. | **Engage:** Contextual prompts. | **Learn:** Prompt suggestions. |
| **36. Copilot AI** | **Pos:** Chat inside Copilot. | **Input:** Sync. | **AI:** Natural language search. | **Trust:** High. | **Engage:** Fast query. | **Learn:** Speed of response. |
| **37. Starling AI** | **Pos:** UK Bank Assistant. | **Input:** Auto. | **AI:** Spending insights. | **Trust:** Absolute. | **Engage:** Native bank integration. | **Learn:** Trust inheritance. |
| **38. Erica (BofA)** | **Pos:** Bank of America voice/chat AI. | **Input:** Voice/Chat. | **AI:** Navigates app, finds TX, locking cards. | **Trust:** Absolute. | **Engage:** Agentic action (Execute commands). | **Learn:** Agentic actions ("Freeze my card"). |
| **39. Fargo** | **Pos:** Wells Fargo AI. | **Input:** Chat. | **AI:** Similar to Erica. | **Trust:** Absolute. | **Engage:** Triage support. | **Avoid:** Robotic tone. |
| **40. Plum** | **Pos:** AI auto-saver. | **Input:** Open Banking. | **AI:** Analyzes balance and auto-transfers to savings. | **Trust:** High. | **Engage:** Facebook Messenger / App. | **Learn:** Chatbot auto-execution with Messenger integration. |

---

## Group E: LINE / MINI App / Conversational Ecosystem (Thai Focus)

> *Focus: How apps in LINE avoid feeling like "just another web view" (Seamless Handoff)*

| Product (Case) | LINE Integration Pattern | UX Strengths | Friction Points | MaewSom Takeaways (LIFF Strategy) |
| :--- | :--- | :--- | :--- | :--- |
| **41. Starbucks TH** | **Rich Menu → LIFF (Membership/Pay)** | Seamless SSO. Barcode renders instantly in LIFF. | Takes 2-3 seconds to load LIFF initially. | Use LIFF for secure, complex visuals (Barcode/QR). |
| **42. PTT Blue Card**| **Rich Menu → LIFF (Points/Redeem)** | Excellent use of Flex Messages for points summary. | Cluttered Rich Menu. | Flex Message for quick status, LIFF for deep catalog. |
| **43. Major Cineplex**| **Chatbot → LIFF (Booking)** | Chat for movie search, LIFF for seat selection. | Context loss if user closes LIFF mid-booking. | **Crucial:** Chat is for Triage, LIFF is for spatial/complex tasks (Seat map = Budget map). |
| **44. SCB Connect** | **Push/Service Message → LINE** | Best-in-class instant transaction notification. | No native LIFF dashboard, relies on deep linking to SCB App. | Real-time push is critical for Trust. |
| **45. LINE BK** | **Native Wallet → App** | Deeply integrated into LINE core tabs. | Requires full KYC onboarding. | MaewSom isn't a bank, but can mimic the visual language of LINE's native UI (fonts, colors). |
| **46. Wongnai** | **Share → Flex Message** | Flex Message looks beautiful and actionable in chat. | None. | Output from MaewSom must be highly shareable/readable via Flex. |
| **47. K PLUS LINE** | **Service Message → Quick Reply** | Uses Quick Reply to ask "Is this fraud?". | Simple binary choices. | **Learn:** Use Quick Reply for [Confirm Category] / [Edit]. |
| **48. Robinhood** | **Deep Link → App** | Chat notification deep links straight to order status. | Kicks user out of LINE. | MaewSom must keep user *inside* LINE via LIFF. |
| **49. Kerry/KEX** | **Chat → LIFF (Tracking)** | Type tracking number in chat, view map in LIFF. | Chatbot is sometimes rigid. | Natural Language Input in Chat → Structured Output in LIFF. |
| **50. H&M TH** | **Chat → LIFF (E-commerce)** | Full store inside LIFF. | Feels like a slow website wrapper. | **Avoid:** Do not build a heavy SPA in LIFF. It must be modular. |
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
