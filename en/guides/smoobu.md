---
title: "Smoobu connection"
description: "Connect your Smoobu account and bring in bookings from every channel you have there — Airbnb, Booking.com, Vrbo and direct."
---

# Smoobu connection

If you use **Smoobu** as your management system, you can connect your account to DeskBoy. Bookings from **every channel** you have there — Airbnb, Booking.com, Vrbo and direct — arrive automatically, along with their amounts, dates and cancellations.

## 1. Create a Key and Secret in Smoobu

Smoobu gives you **two** details: a **Key** and a **Secret**. You need both.

<Steps>
  <Step title="Open Advanced → API Keys">
    Sign in to Smoobu and open **Advanced → API Keys** from the left-hand menu.
  </Step>
  <Step title="Create the key">
    Under **"Private API keys"**, choose **"Create New"** and give it a name in the **Label** field (e.g. `DeskBoy`) so it stands out from other tools you use.
  </Step>
  <Step title="Keep the Secret">
    Smoobu then shows the **Key** and the **Secret** — the Secret only at that moment.
  </Step>
  <Step title="Copy both">
    Copy the **Key** and the **Secret**.
  </Step>
</Steps>

<Warning>
Smoobu shows the **Secret once**, at the moment you create it. If you lose it, create a new one from the same screen.
</Warning>

<Note>
Smoobu also has an older **Profile → API Key** page. What you need here are the details from **Advanced → API Keys**, because only those come with a Secret.
</Note>

## 2. Connect the account in DeskBoy

<Steps>
  <Step title="Open the Smoobu card">
    Under **Settings → Integrations**, find the **Smoobu** card and click **Connect**.
  </Step>
  <Step title="Paste the Key and the Secret">
    Fill in the **"Key"** and **"Secret"** fields and continue. DeskBoy checks the details with Smoobu before storing them — encrypted.
  </Step>
  <Step title="The first sync starts">
    Once the details are confirmed, the first sync starts automatically. Your properties and bookings appear as soon as it finishes.
  </Step>
</Steps>

<Note>
Smoobu properties are added as a **separate set**, alongside the ones you already have. Each set keeps its own **Climate Resilience Fee (ΤΑΚΚ)** characteristics and its own invoicing settings — you set those once under **Properties**.

Bookings that already arrive from another connection are **invoiced once**.
</Note>

## 3. Turn on instant updates

With instant updates, changes to your bookings reach DeskBoy right away. Sync also works without them, on a schedule — just more slowly.

<Steps>
  <Step title="Open the setting">
    On the connection row click **"Set up instant updates"** — or **Configure** and then the **"Instant updates"** section.
  </Step>
  <Step title="Click 'Turn on instant updates'">
    DeskBoy registers an updates entry in your Smoobu account. It is the only entry it creates there, and it is removed when you turn them off.
  </Step>
  <Step title="Confirm">
    The badge changes to **"On"**, and as soon as the first update arrives the time of the last one appears.
  </Step>
</Steps>

<Tip>
If updates stop arriving, **"Re-register"** creates a new entry in Smoobu in place of the previous one.
</Tip>

## What "booking needs review" means

If a booking has an **extra charge** the app doesn't recognise yet, the booking appears under **Bookings** marked as **needing action**, waiting for you to confirm it.

This is deliberate: every channel names its charges differently, and the amount that gets declared has to be the amount actually received. That way a charge such as a city tax never ends up on the wrong document. You review the booking, confirm the amounts, and the document proceeds as normal.

## Managing the connection

From the **Smoobu → Configure** card you can see the connected account, the last sync and the properties that came from this connection.

### Replacing the keys

If you create a new pair in Smoobu, click **Replace keys** and paste **both** fields together — the Secret is never shown again. The new pair must belong to the **same** Smoobu account, so the properties and bookings you already have stay connected. For another account, create a new connection.

### "New keys needed"

If you see this badge, Smoobu no longer accepts these keys and syncing has stopped. Create a new Key and Secret in Smoobu (**Advanced → API Keys**) and paste them here — your bookings and documents stay as they are.

### If Smoobu doesn't respond

If you see a message saying we couldn't reach Smoobu, try again shortly — your keys don't need changing.

<Note>
Each Smoobu account connects once, so every booking is invoiced once.
</Note>
