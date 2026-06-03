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
| Account | Active subscription |

## What is NOT auto-invoiced

- Bookings in `NEEDS_SETUP`, `SENT`, `SENT_WITH_ERRORS`, `ERROR`, `SPLIT`
- Paused bookings (manual Pause or `##sync-skip`)
- Bookings belonging to **Off** properties
- Cancelled bookings

To exclude **individual bookings**, use [Pause](/en/guides/checkouts#pause--resume). To exclude **an entire property** (e.g. if that property is invoiced directly in the invoicing platform), set it to Off in [Properties](/en/guides/properties).

## Execution results

After each auto-invoicing run, the status of each booking is updated automatically in the **Checkouts** table (`SENT`, `ERROR`, etc.). If you have the **daily report** enabled (from Team Management), you also receive an email with a summary of invoiced and uninvoiced checkouts.

<Note>
If no `READY` bookings exist at execution time, auto-invoicing completes without doing anything — no error is generated.
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
