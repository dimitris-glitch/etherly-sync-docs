---
title: "Getting Started"
description: "Connect Hosthub and Elorus in 4 simple steps and send your first invoice in under 10 minutes."
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
Your account starts with a **30-day free trial** — unlimited invoice sends, no credit card required.
</Info>

---

## Step 2: Connect Hosthub

<Steps>
  <Step title="Find your Hosthub API key">
    Log in to Hosthub → **Settings** → **API** → copy your **Personal API Token**.
  </Step>
  <Step title="Enter the key in Etherly Sync">
    In the setup wizard, select **"Connect Hosthub"**, paste the key, and click **Validate**.
  </Step>
  <Step title="Confirm the connection">
    The system automatically detects your properties and shows the count. If you see an error, make sure you copied the full token without any trailing spaces.
  </Step>
</Steps>

---

## Step 3: Connect Elorus

<Steps>
  <Step title="Find your Elorus API key">
    Log in to Elorus → **Settings** → **Integrations** → **API Keys** → create a new key or copy an existing one.
  </Step>
  <Step title="Enter the key in Etherly Sync">
    Select **"Connect Elorus"**, paste the key, and click **Validate**.
  </Step>
  <Step title="Automatic detection">
    Etherly Sync automatically retrieves from Elorus:
    - Your organizations
    - The 13% VAT rate (or the closest available)
    - Available document types (invoice, receipt)
  </Step>
</Steps>

<Warning>
Your Elorus API key is stored **encrypted** (AES-256-GCM) and is never displayed in plain text after saving.
</Warning>

---

## Step 4: Configure your first property

After connecting, your properties appear in the dashboard. Each property needs four settings before invoicing can begin:

| Setting | What it is |
|---------|-----------|
| **Elorus Contact** | The customer account in Elorus (e.g., "Retail Customer") |
| **Invoice Sequence** | The document numbering series (e.g., "INV-2025") |
| **Fee Category** | The category for the Climate Resilience Fee |
| **Elorus Organization** | The organization under which documents are issued |

<Tip>
See the detailed [Property Configuration Guide](/en/guides/properties) for step-by-step instructions.
</Tip>

---

## Sending your first invoice

Once a property is configured, its checkouts appear with status **READY** (green indicator).

<Steps>
  <Step title="Find a READY checkout">
    In the main dashboard, ready checkouts are shown with a green status badge.
  </Step>
  <Step title="Click «Send»">
    Click the **Send** button next to the checkout, or select multiple for bulk sending.
  </Step>
  <Step title="Watch the status update">
    In a few seconds, the status changes to **SENT**. A direct link to the Elorus document appears automatically.
  </Step>
</Steps>

<Check>
Congratulations! Your first invoice has been automatically issued in Elorus and submitted to myDATA.
</Check>

---

## What's next

<CardGroup cols={2}>
  <Card title="Property Configuration" icon="house" href="/en/guides/properties">
    Set up contacts, sequences, and fee categories for each property.
  </Card>
  <Card title="Auto-Invoicing" icon="clock" href="/en/guides/auto-invoicing">
    Enable nightly auto-invoicing for zero manual work.
  </Card>
  <Card title="Understanding Checkouts" icon="list-check" href="/en/guides/checkouts">
    Learn what each checkout status means and how to act on it.
  </Card>
  <Card title="Add Team Members" icon="users" href="/en/guides/team">
    Invite colleagues to manage checkouts alongside you.
  </Card>
</CardGroup>
