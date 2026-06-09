---
title: "Short-Term Rental Declarations (AADE)"
description: "Submit declarations to AADE via AADE-Connect: manual and automatic submission, guest identification, and platform mapping."
---

# Short-Term Rental Declarations

Every invoiced booking must be declared to AADE (Greek tax authority) via **AADE-Connect**. Etherly Sync handles this automatically on your behalf.

## myDATA and AADE-Connect: two separate obligations

Many users confuse the two systems — they are independent:

| | myDATA | AADE-Connect |
|---|---|---|
| **What it is** | Electronic invoicing record | Short-term rental stay declaration |
| **Per** | Document (invoice, receipt) | Booking |
| **When** | Automatically on issuance | After invoicing |
| **Via** | Elorus (automatic) | AADE-Connect (Etherly Sync) |

Etherly Sync handles both automatically: documents are sent to myDATA via Elorus when issued, and stay declarations are submitted separately via AADE-Connect.

<Warning>
A successful myDATA document submission **does not mean** the AADE-Connect declaration has been filed — and vice versa. The two obligations are tracked independently.
</Warning>

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

The system also recognizes **Hosthub sub-channel composite names** (e.g. `"Booking.com for Ariadnis + Collection"`, `"Airbnb Plus"`) via substring matching — mapping is correct even when the name is not an exact match.

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
