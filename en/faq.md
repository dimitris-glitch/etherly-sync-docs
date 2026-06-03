---
title: "FAQ & Troubleshooting"
description: "Solutions for the most common issues with Etherly Sync — from initial setup to failed invoice sends."
---

# Frequently Asked Questions

## Setup & Connection

<AccordionGroup>
  <Accordion title="My bookings show NEEDS_SETUP status. What do I do?">
    The property isn't fully configured. Go to **Properties**, select the property, and complete all required fields:
    - **Default Receipts Contact** — a customer account in Elorus
    - **Invoices Series** — a document numbering series for invoices
    - **Category** — for the Climate Resilience Fee
    - **Organization** — which Elorus organization issues the documents

    After clicking **Save**, bookings change from `NEEDS_SETUP` to `READY` on the next sync.
  </Accordion>

  <Accordion title="My Hosthub API key has changed. How do I update it?">
    Go to **Settings** → **Integrations**. Find the Hosthub connection and update the API key. Sync resumes normally without any data loss.
  </Accordion>

  <Accordion title="Can I have multiple Elorus organizations under the same account?">
    Yes. Go to **Settings** → **Integrations** → **"New Connection"** to add a new Elorus API key. Each property can then be independently assigned to a different **Organization** — useful if you manage properties under different tax IDs.
  </Accordion>
</AccordionGroup>

## Failed Sends

<AccordionGroup>
  <Accordion title="The send fails with a contact error. What does that mean?">
    The **Default Receipts Contact** configured for the property doesn't exist or is inactive in Elorus. Check Elorus → Contacts to confirm the contact is active, then re-select it from **Properties**.
  </Accordion>

  <Accordion title="A booking shows SENT_WITH_ERRORS. What happened?">
    The Invoice and Receipt were **issued successfully**, but the **Climate Resilience Fee** document failed. Check:

    1. Whether the **Category** is correctly configured in **Properties**
    2. Whether the tax rules in Elorus are up to date

    Contact support at [support@etherly.app](mailto:support@etherly.app) if the issue persists.
  </Accordion>

  <Accordion title="Can I cancel a document that was issued by mistake?">
    Document cancellation is done **directly in Elorus** — it's not available through Etherly Sync. After cancelling in Elorus, the booking in Etherly Sync remains in `SENT` status. Contact support if you need the status reset for re-issuing.
  </Accordion>

  <Accordion title="A send keeps failing repeatedly. What should I check?">
    In order:
    1. **Elorus API key** — verify it's still valid in **Settings** → **Integrations**
    2. **Invoices Series** — confirm the series is active in Elorus
    3. **Organization** — ensure the organization allows the document type
    4. **Credits** — check your balance under **Credits**

    If none of the above resolves it, contact support with the error message.
  </Accordion>
</AccordionGroup>

## Sync

<AccordionGroup>
  <Accordion title="Why aren't new bookings syncing?">
    Possible causes:
    - **Hosthub API key expired or invalid** — check **Settings** → **Integrations**
    - **New bookings without a checkout date** — they won't appear until a checkout date is set in Hosthub
    - **Hosthub API timeout** — the system retries automatically, but contact support if it persists

    Try a manual sync by clicking **"Sync from Hosthub"** in **Bookings**.
  </Accordion>

  <Accordion title="A booking was cancelled in Hosthub but still shows as active. Why?">
    Cancellations are detected on the next sync. Once detected, the booking is marked cancelled and removed from the invoicing queue. If it still shows as active, click **"Sync from Hosthub"**.
  </Accordion>
</AccordionGroup>

## Climate Resilience Fee

<AccordionGroup>
  <Accordion title="How does the fee calculation work for bookings spanning two seasons?">
    If a booking crosses between the winter season (Nov 1 – Mar 31) and summer season (Apr 1 – Oct 31), the system:
    1. Calculates the nights per season
    2. Applies the correct rate for each season
    3. Creates **separate fee documents** — one per season

    This happens automatically with no action required from you.
  </Accordion>

  <Accordion title="What happens if the fee amounts change by law?">
    Fee amounts are pulled from the **tax codes in Elorus** — they're not hardcoded in Etherly Sync. If the law changes, simply update the amounts in Elorus and Etherly Sync retrieves them automatically on the next send.
  </Accordion>

  <Accordion title="I can't find the right Category for my property. What do I do?">
    Categories come from the tax codes you've set up in Elorus. If the right **Category** doesn't appear, make sure you've created the corresponding tax code in Elorus. If you're unsure which category applies, consult your accountant.
  </Accordion>
</AccordionGroup>

## Auto-Invoicing

<AccordionGroup>
  <Accordion title="Auto-invoicing didn't run last night. Why?">
    Possible causes:
    - No bookings were in `READY` status at the **Execution time**
    - Credits ran out — check **Credits**
    - The account's **Grace Period** had expired
    - A rare technical issue — contact support
  </Accordion>

  <Accordion title="Can I change the auto-invoicing execution time?">
    Yes, anytime. In **Bookings → Auto-invoicing**, change the **Execution time**. The change saves automatically and takes effect from the next execution.
  </Accordion>
</AccordionGroup>

## Billing & Credits

<AccordionGroup>
  <Accordion title="When does my Free Trial Period end?">
    The **Free Trial Period** lasts **30 days** from account creation. The exact expiry date is shown under **Credits**.
  </Accordion>

  <Accordion title="What happens when my credits run out?">
    The **Grace Period** activates automatically — invoicing continues normally even with 0 credits. Once the Grace Period ends, new sends are blocked until you purchase credits under **Credits** → **"Buy Credits"**.
  </Accordion>

  <Accordion title="How do I set up automatic credit renewal (Auto Top-up)?">
    Go to **Credits** → **Auto Top-up** section → **"Enable Auto Top-up"**. Set the **Top-up Threshold** (e.g. 10 credits) and choose which package to purchase automatically. A saved card is required via **"Add Card"**.
  </Accordion>
</AccordionGroup>

## General

<AccordionGroup>
  <Accordion title="I need help that's not covered here.">
    Contact us at [support@etherly.app](mailto:support@etherly.app). We typically respond within **1-2 business days**. In your message, include:
    - The property or booking experiencing the issue
    - The error message (if any)
    - The date you first noticed the problem
  </Accordion>
</AccordionGroup>
