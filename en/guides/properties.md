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
  <Step title="Done">
    Settings save automatically on every change. Once all fields are filled in, bookings change from `NEEDS_SETUP` to `READY` on the next sync.
  </Step>
</Steps>

## Organization settings — Document Types

In **Settings → "Organizations" tab**, for each Elorus organization you define which document types the auto-invoicing uses:

- **Receipts** — the document type for accommodation receipts
- **Invoices** — the document type for accommodation invoices

The available options are **loaded dynamically from Elorus** and correspond to the document types you have created for that organization (e.g. "Service Invoice", "Retail Receipt", etc.). The selection applies to every document issued automatically for properties under that organization.

## Location & Coordinates

On each property card, under **"Location & Details"**, you can set the city, country, timezone and — optionally — the property's **coordinates**, its **property type** (villa, apartment, studio etc.), its **maximum guests**, **bedrooms** and **bathrooms**.

The more complete the profile, the more precise the comparisons: with coordinates, guests, bedrooms and bathrooms filled in, Etherly Insights can show where your property sits against **comparable** listings in its area (rate, occupancy and revenue as a position in the distribution).

Type and capacity enable comparisons against similar-profile listings in your area. For properties connected via Hosthub, capacity is filled in automatically by sync — the property type is always set by you.

Coordinates enable a more precise market analysis for the property's area (e.g. comparing occupancy against your neighborhood instead of the whole city).

**How to find them in Google Maps:**

1. Open [Google Maps](https://maps.google.com) and locate your property.
2. **Right-click** exactly on the property's spot.
3. Click the coordinates shown at the top of the menu — they are copied automatically.
4. Paste them into the **"Coordinates"** field (e.g. `37.9838, 23.7275`). Saving happens automatically.

<Note>
For properties connected via Hosthub, coordinates are filled in **automatically** from the property's details in Hosthub during sync. Anything you enter manually is preserved — sync never overwrites it.
</Note>

## Enabling / Disabling a property

In **Settings → Advanced**, under **"Property Invoicing"**, use the toggle next to the property.

| State | Invoicing | Sync |
|-------|-----------|------|
| **On** | ✅ Normal | ✅ Continues |
| **Off** | ❌ Suspended | ✅ Continues |

<Note>
**Off** does not stop sync. Data stays current — only auto-invoicing is suspended. Useful when you want to handle billing manually or through a different invoicing platform.
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
