---
title: "User Management"
description: "Add users, set roles, and control who has access to what in your Etherly Sync account."
---

# User Management

Etherly Sync supports **multiple users** per account. Each user has a role that defines exactly what they can do. Find it in the **user dropdown menu** (click the user icon at the top right → **"Users"**).

## Roles and permissions

| Role | Invoicing | Settings | Users | Billing | Report Date |
|------|-----------|----------|-------|---------|-------------|
| **Owner** | ✅ Full | ✅ Full | ✅ Full | ✅ Full | ✅ |
| **Admin** | ✅ Full | ✅ Full | ❌ | ❌ | ✅ |
| **User** | 👁️ Read-only | ❌ | ❌ | ❌ | ❌ |

**Owner**: Full control — can delete the account, manage billing, and manage users.

**Admin**: Can send invoices, change property settings, and run syncs — but cannot see billing or manage users.

**User**: Can view bookings and statuses, but cannot make any changes.

## Inviting a new user

<Steps>
  <Step title="Go to Users">
    Click the user icon at the top right → **"Users"** → click **"Invite User"**
  </Step>
  <Step title="Enter email, name and role">
    Enter the new user's **Email** and **Name**, and select a **Role** (Admin or User).
  </Step>
  <Step title="Send the invitation">
    Click **"Send Invite"**. The user receives an email with an acceptance link that expires in **7 days**.
  </Step>
  <Step title="Accepting the invitation">
    The user clicks the link, creates an account (or signs in if they already have one), and gains access automatically.
  </Step>
</Steps>

<Note>
If an invitation expires, you can copy the invite link with **"Copy link"** or revoke it with **"Revoke invite"** and send a new one.
</Note>

## Removing a user

1. Click the user icon at the top right → **"Users"**
2. Click **"Remove user"** next to the user
3. Confirm

Access is removed **immediately**.

<Warning>
Only the **Owner** can remove users. If the Owner wants to leave, they must first transfer the Owner role to another user — otherwise the account is left without an Owner.
</Warning>

## Activity history

Every action (invites, role changes, removals) is recorded with the user who performed it, giving you a full audit trail of who did what and when.
