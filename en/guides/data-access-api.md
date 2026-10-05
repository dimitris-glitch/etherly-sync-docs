---
title: 'Data Access (API)'
description: 'Programmatic access to your booking, document and revenue data, through a REST API and webhooks.'
---

## What is Data Access

Data Access lets you read your data programmatically, through a key-based REST API, and have your
application notified by webhooks when something changes. It's useful if you want to feed your own
dashboards, spreadsheets, or internal tools with your data.

<Note>
Looking to connect an AI tool (Claude, ChatGPT, Grok) so you can ask questions about your data
in plain language? See the **"DeskBoy MCP"** guide.
</Note>

<Note>
The Data Access API and its keys are read-only — no endpoint of this API issues, modifies or
declares anything.
</Note>

---

## What you can read

- **Properties** and **bookings**, with dates, channel, amounts and each booking's invoicing status.
- **Documents** issued for your bookings.
- **AADE declarations** and their status.
- **Online check-in** for your bookings.
- **Reports** of revenue and occupancy per month, property and channel.
- **Monthly files** (CSV or JSON) with a month's bookings, documents or AADE declarations — ready
  for your accountant; CSV also in a format for Excel with Greek regional settings.

---

## What each key can read

For each key you choose what it can read — for example only **Reports** for a revenue
dashboard, or **Bookings** for an operations tool. Give each key only what the application
using it needs.

To change what a key can read, create a new key with the choices you want, put it in your
application, and then revoke the old one.

The OpenAPI document shows the access each endpoint needs. If a key lacks it, the call returns an
error naming the access that is missing.

---

## Guest privacy

Guest personal details — name, email and phone on bookings; phone, notes and fellow guests' names
from online check-in; the link to each invoice — are not returned unless the account **Owner**
turns on **Guest details** for a key, when creating it; the account admins are notified by email.
Without them, only non-identifying fields are returned (nights, amounts, booking channel, and
guest country of origin — derived from the phone's country code, not actual nationality).

<Note>
A guest's identity document number is not included in any response, with any key.
</Note>

---

## Enabling it

<Steps>
  <Step title="Go to settings">
    Go to **Settings → Data access (API)**.
  </Step>
  <Step title="Enable the feature">
    Click **"Enable"**.
  </Step>
  <Step title="Create an API key">
    Click **"New key"**, give it a label (e.g. "Internal dashboard"), choose **what this key can
    read**, and click **"Create"**.

    <Warning>
    The key is shown **only once**. Copy it immediately — you won't be able to see it in full again.
    </Warning>
  </Step>
</Steps>

Each key expires 12 months after it is created, and is revoked automatically if it goes unused for
90 days. The expiry date is shown next to each key.

---

## Connecting your application

On the same page you'll find:

| Item | Use |
|---|---|
| **REST endpoint** (`/api/data-access/v1`) | Base for your calls (e.g. `/api/data-access/v1/bookings`) |
| **OpenAPI document** (`/api/data-access/v1/openapi.json`) | Full schema for tools that generate clients automatically |
| **Developer guide** | Pagination, errors, monthly files, webhooks, signature verification and ready-made examples |

The developer guide is inside the app and opens once you are signed in.

Use your key as a **Bearer token** in the `Authorization` header:

```bash
curl -H "Authorization: Bearer deskboy_data_..." \
  "https://app.deskboy.app/api/data-access/v1/bookings?limit=50"
```

---

## Available tools

Beyond the above, the API offers the same analysis tools as DeskBoy MCP. Their endpoints are
described in the OpenAPI document (`/api/data-access/v1/openapi.json`), and the list with
descriptions is in the
[DeskBoy MCP → Available tools](/en/guides/etherly-insights#available-tools) guide.

<Note>
Market tools rely on an external market-data source and have their own daily usage limit per account.
</Note>

---

## Webhooks

With a webhook, your application is notified a few minutes after each event you choose — a new
booking, a booking change or cancellation, documents issued or an issue that needs review, an
online check-in completed, an AADE declaration submitted or failed — without having to keep
asking the API.

<Steps>
  <Step title="Add a webhook">
    In **Settings → Data access (API)**, in the **Webhooks** section, click **"New webhook"**.
  </Step>
  <Step title="Set the address and events">
    Enter your application's `https://` address and choose the **events to send**.
  </Step>
  <Step title="Keep the signing secret">
    After saving, the **signing secret** is shown, only once. Your application uses it to confirm
    that each message is genuine — the developer guide shows how.
  </Step>
</Steps>

**"Send test event"** checks the connection. **Delivery history** shows what was sent and what your
application answered, and lets you send a message again.

For a new secret, click **"New signing secret"**: the current one keeps signing messages for 24
hours, so you have time to update your application.

If deliveries keep failing, the account admins are notified by email; if none succeeds for 7 days,
the webhook is turned off automatically. When you turn it back on, it sends events from that
moment on; whatever happened in between is available through the API.

<Note>
Guest details are included in booking, invoice and online check-in events only if the Owner turns
them on for that webhook. If the webhook's address changes, or events are added that carry guest
details it did not send before, they are turned off again.
</Note>

---

## Usage limits

A daily usage limit applies, shared across all your keys, along with a per-minute call limit.
Today's usage is shown on the Data access page and returned by `GET /me`. If a limit is exceeded,
the call returns an error that says when to retry.

---

## Revoking access

- To revoke a specific API key, click the delete icon next to it in the list.
- To fully disable Data Access, click **"Disable"** — all active keys are revoked and all webhooks
  turned off immediately.

<Note>
Revocation takes effect immediately — there is no delay or cache that would let a revoked key keep working.
</Note>
