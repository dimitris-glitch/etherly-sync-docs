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

## Finding a property in the list

A **search** field sits above the list. Type part of a property's name, location or city and the list narrows immediately to the ones that match.

Search works with upper or lower case and with or without accents — "χανια" finds "Χανιά". The `×` inside the field brings the full list back, and any properties you had expanded stay expanded.

## Property groups

Groups let you organise your properties the way you think about them — by area ("Crete", "Attica"), by owner, or any other way that suits you. Each property belongs to **one group**.

Groups are purely organisational: they help you find and sort your properties in the list. Invoicing settings, taxes and automatic document issuing stay exactly as you have set them per property.

### Creating a group

1. **Settings → Properties → "New group"**
2. Give it a name (up to 40 characters)
3. Add as many properties as you want from the list in the dialog
4. **Save**

Each group name is unique, and its colour is assigned automatically so creating one stays quick. You can change it whenever you like from **Edit group**. You can create up to 20 groups.

### How the list changes

As soon as one group exists, the list is shown grouped: each group is a card with its name and property count, and opens on click. Properties without a group are collected under **"Ungrouped"** at the end of the list. The app remembers which groups you had open.

While searching, the groups that contain matching properties are shown open.

### Assigning a property to a group

Four ways, same result:

- **From the property's settings** — open the property and pick a group in the **Group** field at the top.
- **From the row's `⋮` menu** — **Move to group** and pick one. It applies immediately, with an **Undo** option.
- **From Edit group** — add or remove several properties at once and save once. This is the fastest way to do the initial organising.
- **By dragging** — see **Organise** below.

The edit dialog lists every property. If you pick one that already belongs to another group, the app tells you before you save. **Remove** returns the property to "Ungrouped" — the property and its settings stay.

### Organising by dragging

The **Organise** button, next to "New group", puts a handle on every property row. Drag the handle onto another group card and drop it: the property moves there immediately, with an **Undo** option. Hover over a collapsed card for a moment and it opens by itself so you can see what is inside, and the card that received the property stays open after the drop.

Dragging works from the keyboard too: focus the handle, press **space** or **Enter** to pick the property up, choose a group with the **arrow keys**, drop it with **space** or **Enter**, and cancel with **Escape**.

While **Organise** is on, "Ungrouped" is always shown, so you can take a property out of its group by dragging it there. **Done** returns you to the normal list.

### Deleting a group

From the card's `⋮` menu → **Delete group**. The group's properties return to "Ungrouped" and all their settings are kept.

### Working inside a group

Once you have groups, you can narrow any property list down to one of them. The **Property** filter gains a **"By group"** section — pick a group and the screen shows only its properties. There is also an **"Ungrouped"** option for the ones you have not organised yet, and **"All properties"** brings the full picture back.

The filter is available on **Bookings**, **Online Check-Ins** and **AADE declarations**.

Each screen remembers its own choice, so the group you work in daily is already selected next time — and a screen you were not looking at stays as you left it. While a group filter is active, a strip above the list names the group you are viewing and how many of your properties it covers, with a **Clear** button. If someone deletes the group you were viewing, the screen returns to "All properties" and tells you.

In the properties list and in the **Settings → Check-In Settings** tab, properties are shown in collapsible cards per group, while in the **Settings → Advanced → Automatic property invoicing** table and in the cleaning-staff assignment they are shown grouped with a heading and a count per group.

In the **Automatic property invoicing** table, each group heading opens and closes with a click: close the groups you are not working on right now and only the ones you want to set up stay in view. While a group is closed, its heading keeps showing the group name and how many properties it holds. The table opens with every group expanded.

<Note>
The **Automatic property invoicing** table also shows switched-off properties, so each group's count there includes them — while the **Settings → Properties** list counts the active ones. Every number always matches the rows it opens.
</Note>

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

<Note>
A booking's documents always stay with the organization that issued them. If you change a property's organization and a send is then attempted for a booking whose documents already exist, the send stops and the booking is flagged **"Manual review"** — assign the property back to the original organization to complete it. New bookings are invoiced normally under the new organization.
</Note>

## Copy / Paste settings

If you have many properties with the same settings, use **"Copy settings"** on one property and **"Paste settings"** on the others for quick configuration.
