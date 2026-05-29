---
title: "Team Management"
description: "Add team members, set roles, and control who has access to what in your Etherly Sync account."
---

# Team Management

Etherly Sync supports **multiple users** per account. Each member has a role that defines exactly what they can do.

## Roles and permissions

| Role | Invoicing | Settings | Members | Billing |
|------|-----------|----------|---------|---------|
| **Owner** | ✅ Full | ✅ Full | ✅ Full | ✅ Full |
| **Admin** | ✅ Full | ✅ Full | ❌ | ❌ |
| **Member** | 👁️ Read-only | ❌ | ❌ | ❌ |

**Owner**: Full control — can delete the account, manage billing, and manage team members.

**Admin**: Can send invoices, change property settings, and run syncs — but cannot see billing or manage team members.

**Member**: Can view checkouts and statuses, but cannot make any changes.

## Inviting a new member

<Steps>
  <Step title="Go to Team">
    Settings → **Team Members** → click **Invite Member**
  </Step>
  <Step title="Enter email and role">
    Enter the new member's email and select a role (Admin or Member).
  </Step>
  <Step title="Send the invitation">
    Click **Send Invite**. The user receives an email with an acceptance link that expires in **7 days**.
  </Step>
  <Step title="Accepting the invitation">
    The user clicks the link, creates an account (or signs in if they already have one), and gains access automatically.
  </Step>
</Steps>

<Note>
If an invitation expires, resend a new one from the Team panel — there's no need to remove the member first.
</Note>

## Changing a member's role

1. Settings → **Team Members**
2. Click **Edit** next to the member
3. Select the new role → **Save**

Role changes take effect immediately.

## Removing a member

1. Settings → **Team Members**
2. Click **Remove** next to the member
3. Confirm

Access is removed **immediately** — the user can no longer sign in to the account.

<Warning>
Only the **Owner** can remove members or change roles. If the Owner wants to leave, they must first transfer the Owner role to another member — otherwise the account is left without an Owner.
</Warning>

## Activity history

Every checkout pause/resume action is recorded with the user who performed it, giving you a full audit trail of who did what and when.
