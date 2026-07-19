---
title: 'Data Access (API)'
description: 'Programmatic access to your booking and revenue data via REST/OpenAPI.'
---

## What is Data Access

Data Access lets you read your booking and revenue data programmatically, through a simple
key-based REST API, with no AI tool involved. It's useful if you want to feed your own
dashboards, spreadsheets, or internal tools with your data.

<Note>
Looking to connect an AI tool (Claude, ChatGPT, Grok) so you can ask questions about your data
in plain language? See the **"Etherly Insights"** guide.
</Note>

<Note>
Data Access is **strictly read-only**. No call can create, modify, or delete data.
</Note>

---

## Guest privacy

Guest personal details are **never** returned: name, email, phone, and identification number
never appear in the results. Only non-identifying fields are allowed (nights, amounts, booking
channel, and guest country of origin — derived from the phone's country code, not actual
nationality).

---

## Enabling it

<Steps>
  <Step title="Go to settings">
    Go to **Settings → Advanced** and find the **"Data access (API)"** section.
  </Step>
  <Step title="Enable the feature">
    Click **"Enable"**.
  </Step>
  <Step title="Create an API key">
    Click **"New key"**, give it a label (e.g. "Internal dashboard"), and click **"Create"**.

    <Warning>
    The key is shown **only once**. Copy it immediately — you won't be able to see it in full again.
    </Warning>
  </Step>
</Steps>

---

## Connecting your application

In the same section you'll find:

| Item | Use |
|---|---|
| **REST endpoint** (`/api/data-access/v1`) | Base for your calls (e.g. `/api/data-access/v1/business-overview`) |
| **OpenAPI document** (`/api/data-access/v1/openapi.json`) | Full schema for tools that generate clients automatically |

Use your key as a **Bearer token** in the `Authorization` header:

```bash
curl -H "Authorization: Bearer eth_data_..." \
  "https://app.etherly.app/api/data-access/v1/business-overview?from=2026-01-01&to=2026-01-31"
```

---

## Available tools

The same tools as Etherly Insights — each endpoint corresponds to one tool.

### Revenue & performance

| Endpoint | Description |
|---|---|
| **business-overview** | Total bookings, nights, revenue, and channel breakdown for a date range |
| **revenue-summary** | Compare bookings, nights, and revenue for this month or week against the previous one |
| **revenue-breakdown** | Breaks amounts down into gross revenue, taxes/fees, channel commission, and net owner payout |
| **cancellation-analysis** | Cancellation rate overall and by booking channel, plus the revenue lost to cancellations |
| **revenue-projection** | Revenue estimate for a future period with fill scenarios for the still-unsold nights |

### Pricing & occupancy

| Endpoint | Description |
|---|---|
| **booking-pace** | How far a future period's occupancy has progressed compared to the same period last year |
| **occupancy** | Occupancy rate, average nightly rate (ADR), and revenue per available room (RevPAR) per property |
| **listed-rates** | A property's listed prices and minimum stay as shown on the channel, with a weekend/weekday summary. Availability is split out: nights open in the price list vs. nights actually free (open **and** unbooked), after cross-referencing the booking calendar |

### Rankings & comparisons

| Endpoint | Description |
|---|---|
| **channel-profitability** | Which booking channel brings in the most net revenue per night |
| **seasonality** | Bookings, nights, and revenue broken down by month for a calendar year |
| **length-of-stay-value** | Compares average nightly rate between long stays (28+ nights) and shorter ones |
| **property-leaderboard** | Ranks all your properties by revenue, bookings, or nights |

### Bookings & guests

| Endpoint | Description |
|---|---|
| **booking-search** | Find a booking by booking id, or by a partial guest name (name is never shown in the results) |
| **checkin-completion-status** | See which upcoming guests have completed Online Check-In |
| **arrivals-departures** | Who's arriving/departing in a date range |
| **guest-nationality-mix** | Breakdown of guest country of origin for a date range |
| **list-properties** | List of your properties (name, channel, location) |

### Operations

| Endpoint | Description |
|---|---|
| **operational-backlog** | Counts of bookings pending invoicing, cancelled, paused, long-stay, or needing manual review |
| **cleaning-readiness** | Which properties are ready for a given day |

### Local market

| Endpoint | Description |
|---|---|
| **market-snapshot** | Snapshot of the short-term-rental market in your area |
| **market-comparison** | Compare your own occupancy and average rate against the local market for a month |
| **property-market-position** | Where one property sits against comparable listings in its area |
| **market-trends** | The local market's monthly trajectory: demand, supply (active listings) and how many days before arrival bookings are made |
| **competitor-lineup** | The comparable listings around one property (rating, reviews, minimum stay and performance estimates) |
| **competitor-rates** | Listed prices, availability and minimum stay of specific competitor listings for the upcoming weeks |

<Note>
Market tools rely on an external market-data source and have a daily usage allowance per account.
</Note>

### Advisor

| Endpoint | Description |
|---|---|
| **etherly-advisor** | The Etherly revenue advisor: takes a question plus results from the other tools and returns grounded pricing and occupancy advice |

---

## Usage limits

- **Daily limit**: up to 500 calls/day in total across all your keys combined.
- A per-minute rate limit also applies for security reasons.

If a limit is exceeded, you'll receive an error and should wait before retrying.

---

## Revoking access

- To revoke a specific API key, click the delete icon next to it in the list.
- To fully disable Data Access, click **"Disable"** — all active keys are revoked immediately.

<Note>
Revocation takes effect immediately — there is no delay or cache that would let a revoked key keep working.
</Note>
