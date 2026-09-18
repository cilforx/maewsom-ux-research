---
topic: liff-competitive-ux
date: 2026-09-18
researcher: ChatGPT
model: GPT-5.6 Sol
status: raw
research_type: independent-pass
canonical: false
---

# MaewSom LIFF Competitive UX Research — Independent Pass

## Objective

หา UX patterns, competitive gaps และ interaction architecture สำหรับ MaewSom โดยไม่พยายามพิสูจน์ว่า product hypothesis เดิมถูกต้อง.

Scope ครอบคลุม 5 กลุ่ม:

1. Thai direct personal finance
2. Thai banking / fintech
3. Global personal finance / budgeting
4. AI / conversational finance
5. LINE / MINI App ecosystem

รวม reference ประมาณ 50 products/cases.

---

# Executive Findings

## 1. OCR / e-Slip / auto-categorization เป็น baseline มากขึ้นแล้ว

คู่แข่งไทยอย่าง MeowJot, Nabtang, รับจ่ายจด, BooJot และ Save Money ต่างขยับไปทาง OCR, slip/receipt ingestion, voice/text capture, auto-category หรือ recurring workflows.

### Implication

MaewSom ไม่ควรแตกต่างด้วย proposition แบบ:

> ส่งสลิปมา แล้ว AI จดให้

อย่างเดียว.

ทิศทางที่น่าสนใจกว่าคือ:

> Multi-source ingestion → financial interpretation → reconciliation → ask only when ambiguous → remember corrections → proactively assist.

---

## 2. Cat + finance ไม่ unique

MeowJot ใช้ cat branding, automation, engagement/streak และ premium อยู่แล้ว และตลาดมี character-driven finance มากขึ้น.

### Implication

Persona ของ MaewSom ต้องสร้าง utility ผ่าน memory เช่น:

- จำคู่โอน
- จำ account relationships
- จำคำเรียกเฉพาะ
- จำ recurring behavior
- จำ correction เดิม
- รู้ว่าเมื่อใดควรถามหรือไม่ควรถาม

> Relationship should increase financial usefulness.

---

## 3. Financial semantics + reconciliation มีโอกาสแตกต่างกว่า OCR

Real-world finance ไม่ได้มีแค่ income/expense.

ต้อง model:

- internal transfer
- credit-card purchase
- credit-card payment
- installment
- refund
- cashback
- debt repayment
- loan
- duplicate
- pending/missing transaction

Piggipo เป็น reference ไทยที่สำคัญด้าน credit-card semantics.

### Product opportunity

แทนที่จะจบที่:

> capture → categorize → report

MaewSom ควรสำรวจ:

> capture → interpret → reconcile → resolve ambiguity → trustworthy financial state

---

## 4. AI finance กำลังเปลี่ยนจาก reactive Q&A → proactive assistant

Reference สำคัญ:

- Rocket Money / Rowan
- Origin AI Advisor
- Copilot Assistant
- Erica
- Starling Assistant

Pattern ที่เกิดขึ้นคือ AI ไม่ใช่แค่ช่อง “Ask AI” แต่เป็น background behavior ที่ surface สิ่งสำคัญก่อนผู้ใช้ถาม.

### MaewSom implication

> LINE Chat = attention surface  
> LIFF = structured work surface

---

## 5. Financially consequential agent actions ต้องมี approval boundary

AI สามารถ automate interpretation ได้มาก แต่ action ที่มีผลต่อความจริงทางการเงินควร conservative.

Proposed rule:

> Automate interpretation aggressively.  
> Automate financial consequences conservatively.

---

## 6. LINE-native เป็น advantage เมื่อ Chat ↔ LIFF ต่อกันจริง

LINE BK และ LINE MINI App cases สนับสนุนแนวคิดลด app-switching / install friction.

แต่ LIFF ที่เป็น dashboard เว็บธรรมดาจะทิ้งข้อได้เปรียบนี้.

Stronger architecture:

> LINE = relationship + attention + lightweight decisions  
> LIFF = contextual financial workspace

---

# Competitive Landscape

## A. Thai Direct Personal Finance

1. **MeowJot** — auto e-receipt, credit-card statement workflows, auto categorization, cat engagement; direct competitor reference.
2. **Nabtang** — text/voice/slip capture; benchmark input friction.
3. **รับจ่ายจด** — voice, slip/receipt, import, budget, assistant.
4. **BooJot** — character finance + slip/OCR/automation + premium.
5. **Save Money** — OCR, recurring, summaries, export.
6. **Piggipo / Piggipo Go** — credit card, installment, refund, cashback, bill verification.
7. **Money Diary** — accounts/assets/liabilities/transfers; important transfer semantics lesson.
8. **Money Note Plus** — fast entry, summary, reminders; scanability lessons.
9. **Lumpsum** — tracking → financial planning/tax/debt/retirement.
10. **MeKinMeChai** — lightweight Thai-first tracker.

## B. Thai Banking / Fintech

1. SCB EASY
2. K PLUS
3. MAKE by KBank
4. Krungthai NEXT
5. Paotang
6. ttb touch
7. Krungsri app
8. Bangkok Bank Mobile Banking
9. TrueMoney
10. LINE BK

Key references:
- **MAKE**: Cloud Pocket / understandable money metaphor.
- **LINE BK**: architecture proof that financial tasks can live inside LINE.
- **Bank apps**: high-stakes confirmation and trust language.

## C. Global Personal Finance

1. YNAB
2. Monarch Money
3. Copilot Money
4. Rocket Money
5. Quicken Simplifi
6. PocketGuard
7. Wallet by BudgetBakers
8. Spendee
9. Emma
10. Honeydue

Key references:
- **Monarch**: aggregation + rules + transaction review; generalized accounting reconciliation is not its core.
- **Copilot**: transaction semantics and proactive assistant direction.
- **Simplifi / PocketGuard**: actionable “what can I spend?” abstractions.

## D. AI / Conversational Finance

1. Cleo
2. Albert / Genius
3. Origin AI Advisor
4. Rocket Money / Rowan
5. Monarch AI Assistant
6. Copilot Assistant
7. Starling Assistant
8. Bank of America Erica
9. Wells Fargo Fargo
10. Plum

Key references:
- **Cleo**: strong personality; proves conversational tone works but has high-stakes tone risk.
- **Rowan**: proactive messaging → action.
- **Starling Assistant**: action with approval boundary.
- **Copilot Assistant**: AI as background intelligence.

## E. LINE / MINI App Ecosystem

Reference cases include:
- Kameya Mannendo
- FANY / Yoshimoto
- VS Games
- Agu Hair
- Alpen
- J.League
- salon/member-card cases
- Pocket RD/game cases
- Makiya
- Nakagawa Masashichi

Main lesson:

> MINI App should complete a contextual task and feed the relationship back into LINE, not behave like a separate standalone website.

---

# MeowJot vs MaewSom

| Dimension | MeowJot direction | MaewSom opportunity |
|---|---|---|
| Entry | app-centric | LINE conversation-centric |
| Capture | e-receipt/manual/statement | chat/slip/text/statement/logs |
| Categorization | automated | automated + uncertainty routing |
| Statement | specific workflows | source-of-truth + reconciliation |
| Character | cat engagement | relationship + financial memory |
| Interaction | tracker-first | assistant-first |
| Insight | reports/planning | proactive message → action |
| Correction | app editing | Quick Reply or LIFF review |
| Semantics | growing | explicit economic semantics |
| Human-in-loop | general editing | ask only where ambiguity remains |

### Strategic warning

MaewSom must not become:

> “MeowJot บน LINE”

Differentiation should come from architecture and financial truth, not mascot or OCR alone.

---

# Chat vs LIFF Responsibility

| User Job | Preferred Surface |
|---|---|
| ส่งสลิป | Chat |
| พิมพ์ “จ่ายข้าว 120” | Chat |
| confirm หมวด 1 รายการ | Quick Reply / Chat |
| proactive alert | Chat / Flex |
| concise insight | Chat / Flex |
| review 20 รายการ | LIFF |
| แก้ transaction ซับซ้อน | LIFF |
| transaction history/search | LIFF |
| statement workflow | Chat entry + LIFF work |
| reconciliation | LIFF |
| account management | LIFF |
| settings | LIFF |
| subscription | LIFF |

### Key rule

A LINE message should deep-link to the exact LIFF task.

Avoid:

> Alert → LIFF Home → menu → task

Prefer:

> Alert → exact Review / Reconcile / Detail screen

---

# Financial Trust Model

A single “Verified” badge is insufficient.

Trust should represent multiple dimensions.

## 1. Source
- Statement
- Slip
- Manual
- Chat
- Imported data/API

## 2. Interpretation
- Exact
- Matched
- AI inferred
- Rule inferred

## 3. Review
- User confirmed
- Auto accepted
- Needs review
- Rejected

## 4. Freshness
- updated through date
- last statement date
- transactions after latest statement

Example:

> Amount exact from SCB Statement  
> Counterparty matched  
> Category AI-inferred  
> No review required

Another:

> Amount exact from slip  
> Counterparty uncertain  
> Needs review

UX should communicate:

> ส่วนไหนรู้จริง / ส่วนไหนส้มเดา

rather than exposing raw probability like “AI confidence 87%” by default.

---

# High-Value UX Patterns

1. Ambient transaction capture
2. Slip/OCR ingestion
3. Statement import
4. Voice/natural text capture
5. Merchant memory
6. Auto categorization
7. Confidence-based routing
8. Review Inbox
9. One-tap confirmation
10. Cheap correction
11. Undo
12. Duplicate detection
13. Transfer neutralization
14. Rich financial semantics
15. Source reconciliation
16. Data provenance
17. Freshness indicator
18. Recurring detection
19. Safe-to-spend abstraction
20. Spending anomaly
21. Personalized proactive insight
22. Conversational query over user data
23. Agent action + explicit confirmation
24. Deep-link task continuation
25. Chat → LIFF → Chat loop
26. Serious Mode
27. Relationship as memory

Highest relevance to MaewSom:

- confidence-based routing
- review inbox
- source reconciliation
- provenance
- rich transaction semantics
- Chat → LIFF deep links
- serious mode
- relationship as memory

---

# Competitor Pain Points → MaewSom Anti-Requirements

| Pain Point | Anti-Requirement |
|---|---|
| manual entry burden | automate capture wherever possible |
| wrong category | correction must be fast |
| transfer counted as expense/income | explicit transfer semantics |
| duplicates | source-aware deduplication |
| stale sync | show freshness |
| AI wrong without explanation | known vs inferred must be visible |
| too many notifications | attention-worthiness threshold |
| intrusive monetization | do not interrupt financial correction |
| data continuity issues | robust account/cloud continuity |
| cute persona during high-stakes problem | Serious Mode |

---

# White Space / Opportunity Areas

## 1. Reconciliation-first personal finance

Most consumer products optimize capture/category/report.

Potential MaewSom signature:

> capture → interpret → reconcile → resolve → trust

## 2. Uncertainty-native UX

Proposed behavior:

```text
Known → process quietly
Likely known → auto-process + reversible
Uncertain → ask simply
Conflict → open structured LIFF review
```

## 3. LINE-native Thai financial agent

Potential combination:

- Thai financial ingestion
- LINE-native conversation
- AI reasoning
- reconciliation
- persistent memory
- human confirmation only when necessary

## 4. Relationship + financial memory

Move from:

> cute mascot

toward:

> assistant that increasingly understands the user's financial world.

## 5. Provenance-first AI finance

Potential signature:

> ส้มรู้จากไหน  
> ส้มมั่นใจอะไร  
> ส้มเดาอะไร  
> คุณเคยยืนยันอะไรแล้ว

---

# Design Principles — Research Candidates

These are **not canonical requirements yet**.

1. LIFF is a workspace, not necessarily the relational home.
2. Deep-link directly to the task that caused the alert.
3. Automate certainty; surface ambiguity.
4. Correction must be cheaper than manual entry.
5. Preserve economic meaning.
6. Important numbers need provenance.
7. Reconciliation should be visible product value.
8. Persona intensity follows financial risk.
9. Relationship must increase usefulness.
10. Consequential action requires explicit approval.
11. Financial correctness must not be a premium privilege.
12. Attention outranks dashboard decoration.

---

# LIFF IA Hypothesis

Not visual design; not yet accepted.

```text
LIFF
├── Attention
│   ├── Needs Review
│   ├── anomalies
│   └── stale/incomplete data
├── Activity
│   ├── Transactions
│   ├── search/filter
│   └── recurring
├── Reconciliation
│   ├── Statements
│   ├── unmatched
│   ├── duplicates
│   └── balance differences
├── Money
│   ├── Accounts
│   ├── Cards
│   ├── Debt
│   ├── Goals
│   └── Overview
└── Profile/System
    ├── Persona
    ├── Relationship
    ├── Notifications
    ├── Privacy
    └── Subscription
```

Unresolved:

> Review/Reconciliation ควรเป็น permanent top-level navigation หรือเป็น contextual task เท่านั้น?

Needs usage testing.

---

# What This Means for LIFF

| Area | Implication | Confidence |
|---|---|---|
| Home | attention/state may matter more than charts | High |
| Navigation | shallow + deep-linkable | High |
| Review Inbox | candidate core differentiator | High |
| Transaction Detail | show source + semantic type + AI interpretation | High |
| Statement | not just file import | High |
| Reconciliation | first-class workflow | High |
| Accounts | source/freshness visible | High |
| Insights | actionable > decorative | High |
| Chat ↔ LIFF | continuous task | Very High |
| Persona | above core financial semantics | High |
| Relationship | should improve memory/context | Medium-High |
| Serious Mode | reduce playful tone under risk | High |
| Notifications | only actionable/valuable | High |
| Premium | monetize depth/automation, not correctness | Medium-High |
| Trust | provenance + review + freshness | Very High |

---

# Open Questions Requiring User Research

- คนไทยยอม upload full statement แค่ไหน?
- คำไทยสำหรับ reconciliation แบบไหนเข้าใจง่ายที่สุด?
- ควรถาม ambiguity ทันทีหรือ batch?
- “มี 4 รายการต้องตรวจ” รู้สึก helpful หรือเหมือนการบ้านบัญชี?
- ผู้ใช้ต้องการเห็น confidence score หรือเพียง known/inferred state?
- Serious Mode ควร trigger จาก risk, task type หรือทั้งคู่?
- Premium value ที่ยอมจ่ายจริงคืออะไร?
- LINE-native เพียงพอระยะยาวหรือ power users ต้องมี standalone web/app?

---

# Main Conclusion

MaewSom ไม่ควรแข่งขันหลักที่:

> ใครจดรายรับรายจ่ายง่ายกว่า

Direction ที่ควรพิสูจน์ต่อคือ:

> ใครเข้าใจ “ความจริงทางการเงิน” ของผู้ใช้ได้ต่อเนื่อง แม่นกว่า และรบกวนน้อยกว่า

Working hypothesis:

> **MaewSom is a persistent financial understanding layer living inside the user's LINE relationship, with LIFF used as a structured workspace whenever conversation alone is not enough.**

This remains a research hypothesis until cross-model synthesis + Owner Direction.
