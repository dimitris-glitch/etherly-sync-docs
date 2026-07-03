---
title: 'Cleaning Staff'
description: 'Manage your cleaners, assign them to properties, and track which properties are ready.'
---

## What it is

Cleaning Staff is part of the **Online Check-In** feature. It lets the host manage cleaners, assign them to properties, and track which properties are clean and ready for the next guest. Cleaners don't need an account on the main application — they log into a separate, mobile-friendly dashboard.

---

## Activation

The feature activates automatically as soon as you add the **first cleaner** — no extra setup needed.

---

## Adding a cleaner

<Steps>
  <Step title="Go to Online Check-In">
    **Settings → Online Check-In → "Cleaning Team Management" sub-tab**
  </Step>
  <Step title="Add the cleaner">
    Click **"Add Cleaner"** and fill in **name** and **phone number**. The phone number must be unique within your account.
  </Step>
  <Step title="Assign properties">
    Select which properties this cleaner will clean from the property list. Saving fully replaces the previous assignment — it does not add to the existing one.
  </Step>
  <Step title="Send the dashboard link">
    Click the SMS icon next to the cleaner to send them their personal dashboard link. Sending is always manual — it is never sent automatically.
  </Step>
</Steps>

---

## How a cleaner logs in

Cleaners don't create an account — they verify their phone number each time:

```
https://app.etherly.app/{tenantId}/cleaning
```

1. They enter their phone number.
2. They receive an SMS with a **one-time code (OTP)**.
3. They verify the code and get access.

<Note>
Login is via SMS verification code only — not a magic link. The session lasts **150 days** and automatically refreshes on every use, so a cleaner who logs in regularly is effectively never logged out. A session left idle expires 150 days after its last use.
</Note>

---

## What the cleaner sees

On their dashboard, the cleaner sees their cleaning tasks:

- **Automatic tasks** — derived from booking checkouts on the properties assigned to them
- **Manual tasks** — any the host has scheduled (see below)

For each task they see: property name, date, arrival/departure time, guest count, number of nights, and any task notes. They can mark a property as **"Ready"** or undo their own mark.

<Warning>
Cleaners **never see** guest details — name, phone number, or identification number. They only see information relevant to the property and the cleaning task.
</Warning>

---

## Manual cleaning tasks

Beyond the automatic tasks generated from checkouts, the host can schedule additional cleaning tasks for a property on a specific date. A manual task can be:

- assigned to a **specific** cleaner, or
- left unassigned — in which case it's visible to **all** cleaners assigned to that property.

---

## Revoking access

The host can deactivate a cleaner at any time. Access is revoked **immediately** — even if the cleaner's session hasn't expired, they will no longer be able to log in or use an existing session.

---

## Action history

Every cleaning action — marking a property "Ready" by the cleaner, undoing it, or a manual mark/reset by the host — is logged along with who performed it and when.

---

## Security & privacy

- Cleaner login works exclusively with a **one-time code via SMS** (OTP).
- Every cleaner action (e.g. marking a property ready) re-validates that the property is actually assigned to them.
- Cleaners are notified via the SMS containing their dashboard link — the host sends it whenever they choose.
