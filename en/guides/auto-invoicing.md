---
title: "Auto-Invoicing"
description: "Set up nightly auto-invoicing and let Etherly Sync issue documents every evening without any manual work."
---

# Auto-Invoicing

Auto-invoicing runs **once daily** at an **Execution time** you choose, automatically invoicing all bookings that meet the eligibility criteria.

## Enabling auto-invoicing

<Steps>
  <Step title="Go to Settings">
    Select **Settings** from the sidebar.
  </Step>
  <Step title="Enable automatic invoicing">
    Find the **"Automatic invoicing"** section and enable the toggle.
  </Step>
  <Step title="Choose Execution time">
    Select a time between **10 PM and midnight**. 10 PM is recommended to leave time to address any errors before midnight.
  </Step>
  <Step title="Save">
    Click **"Save"**. Auto-invoicing activates starting from the next **Execution time**.
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

- Bookings you've already sent manually won't be re-sent
- You can send manually at any time, independently of the auto-invoicing schedule
- Disabling the toggle only stops the automated runs

## Changing the execution time

Change the **Execution time** at any point from **Settings** → **Automatic invoicing**. The change takes effect from the next execution.
