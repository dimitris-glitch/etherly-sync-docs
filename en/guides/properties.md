---
title: "Property Setup"
description: "The fields on each property's card — Organization, Regime, House type, Climate-fee tax, VAT, Stay Tax with municipality, receipts contact, Branch, series, location and coordinates — which are needed to issue documents and which take their value from the organization; copying settings to many properties, properties under different tax IDs (a second organization or a second Elorus connection), and turning invoicing off under Advanced; notice and email to the Owner and Admins when the municipality changes the Stay Tax."
---

# Property Setup

To issue a property's documents automatically, the app needs a few details about it: which organization issues them, what kind of accommodation it is and which Elorus contact receipts are issued to. You set them once in **Settings → Properties**. While something is missing, the property's bookings show as **"Needs setup"**.

## The property card

Each property is a card in the list. Click its name, or **Settings** on the right, to open it. To find a property quickly, type part of its name or city in the search above the list — with or without accents.

Every change is saved automatically, and you see next to the field that it was saved. When a setting changes from elsewhere — e.g. by **Nio**, after you confirm — the card briefly shows **"Updated"**.

## What documents need

| Field | Why it's needed |
|-------|-----------------|
| **Organization** | It is the one that issues the property's documents. |
| **House type** | It sets the Climate Resilience Fee (ΤΑΚΚ) per night. |
| **Climate-fee tax** | The organization needs the tax with the legal amount of the property's category. |
| **Default Receipts Contact** | Elorus issues every receipt to a contact. |

The other fields take their value from the organization, or are only needed if they apply to you.

## The card's fields

### Organization

The Elorus organization that issues the property's documents. If you have properties under different tax IDs, you pick each one's own (see [Properties under different tax IDs](#properties-under-different-tax-ids)). If you rent as a private individual without a registered business, choose **Private individual** — see [Private individual](/en/guides/private-individual).

### Property details

- **Regime** — what the property's rental legally is. It decides whether a document is issued, whether VAT and the Stay Tax apply, the ΤΑΚΚ amount, and whether a Short-Term Stay Declaration is submitted.
- **House type** — **Room or apartment**, **Detached house up to 80 m²** or **Detached house over 80 m²**. Together with the regime it sets the property's ΤΑΚΚ category.
- **Maximum guests** — counts as "beds" in AADE's ΤΑΚΚ form and in the market comparison. If your booking provider sends it, it is filled in by the sync while it is empty.
- **Bedrooms** and **Bathrooms** (optional) — used in the market comparison. For furnished rooms & apartments for rent, Bedrooms also count as "available rooms" in the ΤΑΚΚ form, so they are needed there.

For the categories and amounts, see the [Climate Resilience Fee guide](/en/guides/climate-fee).

### Climate-fee tax

Shows the property's AADE category and the organization's tax for summer and winter. The organization needs each category's own tax, with exactly the legal amount — so a ΤΑΚΚ receipt is never issued with the wrong amount. If it says **Pending**, pick the matching Elorus tax for each period.

### VAT and Stay Tax

**VAT** is the rate of the accommodation documents — the standard rate for accommodation is 13%. If a rate is missing in Elorus, it is created there.

For the **Stay Tax**, choose the property's municipality and the app sets its rate — 0.5%, or 0.75% where the municipal council has decided an increase. If the property already had 0.75%, or if the municipality does not set one rate for all accommodation (for example, it sets a different rate per area), you choose. **Details** shows the municipality's decision and upcoming changes. You can always choose the other rate.

When the municipality changes its rate or decision, you see a notice on the home page and the **Stay tax: Pending** badge on the property's card until you choose the rate you apply. Municipal rates and decisions are updated once a month. The Owner and Admins also receive an email.

### Customer on receipts

Elorus issues every receipt to a contact, even when the guest is a private individual. This is where you choose which one:

- **One contact for all receipts** — the property's receipts are issued to the contact in the **Default Receipts Contact** field. If you don't choose a contact, the app creates and uses a "Retail Guest" contact automatically.
- **A separate contact with the guest's details, for each booking** — a contact with the guest's name and country is created in Elorus, and the receipt is issued to it. If a booking has no guest name, the receipt is issued to the "Retail Guest" contact.

The setting carries over to other properties with **Copy settings** / **Paste settings**. For an invoice to a company, see [My guest asked for an invoice](/en/faq#my-guest-asked-for-an-invoice-what-do-i-do).

### Branch

If your business has branches in Elorus, the branch the property's documents are issued under. Companies are usually required to register a separate branch for each property at a different address.

### Receipts Series and Invoices Series

The numbering series of receipts and invoices. If your business does not use series, choose **No series**. If you want some of your properties to issue documents in a different series, create it in Elorus: Settings > Document types > choose the type and Add series.

### Location & Details

**City / Area**, **Country**, **Timezone** and, optionally, **Coordinates**. The timezone is filled in from the country; we only ask for it when the country has more than one.

With coordinates, DeskBoy MCP compares your property with similar ones in its neighbourhood rather than the whole city. To find them in Google Maps:

1. Open [Google Maps](https://maps.google.com) and find your property.
2. Right-click exactly on it.
3. Click the coordinates shown first in the menu — they are copied automatically.
4. Paste them into the **Coordinates** field (e.g. `37.9838, 23.7275`).

If your booking provider sends them, the coordinates are filled in by the sync. Anything you enter yourself is never overwritten.

## Many properties

### Same settings on many properties

In a card's header press **Copy settings**, then **Paste settings** on each other property: the organization, VAT, Stay Tax with its municipality, receipts contact, branch and series are carried over. On mobile you'll find them in the card's **⋮** menu.

For the municipality there is a shorter way: once you set it on one property, press **Use on … more properties** under the Stay Tax and pick the ones in the same municipality — they get the municipality and the rate.

### Properties under different tax IDs

Each tax ID is one organization. If the organization is in the same Elorus account, add it in **Settings → Tax details** with **Add Elorus Organization**. If it is in another Elorus account, first add a connection: **Settings → Integrations** → **Elorus** card → **New Connection**, with that account's API key. Then pick the right **Organization** on each property. If you change a property's organization, its unsent invoice bookings lose the company you had picked, because it belongs to the previous organization; pick it again from the new one before sending.

<Note>
On the Free plan all properties belong to one organization (or the private individual). If you pick another organization on a property, the app offers to **move all** properties to it or to **upgrade**, for properties across more organizations. After the move, bookings not yet invoiced are invoiced by the new organization; documents already issued stay as they are.
</Note>

## Turning invoicing on and off

In **Settings → Advanced**, in the **Active Properties** table, you turn invoicing on or off for each property. Booking sync carries on as normal.

While a property is off, its bookings with check-out from that day on are **Skipped**. When you turn it back on, those with check-out from the day you turned it on come back; for earlier ones you decide, with **Undo skip** in **Bookings**. Bookings you skipped manually are not affected.

## Property groups

To organise your properties into groups, e.g. by area or owner, see [Property Groups](/en/guides/property-groups).
