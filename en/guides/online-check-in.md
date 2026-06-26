---
title: 'Online Check-In'
description: 'Let guests complete their check-in online before arrival.'
---

## What is Online Check-In

Online Check-In lets guests submit their details before they arrive at the property. You receive an automatic email notification as soon as a guest submits, and all data is available in the dashboard.

---

## Enabling the feature

Online Check-In is enabled per account by an administrator. Once active, a modal appears with the check-in URL you need to share with guests, along with a **Check-In Settings** tab in Settings and an **Online Check-Ins** entry in the sidebar.

---

## Check-In Link

The check-in link follows this format:

```
https://app.etherly.app/{tenantId}/checkin/{booking_id}
```

Replace `{booking_id}` with the **external booking ID** (e.g. the ID provided by Airbnb or your booking platform). The link is also available to copy from the **Check-In Settings** tab and from the bookings list in the dashboard.

<Note>
The check-in link requires no login. It is public but rate-limited, and only valid until 23:00 on the check-in day.
</Note>

---

## Access window

The form is accessible from any point in the future up to **23:00 on the check-in date**. There is no minimum lead time — guests can complete their check-in at any time before arrival.

Outside the window, or if the check-in has already been submitted, guests see an appropriate message.

---

## Per-property settings

Go to **Settings → Check-In Settings** to configure each property individually.

### Basic options

| Setting | Description |
|---|---|
| **Check-in from** | Earliest arrival time shown to the guest |
| **Check-in until** | Latest arrival time shown to the guest |
| **Check-out from / until** | Check-out times shown as informational text to the guest |
| **Require additional guests** | When on, guests are prompted to provide names of accompanying guests |

### Request options

Define up to 20 request options that guests can select (e.g. "Baby Cot", "Parking Information"). Each request is automatically AI-translated into 6 languages so guests see it in their own language. If the list is empty, the app defaults are used.

### Form preview

Click the **Preview** icon next to any property to see how the check-in form looks from the guest's perspective.

### Copy settings between properties

Use the **Copy** icon on any property and **Paste** on another to replicate settings quickly. The **Paste to all** button applies the copied settings to every property at once.

---

## Language support

The guest form supports **6 languages**:

| Language | Auto-detected |
|---|---|
| English | Default fallback |
| Greek (Ελληνικά) | ✓ |
| German (Deutsch) | ✓ |
| French (Français) | ✓ |
| Dutch (Nederlands) | ✓ |
| Italian (Italiano) | ✓ |

The form automatically detects the guest's browser language. A language toggle is always visible in the header so guests can switch at any time.

---

## Guest form steps

Guests follow a step-by-step wizard:

1. **Welcome** — Booking summary (property, dates, nights)
2. **Guest details** — Phone number, country, identification type (Tax ID / Passport / National ID) and number
3. **Additional guests** *(if enabled)* — Names of accompanying guests
4. **Arrival time** — Select an arrival time and optionally a departure time using a scroll wheel picker
5. **Requests & Submit** — Choose from your configured list, add free-text notes, and accept the privacy policy

<Note>
The form automatically saves the guest's progress on their device. If a guest closes the page and returns, the form resumes from where they left off.
</Note>

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
| **Completed** | Bookings with a submitted check-in |
| **Pending** | Bookings where the check-in window is open but not yet submitted |
| **Upcoming** | Today's and future bookings (submitted or pending) |
| **All** | All bookings with no date filter |

### Booking detail

Click **View** to see the full submission: phone, country, identification type and number (decrypted), arrival time, additional guests, requests, and notes.

### Sidebar badge

The sidebar shows a badge with the number of submissions in the last **48 hours**.

---

## Email notifications

### Host notification

As soon as a guest submits the form, an email is automatically sent to **all active users** on the account with:
- Guest name and property
- Check-in date and arrival time
- Requests and notes
- A link to the dashboard

Each user can opt out of these notifications in their notification preferences.

### Guest reminder email

For bookings where check-in is still pending, you can send a **manual reminder** to the guest with a link to the check-in form. This option is available from the booking detail view in the dashboard.

<Note>
The reminder requires a guest email to be on file for the booking, and can only be sent once per hour.
</Note>
