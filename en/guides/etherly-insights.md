---
title: 'Etherly Insights'
description: 'Give AI tools like Claude, ChatGPT, or Gemini access to your booking and revenue data.'
---

## What is Etherly Insights

Etherly Insights lets AI tools (Claude, ChatGPT, Gemini, and anything else that supports MCP or OpenAPI) read your booking and revenue data, so you can ask questions like "How much revenue did I make last month?" or "Find the booking for John Smith" directly in your AI tool of choice.

<Note>
Etherly Insights is **strictly read-only**. No AI tool can create, modify, or delete data through this connection.
</Note>

---

## Guest privacy

Guest personal details are **never** shared through Etherly Insights: name, email, phone, and identification number never appear in the results. Only non-identifying fields are allowed (nights, amounts, booking channel, guest country, and nationality derived from the phone's country code).

---

## Enabling it

<Steps>
  <Step title="Go to settings">
    Go to **Settings → API Keys** and find the **Etherly Insights** card under the Apps
    section. Click **"Enable"** — a consent popup opens.
  </Step>
  <Step title="Enable the feature">
    Read the short consent notice in the popup and click **"Enable"**. Once enabled, the
    **"Etherly Insights"** tab appears permanently in the Settings menu, and you can click
    **"Configure"** in the same popup to continue.
  </Step>
  <Step title="Create an API key">
    On the **Etherly Insights** tab, click **"New key"**, give it a label (e.g. "Claude
    Desktop"), and click **"Create"**.

    <Warning>
    The key is shown **only once**. Copy it immediately — you won't be able to see it in full again.
    </Warning>
  </Step>
</Steps>

---

## Connecting an AI tool

On the same page you'll find two endpoints:

| Endpoint | Use |
|---|---|
| **MCP endpoint** (`/api/insights/mcp`) | For tools that support MCP (e.g. Claude Desktop, custom connectors) |
| **OpenAPI document** (`/api/insights/v1/openapi.json`) | For tools that connect via REST/OpenAPI (e.g. ChatGPT custom actions) |

### Connecting via Claude.ai (OAuth) — no API key needed

Claude.ai's **"Add custom connector"** feature only supports OAuth, not a raw API key. To connect it:

<Steps>
  <Step title="Add the connector">
    In Claude.ai, go to **Settings → Connectors → Add custom connector** and paste the
    **MCP endpoint** URL (`https://<your-domain>/api/insights/mcp`). No key required — leave any
    "OAuth Client ID / Secret" fields blank.
  </Step>
  <Step title="Sign in and approve">
    Claude opens a sign-in and consent screen. Sign in with your usual hosthub-elorus
    account, then click **"Allow"** to grant access.
  </Step>
  <Step title="Done">
    The connection appears in **Settings → Etherly Insights** alongside any manually-created
    API keys, labeled **"Connected app"**, with a **"Connected since"** date and its own
    disconnect button.
  </Step>
</Steps>

<Note>
If Etherly Insights wasn't enabled yet, approving the Claude.ai connection enables it
automatically — there's no separate manual "Enable" step first.
</Note>

### Connecting anything else (manual API key)

For `mcp-remote`-based local configs, or REST/OpenAPI tools like ChatGPT custom actions,
create an API key as described above and use it as a **Bearer token** in the `Authorization`
header when setting up the connection in your AI tool.

---

## Available tools (Phase 1)

| Tool | Description |
|---|---|
| **business-overview** | Total bookings, nights, revenue, and channel breakdown for a date range |
| **booking-search** | Search for a booking by guest name or booking id |

More tools will be added gradually.

---

## Usage limits

- **Rate limit**: up to 20 calls/minute per key.
- **Daily limit**: up to 500 calls/day per key.

If a limit is exceeded, the AI tool will receive an error and should wait before retrying.

---

## Revoking access

- To revoke a specific API key, or disconnect an OAuth-connected app (e.g. Claude), click the
  delete icon next to it in the list — both kinds are managed from the same place.
- To fully disable Etherly Insights, click **"Disable"** — all active keys and connected apps
  are revoked immediately.

<Note>
Revocation takes effect immediately — there is no delay or cache that would let a revoked key or disconnected app keep working.
</Note>
