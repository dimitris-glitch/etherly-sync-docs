---
title: "How Invoicing Works"
description: "The three documents issued per checkout, the order they're created, and how myDATA submission works."
---

# How Invoicing Works

For every checkout that is sent, Etherly Sync automatically creates **three documents** in Elorus, in a strictly defined order.

## The 3 documents

<CardGroup cols={3}>
  <Card title="1. Accommodation Invoice" icon="file-invoice">
    **myDATA type**: 11.2  
    **VAT**: 13%  
    The primary document for the accommodation service.
  </Card>
  <Card title="2. Payment Receipt" icon="receipt">
    Linked to the invoice.  
    Confirms payment received.  
    Issued immediately after the invoice.
  </Card>
  <Card title="3. Climate Resilience Fee" icon="leaf">
    Separate cash receipt.  
    Calculated per night and category.  
    Split per season if the booking spans winter/summer.
  </Card>
</CardGroup>

<Note>
The creation order **cannot be changed**: invoice → receipt → fee. If any step fails, the system stops and records the error — subsequent steps are not attempted.
</Note>

## myDATA submission

Every document issued in Elorus is **automatically submitted** to myDATA, provided the option is enabled in settings.

- myDATA returns a MARK (Unique Registration Number) for each document
- If myDATA submission fails, the document **is still issued** in Elorus — manual submission may be required

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

<Info>
Bulk sends are processed **sequentially** (one at a time) to avoid Elorus API rate limits. Allow a few seconds per checkout for large batches.
</Info>

## SENT_WITH_ERRORS status

This appears when the invoice and payment receipt were successfully issued, but the **Climate Resilience Fee** document failed.

**What to do:**
1. Check the error message in the dashboard
2. Verify the fee category is correctly configured in Properties
3. Check that the tax rules in Elorus are current

## Duplicate prevention

Etherly Sync **checks before every issuance** whether documents already exist for that checkout. If found, the send is cancelled without error — duplicates are never created.

## Automatic retries

On failures due to rate limits or temporary Elorus API unavailability, the system **automatically retries** up to 3 times with exponential backoff. Errors 400/401/403/404/409/422 are not retried (they are permanent failures).
