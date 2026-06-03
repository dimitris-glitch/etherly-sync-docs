---
title: "What is Etherly Sync"
description: "Automated invoicing for short-term rentals — from Hosthub to Elorus and myDATA, with zero manual work."
---

# Welcome to Etherly Sync

**Etherly Sync** is an automation platform that connects **Hosthub** (booking management) with **Elorus** (electronic invoicing), automatically generating all required fiscal documents for every short-term rental checkout.

## The problem it solves

Every guest checkout requires creating fiscal documents in Elorus — typically three, or four if the booking spans two seasonal periods:

1. **Accommodation Document** — Receipt for private guests / Invoice for businesses, 13% VAT
2. **Payment Receipt** — linked to the accommodation document
3. **Climate Resilience Fee** — calculated per night and property category

With dozens of checkouts per month and multiple properties, this becomes time-consuming and error-prone. Etherly Sync automates it entirely.

## How it works

```text
Hosthub  ──→  Etherly Sync  ──→  Elorus  ──→  myDATA
(Bookings)    (Automation)     (Documents)    (Tax Authority)
```

The system **syncs** checkouts from Hosthub on a regular schedule, **verifies** that each property is fully configured, and **issues** the fiscal documents automatically — submitting to myDATA if enabled.

## Core features

<CardGroup cols={2}>
  <Card title="Automatic Sync" icon="arrows-rotate">
    New bookings, changes, and cancellations are detected automatically from Hosthub. You can also trigger a manual sync from the dashboard.
  </Card>
  <Card title="Documents per Checkout" icon="file-invoice">
    Accommodation document, payment receipt, and climate fee — issued automatically in the correct order.
  </Card>
  <Card title="Auto-Invoicing" icon="clock">
    Set a daily execution time and the system invoices all eligible checkouts overnight, hands-free.
  </Card>
  <Card title="Multiple Properties & Organizations" icon="building">
    Manage dozens of properties across multiple Elorus organizations from a single dashboard.
  </Card>
  <Card title="Climate Resilience Fee" icon="leaf">
    Automatic calculation based on property category and season. For bookings spanning two seasons, separate documents are created per season.
  </Card>
  <Card title="Secure & Reliable" icon="shield-check">
    Encrypted API key storage (AES-256-GCM), duplicate prevention, automatic retries on failures.
  </Card>
</CardGroup>

## Who it's for

Etherly Sync is ideal for:

- **Property managers** with 5+ properties on Hosthub who spend hours on manual invoicing
- **Accountants** managing invoicing for multiple rental property owners
- **Owners** who want full myDATA compliance without technical expertise

## Next step

<Card title="Get started in 10 minutes →" icon="rocket" href="/en/getting-started">
  Connect Hosthub and Elorus and send your first document.
</Card>
