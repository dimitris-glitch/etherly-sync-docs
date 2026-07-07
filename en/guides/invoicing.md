---
title: "How Invoicing Works"
description: "The three documents issued per checkout, the order they're created, and how myDATA submission works."
---

# How Invoicing Works

For every checkout that is sent, Etherly Sync automatically creates documents in Elorus, in a strictly defined order.

## The documents created

<CardGroup cols={3}>
  <Card title="1. Accommodation Document" icon="file-invoice">
    The primary document for the accommodation service: **Receipt** for private guests or **Invoice** for businesses.
  </Card>
  <Card title="2. Payment Receipt" icon="receipt">
    Linked to the accommodation document.  
    Confirms payment received.  
    Issued immediately after the accommodation document.
  </Card>
  <Card title="3. Climate Resilience Fee" icon="leaf">
    Calculated per night and category. If the booking spans winter and summer, two separate documents are issued.
  </Card>
</CardGroup>

## Document Description

The text shown on the service line of the Accommodation Document (e.g. "John Doe | 01/07/2026 → 03/07/2026 | City Vibes Loft") is generated from a template, which you configure under **Settings → Document Description**.

Even if you haven't customized anything, an effective template is always in use: either the one you've set, or the built-in default:

```
@name @lastname | @checkindate → @checkoutdate | @accommodationname
```

**Available variables:**
- `@name` — Guest first name
- `@lastname` — Guest last name
- `@checkindate` — Check-in date
- `@checkoutdate` — Check-out date
- `@accommodationname` — Property name
- `@nights` — Number of nights
- `@amount` — Total amount
- `@currency` — Currency
- `@channel` — Booking platform (e.g. Airbnb, Booking.com)
- `@bookingid` — Booking reference

The settings page shows a live preview of the final text using sample data, so you can see exactly how the description will appear on your documents.

## myDATA submission

Every document issued in Elorus is **automatically submitted** to myDATA, provided the option is enabled in settings.

<Warning>
A myDATA failure **does not cancel** the Elorus document. myDATA failure management is handled within Elorus, not Etherly Sync.
</Warning>

## Manual send

<Steps>
  <Step title="Select checkouts">
    In **Bookings**, select one or more checkouts in `READY` status using their checkboxes.
  </Step>
  <Step title="Click «Send»">
    Use the **Send** button in the toolbar for bulk sending, or the button next to each checkout for individual sends.
  </Step>
  <Step title="Watch the results">
    Status changes to `SENT` (success), `SENT_WITH_ERRORS` (partial), or `ERROR` (failure). Error messages appear inline on failure.

    **myDATA delay:** If myDATA is not ready immediately after document creation, the status transitions to `WAITING_MYDATA_FINALIZATION`. The system automatically retries up to 9 times (~17-hour window). If retries are exhausted, the status becomes `NEEDS_MANUAL_REVIEW` — the document was created successfully in Elorus; only myDATA finalization is pending.
  </Step>
</Steps>

## Bulk Send

Select multiple checkouts with checkboxes and click **Send Selected** to process them in batch.

## SENT_WITH_ERRORS status

This appears when the Accommodation Document and Payment Receipt were successfully issued, but the **Climate Resilience Fee** document failed.

**What to do:**
1. Check the error message on the Bookings page
2. Verify the fee category is correctly configured in Properties
3. Check that the tax rules in Elorus are current

