---
title: "Etherly Chrome Extension"
description: "Install and set up the Chrome Extension for automatic Airbnb reservation sync."
---

# Etherly Chrome Extension

The Etherly Chrome Extension automatically downloads your Airbnb reservations every hour and sends them to Etherly Sync — no manual action required.

<Note>
The extension requires Chrome to be open and you to be logged in to Airbnb.
</Note>

## Installation

<Steps>
  <Step title="Enable Developer Mode in Chrome">
    Open **chrome://extensions** in Chrome.
    Toggle on **«Developer mode»** in the top right corner.
  </Step>
  <Step title="Download and install the extension">
    Go to **Settings → Airbnb → Chrome Extension** and click **«Install Etherly Extension»**.

    Chrome will ask if you want to install the extension — click **«Add extension»**.

    <Warning>
    If Chrome shows «This extension is not from the Chrome Web Store», this is expected for private extensions. Click **«Add extension»** to continue.
    </Warning>
  </Step>
  <Step title="Connect the extension to your account">
    Go to **Settings → Airbnb** in Etherly and copy your **Extension Token**.

    Click the Etherly icon in the Chrome toolbar, paste the token and click **«Connect»**.
  </Step>
</Steps>

## Automatic updates

The extension updates automatically — no action needed. Chrome checks for new versions every 5 hours.

To check for an update immediately: open **chrome://extensions** and click **«Update»**.

## How it works

Every hour the extension:

1. Opens the Airbnb reservations page (or uses an existing tab)
2. Automatically downloads the CSV with reservations
3. Sends it to Etherly Sync
4. Closes the tab if it opened it

You can also trigger a sync manually by clicking **«Sync now»** from the extension popup.

## Troubleshooting

**«Token not found»**: Repeat the token connection step from Settings.

**«CSV download returned empty result»**: Make sure you are logged in to Airbnb in Chrome.

**Extension not showing new reservations**: Check that the Airbnb tab loads normally and try a manual sync.
