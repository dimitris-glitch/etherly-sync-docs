---
title: "Airbnb Sync"
description: "Set up automatic Airbnb booking ingestion via a direct connection, email forwarding or iCal."
---

# Airbnb Sync

Etherly Sync receives Airbnb bookings automatically in the following ways:

- **Direct connection (Airbnb Live)** — Connect your Airbnb account once and bookings arrive automatically. The simplest option.
- **Email sync** — You forward Airbnb emails to your Etherly address. Best for real-time amounts and booking details.
- **iCal sync** — Etherly periodically reads your property's Airbnb iCal link to confirm dates.

## Direct Airbnb connection (Airbnb Live)

As an alternative to email forwarding, you can connect your Airbnb account directly. Bookings, amounts and cancellations arrive automatically — no browser extension and no forwarding setup.

It works even when your properties are already connected to another management system.

### How it works

1. **Start the connection** — In **Settings → Integrations**, on the **Airbnb Live** card, click **Connect**.
2. **Approve on Airbnb** — A new window opens. Sign in to Airbnb as usual and approve access to your properties and bookings. You enter your password directly with Airbnb — the app never sees it.
3. **Return** — The window closes on its own and the Settings page refreshes. Your properties appear automatically.

### Are you an Airbnb co-host?

If you are an Airbnb co-host, approval must come from the primary host's Airbnb account — they do not need an account with the app:

1. **Create a link** — In the **Airbnb Live** connection dialog, choose **"Is the property owned by someone else?"** and click **Create link**.
2. **Send it to the primary host** — Copy the link and send it any way you like. The link is shown only once and is valid for 14 days — if needed, create a new one (the previous link stops working).
3. **The primary host approves** — Opening the link, they see who is requesting access and continue to Airbnb to approve. Their password goes directly to Airbnb.
4. **Done** — Once they approve, the connection appears in **Settings → Integrations** and the properties come in automatically.

### Disconnecting

Deleting the connection from **Settings → Integrations** also revokes access to your Airbnb account.

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
