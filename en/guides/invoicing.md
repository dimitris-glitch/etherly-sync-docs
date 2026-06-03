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
    Issued immediately after the invoice.
  </Card>
  <Card title="3. Climate Resilience Fee" icon="leaf">
    Calculated per night and category. If the booking spans winter and summer, two separate documents are issued.
  </Card>
</CardGroup>

## myDATA submission

Every document issued in Elorus is **automatically submitted** to myDATA, provided the option is enabled in settings.

<Warning>
A myDATA failure **does not cancel** the Elorus document. myDATA failure management is handled within Elorus, not Etherly Sync.
</Warning>

## Manual send

<Steps>
  <Step title="Select checkouts">
    In the dashboard, select one or more checkouts in `READY` status using their checkboxes.
  </Step>
  <Step title="Click «Send»">
    Use the **Send** button in the toolbar for bulk sending, or the button next to each checkout for individual sends.
  </Step>
  <Step title="Watch the results">
    Status changes to `SENT` (success), `SENT_WITH_ERRORS` (partial), or `ERROR` (failure). Error messages appear inline on failure.
  </Step>
</Steps>

## Bulk Send

Select multiple checkouts with checkboxes and click **Send Selected** to process them in batch.

## SENT_WITH_ERRORS status

This appears when the invoice and payment receipt were successfully issued, but the **Climate Resilience Fee** document failed.

**What to do:**
1. Check the error message in the dashboard
2. Verify the fee category is correctly configured in Properties
3. Check that the tax rules in Elorus are current

