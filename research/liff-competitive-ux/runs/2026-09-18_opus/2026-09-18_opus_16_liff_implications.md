---
topic: liff-competitive-ux
date: 2026-09-18
researcher: Claude
model: Opus 4.6
status: raw
research_type: independent-pass
canonical: false
---
# DELIVERABLE 16: What This Means for MaewSom LIFF

Using the Evidence → Insight → Implication → MaewSom Design Requirement framework, here are the recommendations for key areas of the MaewSom experience.

### 1. Home
*   **Observed Pattern:** Cluttered dashboards cause churn; single-metric dashboards drive daily use.
*   **Evidence:** PocketGuard’s "In My Pocket" metric; complaints about TrueMoney’s bloat.
*   **Recommendation:** Center the Home screen entirely around a "Safe to Spend today" large metric and the Cat persona's current mood.
*   **Confidence:** High

### 2. Navigation
*   **Observed Pattern:** Persistent, simple bottom tabs out-perform hamburger menus.
*   **Evidence:** Bualuang mBanking’s hybrid menu is confusing; Copilot’s 5-tab bar is fluid.
*   **Recommendation:** Strict 4 or 5 tab bottom navigation. No hidden side menus for core features.
*   **Confidence:** High

### 3. Review Inbox
*   **Observed Pattern:** Dedicated approval queues build trust and habit.
*   **Evidence:** Copilot Money’s "To Review" feature is considered best-in-class; Monarch uses explicit review rules.
*   **Recommendation:** Implement a Tinder-style swipe or 1-tap Approve/Dismiss queue for all AI-categorized e-slips.
*   **Confidence:** High

### 4. Transaction Detail
*   **Observed Pattern:** Users need to correct AI context quickly.
*   **Evidence:** Cleo's AI fails when users can't override its assumptions.
*   **Recommendation:** Detail view must allow 1-tap category changes and prompt the user: "Create a rule for future merchants named [X]?"
*   **Confidence:** Medium

### 5. Statement / Reconciliation
*   **Observed Pattern:** Distinguishing verified vs manual data is crucial.
*   **Evidence:** YNAB's "Cleared" icon.
*   **Recommendation:** Use visual markers (e.g., a green checkmark) for e-slip verified transactions vs. manual entries to ease end-of-month reconciliation.
*   **Confidence:** High

### 6. Accounts (Pockets)
*   **Observed Pattern:** Visual envelope budgeting resonates deeply with Gen Z.
*   **Evidence:** MAKE by KBank’s massive success with Cloud Pockets.
*   **Recommendation:** Replace traditional ledger accounts with visual, drag-and-drop "Pockets".
*   **Confidence:** High

### 7. Insights
*   **Observed Pattern:** Actionable > Passive charts.
*   **Evidence:** ttb touch and Origin provide specific advice ("You have duplicate subscriptions").
*   **Recommendation:** Insights must lead with a text-based "Cat Insight" (e.g., "You're spending 20% more on food. Reallocate 500THB from Travel? [Yes] [No]") rather than just a pie chart.
*   **Confidence:** High

### 8. Chat ↔ LIFF Transition
*   **Observed Pattern:** Seamless transitions retain users in the ecosystem.
*   **Evidence:** Mor Prom and Watsons use instantaneous LIFF half-modals.
*   **Recommendation:** Use `liff.init()` silently. Use skeleton loaders. Close LIFF immediately after a task and push a Flex Message summary to the chat.
*   **Confidence:** High

### 9. Persona
*   **Observed Pattern:** Emotional connection drives retention, but tone-deafness destroys it.
*   **Evidence:** MeowJot and Piggipo succeed with mascots; Cleo fails during high-stakes distress.
*   **Recommendation:** The Orange Cat should be playful during logging, encouraging during goal setting, but entirely objective during errors.
*   **Confidence:** High

### 10. Relationship Stage
*   **Observed Pattern:** Progressive onboarding is required.
*   **Evidence:** YNAB's steep setup causes churn; TrueMoney scales up KYC gradually.
*   **Recommendation:** Day 1: Just log slips. Day 7: Introduce budgets/pockets. Day 30: Introduce tax/insights.
*   **Confidence:** Medium

### 11. Serious Mode
*   **Observed Pattern:** Scam anxiety and financial distress require friction and empathy.
*   **Evidence:** Starling Bank’s Scam Intelligence; Wells Fargo's robotic tone.
*   **Recommendation:** "Serious Mode" must trigger automatically on negative balances or suspected duplicate charges. The UI shifts to neutral colors, and the Cat uses formal Thai phrasing.
*   **Confidence:** High

### 12. Notification
*   **Observed Pattern:** Real-time, contextual alerts replace SMS.
*   **Evidence:** SCB Connect’s push notifications.
*   **Recommendation:** All transaction alerts must be rich Flex Messages in LINE. Avoid spamming promotional broadcasts to protect OA trust.
*   **Confidence:** High

### 13. Premium
*   **Observed Pattern:** Transparent walls vs. deceptive upsells.
*   **Evidence:** Albert's dark patterns anger users.
*   **Recommendation:** Keep logging and pockets free. Lock advanced tax planning and multi-aggregator sync behind a clear, upfront paywall.
*   **Confidence:** Medium

### 14. Trust / Provenance
*   **Observed Pattern:** Hallucinations ruin financial apps.
*   **Evidence:** Monarch AI's math hallucinations.
*   **Recommendation:** Never let the AI do math in plain text without a structured UI component (Flex Message or LIFF Card) validating the calculation.
*   **Confidence:** High

### 15. Empty State
*   **Observed Pattern:** Blank pages cause writer's block.
*   **Evidence:** Starling Bank mitigates blank pages with suggested chips.
*   **Recommendation:** LIFF and Chat empty states must feature the Cat providing 3 Quick Reply chips (e.g., "Upload Slip", "Set a Goal").
*   **Confidence:** High

### 16. Error State
*   **Observed Pattern:** Dead ends cause abandonment.
*   **Evidence:** BofA’s Erica hands off to humans; generic bank errors ("9000") confuse users.
*   **Recommendation:** If OCR fails, the Cat must say "I can't read this slip clearly. Can you type the amount?" Never show a generic API timeout error.
*   **Confidence:** High

