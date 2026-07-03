---
title: 'Online Check-In'
description: 'Let guests complete their check-in online before arrival.'
---

## What is Online Check-In

Online Check-In lets guests submit their details before they arrive at the property. You receive an automatic email notification as soon as a guest submits, and all data is available in the dashboard.

---

## Enabling the feature

Online Check-In is enabled from **Settings → Integrations**, in the **Apps** section — click **Enable** on the **Online Check-In** card, the same way you would connect Hosthub, Airbnb, or Elorus. It is not a toggle inside a settings tab; the **Check-In Settings** tab itself only appears after the feature is enabled. Once active, a modal appears with the check-in URL you need to share with guests, along with the **Check-In Settings** tab in Settings and an **Online Check-Ins** entry in the sidebar.

<Note>
The **Check-In Settings** tab has its own "Notify host when guest completes check-in" toggle under General Settings. That toggle only controls email notifications — it does not enable or disable the feature itself.
</Note>

---

## Check-In Link

Copy the check-in link from **Settings → Online Check-In** (or from the bookings list in the dashboard). The link ends in `{booking_id}` — the only part that changes per booking: replace it with the **external booking ID** (the ID provided by Airbnb, Booking.com, or your booking platform).

<Note>
The check-in link requires no login — guests open it directly. It is valid until 23:00 on the check-in day.
</Note>

### Automatic delivery via your booking platform (recommended)

The most practical way to get the link to every guest is a **scheduled message (template)** in your booking platform (Airbnb, Booking.com, etc.):

<Steps>
  <Step title="Create a message template">
    In your booking platform, create a scheduled message that is sent automatically **2–3 days before arrival**, inviting the guest to complete their online check-in via the link.
  </Step>
  <Step title="Use the platform's dynamic booking variable">
    Platforms support **dynamic variables** in templates (e.g. confirmation/booking code). Put the platform's booking variable in place of `{booking_id}` — this way every guest receives their own link and Etherly automatically knows which booking the check-in belongs to.
  </Step>
  <Step title="Test with a real booking">
    Send the message on a test or real booking and open the link — the check-in form should load with that booking's details.
  </Step>
</Steps>

---

## Access window

The form is accessible from any point in the future up to **23:00 on the check-in date** — guests can complete their check-in at any time before arrival, even right after booking.

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

Define up to 20 request options that guests can select (e.g. "Baby Cot", "Parking Information"). Each request is automatically translated into 6 languages so guests see it in their own language.

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

- The identification number (Tax ID / Passport / National ID) is stored **encrypted**.
- On the public form, the guest's name and phone are shown **partially masked** (e.g. `Di****is K*****is`).

---

## Dashboard: Online Check-Ins

Navigate to **Online Check-Ins** in the sidebar to view all submissions.

### Filters

| Filter | Description |
|---|---|
| **Today** | Arrivals and departures for the selected day. Use the navigation arrows or the calendar next to the title to view any other day, not just today. |
| **Pending** | Bookings where the guest hasn't started the check-in form yet |
| **In Progress** | Bookings where the guest has started the form but hasn't submitted it yet |
| **Completed** | Bookings with a submitted check-in |
| **Upcoming** | Bookings with an arrival date from today onward, regardless of check-in status |

<Note>
The **Today** tab gives the full picture for a given day, while the other tabs filter by status or date.
</Note>

### Search

Above the list there's a search field that matches on **guest name, booking code, and property name**. Search works on the status tabs; typing while on the **Today** tab automatically switches the view to **Pending**, where the search is applied.

### Cleaning status

Each booking row shows a ✨ indicator with a timestamp if the property has already been marked clean, with a tooltip showing who marked it. The detail view for a booking (**View**) has a separate **Cleaning** section with the current status, who marked it and when, and the full action history. See the [Cleaning Staff guide](/en/guides/cleaning-staff) for details.

### Booking detail

Click **View** to see the full submission: phone, country, identification type and number (decrypted), arrival time, additional guests, requests, notes, and cleaning status.

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
