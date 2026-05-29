---
title: "Auto-Invoicing"
description: "Set up nightly auto-invoicing and let Etherly Sync issue documents every evening without any manual work."
---

# Auto-Invoicing

Auto-invoicing runs **once daily** at a time you choose, automatically invoicing all checkouts that meet the eligibility criteria.

## Enabling auto-invoicing

<Steps>
  <Step title="Go to Settings">
    Select **Settings** → **Auto-Invoicing** from the sidebar.
  </Step>
  <Step title="Enable the toggle">
    Turn on **"Enable Auto-Invoicing"**.
  </Step>
  <Step title="Choose execution time">
    Select a time between **10 PM and midnight**. 10 PM is recommended to leave time to address any errors before midnight.
  </Step>
  <Step title="Save">
    Click **Save**. Auto-invoicing activates starting from the next scheduled execution.
  </Step>
</Steps>

## Eligibility criteria

During auto-invoicing, only checkouts that meet **all** of the following are processed:

| Criteria | Required state |
|----------|---------------|
| Checkout status | `READY` |
| Paused | Not paused |
| Property | Enabled (On) |
| Booking | Not cancelled |
| Account | Active subscription or sufficient credits |

## What is NOT auto-invoiced

- Checkouts in `NEEDS_SETUP`, `SENT`, `SENT_WITH_ERRORS`, `ERROR`, `SPLIT`
- Manually paused checkouts
- Checkouts with `##sync-skip` in Hosthub notes
- Checkouts belonging to disabled (Off) properties
- Cancelled bookings

## Execution results

After each auto-invoicing run, you can see:
- How many checkouts were successfully invoiced
- How many failed and which ones
- Total credit consumption (if applicable)

<Note>
If no `READY` checkouts exist at execution time, auto-invoicing completes without doing anything — no error is generated.
</Note>

## Combining with manual sends

Auto-invoicing and manual sends **work seamlessly together**:

- Checkouts you've already sent manually won't be re-sent
- You can send manually at any time, independently of the auto-invoicing schedule
- Disabling the toggle only stops the automated runs — manual sending remains available

## Changing the execution time

Change the time at any point from Settings → **Auto-Invoicing**. The change takes effect from the next execution.
