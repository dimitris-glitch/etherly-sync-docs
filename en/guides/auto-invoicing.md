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
| Account | Active trial, Grace Period, or sufficient credits |

## What is NOT auto-invoiced

- Bookings in `NEEDS_SETUP`, `SENT`, `SENT_WITH_ERRORS`, `ERROR`, `SPLIT`
- Paused bookings (manual Pause or `##sync-skip`)
- Bookings belonging to **Off** properties
- Cancelled bookings

To exclude **individual bookings**, use [Pause](/en/guides/checkouts#pause--resume). To exclude **an entire property** (e.g. during renovation), set it to Off in [Properties](/en/guides/properties).

## Execution results

After each auto-invoicing run, you can see:
- How many bookings were successfully invoiced
- How many failed and which ones
- Total credit consumption

<Note>
If no `READY` bookings exist at execution time, auto-invoicing completes without doing anything — no error is generated.
</Note>

## Combining with manual sends

Auto-invoicing and manual sends **work seamlessly together**:

- Bookings you've already sent won't be re-sent
- You can send at any time, independently of the auto-invoicing schedule
- Disabling the toggle only stops the automated runs

## Changing the execution time

Change the **Execution time** at any point from the **Checkouts** page (same toggle). The change saves automatically and takes effect from the next execution.
