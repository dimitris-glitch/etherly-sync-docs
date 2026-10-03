---
title: "Connect Hostfully"
description: "Connect your Hostfully account and bring in bookings from your channels — Airbnb, Booking.com, Vrbo and direct."
---

# Connect Hostfully

If you use **Hostfully** as your property management system, you can connect your account to DeskBoy. DeskBoy brings in bookings from the channels you have there — Airbnb, Booking.com, Vrbo and direct.

## 1. Find the API key in Hostfully

To connect, you need just one detail: your Hostfully account's **API key**.

<Steps>
  <Step title="Open Agency Settings">
    Sign in to Hostfully and open the **Agency Settings** page.
  </Step>
  <Step title="Find the API Key field">
    Scroll down to the **API Key** field.
  </Step>
  <Step title="Copy the API key">
    Copy it in full.
  </Step>
</Steps>

<Note>
The API key is available on Hostfully subscriptions that include API access. If you don't see the **API Key** field, add API access to your Hostfully subscription.
</Note>

## 2. Connect the account to DeskBoy

<Steps>
  <Step title="Open the Hostfully card">
    Under **Settings → Integrations**, find the **Hostfully** card and click **Connect**.
  </Step>
  <Step title="Paste the API key">
    Fill in the **"API key"** field and click **Connect**. DeskBoy stores it encrypted.
  </Step>
  <Step title="We finish the connection">
    Our team checks the connection and finishes it within 24 hours; until then the connection shows **"Finalising"**, and we email you as soon as it's live. Every new connection goes through this check, so your bookings and amounts match your account from the very first document. Once it's live, the first sync starts, and your properties and bookings appear as soon as it finishes.
  </Step>
</Steps>

<Note>
If you connect Hostfully while activating your account, at the **"Connect your channel manager"** step choose **Hostfully**, paste the API key and click **Connect Hostfully**. Our team's check is the same, and you can carry on with setup in the meantime.
</Note>

<Note>
Hostfully properties are added as a **separate set**, alongside the ones you already have. Each set keeps its own **Climate Resilience Fee** categories and invoicing settings — you set them once under **Properties**.

If the same properties are already connected through another connection, keep one source per property, so that each booking is invoiced once.
</Note>

## Instant updates

When you connect, DeskBoy asks Hostfully for **instant updates** on your bookings, so changes arrive right away.

When they're on, the **"Instant updates"** section under the connection's **Configure** shows the **"On"** badge and the time of the last update. Syncing works without them too, on scheduled checks — just more slowly. If the section doesn't appear on a connection marked **"Connected"**, changes arrive with the scheduled checks.

## What "booking in manual review" means

If a booking has a **charge the app doesn't recognise yet**, or details it can't process safely, it is recorded under **Bookings** marked **"Manual review"** and **isn't invoiced until that's resolved**, so no incorrect document goes out in your name.

A notice on the home page says what happened and what's needed — correcting the booking in Hostfully, or contacting support. Its button shows you all bookings in manual review.

## Managing the connection

From the **Hostfully → Configure** card you can see the API key (partly masked), the last sync and how many properties came from this connection.

### Replacing the API key

To change the key, ask Hostfully for a new API key. Once you have it, under **Configure** click **Replace API key**, paste it in and click **Save API key**. The new key must belong to the **same** Hostfully account — that way the properties and bookings you already have stay connected.

### "This API key wasn’t accepted"

Check that you copied the API key in full from Hostfully's **Agency Settings**. If it still isn't accepted, ask Hostfully for a new one.

### "New API key needed"

If you see this badge on the connection, or a notice about it on the home page, Hostfully no longer accepts this connection's API key, so syncing has stopped. Get a new API key for the same Hostfully account, open **Configure** on the Hostfully card, paste it into the **"New API key"** field and click **Save API key** — your bookings and documents stay exactly as they are.

### If Hostfully doesn't respond

If you see a message that we couldn't reach Hostfully, or that it isn't accepting requests right now, try again later — if the message shows a time, after that time. You don't need a new API key for this.

### "Inactive"

If the connection shows **"Inactive"**, syncing has stopped. Contact us to reactivate this connection.

<Note>
Each Hostfully account connects once, so every booking is invoiced once. Each workspace has one Hostfully connection; for another account, delete the existing one first (**Configure → Delete**), so bookings from the two accounts don't get mixed up.
</Note>
