## Screen Overview

This document describes the main screens for the MVP of the financial literacy app, with an explicit **neurodivergent-first but inclusive** design mindset. Each screen should:

- Use a **predictable layout** pattern.
- Present **few choices at a time**.
- Offer **progressive disclosure** (simple first, details on demand).
- Clearly distinguish **real account data** from **virtual/simulation data**.

Planned screens:

1. Home / Overview  
2. Notifications & Next Steps  
3. Smart Spending Profile / Insights  
4. Quests & Simulation Hub  
5. Achievements & Progress  
6. Settings & Mode / Account  

---

## 1. Home / Overview Screen

**Goal:** Give a calm, at-a-glance view of the user’s current situation and one or two obvious next actions.

### Main content (above the fold)

- **Mode banner (small):**
  - Text only, at the top:
    - `Practice mode – virtual money only` **or**
    - `Real account – read-only data from [Bank Name]`
  - Short explanatory subline:
    - “We cannot move or spend your money, only analyze it.”

- **Card 1 – Current Money:**
  - Large number with label:
    - `Available this month` (virtual or real, depending on mode).
  - Optional small breakdown indicator:
    - “Essentials / Wants / Savings: 60% / 25% / 15%”.
  - Optional button: `View details` → opens breakdown in Profile/Insights.

- **Card 2 – Main Goal:**
  - Goal name: e.g. `Emergency buffer`, `Move-out fund`.
  - Simple progress bar:
    - Label: `€350 / €1 000` plus approximate time estimate if available (`~5 months at current pace`).
  - Button: `Adjust goal` (opens goal editor or suggestion flow).

- **Card 3 – Short status message:**
  - One sentence, neutral tone:
    - “You’re roughly on track this month.”  
    - “You’re spending more than your usual pattern in Wants.”  
    - “Your impulse spending is higher than last month; want to review?”
  - Button row below:
    - `Next steps` (opens Notifications & Next Steps).
    - `Practice quests` (opens Quests & Simulation Hub).

### Neurodivergent-inclusive notes

- Limit to **3 core cards** above the fold, with consistent order.
- Use **icon + label** combinations; never icon-only.
- Provide a “**Focus mode**” toggle (perhaps in settings but affecting this screen):
  - When on, only show:
    - Mode banner
    - Current Money card
    - Main Goal card
  - Hide the short status card and extra hints.

---

## 2. Notifications & Next Steps Screen

**Goal:** Show insights and suggested actions without pressure or overload.

### Structure

- **Tabs or filters (simple):**
  - `Insights`
  - `Wins`

- **Insights tab:**
  - List of short cards (max ~5 visible; older ones archived):
    - Example: “Your spending in Wants is 23% higher than your usual week. [Review pattern]”
    - Example: “Spending looks more impulsive than usual this month. [See impulse radar]”
  - Each card:
    - Label/tag indicating **real data** or **practice suggestion**.
    - Optional tiny icon showing category (food, shopping, etc.).

- **Wins tab:**
  - Cards like:
    - “You kept your Essentials within plan for 3 weeks.”
    - “You added €50 to your emergency fund this month.”
  - Button on each card: `See details` → typically goes to Profile/Insights or Achievements.

- **Next Steps strip (top or bottom):**
  - Show up to **3 “next steps”** derived from the Smart Spending Profile:
    - “Review last week’s spending in Wants.”
    - “Try the ‘First month alone’ practice quest.”
    - “Adjust your savings amount for next month.”
  - Each next step has:
    - Title + one-line explanation
    - One action button (e.g. `Start`, `Open`).

### Neurodivergent-inclusive notes

- Provide notification intensity options in Settings:
  - `Quiet` (e.g. daily summary only), `Normal`, `Active`.
- Avoid alarming wording; use **neutral, descriptive language** (“looks more than usual”, not “dangerous”).
- Keep **actions optional** with clear “Dismiss” or “Not now” on each card.

---

## 3. Smart Spending Profile / Insights Screen

**Goal:** Explain the user’s financial “DNA” in a clear, non-judgmental way.

### Sections

1. **How you usually spend**
   - Horizontal bar or simple donut for:
     - `Essentials`, `Wants`, `Savings` over a selected period.
   - Plain-language summary:
     - “You typically spend about 65% on Essentials, 20% on Wants, and 15% goes to Savings.”

2. **Your patterns**
   - A few bullet points based on analysis and Nyrhinen-inspired impulse radar:
     - “Most of your impulse-like purchases happen after 21:00.”
     - “Spending spikes in [category] once a month around payday.”
   - Link to “See impulse radar” (more detail optional).

3. **Your strengths**
   - At least 2–3 positive points:
     - “You pay rent consistently and on time.”
     - “You have not used overdraft in the last 3 months.”
     - “You have kept your Savings share at or above 10% for 2 months.”

### Controls

- Time range selector (simple): `Last 30 days`, `Last 90 days`.
- “More details” toggles for users who want deeper stats (category-level charts).

### Neurodivergent-inclusive notes

- Avoid evaluative labels like “bad”, “reckless”; use neutral descriptors (“higher risk zone”, “less stable area”).
- Text should be short and bullet-based, with optional “More info” links for those who like depth.
- Structure should be identical every time (3 sections), so users know what to expect.

---

## 4. Quests & Simulation Hub

**Goal:** Provide a safe space to experiment with decisions using **virtual money** (and optionally real numbers as a starting point).

### Screen layout

- **Header:**
  - Title: `Practice area – virtual money only`
  - Subtext: “Scenarios here never affect your real bank account.”

- **Quest list:**
  - Show a small set of recommended quests (e.g. 3–5):
    - `Survive your first month living alone`
    - `Build your first emergency fund`
    - `Impulse challenge: avoid last-minute buys for a week`
  - Each quest card:
    - 1-line description.
    - Duration label: `Short (~5 min)`, `Medium (~10 min)`.
    - Tag:
      - `Purely virtual` (no real data) or
      - `Starts from your real numbers` (income, rent).

- **Inside a quest (flow pattern)**:

  1. **Intro Step**  
     - Brief description of scenario.  
     - Clear statement “Virtual money only.”
     - Button: `Start`.

  2. **Setup Step**  
     - Pre-filled fields (income, rent, etc. – from real data if applicable).  
     - User can adjust via sliders or simple inputs.  
     - Button: `Next`.

  3. **Decision Steps** (2–3 screens)  
     - Each shows:
       - Short situation text.
       - 2–3 options (buttons) with short labels.
     - No timers; no more than 3 choices per screen.

  4. **Result Step**  
     - Summary: “At this plan, you would reach your goal in ~5 months.”  
     - Simple visual (bars/timeline) plus bullet list (pros/cons).  
     - Optional: `Save this as a plan` or `Leave it as practice only`.

### Neurodivergent-inclusive notes

- All quests follow the **same step pattern**, so the interaction becomes predictable.
- Offer a “**Skip story text**” toggle for users who prefer to jump straight to decisions.
- No penalty for quitting mid-quest; make `Exit` always visible and safe.

---

## 5. Achievements & Progress Screen

**Goal:** Celebrate learning and behavior progress without pressure or competition.

### Content

- **Sections:**
  - `Learning` – quest completions, knowledge checkpoints.
  - `Habits` – savings milestones, streaks, reduced impulse episodes.

- **Badge design:**
  - Each badge:
    - Icon + short title.
    - 1-line “what it means”.
  - Example:
    - “First 100€ buffer – You’ve saved your first €100 towards your emergency fund.”
    - “Calmer spending month – Your impulse radar looked more stable this month.”

- No leaderboards or comparison to other users.

### Neurodivergent-inclusive notes

- Offer option to **hide or collapse** certain groups (e.g. streak-based badges) if they cause stress.
- Avoid gamified pressure like “daily login streaks”; focus on meaningful, self-relevant milestones.

---

## 6. Settings & Mode / Account Screen

**Goal:** Give users control over modes, notifications, and sensory load, and clarify what the app can and cannot do.

### Sections

1. **Mode & Accounts**
   - Current mode indicator:
     - `Practice mode – virtual money only`
     - or `Real account – read-only from [Bank Name]`
   - Short explanation of read-only access:
     - “We can see balances and transactions but cannot move or spend your money.”
   - Button(s):
     - `Connect bank account` (if not connected).
     - `Manage connected accounts`.

2. **Notifications**
   - Intensity selector (radio buttons or slider):
     - `Quiet (daily summary)`, `Normal`, `Active`.
   - Toggle: `Digest mode` (combine multiple messages into one).

3. **Accessibility & Sensory**
   - Toggles:
     - `Low stimulation mode` (simplify visuals, reduce animations).
     - `Larger text`.
   - Option: `Show fewer advanced stats (keep it simple)`.

4. **Privacy & Data**
   - Summary of what data is stored and how it’s used in simple language.
   - Link to full policy (for later).

### Neurodivergent-inclusive notes

- Group settings logically with clear headings and spacing; avoid long, unstructured lists.
- Use toggles and simple choices rather than nested, complex menus.
- Default settings should already be safe and calm; these options let users opt into “more”.

---

## Notes for Future Iteration

- When designing actual mocks, keep:
  - **One main CTA per screen** (others secondary).
  - **Consistent iconography and colour coding** for:
    - Practice vs real modes.
    - Insights vs wins.
  - The ability to test with both neurodivergent and neurotypical users for feedback on wording and visual density.
