---
title: "Airbnb Import (CSV)"
description: "How to import Airbnb bookings via CSV for users without a Hosthub connection."
---

# Airbnb Import (CSV)

If you manage properties on **Airbnb** without a Hosthub connection, you can import payment data directly from the CSV file that Airbnb provides.

<Note>
This feature is for users **without** Hosthub. If you use Hosthub, the automatic sync is more reliable and requires no manual steps.
</Note>

## What you need

- An Airbnb account with active listings
- Access to Airbnb Transactions / Earnings
- At least one property configured in Etherly Sync

---

## Step 1: Export CSV from Airbnb

<Steps>
  <Step title="Go to Transactions">
    Log in to Airbnb → **Transactions** (or Earnings, depending on your region).
  </Step>
  <Step title="Select a date range">
    Set the date range you want to import. A 1–3 month window is recommended for easier review.
  </Step>
  <Step title="Download the CSV">
    Click **Export as CSV** and save the file locally.
  </Step>
</Steps>

---

## Step 2: Import into Etherly Sync

<Steps>
  <Step title="Open Import">
    Dashboard → **Import** → **Airbnb CSV**
  </Step>
  <Step title="Upload the file">
    Drag the CSV file into the upload area or click **Choose File**.
  </Step>
  <Step title="Dry Run — Preview changes">
    The system automatically runs a **dry run**: it shows what would happen without making any changes:
    - New bookings that would be added
    - Bookings that would be cancelled (absent from the CSV within the date range)
    - New properties that would be automatically created from listing names
  </Step>
  <Step title="Review the results">
    Read the preview carefully. Make sure the changes reflect what you expect.
  </Step>
  <Step title="Apply">
    If everything looks correct, click **Apply** for the final import.
  </Step>
</Steps>

<Warning>
**Always** review the dry run results before clicking Apply. Cancellations created by the import are **not automatically reversed**.
</Warning>

---

## Automatic property creation

If the CSV contains listing names that don't exist yet in Etherly Sync, new properties are created automatically. These properties:

- Appear in the Properties list
- Need configuration (Contact, Sequence, Fee Category, Organization) before they can be invoiced
- Start with their checkouts in `NEEDS_SETUP` status

---

## Reconciliation

During import, the system **automatically cancels** bookings that:

- Fall within the CSV's date range
- Are not present in the file (therefore likely cancelled in Airbnb)

This ensures your data stays in sync with Airbnb.

---

## Import FAQ

**Can I import the same file twice?**  
Yes. The system detects duplicates by booking ID and doesn't re-import them.

**What happens if the import fails?**  
If any step fails, nothing is saved — imports are **all-or-nothing**. Review the error message and try again.

**Can I import a CSV with multiple listings at once?**  
Yes, Airbnb's CSV includes all your listings. The import processes them all together.
