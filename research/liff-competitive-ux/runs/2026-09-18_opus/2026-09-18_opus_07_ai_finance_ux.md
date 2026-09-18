---
topic: liff-competitive-ux
date: 2026-09-18
researcher: Claude
model: Opus 4.6
status: raw
research_type: independent-pass
canonical: false
---
# AI Finance UX Analysis (07_ai_finance_ux.md)

## Recurring Patterns in AI Finance

**A. Patterns that consistently work:**
- **Contextual Nudges:** AI suggestions embedded natively into the UI (e.g., Copilot) rather than purely chat-based.
- **Frictionless Review:** Tinder-style swiping or 1-tap Approve/Dismiss buttons for rapid transaction categorization.
- **Visual Confirmations:** Using rich cards (like Ask Zopa) to summarize AI intent before executing agentic actions.
- **Seamless Human Handoff:** Providing a flawless bridge to human support (e.g., BofA Erica) without forcing users to repeat context.

**B. Patterns that cause friction:**
- **Black-Box Categorization:** AI auto-categorizing or moving money without providing a UI panel for the user to see *why* or how to override the rule (Albert, Copilot).
- **Tone-Deaf Humor:** Playful personas (Cleo) roasting users during moments of real financial distress.
- **Hallucinated Math:** AI assistants confidently outputting incorrect aggregate sums (Monarch).
- **Conversational Loops:** Failing to recognize intent and repeating "I didn't understand" instead of escalating to a human.

**C. Emerging 2025–2026 patterns:**
- **Visual Auditability:** AI explicitly showing its decision tree/logic for high-stakes actions (Ask Zopa).
- **Proactive SMS/Chat Anomaly Detection:** Initiating conversations based on backend data streams (Rocket Money/Rowan) rather than waiting for users to open dashboards.

**D. Thai-specific AI patterns:**
- **Slip-Based Tracking:** Users forwarding PromptPay e-slips into chat as the primary data entry method (MeowJot, MAKE by KBank).
- **PromptPay Name Classification:** AI dealing with the ambiguity of Thai personal names in transfers to deduce categories (e.g., separating peer-to-peer transfers from small merchants).

**E. LINE-specific AI patterns:**
- **Pre-filled Quick Replies:** Avoiding the "blank page" problem by offering contextual chips.
- **Social Split-Bills:** Using Flex Messages to generate bill-splitting requests that can be shared directly into LINE groups.

**F. Financial trust in AI patterns:**
- **Transparency:** Clearly distinguishing between confident deterministic data (bank API) and uncertain AI guesses.
- **Reversibility:** Ensuring any automated action (especially agentic ones) can be easily undone.

## AI Confidence Communication Model
MaewSom must adapt its UI based on its confidence level:
- **High Confidence (95%+):** (e.g., standard utility bill, known corporate PromptPay). Auto-categorize, silently update the ledger, and include in the daily digest.
- **Medium Confidence (70-94%):** (e.g., OCR on a faded slip, ambiguous merchant name). Draft the record, but prompt the user in chat using Quick Replies: "Did you spend ฿200 on Food? [Yes] [Edit]".
- **Low Confidence (<70%):** (e.g., unrecognizable personal PromptPay transfer). Ask the user directly: "What category is this for? [Food] [Transport] [Other]".
- **Agentic Actions (High Stakes):** ALWAYS require explicit confirmation before execution (e.g., "Should I transfer ฿500 to your savings pocket?"). Use Flex Message visual cards for explicit review.

## Personality Mode Framework
When should the Orange Cat persona be active?

**Cat Persona Active (Default State):**
- **Triggers:** Daily logging, goal celebrations, general insights, gamified streaks, normal balances.
- **Behavior:** Playful, sassy but helpful, uses emojis, acts as a financial "intern" or buddy (inspired by Cleo/Emma/MeowJot).
- **Why:** Drives emotional engagement, makes finance fun, and breaks the "ostrich effect" of avoiding budgets.

**Serious Mode Active:**
- **Triggers:** Account balance nearing zero, overdraft warnings, explicit debt management, suspected scams, or explicit user requests for "just the facts".
- **Behavior:** Persona drops the sass. Language shifts to "Service Mind" (polite, empathetic, objective). No jokes, clear actionable advice.
- **Why:** Based on failures from Cleo and Wells Fargo, playfulness during financial distress reads as condescending and destroys trust.

## Human-in-the-Loop Decision Framework
- **Ask the User (Human Input Required):** When executing agentic actions (moving money, canceling subscriptions), when altering budget limits, or when AI classification confidence is <80%.
- **Act Autonomously (AI Only):** Logging verified KBank/SCB e-slips, generating daily summaries, updating visualizations, identifying duplicate charges for later review.
- **Handoff to Human Agent (Fail-safe):** After 2 consecutive failed intent recognitions, if the user explicitly types "talk to human", or if high-risk scam parameters are met.

