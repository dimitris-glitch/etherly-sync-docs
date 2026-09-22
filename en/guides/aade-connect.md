---
title: "AADE Connect Settings"
description: "Connect your AADE account and configure property mappings and default payment methods per booking channel."
---

# AADE Connect Settings

Setup happens on two pages, in this order: first you create the connection under **Integrations**, then you configure the rest under **Settings → AADE Connect**.

---

## Connecting to AADE

Before anything else, create the connection. Open **Settings → Integrations**, find the **AADE Connect** card and press **Enable**. Fill in the title you want the connection to have, your **AADE Username** and **Password**. Press **Test connection** and, once it succeeds, press **Save** — until the test succeeds, Save stays disabled.

Once the connection exists, continue to **Settings → AADE Connect**, where two sections await you:

1. **Property mapping** — link each of your properties to the corresponding AADE property
2. **Rental payment method** — set a default payment method for each booking channel

This page lists properties only once a connection exists.

---

## Property mapping

For each property in the list, select the corresponding AADE property from the dropdown. This mapping is required for short-term rental declaration submissions. After connecting, map each property to its AADE property (AMA) from the AADE Connect settings. Until then, its bookings appear in Declarations without the option to submit.

<Note>
If no properties appear, make sure you have connected at least one booking channel in Settings.
</Note>

---

## Rental payment method

Every declaration sent to AADE requires information about **how the booking channel (Airbnb, Booking.com, etc.) pays out the rent to your business**. This is not about how the guest pays, but the flow of money from the channel to you. Here you set the default per channel.

| Option | AADE code | When to use |
|--------|-----------|-------------|
| Bank in Greece | `DOMESTIC_PAYMENTS_ACCOUNT` | Channel pays into a Greek bank account |
| Bank abroad | `FOREIGN_PAYMENTS_ACCOUNT` | Channel pays into a foreign bank account |
| Cash | `CASH` | Payment in cash |
| Other | `OTHER` | Payment via third party, voucher, etc. |

**The setting applies per channel** — Airbnb, Booking.com, VRBO etc. each have their own default.

### Priority order

If you have changed the payment method for a specific booking (from the Declarations page), that value takes precedence:

1. Per-booking manual override (✏️ on the Declarations page)
2. **Per-channel default — this page**
3. General default: Bank in Greece

<Tip>
For more details on per-declaration payment method overrides, see the [Declarations Guide](/en/guides/declarations).
</Tip>
