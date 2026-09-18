---
topic: liff-competitive-ux
date: 2026-09-18
researcher: Claude
model: Opus 4.6
status: raw
research_type: independent-pass
canonical: false
---
# Group E — LINE / MINI App / Conversational Ecosystem

## Summary
This research explores the LINE ecosystem to identify UX best practices for **MaewSom (แมวส้ม)**, a LINE-based Personal Finance Assistant for Thai users. The goal is to design an experience where users feel they are interacting with a cohesive, native application rather than being bounced to "another website." By analyzing 10 leading Thai case studies across various sectors—including finance, health, and retail—this report details how they leverage LINE Official Accounts (OA), LIFF, LINE MINI Apps, Flex Messages, and Rich Menus to create seamless, habit-forming user journeys.

## LINE Platform Technical Capabilities

To design a native-feeling experience, we must understand the boundaries and capabilities of the LINE platform:

*   **LIFF (LINE Front-end Framework):** The core framework for running web apps inside LINE. It allows web apps to get the user's LINE profile, send messages on behalf of the user, open QR code scanners, and use the Share Target Picker. *Source: [LINE Developers - LIFF](https://developers.line.biz/en/docs/liff/)*
*   **MINI App vs. LIFF:** LIFF is the underlying technology, while LINE MINI App is a specific service format built on LIFF. MINI Apps provide a more "app-like" integration, including the ability to pin the app to the LINE Home tab, send free "Service Messages" (transactional notifications), and deeply integrate with LINE Pay. MINI Apps require a review process, whereas LIFF apps are open. *Source: [LINE Biz - MINI App](https://www.linebiz.com/th/service/line-mini-app/)*
*   **Flex Messages:** Highly customizable JSON-based message layouts. They can include images, buttons, and text formatted similarly to CSS flexbox. A carousel can contain up to 12 bubbles. *Source: [LINE Developers - Flex Message](https://developers.line.biz/en/docs/messaging-api/flex-message/)*
*   **Rich Menu:** The persistent menu at the bottom of the chat. It supports up to 20 tappable areas. With the Messaging API, developers can dynamically link different Rich Menus to specific users (e.g., showing a "Logged In" menu vs. a "Guest" menu). *Source: [LINE Developers - Rich Menu](https://developers.line.biz/en/docs/messaging-api/using-rich-menus/)*
*   **Quick Reply:** Up to 13 temporary buttons appearing above the chat input. They disappear once the user sends a message. Supported actions include message, postback, datetime picker, camera, camera roll, and location. Excellent for frictionless quick inputs. *Source: [LINE Developers - Quick Reply](https://developers.line.biz/en/docs/messaging-api/using-quick-reply/)*
*   **Service Messages:** Free, template-based push messages allowed for MINI Apps to send utility notifications (e.g., receipts, booking confirmations). Strict rules prohibit promotional content. *Source: [LINE Developers - Service Messages](https://developers.line.biz/en/docs/line-mini-app/develop/service-messages/)*
*   **LINE Login & Profile:** Enables seamless authentication. Within the LINE app, users are auto-logged in without typing passwords, yielding instant access to their User ID, display name, and profile picture. *Source: [LINE Developers - LINE Login](https://developers.line.biz/en/docs/line-login/)*
*   **Share Target Picker:** Allows a LIFF app to render a native LINE contact picker, letting users send a predefined Flex Message to their friends or groups directly from the app. *Source: [LINE Developers - Share Target Picker](https://developers.line.biz/en/docs/liff/using-share-target-picker/)*

## Case Studies

### 1. SCB Connect (SCB EASY)
*   **What is it:** Banking notification and quick-action OA.
*   **LINE Integration Architecture:** OA, Rich Menu, Messaging API, Flex Messages.
*   **Entry Points:** Promoted inside the SCB EASY app, bank branches, and website.
*   **Chat ↔ App Transition:** Uses Rich Menu to jump directly into deep-linked sections of the native SCB EASY app.
*   **Authentication & Identity:** Links LINE ID to the SCB bank account via a secure webview during initial onboarding.
*   **Core User Flow:** Perform transaction → Receive instant Flex Message push notification → Check balance via Rich Menu.
*   **Rich Menu Design:** Dynamic. Changes based on whether the user has linked their account. Features quick balance check and statement requests.
*   **Notification Strategy:** Real-time push notifications for every transaction. Replaces traditional SMS alerts.
*   **Repeat Usage Loop:** Users rely on the chat for instant transaction confirmation.
*   **UX Strengths:** Extremely fast, reliable notifications. The Rich Menu acts as a mini-dashboard.
*   **Lessons for MaewSom:** Push notifications (Flex Messages) for financial transactions create strong habitual reliance on the LINE OA.

### 2. Mor Prom (หมอพร้อม)
*   **What is it:** Thai Ministry of Public Health's digital health platform.
*   **LINE Integration Architecture:** OA, LIFF, Rich Menu, Chatbot.
*   **Entry Points:** Mass national promotion, QR codes at hospitals.
*   **Chat ↔ App Transition:** Users tap the Rich Menu and a LIFF modal slides up instantly. Transition is seamless because the UI uses LINE's native design language (fonts, colors).
*   **Authentication & Identity:** LINE Login + Thai National ID verification (OTP).
*   **Core User Flow:** Open Chat → Tap "Health Certificate" → LIFF opens → View certificate → Close LIFF.
*   **Rich Menu Design:** 6-panel grid (Appointments, Certificates, Evaluation, etc.).
*   **Notification Strategy:** Appointment reminders via push messages.
*   **UX Strengths:** Persona-based experience (managing family members).
*   **Lessons for MaewSom:** High trust is required for sensitive data (health/finance). The LIFF app must feel native and load instantly to reduce friction for less tech-savvy users.

### 3. FINNOMENA
*   **What is it:** Wealth management and mutual fund investment platform.
*   **LINE Integration Architecture:** LINE MINI App, OA, Rich Menu.
*   **Entry Points:** Social media links, LINE search.
*   **Chat ↔ App Transition:** Opens as a MINI App, providing a full-screen app-like experience without leaving LINE.
*   **Authentication & Identity:** LINE Login, mapping to FINNOMENA accounts.
*   **Core User Flow:** Read article in chat → Tap to invest → MINI App opens → View portfolio/execute trade.
*   **Rich Menu Design:** Tabbed-style Rich Menu (Market, Portfolio, Knowledge).
*   **UX Strengths:** Seamless transition from content consumption (chat/broadcasts) to action (MINI App portfolio).
*   **Lessons for MaewSom:** Use the chat for insights and alerts, and the MINI App/LIFF for heavy data visualization (charts, portfolio).

### 4. Starbucks Thailand
*   **What is it:** Starbucks Rewards loyalty and mobile order platform.
*   **LINE Integration Architecture:** OA, LIFF, Rich Menu, LINE Pay.
*   **Entry Points:** In-store QR codes, barista recommendations.
*   **Chat ↔ App Transition:** Tapping "Order" opens a highly polished LIFF app.
*   **Authentication & Identity:** Links existing Starbucks Rewards or creates a new one via LINE profile.
*   **Core User Flow:** Tap Rich Menu → Open LIFF → Browse Menu → Add to Cart → Pay via Rabbit LINE Pay → Receive order queue Flex Message in chat.
*   **Notification Strategy:** Flex Messages for order status ("Preparing", "Ready for Pickup").
*   **UX Strengths:** Perfect closed-loop integration with LINE Pay. User never leaves the LINE ecosystem.
*   **Lessons for MaewSom:** Financial transactions (payments/transfers) within LIFF are highly effective when paired with immediate Flex Message confirmations in the chat.

### 5. LINE MAN
*   **What is it:** On-demand food delivery and ride-hailing.
*   **LINE Integration Architecture:** OA, MINI App / Native App deep links.
*   **Entry Points:** LINE Home tab, Chat share.
*   **Chat ↔ App Transition:** Often transitions to the native app, but leverages the Share Target Picker beautifully.
*   **Core User Flow:** Order food → Share tracking link to a LINE group chat.
*   **UX Strengths:** Group social features. Users can share a cart or delivery tracking into a group chat natively.
*   **Lessons for MaewSom:** For a finance app, the ability to share a "Split Bill" Flex Message or a "Donation" link into a LINE group chat using the Share Target Picker is a massive growth vector.

### 6. Major Cineplex
*   **What is it:** Movie ticket booking service.
*   **LINE Integration Architecture:** MINI App, OA.
*   **Entry Points:** LINE Home Tab (Services).
*   **Chat ↔ App Transition:** Fully contained MINI App.
*   **Core User Flow:** Browse movies → Select seats → Pay (LINE Pay) → Receive e-ticket via Service Message.
*   **Rich Menu Design:** 'Book Ticket', 'My Tickets', 'Promotions'.
*   **Notification Strategy:** Uses Service Messages for e-ticket delivery, ensuring it isn't buried under promotional broadcasts.
*   **Lessons for MaewSom:** Use Service Messages (if a MINI App) for critical, non-promotional financial receipts to keep the user's chat clutter-free but easily searchable.

### 7. Watsons Thailand
*   **What is it:** E-commerce and digital membership card.
*   **LINE Integration Architecture:** OA, LIFF, Rich Menu.
*   **Entry Points:** Cashier prompts user to open LINE for member barcode.
*   **Chat ↔ App Transition:** Tapping the Rich Menu instantly pops up a LIFF modal displaying the member barcode and current points.
*   **Authentication & Identity:** LINE Login linked to phone number.
*   **UX Strengths:** Extremely fast load times for the barcode LIFF page.
*   **Lessons for MaewSom:** For quick tasks (e.g., showing a QR code to receive money, checking a daily budget), the LIFF page must load in under 1 second. Use skeleton screens.

### 8. Dusit Central Park / Dusit Thani
*   **What is it:** Hospitality services and membership.
*   **LINE Integration Architecture:** LINE MINI App.
*   **Entry Points:** On-site QR.
*   **Core User Flow:** Register → View services/zones → Book → Pay.
*   **UX Strengths:** Eliminates the need to download a heavy hotel app for a single stay.
*   **Lessons for MaewSom:** High-end, polished UI within LIFF can build trust. The design language must match the brand, not just default web styles.

### 9. PTT Blue Card (xplORe)
*   **What is it:** Gas station and retail loyalty program.
*   **LINE Integration Architecture:** OA, Rich Menu, LIFF.
*   **Entry Points:** Gas stations, Cafe Amazon.
*   **Rich Menu Design:** Dynamic Rich Menu updating point balances directly on the menu image (via backend API rendering).
*   **UX Strengths:** Users can see their points immediately on the Rich Menu without even opening a LIFF app.
*   **Lessons for MaewSom:** Render dynamic financial data (like "Current Balance") directly onto the Rich Menu image via the Messaging API to provide zero-click value.

### 10. KBank Live
*   **What is it:** Kasikornbank's LINE OA.
*   **LINE Integration Architecture:** OA, Rich Menu, Chatbot.
*   **Core User Flow:** Ask chatbot for exchange rates or branch locations → Receive Flex Message.
*   **UX Strengths:** Uses Quick Replies effectively to guide users through chatbot flows (e.g., "Select Currency" -> [USD] [EUR] [JPY]).
*   **Lessons for MaewSom:** Use Quick Replies for conversational finance tasks (like categorizing an expense: "Is this 🍔 Food or 🚗 Transport?") to make data entry frictionless.

## LINE ↔ LIFF Transition Patterns

Based on the case studies, successful services employ the following patterns to prevent the "leaving the app" feeling:

1.  **Immediate LINE Login (`liff.init()`):** Apps use `liff.init()` to authenticate silently. Users should *never* see a secondary login screen unless they are linking an external legacy account.
2.  **Half-Modal vs. Full-Screen:**
    *   **Half-Modal (LIFF Size: Tall/Compact):** Used for quick actions (e.g., showing a barcode, quick transfer confirmation). Keeps the chat visible in the background, reinforcing context.
    *   **Full-Screen (LIFF Size: Full):** Used for complex tasks (e.g., viewing a dashboard, editing settings, reading reports).
3.  **UI/UX Continuity:** LIFF apps must use native-feeling UI components. Using LINE's seed colors or matching iOS/Android native standard fonts (San Francisco/Roboto) makes the webview feel like a native screen.
4.  **Graceful Exits:** Using `liff.closeWindow()` tied to a clear "Done" or "Back to Chat" button, returning the user smoothly to the conversational context, often accompanied by sending a confirmation message to the chat (`liff.sendMessages()`).
5.  **Skeleton Loading:** Because LIFF relies on webviews, initial load can take 1-2 seconds. Best cases use skeleton screens matching the final layout rather than blank white screens or spinning loaders.

## Chat vs LIFF Responsibility Matrix

To optimize the MaewSom experience, we must delineate what belongs in the chat interface versus the LIFF web application.

| User Job | Chat | Quick Reply | Flex Message | Rich Menu | LIFF | Why |
| :--- | :---: | :---: | :---: | :---: | :---: | :--- |
| **View real-time alerts** (e.g., large expense) | ✅ | | | | | Push notifications are immediate and demand attention. |
| **Quick Expense Categorization** | ✅ | ✅ | | | | Quick Replies reduce a multi-step form to a single tap in the chat flow. |
| **View Daily Overview / Balance** | | | | ✅ | | Dynamic Rich Menu provides zero-click information every time the chat is opened. |
| **Share Split-Bill Request** | ✅ | | ✅ | | | Flex Messages look professional and can be shared to groups natively. |
| **Review Transaction History** | | | | | ✅ | Scrolling through deep history requires a list view and filters, poorly suited for chat bubbles. |
| **Statement Reconciliation** | | | | | ✅ | Requires complex data comparison, sorting, and editing—a full UI is needed. |
| **Account Settings & Profile** | | | | | ✅ | Low frequency, high complexity task. Belongs in a full-screen LIFF. |
| **Goal Tracking Dashboard** | | | | | ✅ | Requires charts, progress bars, and dense information visualization. |
| **Quick Confirmation** (Yes/No) | ✅ | ✅ | | | | Chat is perfect for binary, immediate decisions. |

## Key Findings for MaewSom

1.  **Zero-Click Context:** Leverage dynamic Rich Menus to show current budget status or balance immediately upon opening the chat.
2.  **Micro-Interactions via Chat:** Use Quick Replies for friction-free expense logging and categorization. Do not force users into a web form for a 2-second task.
3.  **Macro-Interactions via LIFF:** Reserve LIFF (Full or Tall sizes) for dashboards, complex forms, and historical data views.
4.  **Closed Loop:** Whenever a user completes an action in the LIFF app (e.g., creating a savings goal), close the window and instantly push a beautifully designed Flex Message into the chat summarizing the action. This confirms success and keeps the chat history as the ultimate source of truth.
5.  **Performance is UX:** The biggest failure point of LIFF is feeling like a slow website. Implement aggressive caching, skeleton screens, and minimal initial bundle sizes so the LIFF modal feels instantaneous.

