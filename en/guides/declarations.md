---
title: "Short-Term Rental Declarations (AADE)"
description: "Submit declarations to AADE via AADE-Connect: manual and automatic submission, guest identification, and platform mapping."
---

# Short-Term Rental Declarations

Every invoiced booking must be declared to AADE (Greek tax authority) via **AADE-Connect**. Etherly Sync handles this automatically on your behalf.

Declarations are found under **Declarations** in the sidebar — only bookings that have been invoiced and have an AADE property mapping are shown.

## Declaration statuses

| Status | Meaning |
|--------|---------|
| Not submitted | Declaration has not been sent yet |
| Sending… | Submission in progress |
| Sent | Draft declaration sent to AADE-Connect |
| Draft | Declaration is in draft state on AADE-Connect |
| Submitted | Final submission — no action required |
| Failed | Submission failed — check the error message |
| Skipped | Manually excluded from declaration |

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

Enable **automatic final declaration** from the Declarations page (toggle above the table). Once enabled, newly invoiced bookings are declared automatically every day.

<Note>
Automatic declaration applies only to bookings invoiced **after** it is enabled — it does not retroactively process older bookings.
</Note>

## Guest identification

Each declaration can include the guest's identification details. Click the **pencil icon** in the "Identification" column to edit.

| Type | When to use |
|------|-------------|
| Tax ID (AFM) | Greek guest — only an active tax number is accepted |
| Passport | Foreign guest with a passport |
| National ID | Foreign guest with a national identity card (e.g. EU) |
| Reservation ID | Fallback — when no AFM or identification document is available |

<Tip>
If the booking already has a Reservation ID from the booking channel, the field is pre-filled automatically.
</Tip>

## Platform mapping

Etherly Sync automatically maps the booking channel to the platform code required by AADE. The **Channel** column in the Declarations table shows the recognized platform name — not the raw channel string.

| Booking channel | Column display |
|-----------------|----------------|
| Airbnb, Airbnb Plus, Airbnb (Greece), etc. | Airbnb |
| Booking.com, Booking.com for …, etc. | Booking.com |
| Clickstay | Clickstay |
| HomeAway, VRBO, Expedia, etc. | HomeAway / VRBO |
| Homestay | Homestay |
| Luxury Retreats | Luxury Retreats |
| Only Apartments | Only Apartments |
| TripAdvisor, Holiday Lettings, etc. | TripAdvisor |
| Phone / Direct / empty | Εκτός πλατφόρμας (off-platform) |
| Any other channel | (raw channel name) |

The system also recognizes **sub-channel composite names** (e.g. `"Booking.com for Athens"`, `"Airbnb Plus"`) via substring matching — mapping is correct even when the name is not an exact match.

<Warning>
**Direct bookings** (phone, email, your own website) are always sent as "Εκτός πλατφόρμας" (off-platform) — this is required by AADE. The system handles this automatically.
</Warning>

## Payment method

Each declaration is sent to AADE with a field indicating **where the booking channel pays out** to the host. The allowed values are:

| Value | Meaning |
|-------|---------|
| Greek bank | Payment into a Greek bank account |
| Foreign bank | Payment into an overseas bank account |
| Cash | Cash payment |
| Other (via third party, voucher, etc.) | Payment via a third party, voucher, etc. |

### Per-channel default

In **Settings → AADE Connect** you can set a default payment method for each booking channel. Changes take effect for **all future submissions** on that channel — as long as no per-booking override is set.

### Per-booking override

The ✏️ pencil icon in the **Payment Method** column of the Declarations page lets you change the payment method for a single booking. The override:
- **always takes precedence** over the channel default
- is shown in normal colour, while channel-default values are shown muted
- can be cleared using the **"Reset to default"** button

Overrides are allowed only for declarations in **draft** or **failed (no checkpoint)** state. Submitted declarations cannot be edited.

**Resolution priority order:**
1. Per-booking override (✏️)
2. Per-channel default (Settings → AADE Connect)
3. Global default: Greek bank

## Declaration history

The **History** tab on the Declarations page shows bookings that have already been submitted or skipped. Guest identification cannot be edited for these bookings.
