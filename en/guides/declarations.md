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

## Declaration history

The **History** tab on the Declarations page shows bookings that have already been submitted or skipped. Guest identification cannot be edited for these bookings.
