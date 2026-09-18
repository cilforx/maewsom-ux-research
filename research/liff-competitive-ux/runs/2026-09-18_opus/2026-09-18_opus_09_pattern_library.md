---
topic: liff-competitive-ux
date: 2026-09-18
researcher: Claude
model: Opus 4.6
status: raw
research_type: independent-pass
canonical: false
---
# UX Pattern Library for MaewSom

This pattern library synthesizes 25 UX patterns identified across competitive products in the Thai banking, global finance, AI conversational, and LINE ecosystem sectors.

## Pattern 1: Chat-Based Transaction Logging
**Used by:** MAKE by KBank, Cleo
**Problem:** Users find traditional form-based transaction entry tedious and high-friction.
**How it works:** Users enter transactions as chat messages (e.g., "Paid 500 for food").
**Why it works:** It feels natural, mimics social chat behavior, and reduces cognitive load.
**Risks:** NLP might fail to parse complex inputs or edge cases.
**Best context:** Daily micro-transactions and quick expense tracking.
**Applicability to MaewSom:** High
**Recommended MaewSom adaptation:** Core feature. Allow users to type naturally, send voice notes, or forward e-slips directly in the LINE chat.

## Pattern 2: E-Slip Image Scanning (OCR)
**Used by:** MeowJot, รับจ่ายจด
**Problem:** Manual entry is slow and error-prone in Thailand where PromptPay e-slips are ubiquitous.
**How it works:** Users upload or auto-scan bank slips from their gallery, and AI extracts the amount, date, and merchant.
**Why it works:** Eliminates typing completely, leveraging a uniquely Thai behavior (saving transfer slips).
**Risks:** Poor OCR accuracy on faded receipts or unusual slip formats; requires gallery permissions.
**Best context:** Thai PromptPay/bank transfer ecosystems.
**Applicability to MaewSom:** High
**Recommended MaewSom adaptation:** Allow users to forward e-slips into the MaewSom LINE chat for instant auto-extraction and categorization.

## Pattern 3: Visual "Envelope" Pockets
**Used by:** MAKE by KBank, Plum
**Problem:** Abstract budgeting numbers (like pie charts) are hard for users to conceptualize.
**How it works:** Money is visually divided into sub-accounts or "pockets" with custom icons (e.g., "Food", "Rent").
**Why it works:** Translates physical envelope budgeting into a tactile digital interface.
**Risks:** Can become cluttered if a user creates too many pockets.
**Best context:** Visual learners and Gen Z budgeting.
**Applicability to MaewSom:** High
**Recommended MaewSom adaptation:** Use LIFF to display visual pockets and allow drag-and-drop allocations, while chat provides quick status updates.

## Pattern 4: The "Inbox" Review Queue
**Used by:** Copilot Money, YNAB
**Problem:** Automated transaction syncing often miscategorizes items, leading to untrusted data.
**How it works:** Unverified transactions are placed in an "Inbox" or "To Review" queue. Users must explicitly approve or edit them (e.g., swipe right to approve).
**Why it works:** Enforces data hygiene and builds trust by keeping a human-in-the-loop.
**Risks:** Can cause "review fatigue" if the inbox gets too large.
**Best context:** Automated aggregator or OCR-based tracking.
**Applicability to MaewSom:** High
**Recommended MaewSom adaptation:** Send a daily "digest" Flex Message in LINE with transactions needing confirmation, using Quick Replies (Approve/Edit).

## Pattern 5: Emotional Gamification (Persona)
**Used by:** Piggipo, Cleo, Emma
**Problem:** Budgeting is stressful and users often avoid looking at their finances (ostrich effect).
**How it works:** An avatar or mascot reacts emotionally to financial behavior (e.g., pig cries when over budget, cat cheers for saving).
**Why it works:** Humanizes data, creates empathy, and makes checking balances entertaining.
**Risks:** Can feel condescending or tone-deaf during serious financial distress.
**Best context:** Habit-building and casual budgeting.
**Applicability to MaewSom:** High
**Recommended MaewSom adaptation:** The MaewSom (Orange Cat) persona should be playful for daily tracking, but switch to a polite "Service Mind" tone for negative balances.

## Pattern 6: The "Safe to Spend" Single Metric
**Used by:** PocketGuard, Quicken Simplifi
**Problem:** Users can't do mental math to figure out how much of their balance is actually free to spend after upcoming bills.
**How it works:** Calculates total balance minus upcoming recurring bills/goals, outputting a single "In My Pocket" number.
**Why it works:** Reduces complex cash flow into one actionable number for daily decision-making.
**Risks:** Relies on accurate prediction of recurring bills.
**Best context:** Daily spending checks before point-of-sale.
**Applicability to MaewSom:** High
**Recommended MaewSom adaptation:** Display the "Safe to Spend" number on the LINE Rich Menu for zero-click visibility.

## Pattern 7: Quick Action Floating FAB / Calculator
**Used by:** BooJot, Piggipo, Nabtang
**Problem:** Multi-step forms for manual entry cause user drop-off.
**How it works:** A prominent "+" button opens a fast, calculator-style numpad for instant entry (often under 3 taps).
**Why it works:** Optimizes for speed, mimicking a cashier's workflow.
**Risks:** Misses detailed metadata (tags, notes) if optimized purely for speed.
**Best context:** Purely manual offline apps.
**Applicability to MaewSom:** Medium
**Recommended MaewSom adaptation:** Use LINE's Quick Replies to mimic this speed for chat-based manual entry, rather than building a custom numpad.

## Pattern 8: In-Context Group Bill Splitting
**Used by:** LINE BK, LINE MAN
**Problem:** Splitting bills requires switching between a calculator, a bank app, and a chat app.
**How it works:** Users initiate a split directly within a group chat, sending a request with a payment link/QR.
**Why it works:** Intercepts intent where the conversation is already happening.
**Risks:** Clutters social chats if overused.
**Best context:** Social outings and shared expenses.
**Applicability to MaewSom:** High
**Recommended MaewSom adaptation:** Leverage the LINE Share Target Picker via LIFF to let users share a "Split Request" Flex Message directly to friends.

## Pattern 9: Dynamic Rich Menu Dashboards
**Used by:** PTT Blue Card, SCB Connect
**Problem:** Forcing users to open a webview just to check a balance adds friction.
**How it works:** The LINE Rich Menu image is dynamically generated via API to display current balances or points directly on the buttons.
**Why it works:** Zero-click information retrieval.
**Risks:** Requires backend image generation; rate limits on updates.
**Best context:** Loyalty points, basic balance checks.
**Applicability to MaewSom:** High
**Recommended MaewSom adaptation:** Render the user's weekly budget progress visually on the LINE Rich Menu.

## Pattern 10: Seamless Human Handoff (The Bridge)
**Used by:** Bank of America (Erica)
**Problem:** Chatbots trapping users in loops when NLP fails causes severe frustration.
**How it works:** If the bot fails twice, it instantly connects to a human agent, passing the entire chat context.
**Why it works:** Preserves trust and prevents rage-quitting.
**Risks:** Increases customer support costs.
**Best context:** Complex financial troubleshooting.
**Applicability to MaewSom:** High
**Recommended MaewSom adaptation:** If MaewSom's AI can't parse a transaction, flag it for manual review in the LIFF app rather than looping, or hand off to human support if it's an account issue.

## Pattern 11: Transaction-Level Commenting
**Used by:** Honeydue
**Problem:** Couples or roommates need to discuss specific, ambiguous transactions.
**How it works:** Users can leave comments or emoji reactions on individual transaction line items.
**Why it works:** Anchors financial discussions to specific data points.
**Risks:** Can cause arguments if not framed well.
**Best context:** Shared household finances.
**Applicability to MaewSom:** Medium
**Recommended MaewSom adaptation:** Allow users to tag a partner or add a note to a transaction within the LIFF app, triggering a LINE notification.

## Pattern 12: Visual Auditability for AI Actions
**Used by:** Ask Zopa
**Problem:** Users distrust "black box" AI making financial decisions or categorizations.
**How it works:** AI explains *why* it made a choice (e.g., "I categorized this as Food because you visited Starbucks").
**Why it works:** Demystifies AI and builds confidence.
**Risks:** Can make the UI text-heavy.
**Best context:** Proactive AI insights and agentic money movement.
**Applicability to MaewSom:** High
**Recommended MaewSom adaptation:** When suggesting a rule or categorization, use a brief subtext indicating the AI's reasoning.

## Pattern 13: Strict Action Confirmation UI
**Used by:** Rocket Money, K PLUS
**Problem:** Fat-finger errors or AI hallucinations in high-stakes actions (money transfers, canceling bills) are catastrophic.
**How it works:** A distinct, high-contrast confirmation screen (or explicit text reply like "Reply YES to cancel") is required before execution.
**Why it works:** Forces cognitive slow-down for critical actions.
**Risks:** Adds friction (which is the point).
**Best context:** Transfers, cancellations, large edits.
**Applicability to MaewSom:** High
**Recommended MaewSom adaptation:** Use a prominent LINE Flex Message with a "Confirm Action" button before applying bulk edits or agentic actions.

## Pattern 14: Progressive KYC Onboarding
**Used by:** TrueMoney, SCB EASY
**Problem:** Full KYC (Know Your Customer) ID scans upfront kill conversion rates.
**How it works:** Allow basic feature access with just a phone number/LINE login, and only prompt for ID scans when higher transfer limits are needed.
**Why it works:** Demonstrates value before asking for sensitive data.
**Risks:** Regulatory compliance complexities.
**Best context:** E-wallets and basic trackers.
**Applicability to MaewSom:** High
**Recommended MaewSom adaptation:** Start with 100% frictionless LINE Login for expense tracking. Only ask for deeper bank auth if true syncing is enabled later.

## Pattern 15: Rich Message Receipts
**Used by:** SCB Connect, Major Cineplex
**Problem:** SMS receipts are ugly, easy to spoof, and hard to organize.
**How it works:** Transactions generate a beautifully formatted LINE Flex Message (or Service Message) that acts as a digital receipt.
**Why it works:** Highly legible, visually appealing, and keeps a persistent record in chat.
**Risks:** Can clutter the chat history if transaction volume is huge.
**Best context:** E-commerce, banking alerts, ticket bookings.
**Applicability to MaewSom:** High
**Recommended MaewSom adaptation:** After processing an e-slip, reply with a clean, branded MaewSom Flex Message summarizing the logged expense.

## Pattern 16: Calendar-Based Spending View
**Used by:** Money Diary
**Problem:** Standard lists make it hard to spot temporal spending patterns (e.g., spending heavily on Fridays).
**How it works:** A traditional monthly calendar where each day displays the total amount spent/earned.
**Why it works:** Intuitive macro-view of financial velocity over a month.
**Risks:** Hard to read on small screens if there are too many transactions per day.
**Best context:** Journal-style expense tracking.
**Applicability to MaewSom:** Medium
**Recommended MaewSom adaptation:** Include a calendar view inside the LIFF dashboard for users who want to review their monthly heatmap.

## Pattern 17: User-Defined Automation Rules
**Used by:** Monarch Money, YNAB
**Problem:** AI categorization constantly misguesses certain niche merchants.
**How it works:** Users explicitly define rules (e.g., "If Payee contains 'PromptPay-John', categorize as 'Rent'").
**Why it works:** Gives power users control and overrides faulty ML.
**Risks:** Requires setup effort from the user.
**Best context:** Web/desktop power-user dashboards.
**Applicability to MaewSom:** High
**Recommended MaewSom adaptation:** If a user corrects MaewSom's category guess in chat, prompt: "Should I always categorize 'John' as Rent?"

## Pattern 18: Zero-State Educational Nudges
**Used by:** Origin, YNAB
**Problem:** Blank dashboards confuse users on what to do first.
**How it works:** Empty states are filled with actionable tutorials or prompts (e.g., "Connect a bank to see your net worth").
**Why it works:** Guides the user through the "Aha!" moment.
**Risks:** Too much text can be skipped.
**Best context:** First-time user experience (FTUE).
**Applicability to MaewSom:** High
**Recommended MaewSom adaptation:** The empty chat should have MaewSom sending a friendly welcome message with a Quick Reply button: "Log my first expense".

## Pattern 19: Proactive Subscription Detection
**Used by:** Rocket Money, Copilot
**Problem:** Users forget about recurring subscriptions and overpay.
**How it works:** AI scans history for recurring identical charges and alerts the user if a bill increases or a free trial ends.
**Why it works:** Delivers instant, high-ROI value to the user (saving money).
**Risks:** False positives (flagging a regular coffee purchase as a subscription).
**Best context:** Automated bank sync.
**Applicability to MaewSom:** Medium
**Recommended MaewSom adaptation:** Since MaewSom relies more on e-slips, it can still look for monthly recurring PromptPay transfers and proactively ask, "Is this a monthly bill?"

## Pattern 20: The "Financial Health" Dashboard
**Used by:** ttb touch, Origin
**Problem:** Raw transaction data doesn't tell a user if they are actually doing "good" or "bad".
**How it works:** Aggregates debt, savings, and spending into a holistic "score" or health indicator.
**Why it works:** Provides clear, actionable motivation.
**Risks:** Can be demoralizing if the score is low without offering solutions.
**Best context:** Comprehensive wealth management.
**Applicability to MaewSom:** Medium
**Recommended MaewSom adaptation:** Provide a weekly "Cat Health" checkup in chat, summarizing if they stayed under budget.

## Pattern 21: High-Contrast "Serious State" UI
**Used by:** SCB EASY, Copilot
**Problem:** Users can miss critical alerts in a colorful, playful app.
**How it works:** When a user is overdrawn, misses a payment, or initiates a large transfer, the UI strips away playful elements and uses stark reds/bold fonts.
**Why it works:** Signals urgency and context switching.
**Risks:** Can induce anxiety.
**Best context:** Errors, overdrafts, high-value transfers.
**Applicability to MaewSom:** High
**Recommended MaewSom adaptation:** When showing an over-budget alert, MaewSom's Flex Message should use a neutral/serious color palette rather than bright orange.

## Pattern 22: Pre-filled Contextual Prompts (Chips)
**Used by:** Starling Bank, Bank of America
**Problem:** The "blank page" problem in conversational AI leaves users not knowing what to ask.
**How it works:** The chat interface provides tappable suggested queries (e.g., "Show my budget", "Recent food expenses").
**Why it works:** Educates the user on AI capabilities and reduces typing.
**Risks:** If the chips aren't context-aware, they clutter the UI.
**Best context:** Conversational entry points.
**Applicability to MaewSom:** High
**Recommended MaewSom adaptation:** Use LINE Quick Replies religiously to surface context-aware actions based on the current conversation state.

## Pattern 23: Mini-App Seamless Transition
**Used by:** FINNOMENA, Watsons
**Problem:** Webviews inside chat apps often feel slow, clunky, and disconnected.
**How it works:** Using LIFF, the webview utilizes native fonts, skeleton loading, and automatic silent LINE Login.
**Why it works:** Feels like a native app extension rather than an external website.
**Risks:** Poor web optimization leads to slow load times.
**Best context:** LINE ecosystem apps.
**Applicability to MaewSom:** High
**Recommended MaewSom adaptation:** The MaewSom LIFF dashboard must be hyper-optimized for speed and perfectly match LINE's design system.

## Pattern 24: "Set and Forget" Automation
**Used by:** Plum, YNAB
**Problem:** Relying on user willpower to save money or track expenses manually usually fails.
**How it works:** The system automatically sweeps small amounts to savings or auto-categorizes based on hard rules.
**Why it works:** Removes willpower from the equation.
**Risks:** Auto-saving can cause overdrafts if algorithms miscalculate.
**Best context:** Savings goals and data entry.
**Applicability to MaewSom:** Medium
**Recommended MaewSom adaptation:** Focus on "Set and Forget" for transaction classification rules to minimize manual review time.

## Pattern 25: Social / Community Proof
**Used by:** TrueMoney (gamification), YNAB (community)
**Problem:** Finance is lonely; users give up on budgets.
**How it works:** Showing aggregate data ("Other people spend X on food") or gamified leaderboards/streaks.
**Why it works:** Leverages social proof and competitiveness.
**Risks:** Privacy concerns if not anonymized properly.
**Best context:** Savings challenges, Gen-Z apps.
**Applicability to MaewSom:** Low-Medium
**Recommended MaewSom adaptation:** Use gamified "Streaks" for daily tracking (like MeowJot), rather than full social sharing.

