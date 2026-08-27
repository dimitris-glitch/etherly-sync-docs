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
So each property lands on the right line, set its **AADE form type** on its card (Room/Apartment, Detached house under or over 80 sq.m., Self-catering/Villa) and its **available rooms and beds**. Properties without a type are flagged on the page.
</Tip>

<Note>
When a month has no stays, no zero declaration is submitted — the page says so.
</Note>

The total is always the fee **owed**, regardless of whether you collected it from the guest: the obligation to pay it is independent.


## Seasonal periods

| Season | Period |
|--------|--------|
| **Winter** | November 1 – March 31 |
| **Summer** | April 1 – October 31 |

<Info>
The exact fee amounts are set in the **TCA Rules** per organization, under **Settings → Tax details**. These correspond to tax codes you have created in Elorus. If the legal amounts change, update both the tax codes in Elorus and the TCA Rules under **Settings → Tax details**.
</Info>

## Property categories

Categories correspond to tax codes you've defined in Elorus. Typical categories include:

- Standard short-term rental
- Villa over 80 m²
- Studio / One-bedroom
- Furnished apartment

<Tip>
If you're unsure which category applies to your property, consult your accountant or refer to the current Greek tax regulations on short-term rentals.
</Tip>

## Calculation example

**Booking**: 6 nights, March 28 – April 3  
**Category**: Standard short-term rental

| Nights | Season | Fee/night | Total |
|--------|--------|-----------|-------|
| 4 (Mar 28–31) | Winter | €2.00 | €8.00 |
| 2 (Apr 1–2) | Summer | €8.00 | €16.00 |
| **Total** | | | **€24.00** |

In this case, the system creates **two separate** fee documents — one for the winter nights and one for the summer nights.

<Note>
The example amounts €2 / €8 are illustrative only. Actual amounts are set by law and configured in Elorus.
</Note>

## Configuring the fee category

<Steps>
  <Step title="Go to Properties">
    Select **Properties** → click the property you want to configure.
  </Step>
  <Step title="Select Category">
    In the **Category** field, the dropdown shows categories from Elorus. Select the appropriate one.
  </Step>
  <Step title="Save">
    Click **Save**. The new category applies to future documents — it does not affect already-issued ones.
  </Step>
</Steps>

## What happens if no category is set

If a property has no fee category configured:

- The send **fails** with an error message
- The booking stays in `NEEDS_SETUP` or `ERROR`
- Configure the category and **resend** the booking

## Viewing the issued climate fee document

In the expanded row of an invoiced booking, next to the **View document** button (which opens the accommodation invoice or receipt), a **View climate fee document** button opens the climate resilience fee document.

The button appears once the invoicing provider returns the document link, shortly after the myDATA transmission completes. If you have just sent the booking, refresh the page in a moment.

When a stay spans both seasonal periods, two climate fee documents are issued. The button then opens a list with one link per period — summer and winter — so you can view both.

## Zero-amount bookings

When the guest has paid nothing (e.g. a free stay or a date block synced with a zero amount from the channel), Etherly Sync automatically skips the booking: no climate resilience fee is calculated and no documents are issued.

If the booking was actually paid (e.g. outside the platform), set the real amount via the **booking override** (pencil icon on the booking row) — document issuing then proceeds normally with the new amount.

## Updating fee amounts

If the law changes:

1. Update the amounts in Elorus → Taxes
2. Etherly Sync retrieves them automatically on the next send
3. No changes are needed in Etherly Sync
