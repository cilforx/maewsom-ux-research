---
topic: liff-competitive-ux
date: 2026-09-18
researcher: Claude
model: Opus 4.6
status: raw
research_type: independent-pass
canonical: false
---
# DELIVERABLE 15: Open Questions for User Testing

The following areas could not be definitively answered by secondary competitive research and require validation through primary user testing and observation with Thai users.

## Critical Priority (Must validate before Beta)

### AI Trust Thresholds
*   **Question:** At what point does a Thai user stop trusting the "Cat" persona with their money?
*   **Context:** Sassy AI (Cleo) works in the West, but Thai culture heavily values respect (Service Mind).
*   **To Test:** Present users with an AI-generated categorization error. Does a humorous apology ("Oops, my paws slipped") mitigate frustration, or does it feel disrespectful compared to a formal system error?

### The E-Slip Workflow
*   **Question:** What is the actual cognitive load of forwarding e-slips to a LINE OA versus using a dedicated app?
*   **Context:** We assume forwarding in LINE is frictionless (based on SCB Connect success), but batch processing might be tedious.
*   **To Test:** Observe users trying to log 5 transactions at once. Do they prefer uploading 5 images to the chat, or opening LIFF to use a multi-image picker?

### Serious Mode Triggers
*   **Question:** When exactly should MaewSom switch to "Serious Mode"?
*   **Context:** We know we need graceful tone degradation, but the trigger is ambiguous.
*   **To Test:** Is it when balance < 10%? When a bill is missed? Or should the user manually toggle it in settings?

## Important Priority (Validate during Beta)

### Thai-Specific Social Behaviors
*   **Question:** How do users actually want to split bills in LINE groups?
*   **Context:** LINE MAN allows sharing tracking links. We want to allow sharing bill splits.
*   **To Test:** Are users comfortable sending a MaewSom Flex Message requesting money into a group chat, or is it considered "impolite" (เกรงใจ) in Thai culture to use a bot to ask for money?

### Review Inbox Friction
*   **Question:** Does the "Review Inbox" pattern cause fatigue over time?
*   **Context:** Copilot's inbox is highly praised, but requires daily maintenance.
*   **To Test:** After 14 days, do users ignore the "Pending Review" queue, or does the gamification keep them engaged?

### Financial Semantics
*   **Question:** Do users understand the "Safe to Spend" metric?
*   **Context:** PocketGuard uses this successfully, but Thai users might have different mental models for daily allowances.
*   **To Test:** Show the dashboard to a user and ask, "How much money can you spend on dinner tonight based on this screen?"

## Nice-to-Have (Validate post-launch)

### Proactive Nudge Timing
*   **Question:** When is the optimal time to send a proactive LINE push notification regarding budget status?
*   **Context:** Too many notifications feel like spam (TrueMoney).
*   **To Test:** A/B test sending a daily digest at 8:00 AM versus 8:00 PM.

### Gamification Rewards
*   **Question:** What digital rewards motivate the habit loop?
*   **Context:** MeowJot uses "Salmon Streaks".
*   **To Test:** Do users prefer accumulating badges (status), unlocking new cat outfits (cosmetic), or unlocking premium features?

