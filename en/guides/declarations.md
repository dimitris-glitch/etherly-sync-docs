---
title: "Short-Term Rental Declarations (AADE)"
description: "Submit declarations to AADE via AADE-Connect: manual and automatic submission, guest identification, and platform mapping."
---

# Short-Term Rental Declarations

Every short-term rental booking must be declared to AADE (Greek tax authority) via **AADE-Connect**. Etherly Sync handles this automatically on your behalf.

## myDATA and AADE-Connect: two separate obligations

Many users confuse the two systems — they are independent:

| | myDATA | AADE-Connect |
|---|---|---|
| **What it is** | Electronic invoicing record | Short-term rental stay declaration |
| **Per** | Document (invoice, receipt) | Booking |
| **When** | Automatically on issuance | When the booking is ready to declare |
| **Via** | Elorus (automatic) | AADE-Connect (Etherly Sync) |

Etherly Sync handles both automatically: documents are sent to myDATA via Elorus when issued, and stay declarations are submitted separately via AADE-Connect.

<Warning>
A successful myDATA document submission **does not mean** the AADE-Connect declaration has been filed — and vice versa. The two obligations are tracked independently.
</Warning>

Declarations are found under **Declarations** in the sidebar — bookings ready to declare with an AADE property mapping are shown: for businesses once the document is issued, for private individuals once the stay is complete.

## Declaration statuses

| Status | Meaning |
|--------|---------|
| Not submitted | Declaration has not been sent yet |
| Sending… | Submission in progress |
| Processing | The submission is being processed by AADE — this can take up to an hour; no action needed |
| Draft | The declaration has been prepared but not yet sent to AADE |
| Draft at AADE | A provisional (draft) declaration exists at AADE awaiting finalization |
| Submitted | Final submission — no action required |
| Failed | Submission failed — the message explains whether it was a temporary AADE issue (worth retrying) or needs your action, e.g. checking your TAXISnet credentials |
| Skipped | Manually excluded from declaration |

## Property filter

Above the list there is a **Property** filter that narrows declarations to the properties you care about. It opens as a checkbox list: **Select all** at the top, the properties grouped by [group](/en/guides/properties) — where the group's checkbox selects all of its members at once — and a search box. You can combine properties from different groups, and with nothing ticked you see all declarations. Filtering covers all of your declarations, not just the ones currently on screen.

While a selection is active, a strip above the list names it, with a **Clear** button. The choice is remembered for this page. Changing the filter clears any selected bookings, so a bulk submission always covers what you are looking at.


## Manual submission

<Steps>
  <Step title="Select bookings">
    On the **Declarations** page, select one or more bookings using the checkboxes.
  </Step>
  <Step title="Choose declaration type">
    Use the **"Send Selected"** button and choose:
    - **Final** — definitive submission to AADE
    - **Draft** — provisional declaration for later finalization
  </Step>
  <Step title="Monitor status">
    Status updates automatically. On failure, the error message is shown inline.
  </Step>
</Steps>

## Automatic final declaration

Enable **automatic final declaration** from the Declarations page (toggle above the table). Once enabled, newly ready-to-declare bookings are declared automatically every day.

<Note>
Automatic declaration applies only to bookings that become ready **after** it is enabled — it does not retroactively process older bookings.
</Note>

<Warning>
Bookings **cancelled after invoicing** are skipped by automatic declaration — even with automatic final declaration enabled, they will **never be sent automatically** to AADE.
</Warning>

### Cancelled bookings

Cancelled bookings stay in the pending declarations list with an orange **"Cancelled"** badge.

The declared amount comes from the **collected cancellation fee** you record on the [Bookings](/en/guides/checkouts) page — it is the same amount as the issued document. The booking is declared as **cancelled** with that amount: automatically with the next run, if you have enabled automatic declaration submission, or manually with the send button.

If you do not wish to submit a declaration, use **Skip**. The booking stays visible in the "To Declare" tab until the end of the day marked as "Skipped", and from the next day it moves to the **"History"** tab, where you can remove the skip if you change your mind.

<Note>
If you wish to issue a **credit note** for the document that was already issued, you will need to do so in your invoicing provider (e.g. Elorus) — credit notes are not issued from within the app.
</Note>

### Booking check before every submission

Before any declaration is sent to AADE, the app confirms directly with your booking channel that the specific booking still stands. The same check runs before a document is issued.

- If the channel reports the booking **has been cancelled**, the submission stops and the booking is marked as cancelled in the app. The reason appears in the daily report.
- If the channel **does not respond** at that moment, the submission is **postponed** and retried later — nothing is sent without confirmation.

<Note>
This check applies to Hosthub connections. Other connections report cancellations to the app in their own way.
</Note>

### A declaration already exists for those dates

If AADE already holds a finalised declaration for the same property and the same dates, a new declaration is not accepted. The booking is shown with a note identifying **which declaration covers it** — period, declaration number (Α/Α) and the other booking's reference — so you can see straight away what it conflicts with.

To declare the booking, first cancel the existing declaration on the AADE platform. Retrying the submission from the app does not change the outcome while the other declaration is still active.

<Note>
If the existing declaration was filed directly on AADE rather than through the app, only its declaration number (Α/Α) is shown — the rest of its details live on the AADE platform.
</Note>

### Overlapping bookings

When two active bookings cover **overlapping dates for the same property**, both rows are marked with a yellow **"Overlap"** badge and the pair is listed in the daily report.

This means one of the two may have been cancelled on the channel without the app being told. Check your booking channel to see which one stands before declaring.

<Note>
A departure and an arrival on the **same day** is normal operation and is not flagged as an overlap.
</Note>

## Pending and undeclared bookings

The app tracks bookings that remain undeclared relative to the AADE deadline — the short-term stay declaration is due by the **20th of the month following the guest's departure**.

- **Banner on the Declarations page**: when bookings remain undeclared more than 3 days after check-out, a persistent banner shows how many there are and how old the oldest is. The banner becomes more prominent when a deadline is approaching or has passed.
- **Daily report email**: with automatic final declaration enabled, the daily report includes a **"Pending declarations"** section listing all undeclared bookings — every day, until they are declared or skipped. When a deadline is approaching, the email subject is flagged with ⚠️.
- **Automatic retry**: declarations that failed due to a temporary AADE platform issue are retried automatically over the following days. If the problem needs your action (e.g. checking your TAXISnet credentials), the booking appears in the report with the relevant explanation.

**Skip** removes a booking from all of the above — use it for bookings that will not be declared through the app.

<Note>
Bookings on **paused properties** are not counted in the banner or the daily report. Pausing means you no longer manage that property through the app, so the related reminders stop. The bookings stay visible in the Declarations list and you can declare them at any time — if a tax obligation exists, it still applies.
</Note>

## Guest identification

Each declaration can include the guest's identification details. Click the **pencil icon** in the "Identification" column to edit.

| Type | When to use |
|------|-------------|
| National ID | Greek citizen with national ID card |
| Passport | Foreign guest |
| Tax ID (AFM) | Greek citizen with tax number (instead of national ID) |
| Reservation ID | Channel booking ID — when no other identification is available |

<Tip>
If the booking already has a Reservation ID from Hosthub, the field is pre-filled automatically.
</Tip>

## Platform mapping

Etherly Sync automatically maps the booking channel to the platform code required by AADE. The **Channel** column in the Declarations table shows the recognized platform name — not the raw Hosthub channel string.

| Booking channel | Column display | AADE code |
|-----------------|----------------|-----------|
| Airbnb, Airbnb Plus, Airbnb (Greece), etc. | Airbnb | `AIRBNB` |
| Booking.com, Booking.com for …, etc. | Booking.com | `BOOKING_COM` |
| Clickstay | Clickstay | `CLICKSTAY` |
| HomeAway, VRBO, Expedia, etc. | HomeAway / VRBO | `HOMEAWAY` |
| Homestay | Homestay | `HOMESTAY` |
| Luxury Retreats | Luxury Retreats | `LUXURY_RETREATS` |
| Only Apartments | Only Apartments | `ONLY_APARTMENTS` |
| TripAdvisor, Holiday Lettings, etc. | TripAdvisor | `TRIPADVISOR_RENTALS` |
| Phone / Direct / empty | Εκτός πλατφόρμας | `OTHER_DIGITAL_PLATFORMS` · `"Εκτός πλατφόρμας"` |
| Any other channel | (raw name) | `OTHER_DIGITAL_PLATFORMS` · the channel name |

<Warning>
**Direct bookings** (phone, email, your own website) are always sent with `platform_name: "Εκτός πλατφόρμας"` — this is required by AADE. The system handles this automatically.
</Warning>

## Payment method

Each declaration is sent to AADE with a field indicating **how the booking channel (Airbnb, Booking.com, etc.) pays out the rent to your business**. This is **not** about how the guest pays — it refers solely to the flow of money from the channel to you. The allowed values are:

| Value | AADE code | Meaning |
|-------|-----------|---------|
| Greek bank | `DOMESTIC_PAYMENTS_ACCOUNT` | Payment into a Greek bank account |
| Foreign bank | `FOREIGN_PAYMENTS_ACCOUNT` | Payment into an overseas bank account |
| Cash | `CASH` | Cash payment |
| Other (via third party, voucher, etc.) | `OTHER` | Payment via a third party, voucher, etc. |

### Per-channel default

In **Settings → AADE Connect** you can set a default payment method for each booking channel. Changes take effect for **all future submissions** on that channel — as long as no per-booking override is set.

### Per-booking override

The ✏️ pencil icon in the **Payment Method** column of the Declarations page lets you change the payment method for a single booking. The override **always takes precedence** over the channel default, and is shown in normal colour while channel-default values are shown muted.

Overrides are allowed only before a declaration has been sent to AADE Connect. Once a declaration has been dispatched — even if it later shows a failed or draft status — the payment method is locked and cannot be changed.

**Resolution priority order:**
1. Per-booking override (✏️)
2. Per-channel default (Settings → AADE Connect)
3. Global default: `DOMESTIC_PAYMENTS_ACCOUNT`

## Declaration history

The **History** tab on the Declarations page shows bookings that have already been submitted or skipped. Guest identification cannot be edited for these bookings.

## AADE Connect Settings

The **Settings → AADE Connect** page has two sections:

### Property mapping

For each property shown in the list, select the corresponding AADE property from the dropdown. This mapping is required for declaration submission — bookings without a property mapping do not appear on the Declarations page.

<Note>
If no properties appear, make sure you have connected at least one booking channel under **Settings → Integrations**.
</Note>

### Per-channel payment method default

Each declaration sent to AADE requires information about **how the booking channel pays out the rent to your business**. Here you set the default per channel (Airbnb, Booking.com, etc.). This is not about how the guest pays.

| Option | AADE code | When to select |
|--------|-----------|----------------|
| Greek bank | `DOMESTIC_PAYMENTS_ACCOUNT` | Channel pays into a Greek bank account |
| Foreign bank | `FOREIGN_PAYMENTS_ACCOUNT` | Channel pays into an overseas bank account |
| Cash | `CASH` | Cash payment |
| Other | `OTHER` | Payment via third party, voucher, etc. |

**Resolution priority order:**

1. Per-booking override (✏️ pencil icon in the Payment Method column on the Declarations page)
2. Per-channel default — this page
3. Global default: `DOMESTIC_PAYMENTS_ACCOUNT`

<Tip>
Per-booking overrides are only allowed **before** a declaration has been sent. Once dispatched — even if it later shows a failed status — the payment method is locked.
</Tip>
