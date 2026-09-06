---
title: "Checkouts & Statuses"
description: "Understand the checkout lifecycle: from Hosthub sync to Elorus document issuance."
---

# Checkouts & Statuses

A **checkout** corresponds to a completed booking from Hosthub — a guest stay that has ended or is expected to end. Each checkout follows a predictable lifecycle.

## Status reference

| Status | Color | Meaning | Action required |
|--------|-------|---------|----------------|
| `NEEDS_SETUP` | 🟡 Yellow | Property missing required configuration | Complete property setup — or, if the tooltip mentions the climate fee tax, pick the right tax under Settings → Organizations |
| `READY` | 🟢 Green | Ready to invoice | Send, or wait for auto-invoicing |
| `SENT` | 🔵 Blue | Documents issued successfully — shown as **“Invoiced”** | None |
| `SENT_WITH_ERRORS` | 🟠 Orange | Accommodation document and payment receipt OK, climate fee failed | Open the row and click **Retry** on the failed step |
| `WAITING_MYDATA_FINALIZATION` | 🟡 Amber — **"Waiting myDATA"** | Accommodation invoice issued — myDATA has not yet indexed it for climate fee linking | Automatic retry in progress for about a day — no action required |
| `NEEDS_MANUAL_REVIEW` | 🔴 Red — **"Manual review"** | myDATA finalization did not complete after about a day of retries — or myDATA permanently rejected the accommodation document — or the property was assigned to a different invoicing organization after documents had already been issued for the booking | **myDATA:** you will receive an email notification — check in your invoicing application and retry myDATA submission manually. **Permanent myDATA rejection:** the reason is shown in the booking's send timeline; correct and resubmit the document from your invoicing application. **Organization change:** assign the property back to the organization that issued the documents, then retry the send. |
| `ERROR` | 🔴 Red | Send failed entirely | Review error message and retry |
| `SPLIT` | ⬜ Gray | Booking spanning two calendar years | Not invoiced directly — two separate checkouts are created automatically |

## Automatic sync

DeskBoy syncs automatically with Hosthub at regular intervals. During each sync:

- **New bookings** are added immediately as checkouts
- **Changes** (dates, amounts, guest info) are updated automatically
- **Cancellations** are detected and the corresponding checkouts are marked as cancelled — only a cancellation fee you record gets invoiced (see below)

You can also trigger a **manual sync** at any time by clicking **Refresh** on the **Bookings** page.

## Cancelled bookings

Every cancelled booking stays in the list with a red **"Cancelled"** badge, placed on the **day of cancellation**, not on the original departure date. Opening its row, the cancellation date is shown in bold under **Booking details**. If documents had already been issued, the **send progress** keeps showing them with their IDs and dates: cancelling does not erase the issuance history, and you receive an **email notification** because action is needed from you.

**If you collected a cancellation fee** (the cancellation policy imposed a charge), open the booking row and enter the amount via the **pencil** on the "Cancellation fee collected" line (under Document details):

1. **Document**: a document is issued **for the cancellation fee only**, without Climate Resilience Fee and without transient tax, since no stay took place. Automatically by the day's auto-invoicing (if you enter the amount before the run time) or manually with the send button.
2. **AADE declaration**: the booking is declared as cancelled with the **fee amount**, the same as the document. You follow its progress under [Declarations](/en/guides/declarations).

A cancelled booking **without** a recorded fee simply stays visible for your records: it does not count toward the day's counter, no document is issued and nothing is declared to AADE.

<Warning>
**Automatic final AADE declaration** includes only cancelled bookings with a recorded cancellation fee. A credit note for a document already issued is created in your invoicing provider (e.g. Elorus).
</Warning>

## Skip / Undo skip

Stop auto-invoicing for a booking without deleting it. Useful when you want certain bookings excluded from automatic processing: they stay in the app marked **"Skipped"** and are not invoiced until you decide how to handle them.

<Tip>
For a permanent exclusion of an entire booking channel or a specific property, configure it in [Settings → Auto-Invoicing](/en/guides/auto-invoicing).
</Tip>

### Manual skip

From the row's **⋮** menu choose **"Skip"**. The booking stays skipped through subsequent syncs; you bring it back from the same menu with **"Undo skip"**. Who skipped or restored it and when is recorded in the activity history.

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

## Amount format

Amounts appear in the Greek convention: a dot for thousands and a comma for decimals, with the currency symbol at the end — for example **2.345,87 €**.

<Note>
The format only affects how you see the amount on screen. The amount issued on the document and declared to AADE is the same.
</Note>

## Sync with invoicing provider

Sync is useful when a document was issued manually in your invoicing provider, outside the app: it brings that information into the app, so the short-term rental declaration and the Climate Resilience Fee form work correctly. From the **⋮** menu next to the **Refresh** button, the **Sync with invoicing provider** option checks the documents that exist in your invoicing app for the month you select. Anything that appears to have been issued outside the app is shown **grouped per booking** — stay document and climate fee receipts together, when they are linked to each other or point to the same booking. If the booking already has a document issued through the app, you will see a **Possible duplicate issuance** notice so you can check it in the provider.

With the **Sync** button, the booking's documents are recorded: the booking becomes "Sent", the climate fee receipts are added to the Climate Resilience Fee form ([more](/guides/climate-fee)), and auto-invoicing will not issue duplicate documents. If the set does not include a climate fee receipt, you can issue it right afterwards from the app. With **Dismiss**, the whole set of documents is marked as reviewed.

## Filtering & Search

In **Bookings** you can filter checkouts by:
- **Status** (READY, SENT, ERROR, etc.)
- **Property** — a single property, a [property group](/en/guides/properties) or a connection
- **Date range** (checkout date)
- **Skipped** (yes/no)

The **Property** filter works as in every list: checkbox selection per property or per [group](/en/guides/properties#selecting-with-checkboxes), with search, and with nothing selected you see all properties. The selection is remembered for this page.

In the **Today** tab, properties are shown grouped, provided you have created groups; properties not assigned to any group go to the "Ungrouped" group at the end. The **Upcoming**, **History** and **All** tabs show bookings in a single chronological order.
