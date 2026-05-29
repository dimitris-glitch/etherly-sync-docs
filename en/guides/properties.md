---
title: "Property Configuration"
description: "How to configure each property so it's ready for automatic invoicing — contacts, sequences, fee categories, and organizations."
---

# Property Configuration

Every property synced from Hosthub needs **complete configuration** before it can be invoiced. Without it, checkouts appear in `NEEDS_SETUP` status.

## Required settings

### 1. Elorus Contact

The Elorus account that appears as the "customer" on documents. For short-term rentals, this is typically a **retail account** (e.g., "Retail Customer").

**How to find the right contact:**
1. Go to Elorus → **Contacts**
2. Find or create an active retail customer
3. Select it from the dropdown in Etherly Sync

### 2. Invoice Sequence

The document numbering series for this property (e.g., "INV-2025-0001"). Each property can use a different sequence.

<Warning>
If the sequence isn't active in Elorus or doesn't allow the document type you're using, the send will fail. Verify under Elorus → Settings → Sequences.
</Warning>

### 3. Climate Resilience Fee Category

The property category used to calculate the nightly fee. Categories correspond to tax codes you've defined in Elorus.

<Tip>
See the [Climate Resilience Fee Guide](/en/guides/climate-fee) for the full list of categories, seasonal differences, and calculation examples.
</Tip>

### 4. Elorus Organization

The organization under which documents are issued. If you manage properties under different tax IDs, you can assign each property to a different organization.

## Step-by-step configuration

<Steps>
  <Step title="Go to Properties">
    Select **Properties** in the sidebar. Alternatively, click the ⚙️ icon next to any `NEEDS_SETUP` checkout.
  </Step>
  <Step title="Select the property">
    You'll see all properties detected from Hosthub. Click on the one you want to configure.
  </Step>
  <Step title="Fill in all 4 fields">
    Select values for Contact, Sequence, Fee Category, and Organization from their respective dropdowns.
  </Step>
  <Step title="Save">
    Click **Save**. The property's checkouts change from `NEEDS_SETUP` to `READY` on the next sync (within 5 minutes).
  </Step>
</Steps>

## Enabling / Disabling a property

Each property can be independently enabled or disabled.

| State | Invoicing | Sync |
|-------|-----------|------|
| **Enabled (On)** | ✅ Normal | ✅ Continues |
| **Disabled (Off)** | ❌ Blocked | ✅ Continues |

<Note>
Setting a property to Off **does not stop sync**. Data stays current — only invoicing is suspended. Ideal for properties under renovation or outside of season.
</Note>

## Multiple organizations

If you manage properties under **different tax IDs** (e.g., sole trader + LLC), add multiple Elorus connections:

<Steps>
  <Step title="Add a new connection">
    Settings → **Invoicing Connections** → **Add Connection**
  </Step>
  <Step title="Enter a new Elorus API key">
    Each connection requires a separate API key from the corresponding Elorus account.
  </Step>
  <Step title="Assign properties">
    Return to Properties and set the correct organization for each property.
  </Step>
</Steps>

Each connection stores its own API key, encrypted separately.
