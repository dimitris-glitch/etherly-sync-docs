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
in plain language? See the **"DeskBoy Insights"** guide.
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
  "https://app.deskboy.app/api/data-access/v1/business-overview?from=2026-01-01&to=2026-01-31"
```

---

## Available tools

The same tools as DeskBoy Insights, one endpoint per tool (e.g. `/api/data-access/v1/occupancy`). The full list with descriptions is in the [DeskBoy Insights → Available tools](/en/guides/etherly-insights#available-tools) guide. Each endpoint's parameters and response schemas are in the **OpenAPI document**.

<Note>
Market tools rely on an external market-data source and have their own daily usage limit per account.
</Note>

## Usage limits

- A daily usage limit applies, shared across all your keys.

If a limit is exceeded, you'll receive an error and should wait before retrying.

---

## Revoking access

- To revoke a specific API key, click the delete icon next to it in the list.
- To fully disable Data Access, click **"Disable"** — all active keys are revoked immediately.

<Note>
Revocation takes effect immediately — there is no delay or cache that would let a revoked key keep working.
</Note>
