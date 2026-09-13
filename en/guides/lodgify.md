---
title: "Connect Lodgify"
description: "Connect your Lodgify account and bring in the bookings from your website, your booking engine and your channels."
---

# Connect Lodgify

If you use **Lodgify** for your website and your bookings, you can connect your account to DeskBoy. Bookings from your **website**, your **booking engine** and the **channels** you have connected there — Airbnb, Booking.com and others — arrive automatically, along with their amounts and dates.

## 1. Get the API key from Lodgify

<Steps>
  <Step title="Open settings">
    Sign in to Lodgify and open the menu at the top right → **Settings**.
  </Step>
  <Step title="Open Public API">
    In the settings menu choose **"Public API"**. Your key is already there.
  </Step>
  <Step title="Copy the key">
    Use the copy button beside the key.
  </Step>
</Steps>

## 2. Connect the account to DeskBoy

<Steps>
  <Step title="Open the Lodgify card">
    Under **Settings → Integrations**, find the **Lodgify** card and click **Connect**.
  </Step>
  <Step title="Paste the key">
    Fill in the **"API key"** field and continue. DeskBoy checks the key with Lodgify before storing it — encrypted.
  </Step>
  <Step title="The first sync starts">
    Once the key is confirmed, the first sync starts automatically. Your properties and bookings appear as soon as it finishes.
  </Step>
</Steps>

<Note>
Lodgify properties are added as a **separate set**, alongside the ones you already have. Each set keeps its own **Climate Resilience Fee** characteristics and its own invoicing settings — you set those once under **Properties**.
</Note>

## 3. Turn on instant updates

With instant updates, changes to your bookings reach DeskBoy right away. Sync also works without them, on a schedule — just more slowly.

<Steps>
  <Step title="Open the setting">
    On the connection row click **"Set up instant updates"** — or **Configure** and then the **"Instant updates"** section.
  </Step>
  <Step title="Click 'Turn on instant updates'">
    DeskBoy registers update entries in your Lodgify account — one per kind of change. They are the only entries it creates there, and they are removed when you turn them off.
  </Step>
  <Step title="Confirm">
    The badge changes to **"On"**, and as soon as the first update arrives the time of the last one appears.
  </Step>
</Steps>

<Tip>
If updates stop arriving, **"Re-register"** creates new entries in Lodgify in place of the previous ones.
</Tip>

## What "booking in manual review" means

If a booking carries an **extra charge** — cleaning, tourist tax, the Climate Resilience Fee — it is recorded under **Bookings** marked **"Needs action"** and is **not invoiced automatically**.

The reason is that Lodgify does not state the **VAT rate per charge**, and the correct rate differs: cleaning is not taxed the same way as tourist tax, and the Climate Resilience Fee is issued on its own document. Without that, an automatic document would go out in your name with the wrong VAT — so the app stops and shows it to you.

The marker clears on its own once the booking no longer carries the charge.

<Tip>
Bookings with **no** extra charge are invoiced as usual and do not pass through here.
</Tip>

## Managing the connection

From the **Lodgify → Configure** card you can see the connected account, the last sync and the properties that came from this connection.

### Replacing the key

If you get a new key from Lodgify, click **Replace key** and paste it in. For the properties and bookings you already have to stay connected, the new key must belong to the **same** Lodgify account. For a different account, create a new connection.

### "New key needed"

If you see this badge, Lodgify no longer accepts this key and syncing has stopped. Get the key again from Lodgify (**Settings → Public API**) and paste it here — your bookings and documents stay as they are.

### If Lodgify does not respond

If you see a message that we could not reach Lodgify, try again shortly — your key does not need changing.

<Note>
Lodgify already brings in the Airbnb bookings of its properties. Keep one source per property, so that each booking is invoiced once. If two connections declare the same property (same registry number, ΑΜΑ), DeskBoy notifies you on the Dashboard — turn the property off in one of the two.
</Note>
