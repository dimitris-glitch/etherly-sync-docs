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
| `SENT_WITH_ERRORS` | 🟠 Orange | Invoice/receipt OK, fee failed | Check error details |
| `ERROR` | 🔴 Red | Send failed entirely | Review error message and retry |
| `SPLIT` | ⬜ Gray | Booking spanning two calendar years | Not invoiced directly — two separate checkouts are created automatically |

## Automatic sync

Etherly Sync syncs with Hosthub every **5 minutes**. During each sync:

- **New bookings** are added immediately as checkouts
- **Changes** (dates, amounts, guest info) are updated automatically
- **Cancellations** are detected and those checkouts are excluded from invoicing

You can also trigger a **manual sync** at any time by clicking **Sync Now** in the dashboard.

## Pause / Resume

Temporarily stop invoicing a checkout without deleting it.

### Manual Pause

Click **Pause** next to the checkout. It stays paused through subsequent syncs — only the user can resume it with **Resume**.

### Automatic skip via notes

If a Hosthub booking has a `##sync-skip` note, the system **automatically pauses** the checkout during sync. Remove the note from Hosthub and the checkout will resume on the next sync.

<Tip>
Use `##sync-skip` in Hosthub booking notes to pause checkouts without logging into Etherly Sync — ideal for property managers who primarily work in Hosthub.
</Tip>

## Bookings spanning two years

If a booking spans two calendar years (e.g., Dec 28, 2024 → Jan 3, 2025), the system handles it automatically: two separate checkouts are created (one per year) with amounts split proportionally per night. Each checkout is invoiced in the correct fiscal year.

<Note>
Year-Boundary Splits happen automatically. No action is required from you.
</Note>

## Filtering & Search

In the dashboard you can filter checkouts by:
- **Status** (READY, SENT, ERROR, etc.)
- **Property**
- **Date range** (checkout date)
- **Paused** (yes/no)
