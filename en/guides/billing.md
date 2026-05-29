---
title: "Billing & Credits"
description: "Understand billing plans, how credits work, the free trial, auto-renew, and the grace period."
---

# Billing & Credits

Etherly Sync uses a **credit-based billing system** for flexible usage. Every checkout successfully sent consumes **1 credit** — regardless of how many documents are issued.

## Available plans

<CardGroup cols={2}>
  <Card title="Credits" icon="coins">
    Purchase a credit package. 1 credit = 1 checkout. Ideal for seasonal or low-volume usage.
  </Card>
  <Card title="Etherly Sync Subscription" icon="calendar">
    Monthly subscription with graduated pricing per property. No per-send fee.
  </Card>
  <Card title="Free Trial" icon="gift">
    30 days of unlimited invoicing at no cost for new accounts.
  </Card>
  <Card title="Grace Period" icon="clock">
    7 extra days of sends if credits run out — no interruption to your workflow.
  </Card>
</CardGroup>

## Free Trial

Every new account starts with **30 days free**:
- Unlimited sends
- No credit card required
- No commitment

After expiry, invoicing pauses until you purchase credits or activate a subscription.

## Buying credits

<Steps>
  <Step title="Go to Billing">
    Settings → **Billing** → **Buy Credits**
  </Step>
  <Step title="Choose a package">
    Select the package that matches your volume.
  </Step>
  <Step title="Complete payment">
    You're redirected to Stripe for secure card payment.
  </Step>
  <Step title="Activation">
    Credits appear in your account **immediately** after payment confirmation.
  </Step>
</Steps>

## Auto-Renew

Prevent invoicing interruptions by setting up automatic credit renewal:

<Steps>
  <Step title="Enable Auto-Renew">
    Settings → **Billing** → **Auto-Renew** → enable the toggle
  </Step>
  <Step title="Set the trigger threshold">
    Choose how many credits must remain for an automatic purchase to trigger (e.g., 10 credits).
  </Step>
  <Step title="Choose the renewal package">
    Which package should be purchased automatically each time.
  </Step>
</Steps>

<Note>
Auto-Renew uses your saved Stripe card. If payment fails **3 times**, auto-renew is automatically disabled and you receive a notification.
</Note>

## Grace Period

If credits run out, you get **7 extra days** during which:
- Invoicing **continues normally**
- Your balance goes negative
- You receive an email notification

After 7 days, new sends are blocked until you purchase credits (the negative balance is deducted from your next purchase).

## Transaction History

View all purchases, sends, auto-renewals, and refunds at:

Settings → **Billing** → **Transaction History**

Each row shows: date, type (purchase / consumption / refund), credit amount, and new balance.
