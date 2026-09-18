---
topic: liff-competitive-ux
date: 2026-09-18
researcher: Claude
model: Opus 4.6
status: raw
research_type: independent-pass
canonical: false
---
# Group B — Thai Banking / Fintech

## Summary
This report analyzes 10 major Thai banking and fintech applications to extract UX/UI patterns, strengths, and weaknesses applicable to **MaewSom**, a LINE-based Personal Finance Assistant. 

Overall trends show a shift towards "Super Apps" (TrueMoney, SCB EASY, K PLUS) that bundle lifestyle services with banking, and "Social Banking" (LINE BK, MAKE by KBank) which integrate financial behavior into chat-like, humanized interfaces. For MaewSom, the core takeaway is the success of chat-based transaction logging (MAKE by KBank) and in-context social payments (LINE BK), while avoiding the cluttered "mini-app" syndrome seen in Paotang and TrueMoney.

## Product Research Cards

### 1. SCB EASY
**1. Positioning:** Full-service digital banking app by Siam Commercial Bank. Target: Mass market. Business model: Cross-selling loans, insurance, investments.
**2. Entry Point:** Standalone app icon, deep links from merchants.
**3. Onboarding:** 4-5 steps. Requires NDID or branch KYC. Bank connection is native. Progressive onboarding: No.
**4. Home Screen:** Prioritizes balance (hideable), quick actions (transfer, top-up), and personalized promotions.
**5. Navigation:** Bottom nav (Home, Transactions, Service, Profile).
**6. Transaction Capture:** Manual transfer/bill pay, automatic from bank backend.
**7. Transaction Review:** Auto-categorization (basic), chronological list. No batch review.
**8. Financial Semantics:** Income, expense, credit card, repayment, loan.
**9. Trust & Data Provenance:** Verified e-slips, real-time balance. Security indicator: Session timeout timer [scb.co.th].
**10. AI:** Proactive recommendations for loans/investments based on cash flow (reactive AI).
**11. Insights:** Basic "My Expense" pie chart. Often hidden deep in the menu. Does not strongly lead to action.
**12. Notification:** Push notifications, robust LINE integration (SCB Connect) for real-time transaction alerts.
**13. Character / Personality:** Professional, secure, purple corporate tone. Mae Manee mascot used for merchant side.
**14. Serious State:** UI turns stark red for overdraft or payment failure; strict PIN/FaceID prompts for large transfers.
**15. Monetization:** Premium banking tiers, interchange fees, cross-selling credit products.
**16. Retention:** Daily transactions, easy bill pay, SCB Point rewards.
**17. Empty State:** Prompts to open accounts or apply for cards.
**18. Error State:** Generic error codes ("9000") which confuse users [Google Play Reviews].
**19. UX Strengths:** Extremely fast transfers, customizable quick actions, excellent LINE notification bot (SCB Connect).
**20. UX Weaknesses:** Bloated with non-banking features (food delivery), heavy app size, basic categorization.
**21. What MaewSom Should Learn:** SCB Connect's LINE notification speed and rich-message e-slip receipts are best-in-class.
**22. What MaewSom Should NOT Copy:** Bloated feature sets that bury core financial insights.

### 2. K PLUS
**1. Positioning:** Kasikornbank's flagship app. Target: Mass market, young adults, SMEs.
**2. Entry Point:** App icon, QR scan widgets.
**3. Onboarding:** Branch/ATM KYC or NDID. 
**4. Home Screen:** Balance, K-Point balance, large transfer/QR buttons.
**5. Navigation:** Bottom nav, but relies heavily on a central "Banking" button.
**6. Transaction Capture:** Native bank transactions.
**7. Transaction Review:** Simple timeline. Basic tagging available but rarely used by users.
**8. Financial Semantics:** Transfers, credit cards, mutual funds.
**9. Trust & Data Provenance:** E-slip generation with QR verification is the gold standard in Thailand.
**10. AI:** "K-Tech" recommends contextual loans or promotions.
**11. Insights:** Monthly income/expense summary, but lacks deep subscription tracking.
**12. Notification:** Push, KBank Live (LINE).
**13. Character / Personality:** Friendly, reliable, green theme.
**14. Serious State:** Distinct confirmation screens with large fonts for recipient names.
**15. Monetization:** Wealth management, personal loans.
**16. Retention:** K-Points gamification, ubiquitous QR payment.
**17. Empty State:** Clear steps to open an e-Saving account.
**18. Error State:** Better human-readable errors than SCB.
**19. UX Strengths:** Unmatched reliability, smoothest QR scan experience, highly readable confirmation screens.
**20. UX Weaknesses:** "Banking" tab is heavily nested; finding past transactions older than 6 months is tedious.
**21. What MaewSom Should Learn:** The visual hierarchy of transfer confirmation screens (preventing wrong transfers).
**22. What MaewSom Should NOT Copy:** Hiding transaction history behind multiple taps.

### 3. MAKE by KBank
*(See Deep Dive below)*

### 4. Krungthai NEXT
**1. Positioning:** State-owned bank app. Target: Government workers, mass market.
**2. Entry Point:** App icon.
**3. Onboarding:** Face verification often required, sometimes strict [App Store Reviews].
**4. Home Screen:** Clean dashboard, accounts, government bonds.
**5. Navigation:** Bottom nav.
**6. Transaction Capture:** Native.
**7. Transaction Review:** Standard list.
**8. Financial Semantics:** Heavy on bill payments (utilities, government fines).
**9. Trust & Data Provenance:** Standard e-slips.
**10. AI:** None apparent. Not verified.
**11. Insights:** Very limited.
**12. Notification:** Push, LINE (Krungthai Connext).
**13. Character / Personality:** Formal, modernizing but still institutional. 
**14. Serious State:** Standard PIN confirmation.
**15. Monetization:** Service fees, government transaction routing.
**16. Retention:** Payroll for government employees, lottery purchases.
**17. Empty State:** Standard onboarding.
**18. Error State:** Often crashes during government subsidy rollout days [Twitter feedback].
**19. UX Strengths:** Clean, updated UI compared to its legacy version; good bill pay ecosystem.
**20. UX Weaknesses:** Slow load times during peak days, strict/failing face scans.
**21. What MaewSom Should Learn:** Clear categorization of billers.
**22. What MaewSom Should NOT Copy:** Sluggish transition animations.

### 5. Paotang (เป๋าตัง)
**1. Positioning:** "Thailand's Open Digital Platform" (Government wallet). Target: All Thai citizens.
**2. Entry Point:** App icon.
**3. Onboarding:** High friction (Krungthai NEXT link or complex ID scan).
**4. Home Screen:** Fragmented "Wallets" (G-Wallet, Health, Gold, Bonds).
**5. Navigation:** Grid of mini-apps.
**6. Transaction Capture:** Wallet top-ups, subsidy spending.
**7. Transaction Review:** Segmented by wallet. Confusing.
**8. Financial Semantics:** Subsidies, bonds, health quotas.
**9. Trust & Data Provenance:** Government-backed.
**10. AI:** None.
**11. Insights:** None. 
**12. Notification:** Push.
**13. Character / Personality:** Utilitarian, bureaucratic.
**14. Serious State:** PIN required for every wallet entry.
**15. Monetization:** Government infrastructure.
**16. Retention:** Government handouts (Half-Half scheme), Lottery.
**17. Empty State:** Requires G-Wallet activation.
**18. Error State:** Notorious for crashing during subsidy registrations.
**19. UX Strengths:** Excellent digital lottery UI (easy search and buy).
**20. UX Weaknesses:** Highly fragmented UX; users must log into sub-wallets repeatedly.
**21. What MaewSom Should Learn:** How to handle massive concurrent traffic (conceptually).
**22. What MaewSom Should NOT Copy:** The mini-app silo structure. Do not fragment the user's money.

### 6. ttb touch
**1. Positioning:** Personal financial assistant app. Target: Young professionals.
**2. Entry Point:** App icon.
**3. Onboarding:** Standard KYC.
**4. Home Screen:** "Smart Dashboard" showing personalized financial health.
**5. Navigation:** Bottom nav.
**6. Transaction Capture:** Native.
**7. Transaction Review:** Consolidates credit cards, loans, and deposits nicely.
**8. Financial Semantics:** Debt tracking, insurance, investments.
**9. Trust & Data Provenance:** Secure PIN architecture (Secret Code).
**10. AI:** Smart insights engine suggests savings optimizations.
**11. Insights:** Best-in-class among traditional banks. Highlights unnecessary spending.
**12. Notification:** Push, LINE.
**13. Character / Personality:** Smart, helpful, minimalist (Blue/Orange).
**14. Serious State:** Warning on high credit card utilization.
**15. Monetization:** Cross-selling mutual funds and loans.
**16. Retention:** Checking the "financial health" score.
**17. Empty State:** Encourages setting up a savings goal.
**18. Error State:** Smooth recovery flows.
**19. UX Strengths:** Holistic view of wealth vs. debt; beautiful data visualization.
**20. UX Weaknesses:** Can feel overwhelming with data on the home screen.
**21. What MaewSom Should Learn:** The "Financial Health" dashboard approach that guides users to action.
**22. What MaewSom Should NOT Copy:** Over-complicating the home screen with too many charts.

### 7. Krungsri app
**1. Positioning:** Core banking app. Target: Mass market, corporate employees.
**2. Entry Point:** App icon.
**3. Onboarding:** Standard.
**4. Home Screen:** Balance and quick menus.
**5. Navigation:** Bottom nav.
**6. Transaction Capture:** Native.
**7. Transaction Review:** Basic list.
**8. Financial Semantics:** Heavy on auto-loans and mutual funds.
**9. Trust & Data Provenance:** Standard.
**10. AI:** Not prominent.
**11. Insights:** Very basic.
**12. Notification:** Push, LINE.
**13. Character / Personality:** Corporate, yellow theme.
**14. Serious State:** Standard.
**15. Monetization:** Loans, funds.
**16. Retention:** Payroll, bill pay.
**17. Empty State:** Standard.
**18. Error State:** Sometimes logs users out unexpectedly [Reviews].
**19. UX Strengths:** Integration with Kept (their secondary savings app) is okay.
**20. UX Weaknesses:** Feels dated compared to K PLUS; credit card management is split to a different app (U CHOOSE).
**21. What MaewSom Should Learn:** N/A.
**22. What MaewSom Should NOT Copy:** Forcing users to download a second app to manage credit cards.

### 8. Bualuang mBanking
**1. Positioning:** Bangkok Bank's app. Target: Older demographic, corporate.
**2. Entry Point:** App icon.
**3. Onboarding:** Historically required branch visit, now supports NDID.
**4. Home Screen:** Very traditional dashboard.
**5. Navigation:** Hamburger menu mixed with bottom nav.
**6. Transaction Capture:** Native.
**7. Transaction Review:** Basic list.
**8. Financial Semantics:** Standard.
**9. Trust & Data Provenance:** Highly secure, conservative limits.
**10. AI:** None.
**11. Insights:** Almost none.
**12. Notification:** Push.
**13. Character / Personality:** Serious, conservative, blue theme.
**14. Serious State:** Very rigid confirmation steps.
**15. Monetization:** Standard fees.
**16. Retention:** Necessity.
**17. Empty State:** Bare.
**18. Error State:** Generic.
**19. UX Strengths:** Extremely stable, rarely crashes.
**20. UX Weaknesses:** Outdated UI, steep learning curve for new features.
**21. What MaewSom Should Learn:** Stability is a feature.
**22. What MaewSom Should NOT Copy:** The outdated navigation paradigms.

### 9. TrueMoney
**1. Positioning:** E-wallet Super App. Target: Unbanked, teens, gamers, mass market.
**2. Entry Point:** App icon, 7-Eleven POS terminals.
**3. Onboarding:** Low friction (Phone number), progressive KYC for higher limits.
**4. Home Screen:** Extremely busy. QR code, promotions, mini-apps (games, loans, Apple Pay).
**5. Navigation:** Endless scrolling home screen, bottom nav.
**6. Transaction Capture:** Wallet top-up, linked credit cards.
**7. Transaction Review:** Hard to read due to heavy gamification and micro-transactions.
**8. Financial Semantics:** Micro-payments, peer-to-peer, subscriptions.
**9. Trust & Data Provenance:** Verified by True.
**10. AI:** Recommendation engine for promotions and micro-loans (Pay Next).
**11. Insights:** None; the app encourages spending, not saving.
**12. Notification:** Aggressive push notifications (ads).
**13. Character / Personality:** Loud, promotional, gamified (Orange).
**14. Serious State:** Minimal friction to encourage payment.
**15. Monetization:** Merchant fees, micro-loans, ads.
**16. Retention:** 7-Eleven integration, cashback games.
**17. Empty State:** Prompts to link card or top-up.
**18. Error State:** "Oops" friendly errors.
**19. UX Strengths:** Incredible merchant integration; gamification drives daily opens.
**20. UX Weaknesses:** Overwhelmingly cluttered; feels like an ad billboard rather than a financial tool.
**21. What MaewSom Should Learn:** The power of micro-rewards and gamification to drive habit.
**22. What MaewSom Should NOT Copy:** Aggressive push notifications and cluttered "super-app" UI. 

### 10. LINE BK
*(See Deep Dive below)*

---

## Deep Dive: MAKE by KBank
**Positioning:** A social, lifestyle banking app targeting Gen Z and young millennials who struggle with traditional budgeting. 

**Transaction Lifecycle & Budgeting Analysis:**
- **Input:** Native KBank backend. Money is transferred into the MAKE ecosystem.
- **Detection:** Instant.
- **Classification:** Categorized by the user via visual "Cloud Pockets". This is physical budgeting (envelope system) rather than AI tagging.
- **Review:** Transactions are displayed in a **Chat Interface**. Users can attach photos and memos to a transaction, making it look like a LINE chat history.
- **Insight:** Visualized spending. You see exactly which "Pocket" is draining. 
- **Action:** Move money between pockets via drag-and-drop. (Approx 2 taps).

**Key UX Highlights:**
- **Cloud Pockets:** Users create infinite sub-accounts (e.g., "Boba Tea", "Rent", "Trip to Japan") with custom icons. Dragging money from the main account to a pocket is incredibly tactile and satisfying.
- **Pop Pay:** Bluetooth-based transfer. App detects nearby MAKE users (like AirDrop). Tap icon -> enter amount -> send. Removes the friction of asking for account numbers.
- **Chat Banking:** History is a chat thread. "You paid 500 THB to John". You can reply with a receipt photo.

**What MaewSom Should Learn:** 
- The Chat Interface for transaction history is genius for Thai users who live in LINE. MaewSom should absolutely format transaction logs as conversational threads.
- The "Envelope" (Pocket) budgeting system is easier for users to understand than abstract pie charts.

---

## Deep Dive: LINE BK
**Positioning:** "Banking in Your Hand" - A joint venture between KBank and LINE, offering a seamless social banking experience entirely within the LINE app.

**Transaction Lifecycle & LINE Integration Analysis:**
- **Entry Point:** A tab inside the LINE app's "Wallet" menu, or directly via chat extensions.
- **Input / Transfer:** Inside a chat with a friend, press '+' -> LINE BK -> Enter amount. (Approx 3 taps). 
- **Detection / Classification:** Automatic. 
- **Notification:** Sent immediately as a rich LINE message to both sender and receiver. No need to manually save and send an e-slip to the chat; the system does it automatically.
- **Lending (Nano-credit):** Users can apply for a credit line instantly. AI assesses their LINE usage and KBank history. Approval takes minutes.

**What works with LINE integration:**
- **Frictionless P2P:** Bill splitting and transferring money in the context of the conversation is the ultimate killer feature. You are talking about dinner, you split the bill right there.
- **Notifications:** LINE Official Account alerts are highly visible and trusted.
- **Trust via Familiarity:** Using LINE characters (Brown, Cony) makes banking less intimidating.

**What doesn't work:**
- Discoverability. Being buried in the LINE "Wallet" tab means users have to dig to find the main dashboard. 
- Clutter. LINE is already heavy; adding a full bank makes the app feel sluggish at times.

**What MaewSom Should Learn:**
- **In-Context Actions:** MaewSom should aim to intercept intent directly in the chat. If a user types "I spent 500 on food", MaewSom should log it instantly.
- **Rich Message Receipts:** Use LINE's Flex Messages to send beautiful, clear transaction summaries back to the user.

---

## Negative Review Analysis
Analysis of 1- and 2-star reviews across App Store and Google Play for these products:

1. **Security Overkill (K PLUS, SCB EASY, Krungthai):** 
   - *Complaint:* Apps force logout if screen recording is on, or if accessibility features (used by visually impaired) are active (anti-scam measures).
   - *Insight:* High friction frustrates users. MaewSom must balance security with ease, perhaps relying on LINE's native authentication.
2. **Clutter and Ads (TrueMoney, SCB EASY):**
   - *Complaint:* "I just want to transfer money, why are there 3 pop-up ads for loans?" 
   - *Insight:* Never block core financial flows with promotional material.
3. **Identity Verification Failures (Krungthai NEXT, Paotang):**
   - *Complaint:* "Face scan failed 20 times."
   - *Insight:* If MaewSom requires onboarding, keep it chat-based and simple.
4. **Opaque Errors:**
   - *Complaint:* "Error code 029X. What does that mean?"
   - *Insight:* MaewSom must use natural language for errors. "The bank's server is down right now, try again in 10 minutes" instead of "Connection Timeout Error 503".

---

## Key Findings for MaewSom
1. **Conversational UI is Proven:** MAKE by KBank proves that Thais prefer chat-based transaction logging. MaewSom being on LINE gives it a massive native advantage here.
2. **Micro-Friction Kills:** Users hate switching apps to send an e-slip. LINE BK solved this. MaewSom should ensure all interactions (logging, checking balance) happen without leaving the chat.
3. **Visual Budgeting > Charts:** Thai users respond better to visual "pockets" or specific goals rather than traditional accounting pie charts.
4. **Tone of Voice:** A friendly, helpful persona (like ttb touch or MAKE) works better than a sterile corporate tone, especially for a personal finance assistant.
5. **Simplicity Wins:** The biggest complaint against TrueMoney and Paotang is UI clutter. MaewSom should maintain a hyper-minimalist chat interface, using Flex Messages to display data only when asked.

