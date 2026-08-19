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
| `SENT` | 🔵 Blue | Documents issued successfully — shown as **“Invoiced”** | None |
| `SENT_WITH_ERRORS` | 🟠 Orange | Accommodation document and payment receipt OK, climate fee failed | Click **Retry** to re-attempt the failed step |
| `WAITING_MYDATA_FINALIZATION` | 🟡 Amber — **"Waiting myDATA"** | Accommodation invoice issued — myDATA has not yet indexed it for climate fee linking | Automatic retry in progress (up to ~24h) — no action required |
| `NEEDS_MANUAL_REVIEW` | 🔴 Red — **"Manual review"** | myDATA finalization did not complete after multiple retries (~24h) — or the property was assigned to a different invoicing organization after documents had already been issued for the booking | **myDATA:** you will receive an email notification — check in your invoicing application and retry myDATA submission manually. **Organization change:** assign the property back to the organization that issued the documents, then retry the send. |
| `ERROR` | 🔴 Red | Send failed entirely | Review error message and retry |
| `SPLIT` | ⬜ Gray | Booking spanning two calendar years | Not invoiced directly — two separate checkouts are created automatically |

## Automatic sync

Etherly Sync syncs automatically with Hosthub at regular intervals. During each sync:

- **New bookings** are added immediately as checkouts
- **Changes** (dates, amounts, guest info) are updated automatically
- **Cancellations** are detected and the corresponding checkouts are marked as cancelled — only a cancellation fee you record gets invoiced (see below)

You can also trigger a **manual sync** at any time by clicking **Refresh** on the **Bookings** page.

## Cancellation after invoicing

If a booking is cancelled **after** its document has already been issued, the checkout does **not** disappear from the list — it stays visible with a red **"Cancelled"** badge, so it stands apart from normal invoiced bookings. The **send progress** in the expanded row keeps showing the documents that were already issued (invoice/receipt, payment, climate resilience fee) with their IDs and timestamps — the cancellation does not erase the issuance history.

In this case you automatically receive an **email notification**, because action is required on your side:

1. **AADE declaration**: if your cancellation policy imposed a charge and you **collected a cancellation fee**, the booking is declared as cancelled with the **amount you collected** — the same amount as the issued document. On the [Declarations](/en/guides/declarations) page you can track the declaration's progress.
2. **Credit note**: if you wish to issue a credit note for the document that was already issued, you will need to do so in your invoicing provider (e.g. Elorus).

<Warning>
**Automatic final AADE declaration** includes cancelled bookings for which you have recorded a collected cancellation fee — they are declared with the cancellation fee amount. Other cancelled bookings are not declared to AADE.
</Warning>

## Cancelled bookings and cancellation fees

Every cancelled booking appears in the list with a red **"Cancelled"** badge, positioned on the **day of the cancellation** — not on the original checkout date. A November booking cancelled today shows up under today's bookings.

Expanding the booking row shows the **cancellation date** in bold under **Booking Details**.

If your cancellation policy imposed a charge and you **collected a cancellation fee**, expand the booking row and record the amount via the **pencil icon** on the "Cancellation fee collected" line (under Invoicing Details):

1. **Document issuance**: once an amount is saved, a document is issued **for the cancellation fee only** — with no climate resilience fee and no stay duty, since no stay took place. Issuance happens **automatically** by that day's auto-invoicing run (as long as you enter the amount before the scheduled run) or **manually** with the send button.
2. **AADE declaration**: the booking is declared as cancelled with the **cancellation fee amount you recorded** — the same amount as the issued document. On the [Declarations](/en/guides/declarations) page you can track the declaration's progress.

A cancelled booking **without** a recorded fee simply stays visible for your records — it is not counted in the day's counter and no document is issued.

## Pause / Resume

Stop auto-invoicing for a checkout without deleting it. Useful when you want certain bookings excluded from automatic processing — they stay in the app and won't be invoiced until you decide how to handle them.

<Tip>
For a permanent exclusion of an entire booking channel or a specific property, configure it in [Settings → Auto-Invoicing](/en/guides/auto-invoicing).
</Tip>

### Manual Pause

Click **Pause** next to the checkout. It stays paused through subsequent syncs — only the user can resume it with **Resume**.

## Billing contact (Business Contact)

Checkouts that issue an **invoice** require a **billing contact** — the _Business Contact (Required for Invoice)_ field in the checkout's expanded row. Click the field to open the search and pick a contact from Elorus.

To change an **already saved** contact, click **Change**: the search opens **without deleting** the existing contact. The new contact is saved only when you select it — if saving fails, the search stays open and the previous contact remains untouched.

<Tip>
If you opened the search by mistake, the previous contact appears as an option below the search field — select it to keep it unchanged. The suggestion hides once you start typing and reappears if you clear the text.
</Tip>

## When a send does not complete

Once you press **send**, the app follows the job and tells you how it ended:

- **If the send fails**, a notification shows the reason. The booking stays in the same status, so you can send again once you have fixed the underlying problem.
- **If the send is taking a while**, a notice tells you it continues in the background. Refresh the list shortly to see the final result.

The details stay recorded in the **send progress**: expand the booking row and the failed step is shown with a **"Show error"** link that opens the full message.

<Tip>
The next morning's **daily report** also summarises the bookings that need attention.
</Tip>

## Bookings spanning two years

If a booking spans two calendar years (e.g., Dec 28, 2024 → Jan 3, 2025), the system handles it automatically: two separate checkouts are created (one per year) with amounts split proportionally per night. Each checkout is invoiced in the correct fiscal year.

<Note>
Year-Boundary Splits happen automatically. No action is required from you.
</Note>

## Filtering & Search

In **Bookings** you can filter checkouts by:
- **Status** (READY, SENT, ERROR, etc.)
- **Property** — a single property, a [property group](/en/guides/properties) or a connection
- **Date range** (checkout date)
- **Paused** (yes/no)

The **Property** filter opens as a checkbox list: **Select all** at the top, the properties grouped by [group](/en/guides/properties) — where the group's checkbox selects all of its members at once — and a search box to find one quickly. You can combine properties from different groups. With nothing ticked you see all properties.

While a selection is active, a strip above the list names it and shows how many properties it covers, with a **Clear** button. The choice is remembered for this page.

As soon as one group exists, the table's rows stand together by group under a heading showing the group's name and colour, with "Ungrouped" last. Inside each section the chronological order stays the same.
