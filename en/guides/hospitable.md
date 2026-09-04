---
title: "Hospitable connection"
description: "Connect your Hospitable account and bring in bookings from every channel you have there — Airbnb, Booking.com, Vrbo and direct."
---

# Hospitable connection

If you use **Hospitable** as your management system, you can connect your account to DeskBoy. Bookings from **every channel** you have there — Airbnb, Booking.com, Vrbo and direct — arrive automatically, along with their amounts, dates and cancellations.

<Note>
The **Hospitable** card is for hosts who already use Hospitable as their management system. If you work with Airbnb only, the **Airbnb Live** card brings your bookings straight from Airbnb.
</Note>

## 1. Issue an API key in Hospitable

<Steps>
  <Step title="Open Settings → Integrations">
    Sign in to Hospitable and open **Settings** (gear) → **"Integrations"**.
  </Step>
  <Step title="Create a new key">
    Under **"Tools"**, choose **"API access"** and then **"Add new"**.
  </Step>
  <Step title="Name it and allow access">
    Give it a name (e.g. `DeskBoy`) and allow access to **properties** and **reservations**.
  </Step>
  <Step title="Copy the key">
    Copy the key that appears. Hospitable shows it **once**.
  </Step>
</Steps>

## 2. Connect the account in DeskBoy

<Steps>
  <Step title="Open the Hospitable card">
    Under **Settings → Integrations**, find the **Hospitable** card and click **Connect**.
  </Step>
  <Step title="Paste the key">
    Paste the key into the **"API key (Personal Access Token)"** field and continue. DeskBoy checks the key with Hospitable before storing it — encrypted.
  </Step>
  <Step title="The first sync starts">
    Once the key is confirmed, the first sync starts automatically. Your properties and bookings appear as soon as it finishes.
  </Step>
</Steps>

<Note>
Hospitable properties are added as a **separate set**, alongside the ones you already have. Each set keeps its own climate resilience fee (ΤΑΚΚ) categories and invoicing settings — you set those once under **Properties**.

Airbnb bookings that already arrive from another connection are **invoiced once**.
</Note>

## 3. Turn on instant updates

With instant updates, changes in Hospitable reach DeskBoy right away. Sync also works without them, on a schedule.

<Steps>
  <Step title="Issue the link">
    On the connection row click **"Set up instant updates"** — or **Configure** and then the **"Instant updates"** section. Click **Issue link** and copy it: it is shown **only then**.
  </Step>
  <Step title="Add it in Hospitable">
    In Hospitable, open **Settings → "Integrations" → "Webhooks"**, add a new webhook and paste the link.
  </Step>
  <Step title="Select the events">
    Select the **reservation**, **property** and **listing** events, then save.
  </Step>
  <Step title="Confirm">
    As soon as the first update arrives, the card shows **"On"** along with the time of the last update.
  </Step>
</Steps>

<Tip>
Need the link again? Click **Issue a new link** and add it in Hospitable. The previous link stops working.
</Tip>

## What "booking needs review" means

If a booking has a charge the app doesn't recognise yet, the booking appears under **Bookings** marked as **needing action**, waiting for you to confirm it.

This is deliberate: every channel names its charges differently, and the amount that gets declared has to be the amount actually received. You review the booking, confirm the amounts, and the document proceeds as normal.

## Managing the connection

From the **Hospitable → Configure** card you can see the connected account, the last sync and the properties that came from this connection.

### Replacing the key

If you issue a new key in Hospitable, click **Replace key** and paste it. The new key must belong to the **same** Hospitable account, so the properties and bookings you already have stay connected. For another account, create a new connection.

### "New key needed"

If you see this badge, Hospitable no longer accepts the key and syncing has stopped. Issue a new key in Hospitable and paste it here — your bookings and documents stay as they are.

<Note>
Each Hospitable account connects once, so every booking is invoiced once.
</Note>
