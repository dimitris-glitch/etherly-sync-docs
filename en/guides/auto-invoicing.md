---
title: "Auto-Invoicing"
description: "Set up nightly auto-invoicing and let Etherly Sync issue documents every evening without any manual work."
---

# Auto-Invoicing

Auto-invoicing runs **once daily** at an **Execution time** you choose, automatically invoicing all bookings that meet the eligibility criteria.

## Enabling auto-invoicing

<Steps>
  <Step title="Go to Checkouts">
    Select **Checkouts** from the sidebar.
  </Step>
  <Step title="Enable the toggle">
    Above the checkouts table, find the **"Automatic invoicing"** toggle and enable it.
  </Step>
  <Step title="Set the Execution time">
    The **"Execution time"** field appears. Select the time you want auto-invoicing to run each day. The setting saves automatically.
  </Step>
</Steps>

## Eligibility criteria

During auto-invoicing, only bookings that meet **all** of the following are processed:

| Criteria | Required state |
|----------|---------------|
| Booking status | `READY` |
| Paused | Not paused |
| Property | **On** (enabled) |
| Booking | Not cancelled |
| Account | Active |

## What is NOT auto-invoiced

- Bookings in `NEEDS_SETUP`, `SENT`, `SENT_WITH_ERRORS`, `ERROR`, `SPLIT`
- Paused bookings (manual Pause or a disabled channel)
- Bookings belonging to **Off** properties
- Cancelled bookings

To exclude **individual bookings**, use [Pause](/en/guides/checkouts#pause--resume). To exclude **an entire property** (e.g. if that property is invoiced directly in the invoicing platform), set it to Off in [Properties](/en/guides/properties).

## Booking check before issuing

Immediately before a document is issued, the app confirms directly with your booking channel that the specific booking still stands — beyond the criteria in the table above.

- If the channel reports the booking **has been cancelled**, issuing stops and the booking is marked as cancelled. The reason appears in the daily report.
- If the channel **does not respond** at that moment, issuing is **postponed** and retried later.

This way a cancellation made after the last sync does not end up as a document. The check applies to Hosthub connections.

## Execution results

After each auto-invoicing run, the status of each booking is updated automatically in the **Checkouts** table (`SENT`, `ERROR`, etc.). If you have the **daily report** enabled (from Team Management), you also receive an email with a summary of invoiced and uninvoiced checkouts.

<Note>
If no `READY` bookings exist at execution time, auto-invoicing completes without doing anything — no error is generated.
</Note>

## Climate Resilience Fee for stays that cross a rate change

When a stay crosses the date on which the Climate Resilience Fee rate changes (e.g. 31 March → 1 April), the booking is automatically split into two parts — one per rate period. Each part issues its own accommodation document and its own fee receipt, with the amounts prorated across its nights. The first part is issued on its last night, so that it is declared in the correct month — in line with the legislation and the AADE guidance — and the second as usual at checkout.

**Example**: a booking from 28 March to 3 April, 6 nights, with €600 accommodation.

| Part | Period | Accommodation document | Fee receipt | Issued |
|------|--------|------------------------|-------------|--------|
| 1st | 28/3 – 1/4 (4 nights) | €400 | winter period, 4 nights | **31 March** |
| 2nd | 1/4 – 3/4 (2 nights) | €200 | summer period, 2 nights | **3 April** (checkout) |

With auto-invoicing enabled, each part's documents are issued automatically on the day they correspond to. With manual sends nothing is issued automatically: on the first part's issue day (31 March in the example) the part appears in **today's bookings** and you send it like any other booking of the day; the second part appears as usual on the departure day. Both parts appear on the [Climate Resilience Fee](/guides/climate-fee) page, each in the month it was issued.

<Note>
If your account needs a different handling of the rate boundary, or your accountant prefers a different approach (e.g. issuing all documents at checkout), the Etherly team can adjust it — contact us.
</Note>

## Combining with manual sends

Auto-invoicing and manual sends **work seamlessly together**:

- Bookings you've already sent won't be re-sent
- You can send at any time, independently of the auto-invoicing schedule
- Disabling auto-invoicing leaves all bookings in the app — you can still send them manually

## Auto-invoicing per channel

In **Settings → Advanced**, you can enable or disable auto-invoicing for each booking channel individually (Airbnb, Booking.com, Phone, etc.).

- **New** bookings from a disabled channel are automatically marked **Skipped** and excluded from auto-invoicing.
- For **existing** bookings: filter by channel in Bookings and bulk-update their status as needed.

## Advanced settings (Settings → Advanced)

### AADE — Tax ID lookup

Enter your **AADE Login Code** and **Password** to enable automatic company lookup by tax ID when creating a new customer in Elorus.

### Year-End — Booking Split

Toggle for automatic cross-year booking splits. Only active when auto-invoicing is enabled.

## Changing the execution time

Change the **Execution time** at any point from the **Checkouts** page (same toggle). The change saves automatically and takes effect from the next execution.
