---
title: "Checkouts & Statuses"
description: "Understand the checkout lifecycle: from Hosthub sync to Elorus document issuance."
---

# Checkouts & Statuses

A **checkout** corresponds to a completed booking from Hosthub — a guest stay that has ended or is expected to end. Each checkout follows a predictable lifecycle.

## Status reference

| Status | Color | Meaning | Action required |
|--------|-------|---------|----------------|
| `NEEDS_SETUP` | 🟡 Yellow | Property missing required configuration | Complete property setup |
| `READY` | 🟢 Green | Ready to invoice | Send, or wait for auto-invoicing |
| `SENT` | 🔵 Blue | Documents issued successfully | None |
| `SENT_WITH_ERRORS` | 🟠 Orange | Accommodation document and payment receipt OK, climate fee failed | Click **Retry** to re-attempt the failed step |
| `WAITING_MYDATA_FINALIZATION` | 🟡 Yellow | Documents created — myDATA has not yet indexed the invoice for fee linking | Automatic retry in progress (up to ~24h) — no action required |
| `NEEDS_MANUAL_REVIEW` | 🟠 Orange | myDATA finalization did not complete after multiple attempts | Check in Elorus and retry manually |
| `ERROR` | 🔴 Red | Send failed entirely | Review error message and retry |
| `SPLIT` | ⬜ Gray | Booking spanning two calendar years | Not invoiced directly — two separate checkouts are created automatically |

## Automatic sync

Etherly Sync syncs automatically with Hosthub at regular intervals. During each sync:

- **New bookings** are added immediately as checkouts
- **Changes** (dates, amounts, guest info) are updated automatically
- **Cancellations** are detected and those checkouts are excluded from invoicing

You can also trigger a **manual sync** at any time by clicking **Refresh** on the **Bookings** page.

## Pause / Resume

Stop auto-invoicing for a checkout without deleting it. Useful when you want certain bookings excluded from automatic processing — they stay in the app and won't be invoiced until you decide how to handle them.

<Tip>
For a permanent exclusion of an entire booking channel or a specific property, configure it in [Settings → Auto-Invoicing](/en/guides/auto-invoicing).
</Tip>

### Manual Pause

Click **Pause** next to the checkout. It stays paused through subsequent syncs — only the user can resume it with **Resume**.

### Automatic skip via notes

If a Hosthub booking has a `##sync-skip` note, the system **automatically pauses** the checkout during sync. Remove the note from Hosthub and the checkout will resume on the next sync.

<Tip>
Useful if you want to pause document issuance for a booking directly from Hosthub.
</Tip>

## Billing contact (Business Contact)

Checkouts that issue an **invoice** require a **billing contact** — the _Business Contact (Required for Invoice)_ field in the checkout's expanded row. Click the field to open the search and pick a contact from Elorus.

To change an **already saved** contact, click **Change**: the search opens **without deleting** the existing contact. The new contact is saved only when you select it — if saving fails, the search stays open and the previous contact remains untouched.

<Tip>
If you opened the search by mistake, click **Cancel** inside the search panel to close it without changes — the previous contact is kept.
</Tip>

## Bookings spanning two years

If a booking spans two calendar years (e.g., Dec 28, 2024 → Jan 3, 2025), the system handles it automatically: two separate checkouts are created (one per year) with amounts split proportionally per night. Each checkout is invoiced in the correct fiscal year.

<Note>
Year-Boundary Splits happen automatically. No action is required from you.
</Note>

## Filtering & Search

In **Bookings** you can filter checkouts by:
- **Status** (READY, SENT, ERROR, etc.)
- **Property**
- **Date range** (checkout date)
- **Paused** (yes/no)
