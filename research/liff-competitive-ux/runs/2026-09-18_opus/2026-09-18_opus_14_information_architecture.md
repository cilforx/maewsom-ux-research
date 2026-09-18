---
topic: liff-competitive-ux
date: 2026-09-18
researcher: Claude
model: Opus 4.6
status: raw
research_type: independent-pass
canonical: false
---
# DELIVERABLE 14: Research-Based Information Architecture

## Level 1 LIFF Information Architecture

Based on the research findings (specifically Copilot’s Inbox pattern, MAKE's Cloud Pockets, and LINE ecosystem constraints), here is the proposed Level 1 IA for the MaewSom LIFF application.

### Top-Level Navigation Structure (Bottom Tab Bar)
1. **Home (Dashboard)**
2. **Review Inbox**
3. **Pockets (Accounts & Budgets)**
4. **Insights**
5. **Settings (Profile & Rules)**

---

## Key Screens / Sections

### 1. Home (Dashboard)
*   **Safe-to-Spend Number:** A prominent, single number (inspired by PocketGuard) showing daily/weekly allowance.
*   **Quick Add FAB:** Floating Action Button for manual entry (crucial for cash transactions, inspired by BooJot).
*   **Recent Activity Snippet:** The last 3 transactions for quick context.
*   **Persona Element:** The Orange Cat mascot reacting to the current financial state (e.g., sleeping if all good, alert if over budget).

### 2. Review Inbox
*   *This is the core daily habit loop.*
*   **Pending Transactions:** List of e-slips or AI-captured transactions requiring categorization confirmation.
*   **1-Tap Approve/Dismiss:** Tinder-style or quick swipe gestures (inspired by Copilot and Emma).
*   **Anomaly Alerts:** Flagged items (e.g., duplicate charges).

### 3. Pockets (Accounts & Budgets)
*   **Visual Envelopes:** Instead of strict ledgers, display money in visual "Pockets" (e.g., "Food", "Rent", "Trip to Japan" - inspired by MAKE by KBank).
*   **Drag & Drop UI:** Move money between pockets visually.
*   **Linked Accounts Status:** Show which external sources (if any) are connected and their sync status.

### 4. Insights
*   **Cash Flow Trends:** Monthly income vs. expense visual.
*   **Actionable Nudges:** AI-generated recommendations (e.g., "You are spending 20% more on food this week").
*   **Tax/Savings Goals:** Progress bars towards long-term objectives.

### 5. Settings & Rules
*   **Smart Rules Engine:** Allow users to create hard rules ("If PromptPay to X, categorize as Y" - inspired by Monarch).
*   **Persona Settings:** Toggle "Serious Mode" manually or adjust the sass level.
*   **Data Export:** CSV export for trust and portability (inspired by MeKinMeChai).

---

## Chat vs. LIFF Responsibility Matrix

To maintain a native LINE feel, responsibilities are strictly divided to avoid UI clutter in LIFF and chat fatigue in LINE.

| Function | Belongs In | Rationale (Evidence) |
| :--- | :--- | :--- |
| **E-slip Upload / Logging** | **Chat** | Frictionless entry. Forwarding an image in chat takes 1 second. (LINE BK, SCB Connect) |
| **Quick Categorization** | **Chat** | Use LINE Quick Replies for binary choices (e.g., "Food or Travel?") immediately after a slip is sent. |
| **Daily Balance Check** | **Chat (Rich Menu)** | Zero-click context. Render balance on the Rich Menu via API. (PTT Blue Card) |
| **Transaction Alerts** | **Chat** | Flex Messages for instant push notifications on large expenses. |
| **Complex Reconciliation** | **LIFF** | Reviewing 20 pending transactions in chat is messy. The LIFF Review Inbox is optimized for this. (Copilot) |
| **Historical Ledger** | **LIFF** | Chat history is linear; LIFF allows sorting, filtering, and deep search. |
| **Budget Planning** | **LIFF** | Setting up "Pockets" requires visual drag-and-drop and multiple inputs. (MAKE by KBank) |
| **Shared Bill Splitting** | **Chat (Share Target)** | Users want to split bills in their friend group chats natively. (LINE MAN) |

---

## IA Rationale Tied to Research Evidence

1.  **Prioritizing the Review Inbox:** Research (Copilot, Monarch) shows that pure AI categorization breaks trust when wrong. An explicit "Review Inbox" builds a daily habit (Zero Inbox) and ensures data accuracy, which is a major pain point in the Thai market where PromptPay names are often ambiguous.
2.  **Visual Pockets over Spreadsheets:** Traditional budgeting apps (Lumpsum) overwhelm users. Visual pockets (MAKE by KBank) align with Thai consumer behaviors of compartmentalizing money.
3.  **De-cluttering the Home Screen:** Apps like TrueMoney and Paotang suffer from massive feature bloat. By moving complex insights to their own tab and keeping the Home screen focused on a single "Safe to Spend" metric, we reduce cognitive load.
4.  **Settings as a Rules Engine:** Users get frustrated with AI that repeats mistakes (Cleo). Giving them a dedicated space to manage explicit "Rules" restores a sense of control (Monarch).

