---
topic: liff-competitive-ux
date: 2026-09-18
local_time: "16:02 Asia/Bangkok"
researcher: Fable
model: Fable 5.1
status: raw
research_type: independent-pass
canonical: false
source_provenance: owner-provided full markdown report
source_filename: "MaewSom_LINE_UX_Research (1).md"
source_quality_note: "Strong on official LINE platform documentation; secondary market/case-study claims still require targeted verification."
immutable: true
---

# MaewSom / แมวส้ม — LINE UX Research
### Product Research + LINE Messaging UX Report

> ขอบเขต: research + UX architecture เท่านั้น — ไม่มี implementation code, ไม่ invent API, ไม่ invent สถิติ
> Accessed: 17 กันยายน 2026 · Confidence: **HIGH** = official docs/direct obs · **MEDIUM** = company/case study · **LOW** = secondary/community · **UNVERIFIED** = ไม่มี source
> หมายเหตุตัวเลข: ตัวเลข follower/MAU ของ OA ไทยส่วนใหญ่ **ไม่เปิดเผยสาธารณะ** ที่ไหนที่ไม่มี source จะเขียน UNVERIFIED และไม่เดา

---

## 1 · Executive Summary

**9 insight ที่สำคัญที่สุด:**

1. **เศรษฐศาสตร์ Reply vs Push คือข้อจำกัดออกแบบอันดับหนึ่ง ไม่ใช่ปรัชญา.** Reply message **ฟรี ไม่นับ quota**; push/multicast/broadcast **นับ quota**. `replyToken` ใช้ครั้งเดียว หมดอายุ **~1 นาที**. หนึ่ง reply ส่งได้ **≤5 message objects** และนับเป็น 1 ข้อความ (ต่างจากส่งแยก 5 request = 5). แปลว่าสถาปัตยกรรมทั้งหมดต้อง **"reply-first, push-rare"** และงาน OCR/LLM ที่อาจเกิน 1 นาทีต้องออกแบบเป็น **reply-then-push** ตั้งแต่วันแรก. [HIGH — developers.line.biz/pricing, /sending-messages]

2. **พฤติกรรม "รับเรื่องเงินใน LINE" ถูก mass-adopt แล้วโดยธนาคาร.** SCB Connect (@scbconnect) push แจ้งเตือน **เงินเข้า-ออก** ผ่าน LINE ฟรี 24 ชม. + แชตเช็กยอด/ถาม/แจ้งโอนผิด/ขอ statement. MaewSom **ไม่ต้องสอนพฤติกรรมใหม่** — แค่ต้อง "เข้าใจสิ่งที่ผู้ใช้ส่งมา" ได้ดีกว่าและ reconcile ได้. [HIGH — scb.co.th]

3. **"ส่งมาได้เลย" เป็นไปได้จริงทางเทคนิค.** Webhook รับ `text/image/video/audio/file/location/sticker` ตรง ๆ โดยผู้ใช้ไม่ต้องกดเมนูก่อน → **validate หลักการ "ไม่บังคับเลือก Slip ก่อนส่งรูป"**. ระบบ classify เอง = differentiator ที่ platform อนุญาต. [HIGH — /receiving-messages]

4. **Loading animation คือเครื่องมือลด perceived latency ที่สำคัญที่สุด** สำหรับ "แมวส้มกำลังคุ้ย…". เป็น typing indicator แบบ native (5–60 วิ, เฉพาะแชต 1:1, แสดงเฉพาะตอนผู้ใช้เปิดแชตอยู่). ใช้คู่กับ OCR/parse ที่ช้า. [HIGH — /use-loading-indicator]

5. **Quick Reply เหมาะที่สุดกับ one-tap uncertainty resolution** (≤13 ปุ่ม, เฉพาะ iOS/Android). ตอบ ambiguity โดยไม่ต้องเปิด LIFF. camera/cameraRoll เป็น quick-reply action ได้ → เป็น **accelerator** ("อยากถ่ายสลิปเลยไหม") ไม่ใช่ **gate**. [HIGH — /using-quick-reply]

6. **Flex carousel = "financial inbox" ที่ดี** สำหรับ review cards แต่มีเพดาน (JSON ≤30KB/carousel, จำนวน bubble จำกัด) → ต้อง paginate. งานที่ต้อง edit หลาย field / เปรียบเทียบ / ดู chart → **LIFF**. [HIGH/MEDIUM — /flex-message-elements]

7. **Contextual Rich Menu ทำได้จริง** ด้วย 2 กลไก: (ก) **rich menu switch action** = สลับ tab ฝั่ง client ไม่มี server round-trip; (ข) **per-user rich menu** = set เมนูเฉพาะคนตาม state. แต่ต้องระวัง cognitive cost ของการ "เปลี่ยนเมนูใต้เท้าผู้ใช้". [HIGH — /switch-rich-menus, /use-per-user-rich-menus]

8. **Push discipline ถูกบังคับด้วยเงิน ไม่ใช่แค่มารยาท.** ทุก push = ต้นทุน + เสี่ยง block. "Pull-over-Push" จึงเป็น cost-control + retention พร้อมกัน. Push เฉพาะ anomaly / due / needs-review. [HIGH]

9. **แมวส้มควรเป็น "voice/presence layer" ไม่ใช่ปุ่ม/destination.** ตัวเลขและ review = serious tone เสมอ; persona เล่นได้เฉพาะ acknowledgement / onboarding / idle. แยก "character presence" ออกจาก "character button" — สองอย่างนี้ไม่ใช่สิ่งเดียวกัน. [MEDIUM]

---

## 2 · LINE Capability Map

ทุกแถวตรวจจาก **developers.line.biz** (official). Confidence = HIGH เว้นระบุเป็นอย่างอื่น.

| Capability | ทำได้จริง | Limitation ที่กระทบ UX | MaewSom use |
|---|---|---|---|
| **Webhook — message event** | รับ `text, image, video, audio, file, location, sticker` เข้ามาตรง ๆ; reply ได้ | ใน group/room `source.userId` อาจไม่มี | รากของ "ส่งมาได้เลย" — capture ทุกชนิดโดยไม่ต้องเมนู |
| **Webhook — postback event** | ปุ่มบน Flex/Rich Menu/Quick Reply ส่ง `data` กลับ webhook, reply ได้ | ต้องออกแบบ data schema เอง | ยืนยัน/แก้ category/settle แบบ 1 tap |
| **Webhook — follow/unfollow** | รู้เมื่อ add เป็นเพื่อน/บล็อก | unfollow = เสีย push channel | trigger onboarding; วัด churn |
| **Reply API** | **ฟรี ไม่นับ quota**; ≤5 message objects/1 reply | token ใช้ครั้งเดียว **หมดอายุ ~1 นาที** | ช่องทางตอบหลัก — ต้องตอบใน window |
| **Push API** | ส่งเมื่อไหร่ก็ได้ | **นับ quota**; ฟรีในโหมด dev เท่านั้น | เฉพาะ notification ที่มี value จริง |
| **Multicast / Narrowcast / Broadcast** | ส่งหลายคน/แบ่ง segment | **นับ quota**; narrowcast มี delay/limit | ไม่ใช่งานหลักของ finance ส่วนตัว (1:1) |
| **Monthly quota** | มี free tier ต่อเดือน; เกินแล้ว error, ไม่ส่ง | JP: 200 / 5,000 / 30,000 ต่อ plan; **ไทยต่างจากนี้ → verify plan** [MEDIUM สำหรับตัวเลขไทย] | ตั้ง budget push ต่อผู้ใช้ต่อเดือน |
| **Loading animation** `POST /v2/bot/chat/loading/start` | typing indicator 5–60 วิ (ทวีคูณของ 5) | **เฉพาะ 1:1**; แสดงเฉพาะตอนผู้ใช้เปิดแชต; หายเมื่อมีข้อความใหม่ | "แมวส้มกำลังคุ้ย…" ระหว่าง OCR/parse |
| **Quick Reply** | ≤13 ปุ่ม, ทุก message type | **เฉพาะ iOS/Android** (ไม่มีบน PC); rich-menu-switch ใช้ในนี้ไม่ได้ | one-tap clarification, accelerator ถ่ายสลิป |
| **QR actions: camera / cameraRoll / location** | เปิดกล้อง/แกลเลอรี/แชร์พิกัดจากปุ่ม | quick-reply-only, มือถือเท่านั้น | ปุ่มลัด "ถ่ายสลิป / เลือกรูป" |
| **Flex Message — bubble** | layout อิสระ (box/text/image/button/icon/video) | video/scaling/maxWidth ต้อง LINE เวอร์ชันใหม่ (ระบุ altContent) | transaction card, review card, summary card |
| **Flex Message — carousel** | หลาย bubble เลื่อนแนวนอน | **JSON ≤30KB/carousel**; จำนวน bubble มีเพดาน (LINE reference — ตัวเลขที่มักอ้างคือ 12; **verify ก่อน build** [MEDIUM]); bubble ใน carousel ต้อง width เท่ากัน | "financial inbox" ของรายการที่ต้องตรวจ (paginate) |
| **Rich Menu — default** | เมนูล่างจอสำหรับทุกคน | image 2500×1686 หรือ 2500×843; chat-bar text ≤14 ตัวอักษร; **≤20 tappable areas** [HIGH/MEDIUM — SDK สะท้อน reference] | navigation หลัก |
| **Per-user rich menu** `POST /v2/bot/user/{id}/richmenu/{id}` | set เมนูเฉพาะคน | ต้อง track state เอง | เมนูเปลี่ยนตาม onboarding/mode |
| **Rich menu alias + switch action** (`richmenuswitch`) | สลับ tab **ฝั่ง client ไม่มี round-trip** | ใช้ใน quick reply ไม่ได้ | tab สลับ "Capture / Insight" ทันที |
| **Postback / Message / URI / Datetime picker / Clipboard action** | ครบ; datetime picker = เลือกวัน/เวลา; clipboard = ก็อปข้อความ | URI action เปิด LIFF/เว็บได้ | เลือกวันครบกำหนดจ่าย, คัดลอกเลขบัญชี |
| **LIFF (web app ใน LINE)** | `getProfile`, LINE Login/openid, `openWindow`, `sendMessages`, `scanCodeV2`, `shareTargetPicker`, `closeWindow` | `scanCodeV2` ต้องเปิด Scan QR (iOS 14.3+/Android/WebRTC); ข้อความที่ส่งด้วย `liff.sendMessages()` **ไม่ยิง webhook** | dashboard, edit หลาย field, chart, จัดการ accounts/commitments |
| **LINE Login / profile** | ยืนยันตัวตน, ดึง displayName/รูป/uid | ต้องขอ consent | ผูกบัญชีผู้ใช้กับ ledger |

---

## 3 · Benchmark LINE OA (ไทยก่อน แล้ว JP/TW)

> **คำเตือน anti-hallucination:** ตัวเลข follower/MAU ของ OA ไทยเกือบทั้งหมด **ไม่มีการเปิดเผยที่ตรวจสอบได้**. ช่องตัวเลขจึงเป็น UNVERIFIED เว้นที่มี source ตรง. บทเรียนด้าน interaction เชื่อถือได้กว่าตัวเลข.

| # | OA / service | ประเทศ | sector | ตัวเลข (source, confidence) | interaction ที่ใช้ | บทเรียนสำหรับ MaewSom |
|---|---|---|---|---|---|---|
| 1 | **SCB Connect** (@scbconnect) | TH | banking | UNVERIFIED (ผู้ใช้จำนวนมาก, ตัวเลขไม่เปิด) | **push แจ้งเงินเข้า-ออก** + แชตเช็กยอด/ถาม/แจ้งโอนผิด/ขอ statement/live agent [HIGH scb.co.th] | ต้นแบบใกล้ MaewSom ที่สุด: "เรื่องเงิน push เข้า LINE" ถูกยอมรับแล้ว; MaewSom ต่างตรงที่ **reconcile ข้าม-บัญชี** ไม่ใช่แจ้งบัญชีเดียว |
| 2 | **หมอพร้อม (Mor Prom)** — MoPH | TH | gov/health | **14.5 ล้านผู้ใช้** (LINE Thailand Awards 2021 "Best Govtech"; beartai อ้าง LINE [MEDIUM-HIGH]) | Rich Menu + Flex + LIFF (นัด/ผลตรวจ/ใบรับรอง) | OA เดี่ยว scale ระดับชาติได้; LIFF เหมาะกับงานหลาย field (นัด/เอกสาร) |
| 3 | **Krungthai NEXT / Connext** | TH | banking | UNVERIFIED | แจ้งเตือนบัญชีผ่าน LINE คล้าย SCB [MEDIUM iphonemod] | ยืนยันว่า "bank alert บน LINE" เป็น pattern มาตรฐานของไทย |
| 4 | **LINE MAN Wongnai** | TH | delivery/food/POS/wallet | ก่อตั้ง 2020 (merge); ตัวเลข MAU UNVERIFIED | app + OA; order ในแชต, tracking, wallet | chat-commerce + real-time status; แต่เป็น super-app ไม่ใช่ finance-personal |
| 5 | **LINE SHOPPING** | TH | e-commerce | UNVERIFIED | Rich Menu nav + Flex product cards + LIFF checkout | Flex card + LIFF สำหรับงานที่ต้องเลือก/เทียบ |
| 6 | **สำนักงานประกันสังคม (SSO)** | TH | gov | UNVERIFIED | OA บริการ/แจ้งสิทธิ [MEDIUM lycorp story] | ภาครัฐใช้ OA เป็น service channel — คนคุ้นกับ "OA ทางการ" |
| 7 | **การประปา / Waterworks** | TH | gov/utility | UNVERIFIED | แจ้งบิล/สถานะ [MEDIUM lycorp] | "bill/commitment reminder" เป็น use case ที่คนไทยรับได้ |
| 8 | **Decathlon TH** | TH | retail | case study (Relevant Audience/LINE) [MEDIUM] | broadcast + Rich Menu + MyShop | เน้น conversion ไม่ใช่ follower-count |
| 9 | **Madame Fin** | TH | retail/beauty | followers 5×, sales via LINE Ads +126% (LY Corp story [MEDIUM]) | LINE Ads + MyShop + OA | ตัวเลข "อัตราการเปลี่ยนแปลง" มี source; absolute count ไม่มี |
| 10 | **Rabbit LINE Pay / LINE Pay** | TH/regional | payment | LINE Pay users ~6.98M (2021, 4 ตลาด, company data [MEDIUM, เก่า]) | wallet ใน LINE | payment layer มีอยู่ แต่ MaewSom = **บันทึก/เข้าใจ** ไม่ใช่ payment rail |
| 11 | **K PLUS (Kasikorn)** | TH | banking | *เป็น app แยก ไม่ใช่ LINE OA* — ระบุเพื่อกันสับสน | — | เตือน: อย่าเทียบ MaewSom กับ mobile-banking app; คนละ surface |
| 12 | **เป๋าตัง (Paotang)** | TH | gov wallet | *เป็น app แยก (Krungthai) ไม่ใช่ OA หลัก* [กันสับสน] | — | ผู้ใช้ระดับสิบล้าน แต่เป็น standalone app — บทเรียนคือ "งานเงินซับซ้อนหนีจากแชตไป app เต็ม" |
| 13 | **LINE OA ญี่ปุ่น (banking/utility)** | JP | fintech | รวมภาพ: LINE JP 98M MAU (Mar 2025, LY Corp [HIGH]) | OA-first notification + LIFF mini-app | ตลาด JP โตกว่า: OA เป็น infra จริง — ยืนยัน viability ของ OA-first finance |

**ภาพรวมตลาด (มี source):**
- LINE Thailand MAU **~54 ล้าน** (30 ก.ย. 2025, LY Corp FY2025 Q2 Appendix) / ~56M (DataReportal ม.ค. 2025) — ~78% ประชากร, ~85% ผู้ใช้เน็ต [HIGH]
- **>70%** ของผู้ใช้เน็ตไทย follow แบรนด์ผ่าน OA อย่างน้อย 1 (DataReportal 2025/26 [MEDIUM-HIGH])
- Thailand มี **~3 ล้าน OA** (2019, LINE Corp PR); global **~13.38M OA** (2026, secondary [MEDIUM])
- เวลาใช้เฉลี่ย ~67 นาที/วัน (8x8 blog, secondary [LOW])

---

## 4 · Winning UX Patterns

| Pattern | Evidence / ตัวอย่าง | ข้อดี | ข้อเสีย | เหมาะกับ MaewSom |
|---|---|---|---|---|
| **A. Chat-first capture** | webhook รับทุก type ตรง ๆ [HIGH]; SCB Connect แชตเช็กยอดได้เลย | 0 tap เพิ่ม, ตรงกับพฤติกรรมพิมพ์ใน LINE | ต้อง classify แม่น | **ใช่ — หัวใจของ product** |
| **B. Rich Menu = navigation ("ไปดู")** | seobangkok: Thai biz ใช้ Rich Menu เป็น 1 ใน 4 เสา เพื่อนำทาง [MEDIUM] | ลด "หาเมนูไม่เจอ" | ถ้าใส่ capture จะขัดกับ A | **ใช่ — nav เท่านั้น** |
| **C. Progressive disclosure** | Quick Reply ถามเฉพาะที่ไม่แน่ใจ [HIGH capability] | ถามเท่าที่จำเป็น, ไม่เปิด form ใหญ่ | ถ้าถามบ่อยเกินจะน่ารำคาญ | **ใช่** |
| **D. Quick Reply for ambiguity** | 13 ปุ่ม, postback [HIGH] | 1 tap แก้ความไม่ชัด | มือถือเท่านั้น; ถ้า >13 ตัวเลือกไม่พอ | **ใช่ — core** |
| **E. Flex = compact state** | Flex bubble/carousel [HIGH] | สรุป transaction/review/เดือน ในแชต | 30KB/แก้ไม่ได้ในตัว | **ใช่ (read-mostly)** |
| **F. LIFF for complex** | LIFF getProfile/openWindow/chart [HIGH] | หลาย field, chart, edit, compare | เปิดช้ากว่า chat, ออกจาก flow | **ใช่ (เฉพาะเกิน breakpoint)** |
| **G. Deep link Flex→LIFF** | URI action บน Flex เปิด LIFF พร้อม context [HIGH] | ไม่ต้องหา context ใหม่ | ต้องส่ง context ผ่าน param | **ใช่** |
| **H. Proactive notification (คุ้มค่า)** | SCB Connect push เงินเข้า-ออก [HIGH] | รู้ทันเรื่องสำคัญ | push = quota + เสี่ยง block | **ใช่ (จำกัด)** |
| **I. One-tap correction** | postback action [HIGH] | แก้ category/account เร็ว | ต้องออกแบบ reversible | **ใช่ — "correction becomes memory"** |
| **J. Conversation memory** | (ฝั่ง backend ของทีมเอง) | ไม่บังคับพิมพ์ซ้ำ | ต้องจัดการ context/privacy | **ใช่** |

---

## 5 · Bad Patterns / Anti-patterns (สิ่งที่ MaewSom ต้องไม่ทำ)

1. **บังคับเลือก "Slip" บน Rich Menu ก่อนส่งรูป** — ขัด chat-first; webhook detect image ได้เอง. Rich Menu ที่มีปุ่ม "ส่งสลิป" ทำให้ผู้ใช้เข้าใจผิดว่า *ต้อง* กดก่อน. [หลักการ product + capability HIGH]
2. **ตอบทุกข้อความด้วย Flex การ์ดใหญ่** — เปลือง 30KB, รก, ช้าต่อ perceived. ธุรกรรมชัดเจน → text acknowledgement สั้นพอ.
3. **push ทุก transaction** — เปลือง quota (เสียเงิน) + spam → block. push เฉพาะ anomaly/due/needs-review.
4. **ยัด dashboard/analysis ทั้งหมดลง chat** — chat ไม่เหมาะกับตารางยาว/กราฟ/edit หลาย field → LIFF.
5. **ให้แมวส้มพูดกวนตอนแจ้งหนี้/เงินหาย** — persona บิด financial truth = เสีย trust.
6. **เปลี่ยน Rich Menu ใต้เท้าผู้ใช้บ่อย ๆ โดยไม่มีสัญญาณ** — per-user switch มากไป = สับสน "เมื่อกี้ปุ่มอยู่ตรงไหน".
7. **ตอบช้าเกิน reply-token window แล้วเงียบ** — token หมดใน ~1 นาที; ถ้าไม่ fallback เป็น push ผู้ใช้จะรู้สึกว่า "ส่งไปแล้วแมวส้มเงียบ".
8. **ใช้ Quick Reply แทน Rich Menu สำหรับ navigation ถาวร** — QR หายเมื่อพิมพ์ต่อ; nav ต้องอยู่คงที่.
9. **วัดความสำเร็จด้วย follower count** — Thai case studies เน้น conversion/retention; follower ที่ไม่ใช้ = ไม่มีค่า. [MEDIUM seobangkok/relevantaudience]

---

## 6 · MaewSom Killer Feature Candidates (12)

### KF-1 · "ส่งมาเลย เดี๋ยวแมวส้มคุ้ยให้" (universal capture)
- **problem:** เครื่องมือเดิมบังคับเลือกประเภทก่อนบันทึก
- **trigger:** ผู้ใช้ส่ง text/รูป/ไฟล์/statement เข้ามาดื้อ ๆ
- **surface:** webhook → loading animation → reply (text/Flex/Quick Reply)
- **flow:** รับ → detect ชนิด → classify → ตอบด้วย surface ที่เบาที่สุดที่ยัง correct
- **why LINE:** webhook รับทุก type + loading indicator ทำให้ "เข้าใจเอง" รู้สึกจริง [HIGH]
- **complexity:** สูง (classifier) · **risk:** classify ผิด → ต้องมี easy correction
- **hypothesis:** ผู้ใช้ >X% ส่ง input โดยไม่แตะ Rich Menu ภายในสัปดาห์แรก

### KF-2 · One-message finance logging ("ข้าว 120")
- **problem:** บันทึกรายจ่ายต้องเปิดแอป/ฟอร์ม
- **trigger:** พิมพ์ภาษาคน
- **surface:** chat reply + (ถ้าไม่ชัด) Quick Reply
- **flow:** parse → ถ้ามั่นใจ → บันทึก + acknowledge สั้น; ถ้าไม่ → ถาม 1 จุด
- **why LINE:** พิมพ์ในแชตคือ native behavior [HIGH]
- **complexity:** กลาง · **risk:** parse หมวดผิดเงียบ ๆ
- **hypothesis:** median taps ต่อการบันทึก 1 รายการ ≤ 1

### KF-3 · One-tap uncertainty resolution
- **problem:** ระบบเดาผิดเงียบ ๆ ทำลาย trust
- **trigger:** confidence ต่ำ (หมวด/บัญชี/บุคคล/จำนวน)
- **surface:** **Quick Reply** (2–4 ตัวเลือก)
- **flow:** "อันนี้คือค่าอะไร?" → [อาหาร][เดินทาง][อื่น ๆ] → postback → บันทึก + จำ
- **why LINE:** Quick Reply = 1 tap, ไม่ต้องเปิด LIFF [HIGH]
- **complexity:** ต่ำ-กลาง · **risk:** ถามบ่อยเกิน = รำคาญ
- **hypothesis:** clarification ที่ตอบด้วย QR สำเร็จ > ตอบด้วยพิมพ์เอง

### KF-4 · Financial inbox (รายการที่ต้องตรวจ)
- **problem:** ของที่ระบบไม่มั่นใจกองรวมกับที่มั่นใจ
- **trigger:** เปิด "รายการรอตรวจ" จาก Rich Menu หรือ push สรุป
- **surface:** **Flex carousel** (review cards) + postback [ยืนยัน/แก้]
- **flow:** การ์ดละรายการ → ปุ่มยืนยัน/แก้/ข้าม → paginate เมื่อเยอะ
- **why LINE:** Flex carousel = compact reviewable state ในแชต [HIGH]
- **complexity:** กลาง · **risk:** เกิน 30KB/เพดาน bubble → ต้อง paginate
- **hypothesis:** อัตราการเคลียร์ inbox ต่อ session

### KF-5 · Monthly mystery ("เงินหายไปไหน")
- **problem:** pie chart ไม่ตอบว่า "หายไปไหน" จริง ๆ
- **trigger:** ถามเป็นภาษาคน
- **surface:** reply text/Flex summary + ปุ่ม→LIFF (drill-down)
- **flow:** reconcile ยอดคาดเทียบจริง → อธิบายส่วนต่าง (เงินสด/ที่ยังไม่ match) ก่อน แล้วค่อยกราฟ
- **why LINE:** ตอบเป็นบทสนทนา แล้ว deep-link ไป LIFF เมื่ออยากเจาะ [HIGH]
- **complexity:** สูง (reconciliation) · **risk:** อธิบายผิด = เสีย trust
- **hypothesis:** ผู้ใช้เข้าใจ "ส่วนต่าง" จาก reply โดยไม่ต้องเปิด LIFF > X%

### KF-6 · Statement trust check
- **problem:** statement/สลิปกับที่บันทึกไม่ตรง
- **trigger:** โยน statement (PDF/รูป) เข้ามา
- **surface:** loading animation → reply Flex สรุป match/ไม่ match/เงินสดหาย
- **flow:** parse → reconcile → รายงาน 3 กลุ่ม (ตรง/ไม่ตรง/หายไป) + ปุ่มแก้
- **why LINE:** ส่งไฟล์ในแชตได้ตรง + ตอบสรุปในแชต [HIGH]
- **complexity:** สูง · **risk:** parse statement หลายรูปแบบ; ไฟล์ใหญ่เกิน token window (>1 นาที) → reply-then-push
- **hypothesis:** เวลาเฉลี่ยจากส่ง statement → เห็นผล ≤ Y วินาที (มี loading)

### KF-7 · Future money (เดือนหน้าต้องจ่ายอะไร)
- **problem:** subscription/ผ่อน/บิล/หนี้ กระจัดกระจาย
- **trigger:** ถาม หรือ push ต้นเดือน/ก่อนครบกำหนด
- **surface:** Flex summary + datetime picker (เลื่อน/ตั้งเตือน)
- **flow:** รวม commitments → คาดยอดคงเหลือ → เตือนเฉพาะที่ due
- **why LINE:** datetime picker + push แบบมี value [HIGH]
- **complexity:** กลาง · **risk:** push บ่อย = spam
- **hypothesis:** อัตราเปิด push "due soon" > push ทั่วไป

### KF-8 · Correction becomes memory
- **problem:** แก้ครั้งเดียวแล้วระบบยังเดาผิดซ้ำ
- **trigger:** ผู้ใช้แก้ (postback/พิมพ์)
- **surface:** postback → reply ยืนยัน "จำแล้ว"
- **flow:** แก้ → เก็บ rule → ครั้งหน้า classify ตามที่แก้
- **why LINE:** 1-tap correction + acknowledgement ในแชต [HIGH]
- **complexity:** กลาง · **risk:** จำ rule ผิดบริบท
- **hypothesis:** อัตราการแก้หมวดเดิมซ้ำ ลดลงหลังแก้ครั้งแรก

### KF-9 · "Som talks when something matters" (push เฉพาะสำคัญ)
- **problem:** noise ทำให้ปิด/บล็อก
- **trigger:** anomaly / due / unknown / needs-review เท่านั้น
- **surface:** push (จำกัด) → Flex + ปุ่มจัดการ
- **flow:** จัด class notification, มี quiet default
- **why LINE:** เศรษฐศาสตร์ push บังคับวินัยนี้อยู่แล้ว [HIGH]
- **complexity:** ต่ำ (policy) · **risk:** เกณฑ์ anomaly ไว/ช้าเกิน
- **hypothesis:** block-rate ต่ำกว่าค่าเฉลี่ย OA เมื่อ push < N/สัปดาห์

### KF-10 · Contextual Rich Menu
- **problem:** เมนูเดียวไม่ตอบทุก state
- **trigger:** สลับ tab (switch action) หรือ state เปลี่ยน (per-user)
- **surface:** rich menu alias/switch + per-user rich menu
- **flow:** tab "Capture ↔ Insight" สลับ instant; onboarding mode เมนูต่างจากปกติ
- **why LINE:** switch action = client-side ไม่มี round-trip [HIGH]
- **complexity:** กลาง · **risk:** เปลี่ยนใต้เท้าผู้ใช้ = สับสน
- **hypothesis:** การใช้ tab ที่สองสูงพอจะคุ้มความซับซ้อน

### KF-11 · Snap-to-log (accelerator ไม่ใช่ gate)
- **problem:** บางคนอยากถ่ายสลิปทันที
- **trigger:** Quick Reply "📷 ถ่ายสลิป / 🖼 เลือกรูป"
- **surface:** camera / cameraRoll quick reply action
- **flow:** เสนอปุ่มลัด *หลัง*บริบทที่เหมาะ (เช่นเพิ่งพูดถึงสลิป) ไม่ใช่บังคับ
- **why LINE:** camera/cameraRoll เป็น QR action ได้ [HIGH]
- **complexity:** ต่ำ · **risk:** ถ้าโชว์ตลอด = กลายเป็น gate โดยพฤตินัย
- **hypothesis:** ปุ่มนี้เพิ่ม capture โดยไม่ลด text/direct-photo

### KF-12 · Reconcile-on-forward (bank alert → MaewSom)
- **problem:** คนไทยรับ alert เงินเข้า-ออกจาก OA ธนาคารอยู่แล้ว (SCB Connect ฯลฯ)
- **trigger:** ผู้ใช้ forward/แคปข้อความแจ้งเตือนธนาคารมาให้แมวส้ม
- **surface:** webhook (text/image) → parse → reconcile
- **flow:** อ่านข้อความ alert → จับคู่กับรายการ → ยืนยัน/เพิ่ม
- **why LINE:** พฤติกรรม "เรื่องเงินอยู่ใน LINE" มีอยู่แล้ว [HIGH scb.co.th]
- **complexity:** กลาง · **risk:** รูปแบบ alert หลายธนาคาร; privacy
- **hypothesis:** ผู้ใช้ที่ใช้ bank-OA alert ยินดี forward ให้แมวส้ม > X%

---

## 7 · Rich Menu IA — 3 architectures (ยังไม่เลือก winner)

> เริ่มจาก **Jobs To Be Done** ไม่ใช่ "6 ช่องใส่อะไร". CAPTURE อยู่ที่ **chat composer** เสมอ (ไม่ใช่ Rich Menu). Rich Menu = NAVIGATE/ACT/MANAGE.
> ข้อจำกัด: image 2500×1686 (แนะนำ grid 3×2 = 6) หรือ 2500×843 (แถวเดียว); API รับได้ **≤20 areas** ถ้าจะทำ grid ละเอียด.

### Option A — Utility-first (เน้นทำงานเสร็จ)
| cell | label | action | surface | เหตุผล / frequency / intent |
|---|---|---|---|---|
| 1 | รายการรอตรวจ | postback | Flex carousel | สูง — เคลียร์ inbox |
| 2 | สรุปเดือนนี้ | postback | Flex/LIFF | สูง |
| 3 | ต้องจ่ายเดือนหน้า | postback | Flex | กลาง |
| 4 | บัญชี/บัตร | URI | LIFF | กลาง |
| 5 | ค้นหา/ประวัติ | URI | LIFF | ต่ำ-กลาง |
| 6 | ตั้งค่า | URI | LIFF | ต่ำ |
- **ไม่ควรใส่:** ปุ่ม "ส่งสลิป/บันทึกรายการ" (capture อยู่ที่ composer), ปุ่มแมวส้ม

### Option B — Insight-first (เน้นเข้าใจ)
| cell | label | action | surface |
|---|---|---|---|
| 1 | เงินหายไปไหน | postback | reply+LIFF |
| 2 | สรุปเดือนนี้ | postback | Flex |
| 3 | แนวโน้ม/กราฟ | URI | LIFF |
| 4 | รายการรอตรวจ | postback | Flex carousel |
| 5 | commitments | postback | Flex |
| 6 | ตั้งค่า | URI | LIFF |
- **intent:** ผู้ใช้ที่มาเพื่อ "เข้าใจภาพรวม" · **ไม่ควรใส่:** capture, character

### Option C — Companion-first (เน้นความสัมพันธ์/ลื่นไหล) + tab switch
| tab | cell | label | action |
|---|---|---|---|
| **Tab 1 (Do)** | 1–2 | รอตรวจ / สรุปเดือน | postback |
| | 3 | ต้องจ่าย | postback |
| | 6 | → สลับไป Tab 2 | **richmenuswitch** |
| **Tab 2 (Explore)** | 1–2 | กราฟ / เงินหายไปไหน | URI/postback |
| | 3 | บัญชี/บัตร | URI→LIFF |
| | 6 | → กลับ Tab 1 | **richmenuswitch** |
- **why:** ใช้ switch action ให้ครบงานโดยไม่อัด 6 ช่อง · **risk:** ต้นทุนการเรียนรู้ 2 tab
- **ไม่ควรใส่:** ปุ่ม "แมวส้ม" เป็น destination — persona = voice layer ทั่วทั้ง flow ไม่ใช่ปุ่ม

**validate สมมติฐาน "Slip ไม่ควรเป็น Rich Menu pre-selection":**
- **สนับสนุน:** webhook detect image ได้เอง [HIGH]; chat-first เร็วกว่า; ปุ่ม slip สร้าง mental model ผิดว่า "ต้องกดก่อน".
- **หลักฐานคัดค้าน (falsify):** OA บางเจ้าใส่ camera quick-reply/ปุ่มลัดเพราะผู้ใช้ใหม่ไม่รู้ว่า "ส่งรูปมาเลยได้". → **เงื่อนไขที่ควรมีปุ่มลัด:** เฉพาะเป็น **Quick Reply accelerator ตามบริบท** (KF-11) หรือใน onboarding — **ไม่ใช่** Rich Menu ถาวรที่สื่อว่าเป็น gate. สรุป: หลักการยืนได้ แต่ให้ทางออกเป็น contextual accelerator.

---

## 8 · Message / Quick Reply / Flex / LIFF Matrix

| input ของผู้ใช้ | surface ที่ควรตอบ | เหตุผล (fewest taps + financial correctness) |
|---|---|---|
| A. "กาแฟ 75" | **text ack สั้น** (+ undo) | ชัดเจน → ไม่ต้องการการ์ด; ยืนยันเบา ๆ พอ |
| B. "โอนให้ต้น 500" | **text ack** + (ถ้า "ต้น" กำกวม) **Quick Reply** เลือกบุคคล | ระบุผู้รับถ้าซ้ำชื่อ |
| C. e-Slip (รูป) | **loading → Flex review card** + ปุ่มยืนยัน/แก้ | ต้องโชว์สิ่งที่อ่านได้ให้ตรวจ |
| D. statement PDF | **loading → reply-then-push Flex สรุป** (match/ไม่/หาย) | งานหนัก อาจเกิน 1 นาที → push ผลลัพธ์ |
| E. screenshot ธนาคาร | **loading → Flex/text** ยืนยันรายการที่จับได้ | เหมือน slip แต่ parse ข้อความ |
| F. "500" (ไม่ชัด) | **Quick Reply** "รายรับหรือรายจ่าย? ค่าอะไร?" | ambiguity → ถาม ไม่เดาเงียบ |
| G. "เดือนนี้หมดไปเท่าไหร่" | **text/Flex summary** + ปุ่ม→LIFF | ตอบตัวเลขในแชต, เจาะลึกใน LIFF |
| H. "เดือนหน้าต้องจ่ายอะไร" | **Flex list** + datetime | รายการ commitments อ่านง่ายเป็นการ์ด |
| I. "รายการนี้ไม่ใช่ค่าอาหาร" | **postback/Quick Reply** เลือกหมวดใหม่ → "จำแล้ว" | 1-tap correction → memory |

**breakpoint "chat เริ่มไม่เหมาะ → LIFF":** เมื่อ (ก) ต้อง edit ≥3 field พร้อมกัน, (ข) ต้องเห็นกราฟ/ตารางยาว, (ค) เปรียบเทียบหลายบัญชี/ช่วงเวลา, (ง) จัดการ list ที่ paginate เกินความสบายใน carousel. ต่ำกว่านี้ = chat + Flex + Quick Reply พอ.

---

## 9 · Notification Strategy (Pull-over-Push)

| class | push? | priority | CTA | quiet behavior | spam risk |
|---|---|---|---|---|---|
| informational (บันทึกสำเร็จ) | **ไม่** (ใช้ reply ack) | ต่ำ | — | เงียบเสมอ | — |
| action needed (ต้องยืนยัน) | เฉพาะค้างนาน | กลาง | เปิด inbox | รวมเป็น batch | กลาง |
| **anomaly** (ผิดปกติ) | **ใช่** | สูง | ตรวจทันที | ไม่ควร quiet | ต่ำ (มี value) |
| **due soon** (ใกล้ครบกำหนด) | **ใช่** | สูง | จ่าย/เลื่อน | เตือนครั้งเดียว/รายการ | ต่ำ |
| statement ready | เฉพาะที่ผู้ใช้ขอ | กลาง | เปิดผล | on-demand | ต่ำ |
| reconciliation complete | **ไม่** (รอผู้ใช้เปิด) | ต่ำ | — | pull | — |
| monthly insight | เฉพาะ opt-in | ต่ำ-กลาง | ดูสรุป | เดือนละครั้ง | กลาง |

**หลัก:** push ทุกครั้ง = เงิน (quota) + เสี่ยง unfollow. Default = **pull**; push เฉพาะสิ่งที่ "ถ้าไม่รู้ตอนนี้จะเสียหาย" (anomaly/due). ตั้ง budget push/ผู้ใช้/สัปดาห์และวัด block-rate.

---

## 10 · Character / Som Strategy

**แยกให้ชัด: "character presence" ≠ "character button".**

| จุดในระบบ | ควรมีแมวส้มแค่ไหน | tone |
|---|---|---|
| onboarding / greeting | **เต็มที่** (แนะนำตัว, สร้างความคุ้น) | เล่นได้ |
| acknowledgement (บันทึกสำเร็จ) | **เบา ๆ** (คำ/emoji สั้น) | เล่นได้เล็กน้อย |
| idle / small talk | มีได้ | เล่นได้ |
| **แสดงตัวเลข / review / reconcile** | **presence เท่านั้น ห้ามบิดเนื้อหา** | **serious, ชัด, ไม่กวน** |
| **anomaly / หนี้ / ใช้เกิน** | น้อยที่สุด | **serious, เห็นใจแต่ตรง** |
| error ของผู้ใช้ทางการเงิน | ไม่ล้อ | สุภาพ, ช่วยแก้ |

- **character = voice/visual layer ทั่ว flow**, ไม่ใช่ปุ่มบน Rich Menu หรือ destination.
- **financial truth เหมือนกันทุก persona** — เปลี่ยนน้ำเสียงได้ เปลี่ยนตัวเลข/การตัดสินใจไม่ได้.
- evidence: งาน character-in-chatbot ช่วย retention ได้เมื่อ *ไม่* ขวาง utility; ทำลาย trust เมื่อ character แทรกตอนผู้ใช้ต้องการความแม่นยำ [MEDIUM — generalized UX literature, ไม่มี Thai-specific number → treat as hypothesis]

---

## 11 · Recommended MVP Experiments (ไม่ต้อง implement)

1. **Capture-path test:** วัด % ผู้ใช้ที่ส่ง input โดยไม่แตะ Rich Menu ในสัปดาห์แรก → validate KF-1/chat-first.
2. **Clarify format test:** เทียบ Quick Reply vs พิมพ์เอง สำหรับ ambiguity → success rate + taps (KF-3).
3. **Latency-tolerance test:** ส่ง slip แล้ววัด abandonment เมื่อมี vs ไม่มี loading animation (KF-1/6).
4. **Inbox review test:** Flex carousel vs รายการ text — วัดอัตราการเคลียร์/ตรวจ (KF-4).
5. **Push-budget test:** เกณฑ์ anomaly/due ต่าง ๆ → วัด open-rate vs block-rate (KF-9).
6. **Rich Menu IA test:** A vs B vs C — วัด task success + การใช้ tab 2 (Section 7).
7. **Character tone test:** persona เล่น vs serious บนหน้า review — วัด trust/perceived accuracy (Section 10).
8. **Bank-forward test:** เชิญผู้ใช้ forward SCB/KTB alert → วัดความเต็มใจ + parse success (KF-12).

*(ทั้งหมดทดสอบด้วย prototype/Wizard-of-Oz ได้ ไม่ต้อง build เต็ม)*

---

## 12 · Open Questions (evidence ยังตอบไม่ได้)

1. **Thailand quota/pricing plan** ปัจจุบันของ LINE OA — ตัวเลข free-message ต่อเดือนต่างจาก JP; ต้องดู linebiz.com/th ก่อนวาง push budget. [ตัวเลขไทย = ยังไม่ verified]
2. **จำนวน bubble สูงสุดต่อ Flex carousel** ที่แน่นอนใน LINE Messaging API reference (มักอ้าง 12) — verify ก่อน design "financial inbox".
3. **Follower/MAU จริง** ของ OA ธนาคาร/รัฐไทย — ไม่มี public source; ต้องหา LINE Thailand Awards / case study ที่เปิดตัวเลข.
4. **ผู้ใช้เต็มใจ forward bank alert** ให้ third-party OA แค่ไหน (privacy) — ต้องทดสอบจริง.
5. **ประสิทธิผล persona กับกลุ่มไทย** โดยเฉพาะบนหน้าเรื่องเงิน — ไม่มี Thai-specific study.
6. **พฤติกรรม LINE notification บนล็อกสกรีน** (มีผู้ใช้รายงานว่า alert เด้งเฉพาะตอนเปิดแอป LINE) — กระทบ reliability ของ push; ต้องตรวจกับ OS/setting จริง. [LOW — Pantip anecdote]

---

## 13 · Sources

**Official LINE docs (HIGH):**
- Receive messages / webhook events — developers.line.biz/en/docs/messaging-api/receiving-messages/
- Messaging API pricing — developers.line.biz/en/docs/messaging-api/pricing/
- Send messages (reply, ≤5 objects, loading note) — developers.line.biz/en/docs/messaging-api/sending-messages/
- Use quick replies (≤13, camera/cameraRoll/location, mobile-only) — developers.line.biz/en/docs/messaging-api/using-quick-reply/
- Display a loading animation (5–60s, 1:1) — developers.line.biz/en/docs/messaging-api/use-loading-indicator/
- Switch between tabs on rich menus (alias + switch action) — developers.line.biz/en/docs/messaging-api/switch-rich-menus/
- Use per-user rich menus — developers.line.biz/en/docs/messaging-api/use-per-user-rich-menus/
- Flex message elements (bubble/carousel/video) — developers.line.biz/en/docs/messaging-api/flex-message-elements/
- Messaging API reference (rich menu ≤20 areas via SDK mirror; per-user/alias endpoints) — developers.line.biz/en/reference/messaging-api/
- LIFF API reference (scanCodeV2, sendMessages no-webhook) — developers.line.biz/en/reference/liff/

**Company / case study (MEDIUM):**
- LINE Thailand MAU 54M (Sep 2025) — LY Corp FY2025 Q2 Appendix (via expandedramblings compilation)
- DataReportal/Meltwater 2025 — Thailand LINE ~56M, ~78% pop, >70% follow brand OA — meltwater.com/en/blog/social-media-statistics-thailand
- LINE Thailand for Business (SCB Connect, SSO, MoPH, Madame Fin +126%) — lycorp.co.jp/en/story/20260106/lineth_forbusiness.html
- 3M Thai OAs (2019) — linecorp.com/en/pr/news/global/2019/40
- SCB Connect (เงินเข้า-ออก, แชตเช็กยอด) — scb.co.th/th/personal-banking/digital-banking/scb-connect
- หมอพร้อม 14.5M / LINE Thailand Awards 2021 — beartai.com/brief/1000022
- LINE MAN Wongnai — en.wikipedia.org/wiki/LINE_MAN_Wongnai

**Independent / secondary (LOW):**
- LINE bot reply-token/quota fixes — conferbot.com/errors/line, /blog/line-bot-not-responding
- ~67 นาที/วัน — cpaas.8x8.com/en/blog/line-marketing-japan-thailand/
- LINE Thai OA usage patterns — seobangkok.com/blog/line-official-account-for-business...
- Pantip notification anecdote — pantip.com/topic/40598510

---

*จบรายงาน — research/architecture เท่านั้น ไม่มี implementation.*
