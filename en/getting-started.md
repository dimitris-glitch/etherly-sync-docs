---
title: "Getting Started"
description: "Connect Hosthub and Elorus in 4 simple steps and send your first document in under 10 minutes."
---

# Getting Started with Etherly Sync

Setup takes **4 steps** and about 10 minutes. Before you begin, make sure you have:

- A **Hosthub** account with at least one active property
- An **Elorus** account with at least one organization
- API keys for both services

---

## Step 1: Create your account

Go to [app.etherly.app/auth/register](https://app.etherly.app/auth/register) and sign up. You'll receive a verification email — click the link and you'll land directly in the setup wizard.

<Info>
Your account starts with a **Free Trial Period** — no credit card required. After the trial ends, billing is per active property per month via Stripe.
</Info>

---

## Step 2: Connect Hosthub

In the setup wizard, select the **"Connect Hosthub"** step.

<Steps>
  <Step title="Find your Hosthub API key">
    In Hosthub, click on your profile name at the top right, then **Settings**. At the bottom of the page you will find the API keys settings. Click "Create new API key", give it any name and Save. Copy the key that will be created.
  </Step>
  <Step title="Enter the key and test the connection">
    Paste the key in the **Hosthub API Key** field and click **"Test connection"**.
  </Step>
  <Step title="Confirm and continue">
    After a successful connection you'll see "Connection successful. Property sync started." Click **"Continue"**.
  </Step>
</Steps>

---

## Step 3: Connect Elorus

Select the **"Connect Elorus"** step.

<Steps>
  <Step title="Find your Elorus API key">
    In Elorus, go to **Settings** (top right, click on your name) → **API Settings** → "Create new key". Copy the key that will appear.
  </Step>
  <Step title="Enter the key and Organization ID">
    Paste the key in the **Elorus API Key** field. For the **Organization ID**: in Elorus go to Settings → Organization — the ID appears in the page URL.
  </Step>
  <Step title="Test connection and continue">
    Click **"Test connection"**. After success you'll see "Connection successful. Ready to use." Click **"Continue"**.
  </Step>
</Steps>

<Warning>
Your Elorus API key is stored **encrypted** and is never displayed in plain text after saving.
</Warning>

---

## Step 4: Configure your first property

Click **"Go to Dashboard"** and navigate to **Settings → "Properties" tab**. Each property needs the following settings:

| Field | What it is |
|-------|-----------|
| **Default Receipts Contact** | The customer account in Elorus for receipts |
| **Invoices Series / Receipts Series** | Numbering series for invoices and receipts (or "No Series") |
| **Category** | The category for the Climate Resilience Fee |
| **Organization** | The Elorus organization that issues the documents |

<Tip>
See the detailed [Property Configuration Guide](/en/guides/properties) for step-by-step instructions.
</Tip>

---

## Sending your first document

Once a property is configured, its bookings appear with status **READY** (green indicator).

<Steps>
  <Step title="Find a READY booking">
    In **Bookings**, ready bookings are shown with a green status badge.
  </Step>
  <Step title="Click the send button">
    Click the send button next to the booking — it is named after the invoicing provider set for that property (for example **"Send to Elorus"**). You can also select multiple bookings for bulk sending.
  </Step>
  <Step title="Watch the status update">
    In a few seconds, the status changes to **SENT**. A direct link to the Elorus document appears automatically. If myDATA submission is enabled, the status may briefly show **WAITING_MYDATA_FINALIZATION** while the tax authority registers the document — it will reach **SENT** automatically once finalization completes.
  </Step>
</Steps>

<Check>
Your first document has been issued successfully in Elorus. If myDATA submission is enabled in your Elorus settings, the document is also forwarded to the tax authority automatically.
</Check>

---

## Available integrations

Under **Settings → Integrations** you'll find all available connections:

| Integration | What it does |
|-------------|-------------|
| **Hosthub** | Automatic booking sync |
| **Elorus** | Document issuance and myDATA submission |
| **Airbnb (CSV)** | Import bookings from a CSV file |
| **AADE Connect** | Connect to AADE for short-term rental declarations |

### Deleting a booking connection

You can delete a booking connection (Hosthub or Airbnb) from
**Settings → Integrations** using the delete icon. Deletion completes safely:

- If the connection is syncing at that moment, the status
  **"Connection is being deleted"** is shown and deletion completes
  automatically in the background — the connection stays visible until it
  finishes.
- The connection's credentials are destroyed immediately when the deletion is
  requested.
- Check-outs with issued documents are **retained** as fiscal history,
  together with their AADE declarations — deletion covers the connection's
  operational data (calendars, non-invoiced bookings, properties without
  fiscal history).
- If deletion does not complete, the connection shows a clear status and a
  retry button — no other action is needed.

## What's next

<CardGroup cols={2}>
  <Card title="Property Configuration" icon="house" href="/en/guides/properties">
    Set up contacts, series, and fee categories for each property.
  </Card>
  <Card title="Auto-Invoicing" icon="clock" href="/en/guides/auto-invoicing">
    Enable nightly auto-invoicing for zero manual work.
  </Card>
  <Card title="Understanding Bookings" icon="list-check" href="/en/guides/checkouts">
    Learn what each booking status means and how to act on it.
  </Card>
  <Card title="Add Users" icon="users" href="/en/guides/team">
    Invite colleagues to manage bookings alongside you.
  </Card>
</CardGroup>
