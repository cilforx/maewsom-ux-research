---
topic: liff-competitive-ux
date: 2026-09-18
status: synthesized
research_type: cross-model-synthesis
canonical: false
models_reviewed:
  - ChatGPT / GPT-5.6 Sol
  - Gemini independent run
  - GLM Flash
  - GLM 5.3
  - Claude / Opus 4.6
  - Gemini 3.8 Flash
  - Fable 5.1
primary_evidence_checked: true
owner_decision_required: true
---

# 01 — Cross-Model Findings

## Purpose

เอกสารนี้สังเคราะห์ independent research runs ทั้งหมดของ stream `liff-competitive-ux` โดยใช้หลัก:

> **Evidence wins, not model majority.**

การที่หลายโมเดลพูดเหมือนกันเพิ่ม “priority to verify” แต่ไม่ทำให้ claim กลายเป็น fact โดยอัตโนมัติ

---

# 1. Research Set Reviewed

1. ChatGPT — independent competitive UX pass
2. Gemini — independent LIFF competitive UX pass
3. GLM Flash — broad UX synthesis
4. GLM 5.3 — implementation-oriented UX synthesis
5. Claude Opus 4.6 — multi-file deep research package
6. Gemini 3.8 Flash — fintech UX + product strategy report
7. Fable 5.1 — LINE Messaging UX / platform architecture research

Fable 5.1 has the strongest source quality for current LINE platform mechanics because it explicitly anchors most platform claims to official LINE Developers documentation.

---

# 2. Highest-Confidence Cross-Model Findings

## Finding A — OCR / slip capture is table stakes, not the moat

### Cross-model signal
Nearly every run converges on the same strategic point:

- automated capture matters,
- manual-only entry causes friction,
- Thai users already operate in an e-Slip-heavy environment,
- but OCR by itself is not sufficient differentiation.

### Primary-evidence correction
MeowJot is materially more capable than several raw runs claimed. Current official/App Store sources show:

- automatic e-Slip expense logging,
- credit-card statement-file ingestion,
- auto-categorization,
- recurring entries,
- graphs,
- CSV export,
- subscriptions.

Therefore MaewSom must **not** position against an outdated “manual/basic MeowJot” strawman.

### Strategic implication
MaewSom differentiation must move upward from:

```text
capture → categorize
```

toward:

```text
capture
→ interpret financial meaning
→ reconcile against evidence
→ surface uncertainty
→ learn corrections
→ proactively explain what matters
```

### Confidence
**Very High**

---

## Finding B — LINE Chat and LIFF should have different jobs

### Cross-model signal
All serious runs converge on a hybrid architecture.

### Best synthesis

**LINE Chat is best for:**
- accepting text / image / audio / file input,
- lightweight acknowledgements,
- contextual clarification,
- urgent/high-value alerts,
- concise financial answers,
- directing the user to the exact next task.

**LIFF is best for:**
- multi-row review,
- multi-field editing,
- history/search/filter,
- reconciliation,
- account/debt management,
- charts/comparison,
- settings/security/subscription.

### Fable 5.1 contribution
Official LINE capability research makes this more than a design preference:

- webhook can receive common user message types directly,
- Quick Reply can resolve small ambiguities,
- Flex can show compact structured state,
- LIFF is available for complex spatial tasks.

### Product principle

> **Chat handles attention and lightweight decisions. LIFF handles structured work.**

### Confidence
**Very High**

---

## Finding C — Rich Menu should navigate, not gate capture

### Cross-model signal
Several runs initially placed “upload slip” or “capture” in Rich Menu.

Fable 5.1 challenges this with stronger platform reasoning:

- a user can already send an image/file/text directly,
- requiring a pre-selection step adds unnecessary friction,
- Quick Reply camera/camera-roll actions can act as contextual accelerators.

### Recommended interpretation

Rich Menu should primarily expose persistent destinations/actions such as:
- items needing attention,
- summary,
- commitments,
- accounts/cards,
- history,
- settings.

It should **not teach users that they must tap “Slip” before sending a slip**.

### Confidence
**High**

---

## Finding D — Review Inbox / uncertainty handling is a core product pattern

### Cross-model signal
Review Inbox appears repeatedly across ChatGPT, Gemini, GLM, Opus, and Gemini 3.8.

### Primary evidence
Current Copilot documentation confirms:
- unreviewed transaction state,
- a dedicated review workflow,
- bulk review capability,
- machine-learning categorization that learns from reviewed transactions.

Monarch provides review/rules patterns, although generalized accounting reconciliation is not native.

### Important refinement
The research does **not** justify a hard-coded confidence threshold such as 90%.

The product principle should be:

> **Automate what is sufficiently certain and reversible; route ambiguity to review.**

Not:

> “90% always auto-accept.”

### Confidence
**High**

---

## Finding E — Reconciliation is a stronger differentiation candidate than OCR

### Cross-model signal
ChatGPT, Gemini 3.8, Opus, GLM and others repeatedly identify reconciliation as strategic white space.

### Primary evidence
Official Monarch documentation explicitly notes that Monarch does not have a reconciling feature for manual-vs-synced transactions.

Piggipo provides strong card-statement checking concepts, but it is credit-card-centric rather than a generalized cross-account truth engine.

MeowJot now supports credit-card statement ingestion and comparison, so “statement support” alone is **not** unique.

### MaewSom opportunity
The stronger concept is:

> **Cross-source financial truth reconciliation**

across:
- e-Slips,
- statements,
- manual/cash entries,
- own-account transfers,
- credit-card liabilities,
- repayments,
- refunds/reimbursements,
- recurring commitments.

### Confidence
**High**

---

## Finding F — Correct financial semantics are non-negotiable

### Cross-model signal
Nearly all higher-quality runs emphasize the damage from treating every movement as “income” or “expense”.

### Primary evidence
Copilot officially distinguishes:
- Income,
- Internal Transfer,
- Regular transaction.

Its documentation explicitly treats monthly credit-card payments as Internal Transfers when the underlying purchases are already accounted for.

Piggipo officially models:
- billing cycle / statement date,
- due date,
- installment,
- early/extra payment,
- card-specific spending.

### MaewSom principle

```text
economic event ≠ cash movement
```

Examples:
- own-account transfer ≠ expense,
- credit-card payment ≠ second expense,
- refund ≠ ordinary earned income,
- reimbursement ≠ ordinary income,
- card purchase creates spending + liability,
- liability settlement moves cash to reduce debt.

### Confidence
**Very High**

---

## Finding G — Trust should be provenance-based, not a single “Verified” badge

### Cross-model signal
Trust/provenance is present in ChatGPT, Opus, Gemini, GLM and Fable.

### Best synthesis
Trust is multidimensional:

1. **Source**
   - statement
   - verified slip
   - uploaded image
   - chat/manual
   - connected source

2. **Interpretation**
   - exact
   - matched
   - rule inferred
   - AI inferred

3. **Review**
   - user confirmed
   - auto accepted
   - needs review

4. **Freshness**
   - “updated through…”
   - last statement date
   - new activity since last verified source

### UX rule
Prefer explaining:

> “ยอดมาจาก Statement แต่หมวดนี้ส้มเป็นคนเดา”

over:

> “AI confidence 87%”

### Confidence
**Very High**

---

## Finding H — Deep-linked Chat → LIFF continuation is better than generic Home routing

### Cross-model signal
Strong agreement across ChatGPT, Gemini 3.8, Opus and Fable.

### Pattern
If the user receives:

> “มี 3 รายการที่ต้องตรวจ”

the CTA should open:

```text
LIFF → relevant Review task
```

not:

```text
LIFF Home → menu → Review → item
```

### Requirement candidate
Every actionable message should carry enough route/task context to continue the exact workflow.

### Confidence
**Very High**

---

## Finding I — Persona helps only when it never distorts financial gravity

### Cross-model signal
All models that analyzed personality reach similar conclusions.

### Best synthesis
Persona should be a **voice/presence layer**, not a destination.

Use stronger personality for:
- onboarding,
- acknowledgement,
- low-stakes education,
- success/celebration,
- small talk.

Reduce personality for:
- debt,
- liquidity risk,
- reconciliation discrepancy,
- security/privacy,
- destructive or consequential changes.

### Important refinement
“Serious Mode” is well-supported as a design principle.

Specific numeric triggers such as:
- discrepancy > 500 THB,
- variance > 5,000 THB,

are **not validated**.

### Confidence
**High**

---

## Finding J — Push discipline is both UX and economics

### Primary LINE evidence
LINE officially states:

- Reply messages are not counted toward the subscription message count.
- Push / multicast / broadcast / narrowcast are counted.
- Up to five message objects can be sent in one request.
- Reply tokens are single-use and should be used as soon as possible; use beyond one minute is not guaranteed.
- Thailand has region-specific OA pricing.

### Implication
MaewSom should architect for:

> **reply-first, push-intentional**

not because “push is bad”, but because:
- it costs quota/money,
- it consumes user attention,
- excessive pushes increase retention risk.

### Confidence
**Very High**

---

# 3. Important Corrections to Raw Research

## MeowJot

### Raw-model error
Several runs described MeowJot as:
- manual-heavy,
- simple OCR,
- no statement support,
- limited automation.

### Corrected view
Current official/product sources support:
- automated e-Slip logging,
- credit-card statement-file logging,
- auto-categorization,
- recurring entries,
- export/reporting,
- subscription tiers.

Therefore:
- “Statement support” alone is not a MaewSom differentiator.
- “Cat + automation” is not a MaewSom differentiator.

What remains promising is **cross-account reconciliation + richer financial semantics + LINE-native interaction + uncertainty/provenance + persistent assistant memory**.

---

## Nabtang

Current App Store listing explicitly says:

> type, speak, or scan a slip, with automatic categorization.

Therefore manual-only/community-centric descriptions are outdated or unsupported.

---

## BooJot

Current App Store listing explicitly includes:
- automatic slip reading,
- monthly budgets,
- monthly/yearly summaries,
- CSV/Excel/PDF/image export,
- Gold/Platinum subscriptions.

Manual-only/no-automation descriptions are incorrect.

---

## Piggipo

Official product/FAQ supports:
- billing cycle,
- due date,
- statement checking,
- installment,
- extra/advance payment,
- credit-card-specific management.

Its most important MaewSom lesson is **financial semantics**, not receipt OCR.

---

# 4. Findings That Are Important but Still Need User Testing

These are not answerable by secondary research alone.

## 4.1 Traditional LIFF Home vs contextual workspace

Two competing models remain:

### Model A — traditional Home
Persistent 4–5 tab shell with:
- Overview
- Review
- Transactions
- Accounts
- Profile

### Model B — LINE as relational home
Most entries deep-link directly into:
- Review
- Reconciliation
- Transaction detail
- Insight

and “Home” is secondary.

**Status:** unresolved.

---

## 4.2 Review location: Flex vs LIFF

Fable suggests Flex carousel can act as a lightweight financial inbox.

Other runs put Review Inbox primarily in LIFF.

Best synthesis:

- one or very few simple items → Chat/Flex/Quick Reply,
- multi-item triage / editing → LIFF.

Exact breakpoint requires testing.

---

## 4.3 Confidence score visibility

Models disagree between:
- explicit percentage,
- High/Medium/Low,
- human language describing known vs inferred.

Recommendation for testing:
- do not expose percentage by default,
- prototype human-readable certainty first.

---

## 4.4 Notification cadence

“20:00 every day” is not evidence-backed.

Test:
- opt-in scheduled digest,
- event-triggered summary,
- quiet default,
- urgency-based exceptions.

---

## 4.5 Rich Menu architecture

Fable proposes three viable IA approaches:
- Utility-first,
- Insight-first,
- Companion/tab-switch.

No winner should be selected from secondary research alone.

---

# 5. Market White-Space Hypothesis After Corrections

The surviving differentiation hypothesis is narrower and stronger than the original:

```text
LINE-native interaction
+ multimodal financial ingestion
+ accounting-aware semantics
+ cross-source reconciliation
+ provenance / uncertainty
+ low-friction correction and learning
+ proactive assistance
+ relationship memory
```

No single competitor reviewed is verified to combine all of these as one Thai consumer product.

This remains a **white-space hypothesis**, not a monopoly claim.

---

# 6. What Research Changed

Before research, it was easy to assume:

> MaewSom = better expense tracker in LINE.

After synthesis:

> **MaewSom should behave more like a financial understanding and reconciliation layer that lives in LINE, using LIFF only when structured work is needed.**

That distinction should drive all subsequent IA and UX decisions.

---

# 7. Sources Used for Cross-Checking

## LINE official
- https://developers.line.biz/en/docs/messaging-api/pricing/
- https://developers.line.biz/en/docs/messaging-api/sending-messages/
- https://developers.line.biz/en/reference/messaging-api/
- https://developers.line.biz/en/docs/messaging-api/use-loading-indicator/
- https://developers.line.biz/en/docs/messaging-api/using-quick-reply/
- https://developers.line.biz/en/docs/messaging-api/switch-rich-menus/
- https://developers.line.biz/en/docs/messaging-api/use-per-user-rich-menus/
- https://developers.line.biz/en/reference/liff
- https://lineforbusiness.com/th/learning-hub/OA-B-01

## Thai financial / product sources
- https://www.meowjot.com/
- https://www.meowjot.com/features/auto-expense
- https://www.kasikornbank.com/th/News/Pages/MeowJot.aspx
- Nabtang App Store listing
- BooJot App Store listing
- https://www.piggipo.com/
- https://www.piggipo.com/faqs

## Global product sources
- https://help.copilot.money/en/articles/3971267-transaction-types
- https://help.copilot.money/en/articles/10671434-credit-card-payment-transactions
- https://help.copilot.money/en/articles/11157550-quick-start-guide
- https://help.monarchmoney.com/hc/en-us/articles/360058441811-Manual-transactions

## Thailand Open Data
- https://www.bot.or.th/th/news-and-media/news/news-20251110.html
- https://www.bot.or.th/th/financial-innovation/digital-finance/open-data.html

---

# 8. Synthesis Status

**Cross-model synthesis:** Complete  
**Primary-source verification:** Sufficient for architecture-level direction  
**Remaining disputed claims:** Tracked in `02_disputed-claims.md`  
**Next artifact:** `03_design-implications.md` → Owner Direction
