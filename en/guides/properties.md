---
title: "Property Configuration"
description: "How to configure each property so it's ready for automatic invoicing."
---

# Property Configuration

Every property synced from Hosthub needs **complete configuration** before it can be invoiced. Without it, bookings show status `NEEDS_SETUP`. Navigate to **Properties** in the sidebar.

## Required fields

### 1. Default Receipts Contact

The Elorus account that appears as the "customer" on receipts — typically a retail account.

**How to find it in Elorus:**
1. Go to Elorus → **Contacts**
2. Find or create an active retail customer
3. In the field, click and type a VAT number or company name (3+ characters) to search

### 2. Invoices Series

The numbering series for invoices. The **Receipts Series** field handles the series for receipts.

<Warning>
If the series isn't active in Elorus or doesn't allow the document type you're using, the send will fail. Verify under Elorus → Settings → Document Series.
</Warning>

### 3. Category

The property category used to calculate the Climate Resilience Fee:

- **Standard** — standard property
- **>80sq.m** — houses over 80 square metres

<Tip>
See the [Climate Resilience Fee Guide](/en/guides/climate-fee) for the calculation method and examples.
</Tip>

### 4. Organization

The Elorus organization under which documents are issued. If you manage properties under different tax IDs, you can assign each property to a different **Organization**.

## Step-by-step configuration

<Steps>
  <Step title="Go to Properties">
    Select **Properties** from the sidebar. Alternatively, click the settings icon next to any `NEEDS_SETUP` booking.
  </Step>
  <Step title="Select the property">
    You'll see all properties detected from Hosthub. Click on the one you want to configure.
  </Step>
  <Step title="Fill in all fields">
    Select values for **Default Receipts Contact**, **Invoices Series**, **Category**, and **Organization** from their respective dropdowns.
  </Step>
  <Step title="Save">
    Click **"Save"**. The property's bookings change from `NEEDS_SETUP` to `READY` on the next sync (within 5 minutes).
  </Step>
</Steps>

## Enabling / Disabling a property

Use the **"Turn on property"** / **"Turn off property"** buttons for each property.

| State | Invoicing | Sync |
|-------|-----------|------|
| **On** | ✅ Normal | ✅ Continues |
| **Off** | ❌ Suspended | ✅ Continues |

<Note>
**Off** does not stop sync. Data stays current — only invoicing is suspended. Ideal for properties under renovation or out of season.
</Note>

## Multiple organizations

If you manage properties under **different tax IDs**, add multiple Elorus connections:

<Steps>
  <Step title="Add a new connection">
    **Settings** → **Integrations** → **"New Connection"**
  </Step>
  <Step title="Enter a new Elorus API key">
    Each connection requires a separate API key. Give it a **Connection Title** for easy identification (e.g. "My Elorus").
  </Step>
  <Step title="Assign properties">
    Return to **Properties** and set the correct **Organization** for each property.
  </Step>
</Steps>

## Copy / Paste settings

If you have many properties with the same settings, use **"Copy settings"** on one property and **"Paste settings"** on the others for quick configuration.
