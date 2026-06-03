---
title: "Property Configuration"
description: "How to configure each property so it's ready for automatic invoicing."
---

# Property Configuration

This is where you define everything the app needs to issue documents correctly for each property: company details, document types, taxes, service descriptions, and more. Configuration is done **once** — after that, the app can run automatically for every new booking at that property.

You always retain full manual control for bookings you want to handle differently — for example, issuing an invoice instead of a receipt, sending at a different time, or excluding a booking from auto-invoicing altogether.

Every property needs **complete configuration** before it can be invoiced. Without it, bookings show status `NEEDS_SETUP`.

## Where to find it

**Settings → "Properties" tab**

## Required fields

### 1. Default Receipts Contact

The Elorus account that appears as the "customer" on receipts.

**In Elorus:**
1. Go to Elorus → **Contacts**
2. Find or create an active retail customer

**In Properties → Default Receipts Contact:**
Click the field and type the contact's **name** (3+ characters) to search.

### 2. Invoices Series / Receipts Series

The numbering series for invoices (**Invoices Series**) and receipts (**Receipts Series**) respectively. If your business does not use numbering sequences, select **"No Series"**.

### 3. Category

The property category used to calculate the Climate Resilience Fee:

- **Standard** — standard property
- **>80sq.m** — houses over 80 square metres

<Tip>
See the [Climate Resilience Fee Guide](/en/guides/climate-fee) for the calculation method and examples.
</Tip>

### 4. Organization

The Elorus organization under which documents are issued. If you manage properties under different tax IDs, you can assign each property to a different **Organization**.

### 5. Branch

The Elorus branch under which documents are issued, if your business has multiple branches in Elorus.

### 6. VAT

The VAT rate applied to accommodation documents for this property.

### 7. Transient Tax

Configuration for the Transient Occupancy Tax, if applicable for this property.

## Step-by-step configuration

<Steps>
  <Step title="Go to Settings">
    **Settings** → **"Properties"** tab.
  </Step>
  <Step title="Select the property">
    You'll see all properties detected from Hosthub. Click on the one you want to configure.
  </Step>
  <Step title="Fill in all fields">
    Select values for **Default Receipts Contact**, **Invoices Series**, **Category**, **Organization**, and any other applicable fields.
  </Step>
  <Step title="Save">
    Click **"Save"**. The property's bookings change from `NEEDS_SETUP` to `READY` on the next sync.
  </Step>
</Steps>

## Organization settings — Document Types

In **Settings → "Organizations" tab**, for each Elorus organization you can define which document types the auto-invoicing uses:

- **Receipts** — select the Elorus document type for receipts
- **Invoices** — select the Elorus document type for invoices

## Enabling / Disabling a property

In **Settings → Advanced**, under **"Property Invoicing"**, use the toggle next to the property.

| State | Invoicing | Sync |
|-------|-----------|------|
| **On** | ✅ Normal | ✅ Continues |
| **Off** | ❌ Suspended | ✅ Continues |

<Note>
**Off** does not stop sync. Data stays current — only invoicing is suspended. Ideal for properties under renovation or out of season.
</Note>

## Multiple Elorus organizations

If you manage properties under **different tax IDs**, add multiple Elorus connections. For example, if some properties are registered under a sole-trader entity and others under a company, create a separate connection for each — then map each property to the correct organization.

<Steps>
  <Step title="Add a new connection">
    **Settings** → **Integrations** → **"New Connection"**
  </Step>
  <Step title="Enter a new Elorus API key">
    Each connection requires a separate API key. Give it a **Connection Title** for easy identification (e.g. "My Elorus").
  </Step>
  <Step title="Assign properties">
    Return to **Settings → Properties** and set the correct **Organization** for each property.
  </Step>
</Steps>

## Copy / Paste settings

If you have many properties with the same settings, use **"Copy settings"** on one property and **"Paste settings"** on the others for quick configuration.
