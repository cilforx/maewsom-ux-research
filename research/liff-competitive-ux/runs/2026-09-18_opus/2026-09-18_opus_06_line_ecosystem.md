---
topic: liff-competitive-ux
date: 2026-09-18
researcher: Claude
model: Opus 4.6
status: raw
research_type: independent-pass
canonical: false
---
# LINE Ecosystem Analysis (06_line_ecosystem.md)

## Chat vs LIFF Responsibility Matrix
To build a seamless native-like experience inside LINE, MaewSom must clearly delineate which user jobs belong in the chat and which require the rich interface of a LIFF app.

| User Job | Chat | Quick Reply | Flex Message | Rich Menu | LIFF | Why |
| :--- | :---: | :---: | :---: | :---: | :---: | :--- |
| **1. View real-time transaction alerts** | ✅ | | | | | Push notifications demand immediate attention. |
| **2. Quick Expense Categorization** | ✅ | ✅ | | | | Reduces multi-step form to a single tap in the chat flow. |
| **3. View Daily Overview / Balance** | | | | ✅ | | Zero-click info available every time the chat is opened. |
| **4. Share Split-Bill Request** | ✅ | | ✅ | | | Looks professional; easily shareable to LINE groups natively. |
| **5. Review Transaction History** | | | | | ✅ | Requires scrolling, filters, and list views—poorly suited for chat. |
| **6. Statement Reconciliation** | | | | | ✅ | Complex data comparison requires a full UI. |
| **7. Account Settings & Profile** | | | | | ✅ | Low frequency, high complexity task. Needs full screen. |
| **8. Goal Tracking Dashboard** | | | | | ✅ | Requires charts, progress bars, and dense data visualization. |
| **9. Quick Confirmation (Yes/No)** | ✅ | ✅ | | | | Binary, immediate decisions fit chat perfectly. |
| **10. Forward e-Slip for tracking** | ✅ | | | | | Frictionless logging directly by forwarding an image to chat. |
| **11. Ask for financial advice** | ✅ | | | | | Natural language queries fit conversational UI perfectly. |
| **12. View monthly spending pie chart** | | | | | ✅ | Interactive charts are best handled in LIFF webviews. |
| **13. Set up new savings goal** | | | | | ✅ | Multi-step forms (dates, amounts, names) belong in webviews. |
| **14. Receive receipt confirmation** | ✅ | | ✅ | | | Service messages provide clear, searchable records in chat. |
| **15. Correct an AI miscategorization** | ✅ | ✅ | | | | 1-tap Approve/Dismiss is perfect for Quick Reply. |
| **16. Connect external bank account** | | | | | ✅ | Requires secure OAuth / webview context. |
| **17. Check remaining budget** | | | | ✅ | | Can be dynamically rendered on the Rich Menu image via backend. |
| **18. Dispute a transaction** | | | | | ✅ | Requires filling out details and providing structured context. |
| **19. Receive bill due reminder** | ✅ | | ✅ | | | Flex messages with visual urgency are best for reminders. |
| **20. Select payment method** | ✅ | ✅ | | | | Quick reply buttons allow fast, frictionless selection. |

## LINE-Specific Patterns

### What makes LINE-native UX succeed
- **Zero-Friction Input:** Allowing users to forward an e-slip directly into the chat to log an expense (capitalizing on Thai PromptPay habits).
- **In-Context Actions:** Using Quick Replies for 1-tap categorizations without leaving the chat.
- **Social Integration:** Utilizing the Share Target Picker to let users share split-bill Flex Messages directly into their existing LINE friend groups.
- **UI Continuity:** LIFF apps that match LINE's design system (seed colors, native fonts) feel like a true extension of the app rather than a third-party website.

### What makes it fail
- **Slow LIFF Load Times:** Users abandon LIFF apps if they show a blank white screen for more than a second.
- **Web Form Forcing:** Forcing users into a LIFF form for a simple 1-tap decision that could have been a Quick Reply.
- **Spamming Chat:** Overusing promotional push messages leads to users muting or blocking the OA.
- **Fragmented Identity:** Forcing secondary logins when LINE Login (`liff.init()`) should be used transparently.

### LIFF Performance Concerns
LIFF relies on embedded webviews. To maintain a native feel:
- Use aggressive caching and minimal initial bundle sizes.
- Implement skeleton loading screens that match the final layout, rather than generic spinners.
- Keep LIFF pages specifically for macro-tasks; avoid opening them for micro-tasks.

### Rich Menu Strategies
- **Dynamic Context:** Change the Rich Menu based on user state (e.g., Guest vs Logged In, or standard vs "Over Budget" mode).
- **Data Rendering:** Render dynamic financial data (like "Current Balance") directly onto the Rich Menu image via backend APIs to provide zero-click value.

### Notification Policies
- **Flex Messages:** Use for high-value transactional alerts (e.g., "Large expense detected", "Bill due tomorrow").
- **Service Messages:** Use strictly for critical, non-promotional financial receipts to keep the chat clutter-free but searchable.
- **Batching:** Send daily or weekly digests rather than pinging for every minor event, unless real-time tracking is explicitly requested.

### Chat ↔ LIFF Transition Best Practices
- **Immediate Authentication:** Use `liff.init()` to authenticate silently. Never show a secondary login screen unless linking an external legacy account.
- **Half-Modal vs Full-Screen:** Use Tall/Compact LIFF sizes (half-modals) for quick actions to keep the chat visible in the background. Reserve Full size for complex dashboards.
- **Graceful Exits:** Always use `liff.closeWindow()` tied to a clear "Done" button, returning the user smoothly to the chat, optionally triggering a chat confirmation message (`liff.sendMessages()`).

