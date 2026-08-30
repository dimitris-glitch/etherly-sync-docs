---
title: "Climate Resilience Fee"
description: "How the Climate Resilience Fee is calculated, which property categories exist, and how to configure your property correctly."
---

# Climate Resilience Fee

The **Climate Resilience Fee** (Τέλος Ανθεκτικότητας στην Κλιματική Κρίση) is a Greek tax obligation charged per night of stay in short-term rentals. The amount depends on:

1. **Property category** — type and characteristics
2. **Season** — winter or summer

Etherly Sync automatically calculates and issues the fee document.

## AADE form — monthly payment

The **Climate Resilience Fee** page gives you the figures in the order the AADE form asks for them, so filling it in is a copy job:

- Pick a **month** and see the header (number of businesses, available rooms, beds, how many were used) and the calculation lines per category, with nights and the fee for each season.
- **Export form (CSV)** downloads the same layout for your accountant.
- The **Per booking** view shows which stays the totals come from.

The payment declaration is submitted on myAADE by the end of the following month — the page reminds you of the date.

<Note>
The fee is declared **per tax ID**. If you have more than one fiscal entity (for example a private individual and a company), the page shows a **separate form for each**, with its own figures. The "number of businesses" fills itself in: **0** for a private individual with no business registration, **1** for a business.
</Note>

<Tip>
So each property lands on the right line, set its **AADE form type** on its card (Room/Apartment, Detached house under or over 80 sq.m., Self-catering/Villa) and its **available rooms and beds**. Properties without a type **or** without rooms/beds are flagged on the page, with a link to their card.
</Tip>

<Note>
When a month has no stays, no zero declaration is submitted — the page says so.
</Note>

Each month includes the fee documents **issued** within it — that is how AADE asks for the declaration. It usually matches the departure month. In the **Per booking** view, the **Issued** column shows each document's date. With [auto-invoicing](/guides/auto-invoicing) enabled, a stay that crosses a rate change gets the receipt for its first part on that part's last night — and appears here in two months, one part in each.

In a closed month, stays that have departed but have no fee document yet appear on the form as **"Fee receipt pending"** and are left out of the total — they will be added to the month in which their document is issued. In the current month the notice is not shown, since receipts for today's departures are issued within the day.

The total is always the fee **owed**, regardless of whether you collected it from the guest: the obligation to pay it is independent.


## Seasonal periods

| Season | Period |
|--------|--------|
| **Winter** | November 1 – March 31 |
| **Summer** | April 1 – October 31 |

<Info>
Fee amounts are set by law and are the same for everyone. Etherly Sync keeps them up to date — you do not need to enter them yourself. Each legislative change takes effect on the date the law specifies, so earlier declarations continue to be calculated with the amounts that applied at the time.
</Info>

## How the amount is determined per property

The amount depends on the property's **regime** and, where it matters, its floor area. On the property card you set:

- **Regime** — Short-term rental, Rented Furnished Rooms/Apartments, Tourist Furnished Residence, or Tourist Furnished Villa.
- **Detached house** and **floor area** — shown only when they change the fee.

From these, the line of the AADE form on which the property counts follows automatically.

## Calculation example

**Booking**: 6 nights, March 28 – April 3  
**Regime**: Short-term rental

| Nights | Season | Fee/night | Total |
|--------|--------|-----------|-------|
| 4 (Mar 28–31) | Winter | €2.00 | €8.00 |
| 2 (Apr 1–2) | Summer | €8.00 | €16.00 |
| **Total** | | | **€24.00** |

In this case, the system creates **two separate** fee documents — one for the winter nights and one for the summer nights.

For a private individual without business registration, who issues the documents outside the app, the **Per booking** view shows such a stay as two parts — one per fee period, each in the month it should be issued (e.g. "4 of 6 nights — winter part, to be issued 31/3").

<Note>
The amounts €2 / €8 are an example only. The applicable amounts are set by law.
</Note>

## Configuring a property

<Steps>
  <Step title="Open the property card">
    **Settings → Properties** → click the property.
  </Step>
  <Step title="Set the regime">
    Choose the **Regime** and answer the questions that appear (detached house, floor area).
  </Step>
  <Step title="Fill in rooms and beds">
    The AADE form asks for the **available rooms** and **beds**.
  </Step>
</Steps>

While any of these is missing, the property appears with a warning on the **Climate Resilience Fee** page and its bookings wait for the configuration before being sent. Fill them in and resend the booking.

## Viewing the issued climate fee document

In the expanded row of an invoiced booking, next to the **View document** button (which opens the accommodation invoice or receipt), a **View climate fee document** button opens the climate resilience fee document.

The button appears once the invoicing provider returns the document link, shortly after the myDATA transmission completes. If you have just sent the booking, refresh the page in a moment.

When a stay spans both seasonal periods, two climate fee documents are issued. The button then opens a list with one link per period — summer and winter — so you can view both.

## Zero-amount bookings

When the guest has paid nothing (e.g. a free stay or a date block synced with a zero amount from the channel), Etherly Sync automatically skips the booking: no climate resilience fee is calculated and no documents are issued.

If the booking was actually paid (e.g. outside the platform), set the real amount via the **booking override** (pencil icon on the booking row) — document issuing then proceeds normally with the new amount.
