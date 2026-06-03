---
title: "Climate Resilience Fee"
description: "How the Climate Resilience Fee is calculated, which property categories exist, and how to configure your property correctly."
---

# Climate Resilience Fee

The **Climate Resilience Fee** (Τέλος Κλιματικής Ανθεκτικότητας) is a Greek tax obligation charged per night of stay in short-term rentals. The amount depends on:

1. **Property category** — type and characteristics
2. **Season** — winter or summer

Etherly Sync automatically calculates and issues the fee document.

## Seasonal periods

| Season | Period |
|--------|--------|
| **Winter** | November 1 – March 31 |
| **Summer** | April 1 – October 31 |

<Info>
The exact fee amounts are pulled directly from the **tax codes in Elorus** — they are not hardcoded in Etherly Sync. If the legal amounts change, simply update them in Elorus.
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

## Updating fee amounts

If the law changes:

1. Update the amounts in Elorus → Taxes
2. Etherly Sync retrieves them automatically on the next send
3. No changes are needed in Etherly Sync
