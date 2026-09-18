---
topic: liff-competitive-ux
date: 2026-09-18
researcher: Claude
model: Opus 4.6
status: raw
research_type: independent-pass
canonical: false
---
# DELIVERABLE 13: Design Principles for MaewSom LIFF

Here are 12 research-backed design principles for MaewSom's LIFF experience, covering critical UX and product dimensions.

### 1. Principle: Frictionless Entry is King
**Evidence:** Nabtang and BooJot are praised for instant input. Users abandon apps like Lumpsum due to manual entry fatigue. MAKE by KBank thrives on simple drag-and-drop actions.
**Reasoning:** In a market dominated by PromptPay and e-slips, users expect immediacy. If logging an expense takes more than 5 seconds, they will churn.
**Implication:** MaewSom LIFF must support instant OCR receipt scanning and Quick Add flows, relying heavily on the Chat interface for micro-inputs (e.g., forwarding an e-slip) rather than complex web forms.

### 2. Principle: Emotion Drives Retention (Persona)
**Evidence:** Piggipo's emotional pig and MeowJot's cat mascot successfully retain users by making finance less intimidating.
**Reasoning:** Personal finance is inherently stressful. A friendly, consistent persona (the Orange Cat) breaks the "ostrich effect" and provides gamified motivation.
**Implication:** Integrate the MaewSom persona throughout the LIFF experience, especially in empty states, goal celebrations, and friendly nudges.

### 3. Principle: The Chat is the Source of Truth (LINE-Native)
**Evidence:** MAKE by KBank’s chat-style history and LINE BK’s in-context transfers are highly successful because Thai users live in LINE.
**Reasoning:** Bouncing users to an external-feeling app breaks immersion. Treating the chat as the primary notification and quick-action hub reduces context switching.
**Implication:** Use LIFF strictly for complex tasks (dashboards, reconciliation), while keeping quick logs, alerts, and binary decisions in the chat using Quick Replies and Flex Messages.

### 4. Principle: Visual Budgeting Over Accounting (Financial Semantics)
**Evidence:** MAKE by KBank’s "Cloud Pockets" (envelope system) is much easier for Gen Z to grasp than YNAB’s strict zero-based budgeting.
**Reasoning:** Traditional pie charts and ledgers are abstract. Users prefer tactile, visual representations of exactly which "bucket" of money is draining.
**Implication:** Design LIFF budget views around visual pockets, savings goals, and a singular "Safe to Spend" number (inspired by PocketGuard).

### 5. Principle: Auditability Builds Trust (Data Provenance)
**Evidence:** Copilot’s "cleared vs uncleared" markers and Zopa’s auditability mode build trust. Black-box AI actions cause anxiety.
**Reasoning:** AI will make mistakes (e.g., misreading a Thai merchant name). Users need to know *why* a decision was made and verify the data source.
**Implication:** Clearly demarcate verified transactions (e-slips) from AI-guessed ones, and provide transparent rules-based logic in the LIFF settings.

### 6. Principle: Graceful Tone Degradation (Serious Mode)
**Evidence:** Cleo and Wells Fargo bots faced severe backlash for being sassy or condescending when users were overdrawn or facing hardship.
**Reasoning:** High stakes require high empathy (Service Mind in Thai culture). Sarcasm fails when users are vulnerable.
**Implication:** The AI persona must dynamically switch to a polite, objective, and supportive tone during negative balances or high-stakes errors within both Chat and LIFF.

### 7. Principle: The Inbox Pattern for Review (Review Workflow)
**Evidence:** Copilot Money’s "To Review" inbox creates a highly addictive daily habit loop (Zero Inbox).
**Reasoning:** Users need a fast way to correct AI categorizations without digging through deep transaction histories.
**Implication:** Create a dedicated "Review Inbox" prominently placed in the LIFF Home screen for unverified or low-confidence AI categorizations.

### 8. Principle: Progressive Onboarding (Onboarding)
**Evidence:** Mor Prom uses a low-friction start, increasing KYC only when needed. YNAB’s strict initial setup causes massive drop-off.
**Reasoning:** Demanding full setup (creating budgets, linking all data) on day one causes churn.
**Implication:** Start with simple chat interactions (upload one slip) and introduce LIFF dashboards gradually. Use skeleton screens to mask any LIFF loading times.

### 9. Principle: Transparent Value Before Monetization (Monetization)
**Evidence:** Albert’s aggressive upsells and TrueMoney’s cluttered ads alienate users.
**Reasoning:** Trust must be established before asking for money.
**Implication:** Keep core features (logging, basic pockets) free and ad-free. Clearly delineate premium features (e.g., advanced tax insights, multi-aggregator sync) without blocking basic utility.

### 10. Principle: No Dead Ends (Error Handling)
**Evidence:** BofA’s Erica hands off to humans flawlessly. Fargo traps users in conversational loops.
**Reasoning:** Users get frustrated when AI fails to understand local context or OCR fails on faded receipts.
**Implication:** Always offer a clear fallback to manual entry in LIFF or human support in Chat when the AI confidence is low.

### 11. Principle: High-Signal Actionability (AI Interaction)
**Evidence:** Origin and ttb touch provide actionable insights ("You have unnecessary subscriptions") rather than just passive data.
**Reasoning:** Users ignore passive dashboards. AI is only valuable if it tells the user *what to do next*.
**Implication:** LIFF Insights should prioritize actionable recommendations (e.g., "Tap here to reallocate funds") over generic charts.

### 12. Principle: Designing for Micro-Friction (Accessibility)
**Evidence:** Watsons and PTT Blue Card utilize Dynamic Rich Menus for zero-click information retrieval.
**Reasoning:** Even opening a LIFF app takes 1-2 seconds. 
**Implication:** Render critical data (like remaining daily budget) directly on the LINE Rich Menu API, reserving LIFF only when deeper interaction is needed.

