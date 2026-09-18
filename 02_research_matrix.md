# 02. 50-Product Research Matrix

> [!NOTE]
> เนื่องจากการแสดงผล 22 dimensions × 50 products ในตารางเดียวจะอ่านไม่ได้บนหน้าจอปกติ เราจึงยุบรวม (Aggregate) Dimensions เป็น 7 เสาหลักทางการออกแบบ เพื่อให้เห็น Pattern ชัดเจน และวิเคราะห์ความเชื่อมโยงได้

## Dimension Grouping:
1. **Positioning & Entry:** Positioning, Entry Point, Onboarding, Monetization
2. **Input & UX/UI:** Transaction Capture, Navigation, Home Screen, Empty State
3. **AI & Review:** AI Capability, Transaction Review, Financial Semantics, Error/Failure State
4. **Data & Trust:** Trust & Data Provenance, Serious State
5. **Engagement:** Notification, Character/Personality, Retention, Insights
6. **UX Analysis:** Strengths, Weaknesses, What to Learn, What NOT to Copy

---

## Group A: Thai Direct Personal Finance Competitors

| Product | Positioning & Entry | Input & UX/UI | AI & Review | Data & Trust | Engagement | MaewSom Takeaways |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **1. MeowJot** | **Pos:** Auto e-Slip tracker with cat persona.<br>**Entry:** App Icon, Share Extension.<br>**Monetize:** Premium for Statement/Deeper AI. | **Input:** OCR e-Slip (Background/Manual).<br>**Nav:** Bottom Tab (Home, Stats, Profile).<br>**Home:** Daily Timeline + Balance. | **AI:** Extracts amount, date, receiver. Auto-categorizes via merchant DB.<br>**Review:** Swipe to approve/edit pending slips. | **Trust:** High trust on amount, medium on category. Shows "Extracted from slip". | **Engage:** Cute Cat UI, "MeowDoo" (fortune), Push notifications. | **Learn:** Zero-entry is king.<br>**Avoid:** Forcing app downloads when LINE is enough. |
| **2. Nabtang** | **Pos:** Simple, clean budget tracker.<br>**Entry:** App Icon.<br>**Monetize:** Freemium. | **Input:** 100% Manual.<br>**Nav:** Bottom Tab.<br>**Home:** Budget remaining circle. | **AI:** None.<br>**Review:** Immediate manual input. | **Trust:** Source of truth is the user. | **Engage:** Clean aesthetic, minimal friction for manual input. | **Learn:** Visual clarity on "Left to spend".<br>**Avoid:** Manual entry dependency. |
| **3. รับจ่ายจด** | **Pos:** Traditional ledger for Thai market.<br>**Entry:** App Icon.<br>**Monetize:** Ads / Premium to remove ads. | **Input:** Manual.<br>**Home:** List of transactions. | **AI:** None. | **Trust:** Basic calculator level. | **Engage:** None. Pure utility. | **Avoid:** Outdated, spreadsheet-like UI. |
| **4. BooJot** | **Pos:** Piggy bank tracker / savings goal.<br>**Entry:** App Icon.<br>**Monetize:** Ads. | **Input:** Manual goal tracking.<br>**Home:** Visual goals. | **AI:** None. | **Trust:** User input. | **Engage:** Visual progress bars for saving. | **Learn:** Visualizing goals (e.g., buying a new phone). |
| **5. Save Money** | **Pos:** No-frills expense tracker.<br>**Entry:** App Icon. | **Input:** Manual. | **AI:** None. | **Trust:** Local storage. | **Engage:** Utility. | **Avoid:** Bland UI. |
| **6. Piggipo** | **Pos:** Credit card manager / Debt visualizer.<br>**Entry:** App Icon.<br>**Monetize:** Premium. | **Input:** Statement import / Manual.<br>**Home:** Cute pig characters indicating debt health. | **AI:** Basic OCR/parsing of statements.<br>**Review:** Batch review of CC statements. | **Trust:** High, but breaks if bank statement format changes. | **Engage:** Pig emotions change based on debt level (Happy = paid, Crying = over limit). | **Learn:** Emotional mapping to financial health (Serious State handling). |
| **7. Money Diary** | **Pos:** Diary-style tracker.<br>**Entry:** App Icon. | **Input:** Manual + Photo attach. | **AI:** None. | **Trust:** User-driven. | **Engage:** Journaling aspect. | **Learn:** Attaching context (photos) to expenses. |
| **8. Money Note+** | **Pos:** Simple spreadsheet alternative. | **Input:** Manual. | **AI:** None. | **Trust:** Basic. | **Engage:** Utility. | **Avoid:** Clunky UI. |
| **9. Lumpsum** | **Pos:** Holistic financial planner.<br>**Entry:** App Icon. | **Input:** Manual / Complex onboarding. | **AI:** Basic forecasting. | **Trust:** Very high (Financial Advisor positioning). | **Engage:** Serious, professional tone. | **Learn:** Long-term wealth overview.<br>**Avoid:** High onboarding friction. |
| **10. MeKinMeChai** | **Pos:** Niche Thai tracker. | **Input:** Manual. | **AI:** None. | **Trust:** Basic. | **Engage:** Thai localization. | **Avoid:** Lack of automation. |

---

## Group B: Thai Banking / Fintech (Internal Context)

| Product | Positioning & Entry | Input & UX/UI | AI & Review | Data & Trust | Engagement | MaewSom Takeaways |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **11. SCB EASY** | **Pos:** Full-service banking.<br>**Entry:** App, Deep link. | **Input:** Auto (from bank TX).<br>**Home:** Accounts & Actions. | **AI:** "Just for You" insights.<br>**Review:** Auto-categorized in "My Expenses". | **Trust:** Absolute (Source of Truth). | **Engage:** Utility, personalized banners. | **Learn:** Absolute trust mapping.<br>**Avoid:** Cluttered action menus. |
| **12. K PLUS** | **Pos:** Lifestyle & Banking.<br>**Entry:** App. | **Input:** Auto.<br>**Home:** Balance & K Point. | **AI:** Basic categorization.<br>**Review:** Can edit category, but buried. | **Trust:** Absolute. | **Engage:** K Point gamification. | **Learn:** Reward loops. |
| **13. MAKE by KBank** | **Pos:** Cloud pocket budgeting (Gen Z).<br>**Entry:** App. | **Input:** Bank transfer via Cloud Pockets.<br>**Home:** Visual Pockets (Drag & Drop). | **AI:** Auto-sort (basic).<br>**Review:** Inbox for unassigned money. | **Trust:** High (KBank backend). | **Engage:** Pop-art UI, high gamification, drag-to-transfer. | **Learn:** Physical metaphor (Drag & Drop) for budgeting. |
| **14. Krungthai** | **Pos:** Mass market banking. | **Input:** Auto. | **AI:** Minimal. | **Trust:** Absolute. | **Engage:** Government scheme integration. | **Avoid:** Sluggish UI. |
| **15. Paotang** | **Pos:** E-wallet / Gov gateway. | **Input:** Top-up. | **AI:** None. | **Trust:** High. | **Engage:** Utility only. | **Avoid:** Fragmented IA. |
| **16. ttb touch** | **Pos:** Financial well-being app. | **Input:** Auto. | **AI:** Comprehensive "Smart Dashboard" (predicts bills). | **Trust:** Very High. | **Engage:** Dashboard warns about upcoming liquidity issues. | **Learn:** Predictive insights (Proactive). |
| **17. Krungsri** | **Pos:** Retail banking. | **Input:** Auto. | **AI:** Kepthemed insights. | **Trust:** High. | **Engage:** Simple utility. | **Avoid:** Generic graphs. |
| **18. Bualuang** | **Pos:** Traditional banking. | **Input:** Auto. | **AI:** Minimal. | **Trust:** High. | **Engage:** Basic. | **Avoid:** Outdated UI. |
| **19. TrueMoney** | **Pos:** Everyday Super App e-Wallet. | **Input:** Payment/Top-up.<br>**Home:** Services grid. | **AI:** Promo targeting. | **Trust:** Medium (E-wallet). | **Engage:** Heavy gamification, loyalty. | **Learn:** Micro-transaction handling. |
| **20. LINE BK** | **Pos:** Social banking in LINE.<br>**Entry:** LINE Wallet tab. | **Input:** Auto.<br>**Home:** Balance & Credit line. | **AI:** Credit scoring.<br>**Review:** N/A. | **Trust:** High (KBank partner). | **Engage:** Seamless chat-to-transfer. | **Learn:** Perfect LINE native integration.<br>**Avoid:** Burying entry point in Wallet tab. |

---

## Group C: Global Personal Finance / Budgeting

| Product | Positioning & Entry | Input & UX/UI | AI & Review | Data & Trust | Engagement | MaewSom Takeaways |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **21. YNAB** | **Pos:** Zero-based budgeting cult.<br>**Monetize:** High Subscription. | **Input:** Bank Sync / Manual.<br>**Home:** "Ready to Assign". | **AI:** Learns categorization from user.<br>**Review:** Must manually approve every synced TX. | **Trust:** Extreme (Reconciliation feature is core). | **Engage:** Rule-based (4 Rules), high retention via ideology. | **Learn:** "Review & Reconcile" workflow.<br>**Avoid:** Too steep learning curve. |
| **22. Monarch** | **Pos:** Premium household finance.<br>**Monetize:** Subscription. | **Input:** Plaid/Finicity.<br>**Home:** Beautiful dashboard. | **AI:** Auto-categorization, custom rules.<br>**Review:** Bulk review inbox. | **Trust:** Very High (Status indicators). | **Engage:** Customizable dashboard. | **Learn:** Collaborative (Multiplayer) finance view. |
| **23. Copilot** | **Pos:** AI-first, design-centric tracker (iOS). | **Input:** Bank Sync.<br>**Home:** Dynamic widgets. | **AI:** Highly accurate ML categorization.<br>**Review:** Tinder-style swipe to review. | **Trust:** AI Confidence scores displayed. | **Engage:** Gorgeous UI, dark mode, smooth animations. | **Learn:** Swipe-to-review UX.<br>**Avoid:** iOS only logic. |
| **24. Rocket** | **Pos:** Subscription cancellation / Bill negotiator. | **Input:** Bank Sync. | **AI:** Identifies recurring charges. | **Trust:** High. | **Engage:** Push alerts for fee increases. | **Learn:** "Upcoming Bills" view. |
| **25. Simplifi** | **Pos:** Quick, easy tracking by Quicken. | **Input:** Sync. | **AI:** Cash flow projection. | **Trust:** High. | **Engage:** "Left to Spend". | **Learn:** Spending plan simplicity. |
| **26. PocketGuard**| **Pos:** "In my pocket" limit tracker. | **Input:** Sync. | **AI:** "In My Pocket" algorithm. | **Trust:** High. | **Engage:** Clear single metric focus. | **Learn:** Boil down to one actionable number. |
| **27. Wallet** | **Pos:** Global multi-currency tracker. | **Input:** Sync / Manual. | **AI:** Basic rules. | **Trust:** Medium. | **Engage:** Extensive charts. | **Avoid:** Overwhelming chart options. |
| **28. Spendee** | **Pos:** Shared wallets, beautiful UI. | **Input:** Sync / Manual. | **AI:** Basic. | **Trust:** Medium. | **Engage:** Shared tracking. | **Learn:** Shared expense UI. |
| **29. Emma** | **Pos:** Gen Z finance, gamified. | **Input:** Open Banking. | **AI:** Chatbot/Insights. | **Trust:** Medium. | **Engage:** Gummy bear mascot, quests. | **Learn:** Gamified saving. |
| **30. Honeydue** | **Pos:** Couples finance. | **Input:** Sync. | **AI:** Shared categorization. | **Trust:** High. | **Engage:** Comment on partner's TX. | **Learn:** Contextual chat inside a transaction. |

---

## Group D: AI / Conversational Finance

| Product | Positioning & Entry | Input & UX/UI | AI & Review | Data & Trust | Engagement | MaewSom Takeaways |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **31. Cleo** | **Pos:** AI that roasts you (Gen Z/Alpha). | **Input:** Chat / Sync.<br>**Home:** Chat Interface. | **AI:** Natural language query, proactive roasting.<br>**Review:** Chatbot asks. | **Trust:** Medium (Focus is on behavior, not exact accounting). | **Engage:** Extreme persona, humor, streaks. | **Learn:** Conversational ingestion.<br>**Avoid:** Being too aggressive; Thais prefer polite/cute. |
| **32. Albert** | **Pos:** Human + AI advisor. | **Input:** Sync.<br>**Home:** Action cards. | **AI:** "Genius" (Auto-savings). | **Trust:** High (Backed by real humans). | **Engage:** SMS/App chat. | **Learn:** Hybrid AI-Human fallback. |
| **33. Origin** | **Pos:** Comprehensive AI Wealth. | **Input:** Sync.<br>**Home:** Dashboard. | **AI:** AI answers complex tax/investment questions. | **Trust:** Very High. | **Engage:** Proactive planning. | **Learn:** AI for deeper advice. |
| **34. Rowan** | **Pos:** AI in Rocket Money. | **Input:** Sync. | **AI:** Chat to query "How much did I spend on Amazon?". | **Trust:** High. | **Engage:** Search via chat. | **Learn:** Chat as a search interface. |
| **35. Monarch AI**| **Pos:** Assistant in Monarch. | **Input:** Sync. | **AI:** Generative answers on dashboard data. | **Trust:** High. | **Engage:** Contextual prompts. | **Learn:** Prompt suggestions. |
| **36. Copilot AI** | **Pos:** Chat inside Copilot. | **Input:** Sync. | **AI:** Natural language search. | **Trust:** High. | **Engage:** Fast query. | **Learn:** Speed of response. |
| **37. Starling AI** | **Pos:** UK Bank Assistant. | **Input:** Auto. | **AI:** Spending insights. | **Trust:** Absolute. | **Engage:** Native bank integration. | **Learn:** Trust inheritance. |
| **38. Erica (BofA)** | **Pos:** Bank of America voice/chat AI. | **Input:** Voice/Chat. | **AI:** Navigates app, finds TX, locking cards. | **Trust:** Absolute. | **Engage:** Agentic action (Execute commands). | **Learn:** Agentic actions ("Freeze my card"). |
| **39. Fargo** | **Pos:** Wells Fargo AI. | **Input:** Chat. | **AI:** Similar to Erica. | **Trust:** Absolute. | **Engage:** Triage support. | **Avoid:** Robotic tone. |
| **40. Plum** | **Pos:** AI auto-saver. | **Input:** Open Banking. | **AI:** Analyzes balance and auto-transfers to savings. | **Trust:** High. | **Engage:** Facebook Messenger / App. | **Learn:** Chatbot auto-execution with Messenger integration. |

---

## Group E: LINE / MINI App / Conversational Ecosystem (Thai Focus)

> *Focus: How apps in LINE avoid feeling like "just another web view" (Seamless Handoff)*

| Product (Case) | LINE Integration Pattern | UX Strengths | Friction Points | MaewSom Takeaways (LIFF Strategy) |
| :--- | :--- | :--- | :--- | :--- |
| **41. Starbucks TH** | **Rich Menu → LIFF (Membership/Pay)** | Seamless SSO. Barcode renders instantly in LIFF. | Takes 2-3 seconds to load LIFF initially. | Use LIFF for secure, complex visuals (Barcode/QR). |
| **42. PTT Blue Card**| **Rich Menu → LIFF (Points/Redeem)** | Excellent use of Flex Messages for points summary. | Cluttered Rich Menu. | Flex Message for quick status, LIFF for deep catalog. |
| **43. Major Cineplex**| **Chatbot → LIFF (Booking)** | Chat for movie search, LIFF for seat selection. | Context loss if user closes LIFF mid-booking. | **Crucial:** Chat is for Triage, LIFF is for spatial/complex tasks (Seat map = Budget map). |
| **44. SCB Connect** | **Push/Service Message → LINE** | Best-in-class instant transaction notification. | No native LIFF dashboard, relies on deep linking to SCB App. | Real-time push is critical for Trust. |
| **45. LINE BK** | **Native Wallet → App** | Deeply integrated into LINE core tabs. | Requires full KYC onboarding. | MaewSom isn't a bank, but can mimic the visual language of LINE's native UI (fonts, colors). |
| **46. Wongnai** | **Share → Flex Message** | Flex Message looks beautiful and actionable in chat. | None. | Output from MaewSom must be highly shareable/readable via Flex. |
| **47. K PLUS LINE** | **Service Message → Quick Reply** | Uses Quick Reply to ask "Is this fraud?". | Simple binary choices. | **Learn:** Use Quick Reply for [Confirm Category] / [Edit]. |
| **48. Robinhood** | **Deep Link → App** | Chat notification deep links straight to order status. | Kicks user out of LINE. | MaewSom must keep user *inside* LINE via LIFF. |
| **49. Kerry/KEX** | **Chat → LIFF (Tracking)** | Type tracking number in chat, view map in LIFF. | Chatbot is sometimes rigid. | Natural Language Input in Chat → Structured Output in LIFF. |
| **50. H&M TH** | **Chat → LIFF (E-commerce)** | Full store inside LIFF. | Feels like a slow website wrapper. | **Avoid:** Do not build a heavy SPA in LIFF. It must be modular. |
