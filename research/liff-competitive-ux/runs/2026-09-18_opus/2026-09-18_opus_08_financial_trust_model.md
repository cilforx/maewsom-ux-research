---
topic: liff-competitive-ux
date: 2026-09-18
researcher: Claude
model: Opus 4.6
status: raw
research_type: independent-pass
canonical: false
---
# Financial Trust UX Model (08_financial_trust_model.md)

## Trust Signals Taxonomy
Across all 50 researched products, trust is established through specific design patterns:

- **Visual indicators:** Verified checkmarks for bank-synced data, "pending" icons for uncleared/manual entries, distinct colors/italics for AI-guessed vs User-confirmed categories.
- **Data provenance:** Clear labels indicating data sources (e.g., "Extracted from KBank Slip", "Manually Entered", "Synced via Plaid").
- **Confidence display:** Using visual cues to indicate AI uncertainty, prompting the user for verification.
- **Reconciliation patterns:** The "To Review" inbox pattern (Copilot, Monarch), which builds a highly trusted habit loop of zero-inbox verification.
- **Error transparency:** Natural language error messaging (e.g., "The bank's server is down, try again in 10 minutes") rather than opaque system codes ("Error 029X").
- **Security signals:** Explicit privacy opt-ins, session timeout indicators, Scam Intelligence warnings (Starling), and biometric confirmation prompts.

## Trust Building Framework for MaewSom
Given that MaewSom is a third-party app utilizing a playful persona and handling sensitive bank slips, trust is its most critical currency. 

### 1. Transparent AI Auditability
- **Evidence:** Starling provides local-cloud execution and Ask Zopa offers a visual auditability mode. Conversely, users hate black-box categorization (Albert, Copilot).
- **Insight:** Users trust AI systems when they understand *why* a decision was made and can easily override it.
- **Implication:** MaewSom must make its AI logic transparent and easily reversible.
- **MaewSom Requirement:** Implement an "Audit Trail" feature. When AI categorizes a slip, allow users to tap it to see the logic (e.g., "Categorized as Food because merchant 'Starbucks' matched our database"). Use the "To Review" pattern via daily LINE digests.

### 2. Adaptive Persona (Tone Mapping)
- **Evidence:** Cleo's "Roast mode" and Wells Fargo's AI both faced heavy backlash for being tone-deaf or condescending during moments of financial distress.
- **Insight:** A playful persona builds retention during good times but becomes a massive liability when user safety or high-stakes money is involved.
- **Implication:** The persona must adapt strictly to the financial state of the user.
- **MaewSom Requirement:** Implement a strict "Serious Mode" trigger. If balances drop below a threshold, or a large transfer is detected, MaewSom must instantly switch to a polite, objective, "Service Mind" tone.

### 3. The Flawless Human Bridge
- **Evidence:** Bank of America's Erica succeeds by seamlessly handing off to human agents, while other bots trap users in frustrating NLP loops.
- **Insight:** Users tolerate AI errors and trust the platform more if they know a competent human can step in instantly.
- **Implication:** The bot must not act as a wall to block access to real help.
- **MaewSom Requirement:** Provide a permanent "Speak to Agent" option in the Rich Menu. If the AI fails intent recognition twice, automatically offer to hand off the full chat context to a human.

### 4. Borrowing Institutional Trust
- **Evidence:** Thai users place immense trust in native K PLUS / SCB EASY e-slip QR verification formats.
- **Insight:** Familiar visual cues borrow trust from established institutions.
- **Implication:** MaewSom should replicate familiar, secure-looking receipts for its own summaries.
- **MaewSom Requirement:** Use Flex Messages that visually resemble official bank e-slips for transaction confirmations and summaries, establishing MaewSom's outputs as "official" and reliable.

