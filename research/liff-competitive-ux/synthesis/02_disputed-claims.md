---
topic: liff-competitive-ux
date: 2026-09-18
status: cross-checked
research_type: disputed-claims-register
canonical: false
---

# 02 — Disputed Claims Register

## Rule

> **Evidence wins, not model majority.**

Status values:

- **RESOLVED** — primary/current source resolves the claim.
- **PARTIALLY VERIFIED** — core claim supported, exact implementation/number not fully supported.
- **OPEN** — insufficient evidence; requires more evidence or user testing.
- **REJECTED** — contradicted by stronger/current evidence.

---

# A. LINE Platform Claims

| ID | Claim | Status | Resolution |
|---|---|---|---|
| LINE-01 | Reply messages count against OA message quota | **REJECTED** | Official LINE pricing says Reply messages are **not counted**. Push/multicast/broadcast/narrowcast are counted. |
| LINE-02 | One reply can contain up to 5 message objects | **RESOLVED** | Official Send Messages / API reference: max 5 message objects per request. |
| LINE-03 | replyToken lasts exactly 1 minute | **PARTIALLY VERIFIED** | Official reference says use within 1 minute; use beyond one minute is not guaranteed. Do not architect around an exact guaranteed TTL. |
| LINE-04 | Loading animation works 5–60 sec in 1:1 chat | **RESOLVED** | Official docs: 5–60 sec, 1:1 only, visible only if user is currently viewing the chat. |
| LINE-05 | Quick Reply supports up to 13 buttons | **RESOLVED** | Official docs: max 13. |
| LINE-06 | Quick Reply is iOS/Android only | **RESOLVED** | Official docs explicitly state iOS/Android support. |
| LINE-07 | Camera/camera-roll/location actions are Quick Reply-only | **RESOLVED** | Official Actions/Quick Reply docs confirm. |
| LINE-08 | Rich menu switch can be used in Quick Reply | **REJECTED** | Official docs: rich-menu switch action is available only on rich menus. |
| LINE-09 | Per-user Rich Menu exists | **RESOLVED** | Official endpoint/documentation confirms per-user rich menu and immediate precedence over default. |
| LINE-10 | Rich Menu supports up to 20 tappable areas | **RESOLVED** | Messaging API reference: max 20 area objects. |
| LINE-11 | Rich Menu is available on LINE PC | **REJECTED** | Official overview says Rich Menu is unavailable on LINE for PC. |
| LINE-12 | Flex carousel max is definitely 12 bubbles | **OPEN** | Do not hard-code from model output until the current API schema/reference is verified at implementation time. |
| LINE-13 | Flex carousel is always the right Review Inbox | **OPEN** | Platform supports carousel, but product breakpoint vs LIFF needs user/task testing. |
| LINE-14 | `liff.getProfile()` is sufficient server authentication | **REJECTED** | Official LIFF docs explicitly warn not to send profile data to server as authentication. Use verified ID token/access-token flows as documented. |
| LINE-15 | `liff.sendMessages()` always triggers normal Messaging API webhook | **REJECTED / nuance** | Official LIFF docs note important webhook differences; especially template/Flex sent by `liff.sendMessages()` do not send webhook. Do not design backend state updates around assuming a webhook. |
| LINE-16 | Thailand OA pricing equals Japan examples | **REJECTED** | LINE pricing is regional. Current Thailand learning hub lists Free/Basic/Pro separately. |
| LINE-17 | Current Thailand free broadcast allowance is 500/month | **REJECTED / outdated** | Current Thailand LINE for Business learning hub lists Free = 300 broadcast messages/month. |
| LINE-18 | Push is “free” because Messaging API has a free plan | **REJECTED** | Push counts toward plan message usage even if some monthly messages are included. |

### Architecture resolution from LINE evidence

```text
Reply-first
→ Push intentionally
→ Direct chat input allowed
→ Quick Reply for small ambiguity
→ Rich Menu for navigation
→ LIFF for structured work
```

---

# B. Thailand Open Data / Open Banking Claims

| ID | Claim | Status | Resolution |
|---|---|---|---|
| BOT-01 | BOT Your Data regulation was enacted in late 2025 | **RESOLVED** | BOT issued the relevant regulation 30 Oct 2025; press release 10 Nov 2025. |
| BOT-02 | Personal deposit-data sharing begins late 2026 | **RESOLVED** | BOT states implementation begins late 2026 with personal deposit data. |
| BOT-03 | Other financial data expands during 2027–2028 | **RESOLVED** | BOT Open Data page states phased expansion in 2027–2028. |
| BOT-04 | Thailand already has a universal consumer Plaid-equivalent available to MaewSom today | **NOT SUPPORTED** | Your Data rollout is phased; do not assume universal real-time multi-bank transaction APIs are available to this product now. |
| BOT-05 | Therefore MaewSom must permanently rely on PDFs/slips forever | **REJECTED** | Current constraints favor slips/statements now, but architecture should remain source-adapter friendly for future standardized data sharing. |

---

# C. MeowJot Claims

| ID | Claim | Status | Resolution |
|---|---|---|---|
| MJ-01 | MeowJot is manual-entry focused | **REJECTED** | Official site emphasizes automatic e-Slip tracking. |
| MJ-02 | MeowJot has no auto-categorization | **REJECTED** | KBank/MeowJot materials describe automatic categorization. |
| MJ-03 | MeowJot has no credit-card statement ingestion | **REJECTED** | Current App Store listing says users can share statement files and transactions are logged by spend date. |
| MJ-04 | MeowJot has no recurring entries | **REJECTED** | Current App Store listing explicitly includes recurring entries. |
| MJ-05 | MeowJot supports slips from 16 major banking apps | **RESOLVED** | KBank official launch/update states 16 major banking apps. |
| MJ-06 | MeowJot has generalized cross-account reconciliation | **OPEN / not verified** | Credit-card statement comparison exists, but generalized multi-account source-of-truth reconciliation has not been verified. |
| MJ-07 | MeowJot automatically understands all own-account transfers | **OPEN** | No strong primary evidence found for generalized self-transfer matching. |
| MJ-08 | MeowJot has 640k+ users and ~29k paid subscribers | **OPEN** | Do not use in positioning until a primary/current source is captured. |
| MJ-09 | MeowJot is a 100MB+ app | **OPEN / low value** | Not strategically important; avoid using as differentiation. |

### Resolution
MaewSom cannot differentiate on:
- cat mascot,
- slip OCR,
- auto-category,
- statement file ingestion alone.

---

# D. Nabtang / BooJot / Piggipo

| ID | Claim | Status | Resolution |
|---|---|---|---|
| NB-01 | Nabtang is manual-only | **REJECTED** | Current App Store listing: type, speak, or scan slip; auto-categorization. |
| NB-02 | Nabtang voice capture exists | **RESOLVED** | Explicit in App Store listing. |
| NB-03 | Nabtang slip scanning exists | **RESOLVED** | Explicit in App Store listing. |
| BJ-01 | BooJot has no automation | **REJECTED** | Current App Store listing includes automatic slip reading and gallery history. |
| BJ-02 | BooJot has budgeting/reports/export | **RESOLVED** | Current App Store listing confirms monthly budget, reports and CSV/Excel/PDF/image export. |
| BJ-03 | BooJot is ad-supported only / no meaningful premium | **REJECTED** | Current App Store listing includes Gold and Platinum subscriptions. |
| PG-01 | Piggipo is primarily receipt OCR | **REJECTED** | Official site/FAQ centers on credit-card management and manual/card semantics. |
| PG-02 | Piggipo models statement date / due date | **RESOLVED** | Official FAQ. |
| PG-03 | Piggipo supports statement recheck | **RESOLVED** | Official FAQ says users can recheck past transactions against bank statements. |
| PG-04 | Piggipo supports installments and early/extra payments | **RESOLVED** | Official product/FAQ supports installment and extra-credit/advance-payment concepts. |

---

# E. Global PFM Claims

| ID | Claim | Status | Resolution |
|---|---|---|---|
| MON-01 | Monarch has generalized reconciliation | **REJECTED** | Official manual-transaction help explicitly says Monarch does not have a reconciling feature. |
| MON-02 | Monarch rules can rename/re-categorize automatically | **RESOLVED** | Official rules documentation. |
| COP-01 | Copilot distinguishes transfers from ordinary spending | **RESOLVED** | Official transaction types: Income, Internal Transfer, Regular. |
| COP-02 | Credit-card payments can remain Internal Transfers to avoid double counting | **RESOLVED** | Official July 2026 credit-card payment documentation. |
| COP-03 | Copilot has transaction review state | **RESOLVED** | Official quick-start/web/iPad documentation shows To Review/unreviewed state and bulk review. |
| COP-04 | Copilot always exposes original bank payload next to cleaned name | **PARTIALLY VERIFIED / platform-dependent** | Current transaction overview says original transaction info is not available in some views. Avoid broad claim. |
| COP-05 | Exact “swipe right approve / swipe left recategorize” is current universal Copilot UX | **OPEN** | Review behavior exists, but exact gesture should not be treated as a universal current requirement without direct verification. |

---

# F. Quantitative Market / Behavior Claims

These appeared in several model runs but do not currently have adequate portable primary evidence.

| Claim | Status |
|---|---|
| 82% of manual finance users churn within 28 days | **OPEN / do not use** |
| 67–68% abandon after 2 categorization errors | **OPEN / do not use** |
| 73% of Thai users prefer starting finance tasks in chat | **OPEN / do not use** |
| 85% of daily Thai peer-to-merchant transactions are PromptPay | **OPEN / do not use** |
| Thai LINE OA block rate exceeds 40% above 1 unsolicited message/day | **OPEN / do not use** |
| exact optimal Review Inbox threshold = 5/10/20 | **OPEN / user-test** |
| exact optimal confidence auto-accept threshold = 90% | **OPEN / calibrate empirically** |
| exact Serious Mode discrepancy threshold = 500 or 5,000 THB | **OPEN / owner + testing** |
| exact Daily Digest time = 20:00 | **OPEN / preference test** |

### Rule
No implementation constant may be derived from these numbers until separately validated.

---

# G. Product Architecture Disputes

## ARCH-01 — Is LIFF Home the primary product home?

**Status: OPEN**

Two hypotheses:

### Traditional app shell
Home + Review + Transactions + Accounts + Profile.

### Contextual workspace
LINE chat is the relational home; most tasks deep-link into specific LIFF workflows.

**Test before locking navigation.**

---

## ARCH-02 — Is Review a top-level LIFF tab?

**Status: OPEN**

Depends on:
- review frequency,
- backlog size,
- user mental model,
- proportion of ambiguity that can be resolved in chat.

---

## ARCH-03 — Should Review occur in Flex carousel?

**Status: PARTIAL**

Recommended breakpoint:
- 1–3 simple binary items → Chat / Quick Reply / Flex.
- multi-item triage, editing, filtering → LIFF.

Exact threshold: user-test.

---

## ARCH-04 — Should confidence percentages be visible?

**Status: OPEN**

Preferred first prototype:
- known vs inferred,
- source,
- review-needed state.

Raw percentage can remain internal unless testing proves users benefit from it.

---

## ARCH-05 — Should Rich Menu dynamically change by relationship stage?

**Status: OPEN**

Technically feasible via per-user Rich Menu.

Risk:
- users lose spatial memory.

Prefer:
- stable core navigation,
- limited contextual changes only where the benefit is clear.

---

# H. Source Links

## LINE
- https://developers.line.biz/en/docs/messaging-api/pricing/
- https://developers.line.biz/en/docs/messaging-api/sending-messages/
- https://developers.line.biz/en/reference/messaging-api/
- https://developers.line.biz/en/docs/messaging-api/use-loading-indicator/
- https://developers.line.biz/en/docs/messaging-api/using-quick-reply/
- https://developers.line.biz/en/docs/messaging-api/switch-rich-menus/
- https://developers.line.biz/en/docs/messaging-api/use-per-user-rich-menus/
- https://developers.line.biz/en/reference/liff
- https://lineforbusiness.com/th/learning-hub/OA-B-01

## BOT
- https://www.bot.or.th/th/news-and-media/news/news-20251110.html
- https://www.bot.or.th/th/financial-innovation/digital-finance/open-data.html

## Thai products
- https://www.meowjot.com/
- https://www.kasikornbank.com/th/News/Pages/MeowJot.aspx
- https://www.piggipo.com/
- https://www.piggipo.com/faqs
- Nabtang App Store listing
- BooJot App Store listing

## Global
- https://help.copilot.money/en/articles/3971267-transaction-types
- https://help.copilot.money/en/articles/10671434-credit-card-payment-transactions
- https://help.copilot.money/en/articles/11157550-quick-start-guide
- https://help.monarchmoney.com/hc/en-us/articles/360058441811-Manual-transactions

---

# I. Verification Result

Architecture-level evidence is now strong enough to proceed to Owner Direction.

Still prohibited:
- copying model-specific numeric thresholds,
- claiming uniqueness as fact,
- locking visual/navigation structure solely from secondary research.
