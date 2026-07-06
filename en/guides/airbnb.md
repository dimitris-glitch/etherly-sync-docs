---
title: "Airbnb Sync"
description: "Set up automatic Airbnb booking ingestion via email forwarding and iCal."
---

# Airbnb Sync

Etherly Sync receives Airbnb bookings automatically via two mechanisms:

- **Email sync** — You forward Airbnb emails to your Etherly address. Best for real-time amounts and booking details.
- **iCal sync** — Etherly periodically reads your property's Airbnb iCal link to confirm dates.

## Setting up Email Sync

### 1. Enable

Go to **Settings → Airbnb → Email Sync** and enable the **«Email Sync»** toggle for your connection. The app gives you a unique inbound address (e.g. `airbnb+xxxxx@app.etherly.app`).

### 2. Configure Gmail

<Steps>
  <Step title="Open Gmail Settings">
    In Gmail → **Settings (⚙)** → **See all settings** → **«Forwarding and POP/IMAP»** tab
  </Step>
  <Step title="Add a forwarding address">
    Click **«Add a forwarding address»** and enter the Etherly address shown in Settings.
  </Step>
  <Step title="Confirm forwarding">
    Gmail will send a confirmation email to Etherly. Etherly detects this email and shows a banner in Settings with a confirmation link. Click **«Confirm Gmail»** and follow the link.

    <Note>
    The confirmation link requires signing in with your Google account. Etherly cannot complete this step automatically.
    </Note>

    Once you've confirmed, click **«Done»** to close the banner. The **«Gmail forwarding confirmed»** badge will appear.
  </Step>
  <Step title="Create a filter">
    In Gmail → **Settings → Filters** → **«Create a new filter»**:
    - **From:** `automated@airbnb.com`
    - **Action:** Forward to the Etherly address
  </Step>
</Steps>

## Setting up iCal Sync

<Steps>
  <Step title="Copy the iCal link from Airbnb">
    In Airbnb → **Calendar** → **«Connect to other platforms»** → **«Export calendar»**. Copy the link.
  </Step>
  <Step title="Paste into Etherly">
    In **Settings → Properties**, find the property and paste the iCal link into the **«Airbnb iCal URL»** field. Enable the **«iCal Sync»** toggle.
  </Step>
</Steps>

<Note>
iCal sync runs every few hours and confirms check-in/check-out dates. Combining email + iCal gives the most complete picture of each booking.
</Note>
