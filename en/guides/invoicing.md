---
title: "How Invoicing Works"
description: "The three documents issued per checkout, the order they're created, and how myDATA submission works."
---

# How Invoicing Works

For every checkout that is sent, DeskBoy automatically creates documents in Elorus, in a strictly defined order.

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
    Calculated per night, at the legal amount of the property's band. If the booking spans winter and summer, two separate documents are issued.
  </Card>
</CardGroup>

## Document Description

The text shown on the service line of the Accommodation Document (e.g. "BK-123456 | 01/07/2026 → 03/07/2026 | City Vibes Loft") is generated from a template, which you configure under **Settings → Document Description**.

Even if you haven't customized anything, an effective template is always in use: either the one you've set, or the built-in default:

```
@bookingid | @checkindate → @checkoutdate | @accommodationname
```

The default template uses the booking reference instead of the guest's name, so that less personal data reaches your invoicing provider. If you need the name in the description, add the `@name` and `@lastname` variables to your own template.

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
A myDATA failure **does not cancel** the Elorus document. myDATA failure management is handled within Elorus, not DeskBoy.
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

    **myDATA delay:** If myDATA is not ready immediately after document creation, the status transitions to `WAITING_MYDATA_FINALIZATION`. The system retries automatically for about a day. If retries are exhausted, the status becomes `NEEDS_MANUAL_REVIEW` — the document was created successfully in Elorus; only myDATA finalization is pending.
  </Step>
</Steps>

## Bulk Send

Select multiple checkouts with checkboxes and click **Send Selected** to process them in batch.

## SENT_WITH_ERRORS status

This appears when the Accommodation Document and Payment Receipt were successfully issued, but the **Climate Resilience Fee** document failed.

**What to do:**
1. Check the error message on the Bookings page
2. Verify the ΤΑΚΚ characteristics are selected on the property and that the organisation has a tax with its band amount (Tax details)
3. Check that the tax rules in Elorus are current

## Sending the receipt to the guest

On issue, the guest receives an email with a link to the receipt, sent under your business name. In the booking's timeline you can see where and when it was sent and whether it was delivered. If the booking has no email address or the platform's address has expired, the email is not sent. If the guest wants the receipt at a different email, change the address with the pencil in the booking details, before or after issue, and press “Send document” or “Resend”. Hover over the step's status to see every send that was made, to which address, and what happened to it. In **Settings → Advanced** you choose which documents are emailed, receipts or invoices, and to which guests: from your business's country or from abroad. A guest on holiday rarely needs a receipt from a business in another country, so the default sends invoices only. Automatic sending applies to stays that ended recently. For older ones, or when your settings do not send, the “Not sent” step explains why and you can send manually with “Send document”.

<Note>
If the booking has no guest country, the document is sent only when it is enabled both for guests from your country and for guests from abroad.
</Note>

<Note>
Bookings from Booking.com and Expedia come with a temporary email address provided by the platform to protect the guest's personal details. While it is active, any message sent there is forwarded by the platform to the guest's real email. It expires about 7 days after check-out; after that DeskBoy does not send to that address, because the message would bounce, and shows "Channel address expired" instead. If an address bounces the message, the receipt is not sent there again: change the address with the pencil, or download it from “View document” and send it from your own email. Any address you enter with the pencil never expires, even if it is the same as the channel's.
</Note>
