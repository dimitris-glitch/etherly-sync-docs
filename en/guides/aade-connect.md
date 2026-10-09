---
title: "AADE Connect Settings"
description: "How you create the AADE Connect connection under Integrations (and a second one for another account), how you map each property to its AADE property (AMA), how you set the rental payment method per channel under Channels (bank, cash, other) and which value takes precedence in the declaration."
---

# AADE Connect Settings

Setup happens on three pages, in this order: first you create the connection under **Integrations**, then you map your properties under **Settings → AADE Connect** and set the payment method per channel under **Settings → Channels**.

---

## Connecting to AADE

Before anything else, create the connection. Open **Settings → Integrations**, find the **AADE Connect** card and press **Connect**. Fill in the title you want the connection to have, your **AADE Username** and **Password**. Press **Test connection** and, once it succeeds, press **Save** — until the test succeeds, Save stays disabled.

For properties registered under another account in AADE's Short-Term Stay Registry, add another connection with **New Connection** on the same card.

Once the connection exists, continue with two settings:

1. **Property mapping**, under **Settings → AADE Connect**: link each of your properties to the corresponding AADE property. This page lists properties only once a connection exists.
2. **Rental payment method**, under **Settings → Channels**: set a default payment method for each booking channel.

---

## Property mapping

For each property in the list, select the corresponding AADE property from the dropdown. This mapping is required for short-term rental declaration submissions. After connecting, map each property to its AADE property (AMA) from the AADE Connect settings. Until then, its bookings appear in Declarations without the option to submit.

<Note>
If no properties appear, make sure you have connected at least one booking channel in Settings.
</Note>

---

## Rental payment method

Every declaration sent to AADE requires information about **how the booking channel (Airbnb, Booking.com, etc.) pays out the rent to your business**. This is not about how the guest pays, but the flow of money from the channel to you. You set the default per channel under **Settings → Channels**.

| Option in DeskBoy | On the AADE form | When to use |
|--------|-----------|-------------|
| Bank in Greece | Λογαριασμός Πληρωμών Ημεδαπής | You have set the channel to pay you into an account at a Greek bank |
| Bank abroad | Λογαριασμός Πληρωμών Αλλοδαπής | You have set the channel to pay you into an account at a bank abroad |
| Cash | Μετρητά | Payment in cash |
| Other | Λοιποί | Payment via third party, voucher, etc. |

The AADE form shows these options in Greek.

**The setting applies per channel** — Airbnb, Booking.com, VRBO etc. each have their own default.

### Priority order

If you have changed the payment method for a specific booking (from the Declarations page), that value takes precedence:

1. Per-booking manual override (✏️ on the Declarations page)
2. **Per-channel default** (Settings → Channels)
3. General default: Bank in Greece

<Tip>
For more details on per-declaration payment method overrides, see the [Declarations Guide](/en/guides/declarations).
</Tip>
