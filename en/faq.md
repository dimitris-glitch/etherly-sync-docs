---
title: "FAQ & Troubleshooting"
description: "Solutions for the most common issues with DeskBoy — from initial setup to failed invoice sends."
---

# Frequently Asked Questions

## Setup & Connection

<AccordionGroup>
  <Accordion title="My bookings show “Needs setup”. What do I do?">
    The property isn't fully configured. Open **Settings → Properties**, select the property, and complete all four required fields:
    - **Default Receipts Contact** — the Elorus contact for receipts ([how to create it](/en/guides/properties#default-receipts-contact))
    - **Invoices Series** — a document numbering series for invoices
    - **ΤΑΚΚ characteristics** — for the Climate Resilience Fee
    - **Organization** — which Elorus organization issues the documents

    After you click **Save**, the “Needs setup” label goes away on the next sync.
  </Accordion>

  <Accordion title="My Hosthub API key has changed. How do I update it?">
    Go to **Settings** → **Integrations**. Find the Hosthub connection and update the API key. Sync resumes normally without any data loss.
  </Accordion>

  <Accordion title="Can I have multiple Elorus organizations under the same account?">
    Yes. Go to **Settings → Integrations** and, in the **Apps** section, click **New Connection** on the **Elorus** card. The steps are the same as for the first connection. Each property can then be independently assigned to a different **Organization**, useful if you manage properties under different tax IDs.
  </Accordion>

  <Accordion title="Can I add more connections?">
    Yes, from **Settings → Integrations**, on each service's card:
    - **Elorus**: for properties under a different tax ID, add their organization — or **New Connection**, if it is in another Elorus account (see [Properties under different tax IDs](/en/guides/properties#properties-under-different-tax-ids)).
    - **AADE Connect**: click **New Connection** for properties registered under another account in AADE's Short-Term Stay Registry, e.g. another owner's.
    - **Booking channels**: each channel connects once, and you can have different channels together, e.g. Hosthub and Smoobu.

    How many connections your plan includes is shown in [Plan & Billing](/en/guides/billing).
  </Accordion>
</AccordionGroup>

## Failed Sends

<AccordionGroup>
  <Accordion title="The send fails with a contact error. What does that mean?">
    The **Default Receipts Contact** configured for the property doesn't exist or is inactive in Elorus. Check Elorus → Contacts to confirm the contact is active, then re-select it from **Properties**.
  </Accordion>

  <Accordion title="A booking shows “Manual review” after I changed the property's organization. What do I do?">
    The booking had already received a document from the previous organization but was not completed (e.g. it was “Partial”). All of a booking's documents must come from the same organization, so it does not continue with the new one. To complete it, temporarily set the property back to the original organization and send it again. Bookings without a document are invoiced by the new organization as normal.
  </Accordion>

  <Accordion title="A booking shows “Partial”. What happened?">
    The Invoice and Receipt were **issued**, but the **Climate Resilience Fee** receipt failed. Open the booking's row and click **Retry**. If it fails again, check:

    1. Whether the ΤΑΚΚ characteristics are selected on the property under **Settings → Properties**
    2. Whether the tax rules in Elorus are up to date

    Contact support at [support@deskboy.app](mailto:support@deskboy.app) if the issue persists.
  </Accordion>

  <Accordion title="Can I cancel a document that was issued by mistake?">
    Document cancellation is done **directly in your invoicing platform** (e.g. Elorus). After cancelling there, the booking in DeskBoy stays **“Invoiced”**. Contact support if you need the status reset for re-issuing.
  </Accordion>

  <Accordion title="A booking was cancelled after an invoice was already issued. What do I do?">
    The document remains valid — cancelling the booking does not automatically reverse it. The process is:

    1. **Create a credit note in Elorus** for the accommodation invoice
    2. **If a Climate Resilience Fee document was also issued**, cancel that separately — it is not reversed automatically
    3. The booking in DeskBoy stays **“Invoiced”** — contact support if you need the status reset for re-issuing

    <Warning>
    For the correct credit note type and myDATA obligations, consult your accountant.
    </Warning>
  </Accordion>

  <Accordion title="A send keeps failing repeatedly. What should I check?">
    In order:
    1. **Elorus API key** — verify it's still valid in **Settings** → **Integrations**
    2. **Invoices Series** — confirm the series is active in Elorus
    3. **Organization** — ensure the organization allows the document type
    4. **Plan & Billing** — check your account status

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
    Cancellations are detected on the next sync (within ~30 minutes). Once detected, the booking is marked cancelled and removed from the invoicing queue. If it still shows as active after 15 minutes, click **"Sync from Hosthub"**.
  </Accordion>

  <Accordion title="If the Hosthub sync fails, will bookings be lost?">
    No. Sync is **one-directional** — DeskBoy fetches bookings from Hosthub but never deletes data due to a connection error. Bookings already synced remain safe.

    If sync fails temporarily:
    - The system retries automatically
    - New bookings created in the meantime are retrieved on the next successful sync
    - Booking changes (cancellations, date updates) are detected on the next sync

    To trigger an immediate sync, click **"Sync from Hosthub"** on the Bookings page.
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
    The statutory amounts are kept up to date by DeskBoy. The ΤΑΚΚ tax for each amount band is matched automatically per organisation under **Settings → Tax details** with the tax codes you created in Elorus. If the law changes, update the tax codes in Elorus; the app checks that their amount matches the statutory one (see [Climate Resilience Fee](/en/guides/climate-fee)).
  </Accordion>

  <Accordion title="I saw that a booking needs setup for the ΤΑΚΚ. What does it mean?">
    The per-night ΤΑΚΚ amount follows from the property's characteristics (detached house, floor area, regime). They must be filled in on the property card under **Settings → Properties**.

    If you have filled them in, the invoicing organisation needs a ΤΑΚΚ tax in the invoicing app with exactly that amount; the app matches it by itself and you can see it under **Settings → Tax details**. This is done so that a receipt with the wrong amount is never issued.
  </Accordion>
</AccordionGroup>

## Auto-Invoicing

<AccordionGroup>
  <Accordion title="Auto-invoicing didn't run last night. Why?">
    Possible causes:
    - No bookings were **ready to invoice** at the **Execution time**
    - The account had an unpaid charge at the stage where auto-invoicing is paused (see [Plan & Billing](/en/guides/billing))
    - A rare technical issue — contact support
  </Accordion>

  <Accordion title="Can I change the auto-invoicing execution time?">
    Yes, anytime. **Settings** → **Automatic invoicing** → change the **Execution time** → **Save**. The change takes effect from the next execution.
  </Accordion>
</AccordionGroup>

## Plan & Billing

<AccordionGroup>
  <Accordion title="How much does it cost?">
    **Free** covers up to 250 checkouts a month. **Business** starts at €29/month and **Agency** at €59/month, with pricing following the month's volume in tiers. A month with no checkouts is not charged on any plan.
  </Accordion>

  <Accordion title="What counts as a checkout?">
    Every booking that had a document issued within the month — once per booking, in the month it was issued.
  </Accordion>

  <Accordion title="How do I pay?">
    By card at each month's close, or from your prepaid balance if you've topped one up. Both are managed in **Plan & Billing**.
  </Accordion>
</AccordionGroup>

## Special Cases

<AccordionGroup>
  <Accordion title="What happens with a 0€ booking (complimentary stay)?">
    The booking is skipped automatically: no Climate Resilience Fee is calculated and no document is issued, the same as for date blocks synced with a zero amount from the channel.

    If the booking was in fact paid (e.g. outside the platform), set the real amount with **Edit booking** (pencil icon on its row) and issuance proceeds normally with the new amount.

    For whether a document is required for a free stay and which type, ask your accountant.
  </Accordion>

  <Accordion title="Are blocks (closed dates) in my PMS invoiced?">
    No. Blocks are not bookings: they do not appear in the bookings list and are never invoiced, regardless of channel settings. If you enter your own stay as a regular booking with an amount, it is treated as a phone booking.
  </Accordion>

  <Accordion title="My guest asked for an invoice. What do I do?">
    You prepare the invoice from DeskBoy, without going into Elorus: if the company isn't in your contacts yet, you create it from the booking and it's added to Elorus.

    Open the booking in **Bookings** and:
    1. In **Document Type**, choose **Invoice**.
    2. In **Customer**, search for the company by name or VAT number.
    3. If it isn't there, press **Add new Business Contact** and fill in its details. For a Greek company, enter the VAT number and press the search button next to it: the name, tax office and address fill in by themselves. This works once you've entered your [AADE access details](/en/guides/auto-invoicing#aade-—-tax-id-lookup) in **Settings → Advanced**.

    You can enter the details whenever the guest gives them to you, even for a booking a month away — you'll find it under **Upcoming**. With **Automatic invoicing** on, the invoice is issued on its own on check-out day and, with the default settings, emailed to the guest. You don't need to remember to issue it.
  </Accordion>

  <Accordion title="Should I issue a receipt or an invoice for a foreign guest?">
    General rule:
    - **Private individual from abroad** → Retail receipt (no tax ID required)
    - **Company from abroad** → Invoice (VAT Number or local tax ID required)

    The document type is set on each booking (default: Receipt) — see [My guest asked for an invoice](#my-guest-asked-for-an-invoice-what-do-i-do). For special cases (intra-EU B2B, specific tax exemptions, etc.), consult your accountant.
  </Accordion>
</AccordionGroup>

## General

<AccordionGroup>
  <Accordion title="I need help that's not covered here.">
    Contact us at [support@deskboy.app](mailto:support@deskboy.app). We typically respond within **1-2 business days**. In your message, include:
    - The property or booking experiencing the issue
    - The error message (if any)
    - The date you first noticed the problem
  </Accordion>
</AccordionGroup>
