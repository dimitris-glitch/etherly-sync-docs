---
title: "FAQ & Troubleshooting"
description: "Solutions for the most common issues with Etherly Sync — from initial setup to failed invoice sends."
---

# Frequently Asked Questions

## Setup & Connection

<AccordionGroup>
  <Accordion title="My checkouts show NEEDS_SETUP status. What do I do?">
    The property isn't fully configured. Go to **Properties**, select the property, and complete all four required fields:
    - **Elorus Contact** — a customer account in Elorus
    - **Invoice Sequence** — a document numbering series
    - **Fee Category** — for the Climate Resilience Fee
    - **Elorus Organization** — which organization issues the documents

    After saving, checkouts change from `NEEDS_SETUP` to `READY` on the next sync (within 5 minutes).
  </Accordion>

  <Accordion title="My Hosthub API key has changed. How do I update it?">
    Go to Settings → **Hosthub Connection** → **Update API Key**. Enter the new key and click Validate. Sync resumes normally without any data loss.
  </Accordion>

  <Accordion title="Can I have multiple Elorus organizations under the same account?">
    Yes. Go to Settings → **Invoicing Connections** → **Add Connection** to add a new Elorus API key. Each property can then be independently assigned to a different organization — useful if you manage properties under different tax IDs.
  </Accordion>
</AccordionGroup>

## Failed Sends

<AccordionGroup>
  <Accordion title="The send fails with «Invalid contact». What does that mean?">
    The contact account configured for the property doesn't exist or is inactive in Elorus. Check Elorus → Contacts to confirm the contact is active, then re-select it from the property settings in Etherly Sync.
  </Accordion>

  <Accordion title="A checkout shows SENT_WITH_ERRORS. What happened?">
    The invoice and payment receipt were **issued successfully**, but the Climate Resilience Fee document failed. Check:

    1. Whether the fee category is correctly configured in Properties
    2. Whether the tax rules in Elorus are up to date

    Contact support at [support@etherly.io](mailto:support@etherly.io) if the issue persists.
  </Accordion>

  <Accordion title="Can I cancel a document that was issued by mistake?">
    Document cancellation is done **directly in Elorus** — it's not available through the Etherly Sync UI. After cancelling in Elorus, the checkout in Etherly Sync remains in `SENT` status. Contact support if you need the status reset for re-issuing.
  </Accordion>

  <Accordion title="A send keeps failing repeatedly. What should I check?">
    In order:
    1. **Elorus API key** — verify it's still valid in Settings
    2. **Invoice Sequence** — confirm the sequence is active in Elorus
    3. **Elorus Organization** — ensure the organization allows the document type
    4. **Credits** — check your balance in Billing

    If none of the above resolves it, contact support with the error message.
  </Accordion>
</AccordionGroup>

## Sync

<AccordionGroup>
  <Accordion title="Why aren't new checkouts syncing?">
    Possible causes:
    - **Hosthub API key expired or invalid** — check Settings → Hosthub Connection
    - **New bookings without a checkout date** — they won't appear as checkouts until a date is set
    - **Hosthub API timeout** — the system retries automatically, but contact support if it persists

    Try a manual sync by clicking **Sync Now** in the dashboard.
  </Accordion>

  <Accordion title="A booking was cancelled in Hosthub but still shows as active. Why?">
    Cancellations are detected on the next sync (within 5 minutes). Once detected, the checkout is marked cancelled and removed from the invoicing queue. If it still shows as active after 15 minutes, try **Sync Now**.
  </Accordion>
</AccordionGroup>

## Climate Resilience Fee

<AccordionGroup>
  <Accordion title="How does the fee calculation work for bookings spanning two seasons?">
    If a booking crosses between winter (Nov 1 – Mar 31) and summer (Apr 1 – Oct 31), the system:
    1. Calculates the nights per season
    2. Applies the correct rate for each season
    3. Creates **separate fee documents** — one per season

    This happens automatically with no action required from you.
  </Accordion>

  <Accordion title="What happens if the fee amounts change by law?">
    Fee amounts are pulled from the **tax codes in Elorus** — they're not hardcoded in Etherly Sync. If the law changes, simply update the amounts in Elorus and Etherly Sync retrieves them automatically on the next send.
  </Accordion>
</AccordionGroup>

## Auto-Invoicing

<AccordionGroup>
  <Accordion title="Auto-invoicing didn't run last night. Why?">
    Possible causes:
    - No checkouts were in `READY` status at execution time
    - Credits ran out — check Billing
    - The account was past its grace period
    - A rare technical issue — contact support

  </Accordion>

  <Accordion title="Can I change the auto-invoicing time?">
    Yes, anytime. Settings → **Auto-Invoicing** → change the time → Save. The change takes effect from the next execution.
  </Accordion>
</AccordionGroup>

## Billing

<AccordionGroup>
  <Accordion title="When does my free trial end?">
    The free trial lasts **30 days** from account creation. The exact expiry date is shown in Settings → Billing.
  </Accordion>

  <Accordion title="What happens when my credits run out?">
    You get a **7-day grace period** during which invoicing continues normally. After 7 days, new sends are blocked until you purchase more credits. The negative balance is deducted from your next purchase.
  </Accordion>
</AccordionGroup>

## General

<AccordionGroup>
  <Accordion title="I need help that's not covered here.">
    Contact us at [support@etherly.io](mailto:support@etherly.io). We respond within **1 business day**. In your message, include:
    - The property or checkout experiencing the issue
    - The error message (if any)
    - The date you first noticed the problem
  </Accordion>
</AccordionGroup>
