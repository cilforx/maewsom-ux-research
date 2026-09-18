---
topic: liff-competitive-ux
date: 2026-09-18
status: synthesized
research_type: design-implications
canonical: false
ready_for_owner_direction: true
---

# 03 — Design Implications for MaewSom

## Purpose

แปลง research ที่ผ่าน synthesis แล้วให้เป็น **Owner-ready product direction candidates**.

This file is not yet canonical implementation specification.

---

# 1. Product Definition After Research

Do **not** define MaewSom as:

> แอปรายรับรายจ่ายใน LINE ที่มีแมว

Stronger product hypothesis:

> **MaewSom is a LINE-native financial understanding and reconciliation layer that captures financial evidence from conversation, preserves accounting meaning, resolves uncertainty with minimal user effort, and uses LIFF only when structured work is necessary.**

---

# 2. Interaction Architecture

## 2.1 LINE Chat — primary conversation and capture surface

### SHOULD
- accept text, image, audio and file input directly,
- interpret intent without requiring pre-selection,
- acknowledge successful capture briefly,
- ask one small clarifying question when necessary,
- answer concise personal-finance questions,
- surface meaningful alerts,
- deep-link into exact LIFF tasks.

### SHOULD NOT
- require “เลือกประเภทก่อนส่ง”,
- become a scrolling transaction database,
- show giant Flex cards for every normal action,
- ask users to confirm every obvious transaction,
- push every transaction proactively.

### Requirement candidate

> **User can send financial input directly to chat without first navigating a menu.**

**Evidence confidence:** Very High.

---

## 2.2 Quick Reply — ambiguity resolver

Use when:
- 2–5 likely answers,
- one tap can resolve uncertainty,
- no multi-field editing is required.

Examples:

```text
รายการนี้เป็นอะไร?
[ค่าใช้จ่าย] [ย้ายเงิน] [ออกให้ก่อน]
```

or

```text
หมายถึง “ต้น” คนไหน?
[ต้น-ที่ทำงาน] [ต้น-น้อง]
```

### Requirement candidate

> **Small ambiguity should be resolved in chat before escalating to LIFF.**

**Evidence confidence:** High.

---

## 2.3 Flex Message — compact state / preview / CTA

Good uses:
- transaction receipt summary,
- daily/weekly summary,
- anomaly preview,
- a few review candidates,
- upcoming commitments,
- CTA into LIFF.

Avoid:
- large editable lists,
- deep hierarchy,
- complex multi-field correction,
- pretending Flex is a full dashboard.

### Requirement candidate

> **Flex communicates state; LIFF performs complex work.**

**Evidence confidence:** High.

---

## 2.4 Rich Menu — persistent navigation

### Research-backed direction
Rich Menu should help users answer:

> “อยากไปทำอะไรต่อ?”

not:

> “ต้องกดอะไรก่อนถึงจะส่งข้อมูลได้?”

Recommended candidate jobs:
- รายการที่ต้องตรวจ,
- สรุป/ภาพรวม,
- ภาระที่กำลังจะถึง,
- บัญชี/บัตร,
- ประวัติ,
- ตั้งค่า.

### Do not permanently gate
- sending slips,
- sending text expense,
- sending statement file.

### Requirement candidate

> **Capture lives in the composer; Rich Menu primarily navigates persistent jobs.**

**Evidence confidence:** High.

---

## 2.5 LIFF — contextual structured workspace

LIFF should open when the task needs:
- multiple rows,
- multiple fields,
- comparison,
- filters/search,
- graph/table,
- reconciliation,
- account/debt structure,
- security/settings.

### Requirement candidate

> **LIFF is not a mandatory step for simple financial input.**

**Evidence confidence:** Very High.

---

# 3. Chat → LIFF Continuity

Every actionable message should carry route/task context.

Examples:

```text
“มี 3 รายการที่ต้องตรวจ”
→ /review?queue=needs-review
```

```text
“ยอด SCB ต่าง 1,240 บาท”
→ /reconcile/{statement_id}
```

```text
“รายการนี้อาจเป็นย้ายเงิน”
→ /transaction/{id}?focus=semantic-type
```

### Requirements

1. Do not route every CTA to generic Home.
2. Preserve task ID/context.
3. Handle stale/completed links gracefully.
4. After completion, return naturally to chat or next task.

**Confidence:** Very High.

---

# 4. Financial Data Lifecycle

Recommended canonical product lifecycle candidate:

```text
INPUT
↓
SOURCE DETECTION
↓
FACT EXTRACTION
↓
FINANCIAL SEMANTIC CLASSIFICATION
↓
MATCH / DEDUPLICATE
↓
UNCERTAINTY EVALUATION
↓
AUTO-ACCEPT OR REVIEW
↓
USER CORRECTION
↓
RULE / MEMORY UPDATE
↓
RECONCILIATION
↓
INSIGHT / ACTION
```

This is a major architectural difference from:

```text
input → category → chart
```

---

# 5. Financial Semantics

## Must model explicitly

At minimum:

- Income
- Expense
- Internal Transfer
- Credit Card Purchase
- Credit Card Payment
- Installment
- Refund
- Reimbursement / Advance-for-someone
- Debt Disbursement
- Debt Repayment
- Cashback / Reward
- Cash Withdrawal
- Adjustment
- Unknown / Needs Review

### Hard anti-requirements

- Never count an own-account transfer as spending by default.
- Never count a normal credit-card bill payment as a second expense when purchases were already recorded.
- Never treat a refund automatically as salary/income.
- Never create another expense when forgiving/closing a balance that was already economically expensed earlier.

**Confidence:** Very High.

---

# 6. Review & Uncertainty

## 6.1 Review Inbox

Review Inbox should be a **first-class workflow**, but research does not yet prove it must be a permanent bottom tab.

### Queue candidates
- unknown semantic type,
- duplicate conflict,
- unmatched transfer,
- uncertain merchant/category,
- source mismatch,
- reconciliation discrepancy.

## 6.2 Routing policy

Avoid hard-coded research thresholds.

Use a policy layer based on:
- consequence of being wrong,
- reversibility,
- confidence,
- transaction amount/materiality,
- user history/rules,
- source quality.

### Example

```text
high certainty + low consequence
→ auto-process

reasonable certainty + reversible
→ auto-process + easy undo

uncertain + simple
→ Quick Reply

uncertain + complex/multiple
→ Review Inbox

conflict with verified source
→ Reconciliation workflow
```

### Requirement candidate

> **Automate certainty; surface ambiguity.**

**Confidence:** Very High.

---

# 7. Reconciliation

## 7.1 Product role

Reconciliation should not be hidden only in backend plumbing.

It is user-visible value:

> “ข้อมูลที่ส้มมี ตรงกับหลักฐานเงินจริงแค่ไหน?”

## 7.2 Sources

Near-term:
- e-Slip,
- bank/credit-card statements,
- manually confirmed records,
- transaction images/files.

Future:
- Your Data / standardized financial data sharing adapters when practically available.

## 7.3 Reconciliation states

Suggested conceptual states:

- matched,
- unmatched source item,
- recorded but not found in source,
- duplicate,
- balance variance,
- pending/unclear,
- resolved adjustment.

### Critical rule

A “true-up” must not silently destroy semantic history.

If a discrepancy cannot be explained, represent it explicitly rather than pretending the system knows what the missing spending was.

### Requirement candidate

> **Reconciliation corrects financial truth without fabricating semantic certainty.**

**Confidence:** Very High.

---

# 8. Trust / Provenance Model

Do not use one universal “Verified” badge.

Each important record should be able to answer:

### Source
Where did this come from?

### Fact certainty
Which fields are exact from evidence?

### Interpretation
Which fields were inferred?

### Review
Has the user confirmed it?

### Freshness
How current is this view?

Example:

```text
Source: SCB statement
Amount: exact
Date: exact
Merchant: normalized
Category: AI inferred
Semantic type: user confirmed
Included through: 31 Aug 2026
```

### Requirement candidate

> **Important financial numbers require provenance and freshness.**

**Confidence:** Very High.

---

# 9. Notification Architecture

## 9.1 Technical/economic principle

Official LINE evidence supports:

> **reply-first, push-intentional**

because replies are not counted toward plan message usage while push-style sends are counted.

## 9.2 Push candidates
- payment/debt due risk,
- potentially material anomaly,
- review backlog that genuinely requires attention,
- user-requested reminder,
- completion of a long-running user-requested task when reply window is unavailable.

## 9.3 Avoid
- push after every normal transaction,
- generic engagement spam,
- fixed daily push without opt-in/value.

### Open variable
Digest frequency/time must be user preference or experiment, not hard-coded from research.

**Confidence:** Very High for principle; Medium for cadence.

---

# 10. Persona / Serious Mode

## Persona is a layer, not financial logic

The same transaction truth must survive every persona.

### Playful allowed
- onboarding,
- normal acknowledgement,
- positive reinforcement,
- low-stakes education,
- idle/small talk.

### Serious required
- debt/liquidity warning,
- reconciliation discrepancy,
- data/privacy/security,
- destructive actions,
- consequential financial decisions.

### Important
Do not hard-code Serious Mode purely from a THB threshold before testing.

Use event/risk type first; materiality can become a configurable factor later.

### Requirement candidate

> **Persona intensity follows financial consequence, never the other way around.**

**Confidence:** High.

---

# 11. Correction → Memory

When a user corrects:

```text
merchant
category
counterparty
account relation
semantic type
recurring status
reimbursement relation
```

the system should be able to learn a deterministic or probabilistic preference.

But never create an over-broad permanent rule without:
- appropriate scope,
- reversibility,
- visibility/editability.

### Pattern

```text
“เปลี่ยนเป็น ค่าเดินทาง”
→ “ใช้กับร้านนี้ครั้งต่อไปด้วยไหม?”
[จำร้านนี้] [ครั้งนี้เท่านั้น]
```

### Requirement candidate

> **A correction should reduce future correction work.**

**Confidence:** High.

---

# 12. Monetization Boundary

Research supports one strong principle:

> **Financial correctness must not be paywalled.**

Free users must be able to:
- correct wrong transaction meaning,
- resolve duplicates,
- fix amounts/dates,
- classify transfers correctly,
- undo mistakes,
- preserve ledger truth.

Premium candidates may include:
- deeper automation,
- advanced reconciliation convenience,
- extended history/export,
- advanced forecasting,
- more accounts,
- household features,
- richer personalized insight,
- premium persona/relationship content.

Exact pricing is not established.

**Confidence:** Medium-High.

---

# 13. Preliminary LIFF IA — Do Not Lock Visual Navigation Yet

Research supports these **domains**, but not their final tab positions:

```text
Attention / Review
├── Needs Review
├── anomalies
└── unresolved source conflicts

Activity
├── transactions
├── search/filter
├── recurring
└── details/splits

Reconciliation
├── statements
├── matches
├── unmatched
├── duplicates
└── balance variance

Money Structure
├── bank/cash accounts
├── credit cards
├── BNPL/debt
├── commitments
└── goals/budgets

System / Relationship
├── category & learned rules
├── persona/relationship
├── notifications
├── privacy/security
└── subscription
```

### Unresolved navigation choice

Do **not** yet decide:
- 5 bottom tabs,
- Review as permanent tab,
- Dashboard Home as default screen.

Those require task-frequency/user testing.

---

# 14. Core User Flows to Prototype Next

## Flow 1 — Direct slip capture

```text
Send slip in Chat
→ extract facts
→ detect duplicate
→ classify semantics
→ if clear: short acknowledgement
→ if simple ambiguity: Quick Reply
→ if complex: Review task
```

## Flow 2 — Natural language cash entry

```text
“ข้าว 75”
→ parse
→ save
→ short ack + undo
```

## Flow 3 — Own-account transfer

```text
outgoing evidence
+ matching incoming evidence
→ propose Internal Transfer
→ one-tap confirm if needed
→ exclude from income/expense
```

## Flow 4 — Credit card

```text
purchase
→ expense + liability

bill payment
→ asset-to-liability transfer
→ no second expense
```

## Flow 5 — Statement reconciliation

```text
upload statement
→ parse source
→ match records
→ show matched / missing / conflicts
→ resolve
→ update verified-through state
```

## Flow 6 — Review Inbox

```text
needs-review queue
→ confirm / correct / mark transfer / merge duplicate
→ optional rule/memory
→ undo
→ next item
```

## Flow 7 — Proactive alert

```text
meaningful condition
→ concise LINE message
→ exact deep link
→ LIFF task
→ completion
→ return to Chat
```

---

# 15. Owner Direction Candidates

The evidence is strong enough to recommend the following for Owner acceptance:

### OD-C1
**MaewSom is Chat-first for capture/attention and LIFF-first for structured work.**

### OD-C2
**Rich Menu is persistent navigation, not a required capture pre-step.**

### OD-C3
**Quick Reply resolves small ambiguity; Flex summarizes state; LIFF handles complex review/editing.**

### OD-C4
**Reconciliation is a first-class MaewSom product capability.**

### OD-C5
**Financial semantics must distinguish economic events from money movements.**

### OD-C6
**Trust UX uses provenance + inference + review + freshness, not one generic Verified state.**

### OD-C7
**Uncertainty is routed; AI should not silently pretend ambiguous interpretation is fact.**

### OD-C8
**Actionable Chat CTAs deep-link to exact LIFF tasks, not generic Home.**

### OD-C9
**Persona must enter Serious Mode for high-consequence finance and never alter financial truth.**

### OD-C10
**Messaging architecture is reply-first / push-intentional.**

### OD-C11
**Corrections should become scoped, reversible memory/rules.**

### OD-C12
**Financial correctness and correction cannot be paywalled.**

---

# 16. Explicitly Deferred Decisions

Do not lock yet:

- exact LIFF Home layout,
- exact bottom-nav tabs,
- Review as permanent tab vs contextual route,
- confidence percentage display,
- numeric auto-accept threshold,
- Serious Mode THB threshold,
- Daily Digest time/frequency,
- exact premium price,
- relationship-stage visual unlocks,
- LINE-group/shared-expense feature,
- standalone app/web expansion.

These belong to Owner prioritization + prototype/user testing.

---

# 17. Next Step

If Owner accepts OD-C1 through OD-C12:

```text
Synthesis
→ Owner Direction
→ Core IA rules
→ Core user-flow specs
→ Low-fidelity prototype
→ User test
→ Navigation decision
→ Visual design
```
