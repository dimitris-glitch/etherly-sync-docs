---
title: "Connect Hostaway"
description: "Connect your Hostaway account and bring in bookings from every channel you have there — Airbnb, Booking.com, Vrbo and direct."
---

# Connect Hostaway

If you use **Hostaway** as your property management system, you can connect your account to DeskBoy. Bookings from **every channel** you have there — Airbnb, Booking.com, Vrbo and direct — arrive automatically, along with their dates and cancellations.

## 1. Get the Account ID and API key from Hostaway

Hostaway gives you **two** details: your account's **Account ID** and an **API key**. You need both.

<Steps>
  <Step title="Open Settings → Hostaway API">
    Sign in to Hostaway and open **Settings → Hostaway API**.
  </Step>
  <Step title="Create the key">
    Choose **Create** and give it a name (e.g. `DeskBoy`) so you can tell it apart from other tools you use.
  </Step>
  <Step title="Copy the API key">
    Hostaway then shows the **API key**. Copy it.
  </Step>
  <Step title="Find the Account ID">
    You'll find the **Account ID** under **Settings → Account Details**. It is digits only.
  </Step>
</Steps>

<Warning>
Hostaway shows the **API key once**, at the moment you create it. If you lose it, create a new one from the same screen.
</Warning>

## 2. Connect the account to DeskBoy

<Steps>
  <Step title="Open the Hostaway card">
    Under **Settings → Integrations**, find the **Hostaway** card and click **Connect**.
  </Step>
  <Step title="Paste the Account ID and API key">
    Fill in the **"Account ID"** and **"API key"** fields and click **Connect**. DeskBoy checks the details with Hostaway before storing them — encrypted.
  </Step>
  <Step title="The first sync starts">
    Once the details are confirmed, the first sync starts automatically. If you're told it will start at the next scheduled check, you can also start it now from the Dashboard. Your properties and bookings appear as soon as it finishes.
  </Step>
</Steps>

<Note>
Hostaway properties are added as a **separate set**, alongside the ones you already have. Each set keeps its own **Climate Resilience Fee** categories and invoicing settings — you set them once under **Properties**.

If the same properties are already connected through another connection, keep one source per property, so that each booking is invoiced once.
</Note>

## 3. Turn on instant updates

With instant updates, changes to your bookings reach DeskBoy right away. Sync also works without them, on a schedule — just more slowly.

<Steps>
  <Step title="Open the setting">
    On the connection row click **"Set up instant updates"** — or **Configure** and then the **"Instant updates"** section.
  </Step>
  <Step title="Click 'Turn on instant updates'">
    DeskBoy registers an updates entry in your Hostaway account. It is the only entry it makes there, and it is removed when you turn them off.
  </Step>
  <Step title="Confirm">
    The badge changes to **"On"**, and as soon as the first update arrives the time of the last one appears.
  </Step>
</Steps>

<Tip>
If the **"Instant updates"** section under **Configure** shows **"Paused in Hostaway"**, Hostaway has stopped sending updates. This happens when Hostaway can't deliver them for a while, or when they're turned off there. Click **"Turn on again"** — meanwhile, changes arrive with the scheduled checks.
</Tip>

## What "booking in manual review" means

If a booking has a **charge the app doesn't recognise yet**, or details it can't process safely, it is recorded under **Bookings** marked **"Manual review"** and **isn't invoiced until that's resolved**, so no incorrect document goes out in your name.

A notice on the home page says what happened and what's needed — correcting the booking in Hostaway, or contacting support. Its button shows you all bookings in manual review.

## Managing the connection

From the **Hostaway → Configure** card you can see the Account ID, the last sync and the properties that came from this connection.

### Replacing the API key

If you create a new API key in Hostaway, click **Replace API key** and paste it in. The Account ID stays the same, so the new key must belong to the **same** Hostaway account — that way the properties and bookings you already have stay connected.

### If Hostaway doesn't recognise the details

Check that you copied the Account ID and the API key in full, and that both come from the **same** Hostaway account. If you no longer have the API key, create a new one — Hostaway shows it once.

### "New API key needed"

If you see this badge, Hostaway no longer accepts this connection's Account ID and API key, so syncing has stopped. Create a new API key in Hostaway (**Settings → Hostaway API**) and paste it here — your bookings and documents stay exactly as they are.

### If Hostaway doesn't respond

If you see a message that we couldn't reach Hostaway, try again shortly — your details don't need changing.

<Note>
Each Hostaway account connects once, so every booking is invoiced once. Each workspace has one Hostaway connection; for another account, delete the existing one first, so bookings from the two accounts don't get mixed up.
</Note>
