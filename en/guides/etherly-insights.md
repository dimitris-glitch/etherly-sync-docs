---
title: 'Etherly Insights'
description: 'Give AI tools like Claude, ChatGPT, or Grok access to your booking and revenue data.'
---

## What is Etherly Insights

Etherly Insights lets AI tools (Claude, ChatGPT, Grok, and anything else that supports MCP) read your booking and revenue data, so you can ask questions like "How much revenue did I make last month?" or "Find the booking with ID HM-12345" directly in your AI tool of choice.

<Note>
Looking for programmatic access to your data (REST/OpenAPI, no AI tool involved)? See the
**"Data Access (API)"** guide.
</Note>

<Note>
Etherly Insights is **strictly read-only**. No AI tool can create, modify, or delete data through this connection.
</Note>

---

## How it works

Etherly Insights isn't a separate app you open — it's a connection that gives the AI tool of
your choice access to your data, so you can ask questions naturally, the way you'd ask a
colleague.

- **Ask freely**: You don't need to know tool names or special syntax. Your AI tool reads your
  question and picks the right slice of data on its own (revenue, bookings, cleaning,
  arrivals/departures, and more).
- **Live data**: Every question pulls the most current data directly from your account at the
  moment you ask.
- **Only your data**: Each connection sees exclusively your own business's properties,
  bookings, and revenue.
- **Multiple connections**: You can connect more than one AI tool at the same time (e.g. Claude
  Desktop and ChatGPT), each as a separate connected app, and manage or disconnect them
  independently.

### Example questions

- "How much revenue did I make last month by booking channel?"
- "Which properties have the highest occupancy rate this year?"
- "What arrivals do I have tomorrow, and which are ready for check-in?"
- "What was my cancellation rate last month?"

---

## Guest privacy

Guest personal details are **never** shared through Etherly Insights: name, email, phone, and identification number never appear in the results. Only non-identifying fields are allowed (nights, amounts, booking channel, and guest country of origin — derived from the phone's country code, not actual nationality).

---

## Enabling it

<Steps>
  <Step title="Go to settings">
    Go to **Settings → API Keys** and find the **Etherly Insights** card under the Apps
    section. Click **"Enable"** — a consent popup opens.
  </Step>
  <Step title="Enable the feature">
    Read the short consent notice in the popup and click **"Enable"**. Once enabled, the
    **"Etherly Insights"** tab appears permanently in the Settings menu, with your **MCP
    endpoint** and the list of connected apps.
  </Step>
</Steps>

<Note>
You can skip this step if you prefer — approving a connection via Claude.ai, Grok, or ChatGPT
(below) enables Etherly Insights automatically.
</Note>

---

## Connecting an AI tool

On the **Etherly Insights** tab you'll find your **MCP endpoint** — the URL you need to connect
any AI tool that supports MCP.

### Connecting via Claude.ai (OAuth)

Claude.ai's **"Add custom connector"** feature only supports OAuth, not a raw API key. To connect it:

<Steps>
  <Step title="Add the connector">
    In Claude.ai, go to **Settings → Connectors**, click the **"Add"** button in the top right,
    and select **"Add custom connector"**.
  </Step>
  <Step title="Fill in the details">
    Give it a name (e.g. "Etherly Insights") and paste the **MCP endpoint** URL
    (`https://app.etherly.app/api/insights/mcp`) into the **"Remote MCP server URL"** field. You
    don't need to fill in the optional "OAuth Client ID / Secret" fields under Advanced
    settings — leave them blank and click **"Add"**.
  </Step>
  <Step title="Sign in and approve">
    Claude opens a sign-in and consent screen. Sign in with your usual Etherly
    account, then click **"Allow"** to grant access.
  </Step>
  <Step title="Done">
    The connection appears in **Settings → Etherly Insights** in the "Connected apps" list,
    with a **"Connected since"** date and its own disconnect button.
  </Step>
</Steps>

<Note>
If Etherly Insights wasn't enabled yet, approving the Claude.ai connection enables it
automatically — there's no separate manual "Enable" step first.
</Note>

### Connecting via Grok (OAuth)

<Steps>
  <Step title="Add the connector">
    In Grok, go to **Skills and Connectors → Connectors** and click **"New Connector"**.
  </Step>
  <Step title="Custom connector">
    In the dialog that opens, select **"Custom"**, give it a name (e.g. "Etherly Insights"),
    and paste the **MCP endpoint** URL (`https://app.etherly.app/api/insights/mcp`).
  </Step>
  <Step title="Sign in and approve">
    Grok opens a sign-in and consent screen. Sign in with your usual Etherly account
    and approve access.
  </Step>
  <Step title="Done">
    The connection appears in **Settings → Etherly Insights** in the "Connected apps" list.
  </Step>
</Steps>

### Connecting via ChatGPT (OAuth)

<Steps>
  <Step title="Enable Developer mode">
    In ChatGPT, go to **Settings → Apps** and enable **"Developer mode"**.
  </Step>
  <Step title="Create a new app">
    Click **"Create app"**, give it a name (e.g. "Etherly Insights"), and optionally a short
    description.
  </Step>
  <Step title="Set the connection and authentication">
    In the **"Connection"** field, leave **"Server URL"** selected and paste the **MCP
    endpoint** URL (`https://app.etherly.app/api/insights/mcp`). Under **"Authentication"**,
    leave the default **"OAuth"**, check **"I understand and want to continue"**, and click
    **"Create"**.
  </Step>
  <Step title="Sign in and approve">
    ChatGPT opens a sign-in and consent screen. Sign in with your usual Etherly
    account and approve access.
  </Step>
  <Step title="Done">
    The connection appears in **Settings → Etherly Insights** in the "Connected apps" list.
  </Step>
</Steps>

---

## Available tools

You don't need to pick a tool yourself — just ask, and your AI tool automatically picks the
right one. The table below shows what you can ask about.

### Revenue & performance

| Tool | Description |
|---|---|
| **business-overview** | Total bookings, nights, revenue, and channel breakdown for a date range |
| **revenue-summary** | Compare bookings, nights, and revenue for this month or week against the previous one |
| **revenue-breakdown** | Breaks amounts down into gross revenue, taxes/fees, channel commission, and net owner payout |
| **cancellation-analysis** | Cancellation rate overall and by booking channel, plus the revenue lost to cancellations |

### Pricing & occupancy

| Tool | Description |
|---|---|
| **booking-pace** | How far a future period's occupancy has progressed compared to the same period last year |
| **occupancy** | Occupancy rate, average nightly rate (ADR), and revenue per available room (RevPAR) per property |

### Rankings & comparisons

| Tool | Description |
|---|---|
| **channel-profitability** | Which booking channel brings in the most net revenue per night |
| **seasonality** | Bookings, nights, and revenue broken down by month for a calendar year |
| **length-of-stay-value** | Compares average nightly rate between long stays (28+ nights) and shorter ones |
| **property-leaderboard** | Ranks all your properties by revenue, bookings, or nights |

### Bookings & guests

| Tool | Description |
|---|---|
| **booking-search** | Find a booking by booking id, or by a partial guest name (matches are found by name, but the guest's name is never shown in the results — see Guest privacy below) |
| **checkin-completion-status** | See which upcoming guests have completed Online Check-In |
| **arrivals-departures** | Who's arriving/departing in a date range, flagging same-day checkout+checkin turnovers |
| **guest-nationality-mix** | Breakdown of guest country of origin (from phone country code) for a date range |
| **list-properties** | List of your properties (name, channel, location) |

### Operations

| Tool | Description |
|---|---|
| **operational-backlog** | Counts of bookings pending invoicing, cancelled, paused, long-stay, or needing manual review |
| **cleaning-readiness** | Which properties are ready for a given day, with overdue and upcoming cleaning tasks |

### Local market

| Tool | Description |
|---|---|
| **market-snapshot** | Snapshot of the short-term-rental market in your area: market occupancy, average daily rate and active listings |
| **market-comparison** | Compare your own occupancy and average rate against the local market for a month — against listings of similar capacity when known (e.g. villa vs villas), and for future months both sides are compared on bookings confirmed so far |
| **property-market-position** | Where one property sits against comparable listings in its area (same size profile): which range of the distribution its rate, occupancy and revenue fall into — requires coordinates, maximum guests, bedrooms and bathrooms to be filled in on the property card |

<Note>
Market tools rely on an external market-data source and have a daily usage allowance per account. Area precision improves when your properties have coordinates — see the "Property Configuration" guide.
</Note>

More tools will be added gradually.

---

## Usage limits

- **Daily limit**: up to 500 calls/day in total across all your connected apps combined. The
  **Etherly Insights** tab shows a bar with today's usage against this limit.
- A per-minute rate limit also applies for security reasons.

If a limit is exceeded, the AI tool will receive an error and should wait before retrying.

---

## Revoking access

- To disconnect an app (e.g. Claude), click the delete icon next to it in the "Connected apps"
  list.
- To fully disable Etherly Insights, click **"Disable"** — all connected apps are disconnected
  immediately.

<Note>
Revocation takes effect immediately — there is no delay or cache that would let a disconnected app keep working.
</Note>
