---
title: 'Online Check-In'
description: 'Let guests complete their check-in online before arrival.'
---

## What is Online Check-In

Online Check-In lets guests submit their details before they arrive at the property. You receive an automatic email notification as soon as a guest submits, and all data is available in the dashboard.

---

## Enabling the feature

Online Check-In is enabled per tenant by an administrator. Once active, a **Check-In Settings** tab appears in Settings and an **Online Check-Ins** entry appears in the sidebar.

---

## Per-property settings

Go to **Settings → Check-In Settings** to configure each property individually.

### Basic options

| Setting | Description |
|---|---|
| **Enable** | Turns online check-in on or off for the property |
| **Hours before** | How many hours before the check-in date the form becomes available (1–720, default: 24) |
| **Check-in from** | Earliest arrival time shown to the guest |
| **Check-in until** | Latest arrival time shown to the guest |
| **Require additional guests** | When on, guests are prompted to provide names of accompanying guests |

### Request options

Define up to 20 request options that guests can select (e.g. "Baby Cot", "Parking Information"). If the list is empty, the app defaults are used.

### Copy settings between properties

Use the **Copy** icon on any property and **Paste** on another to replicate settings quickly. The **Paste to all** button applies the copied settings to every property at once.

---

## How guests receive the check-in link

The check-in link follows this format:

```
https://app.etherly.app/checkin/{channel}/{bookingId}
```

`channel` matches the booking source (e.g. `airbnb`, `booking`, `direct`) and `bookingId` is the unique booking ID in the system.

<Note>
The check-in link requires no login. It is public but rate-limited, and only valid within the configured time window.
</Note>

---

## Access window

The form is accessible:
- **Opens:** `hoursBefore` hours before the check-in date
- **Closes:** end of the check-in day (23:59:59)

Outside the window, or if the check-in has already been submitted, guests see an appropriate message.

---

## Language support

The guest form automatically detects the guest's browser language and displays in **Greek** if the browser is set to Greek, or **English** otherwise. A language toggle button is always visible in the header so guests can switch at any time.

---

## Guest form steps

Guests follow a step-by-step wizard:

1. **Welcome** — Booking summary (property, dates, nights)
2. **Guest details** — Phone number, country, identification type (Tax ID / Passport / National ID) and number
3. **Additional guests** *(if enabled)* — Names of accompanying guests
4. **Arrival time** — Select an arrival time and optionally a departure time
5. **Requests** — Choose from your configured list and add free-text notes
6. **Review & Submit** — Confirm details and accept the privacy policy

---

## Security & privacy

- The identification number (Tax ID / Passport / National ID) is **encrypted** with AES-256-GCM before being stored in the database.
- On the public form, the guest's name and phone are shown **partially masked** (e.g. `Di****is K*****is`).
- Rate limiting: 20 GET/min per IP, 5 POST/10 min per IP, 3 POST/hour per booking.

---

## Dashboard: Online Check-Ins

Navigate to **Online Check-Ins** in the sidebar to view all submissions.

### Filters

| Filter | Description |
|---|---|
| **Submitted** | Bookings with a completed check-in submission |
| **Pending** | Bookings where the check-in window is open but not yet submitted |
| **All** | All bookings for properties with online check-in enabled |

### Booking detail

Click **View** to see the full submission: phone, country, identification type and number (decrypted), arrival time, additional guests, requests, and notes.

### Sidebar badge

The sidebar shows a badge with the number of submissions in the last **48 hours**.

---

## Email notifications

As soon as a guest submits the form, an email is automatically sent to **all active users** on the account with:
- Guest name and property
- Check-in date and arrival time
- Requests and notes
- A link to the dashboard
