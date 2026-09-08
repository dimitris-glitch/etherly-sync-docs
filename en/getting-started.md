---
title: "Getting Started"
description: "Account, activation, booking-channel connection, invoicing provider and AADE Connect: the steps to your first ready booking, in about 10 minutes."
---

# Getting Started with DeskBoy

Setup takes about **10 minutes**. Before you begin, it helps to have at hand:

- Access to your **booking channel**: your Hosthub API key, your Hospitable API key, or simply your Airbnb account details.
- If you issue documents, an account with the **invoicing provider** you use (e.g. Elorus). If you rent as a private individual without a business registration, you do not need one (see [Private individual](/en/guides/private-individual)).
- Your TAXISnet credentials for AADE declarations.

---

## Step 1: Create your account

Go to [app.deskboy.app/register](https://app.deskboy.app/register) and create an account, with email and password or with Google. You will receive a verification email; click the link and you land directly in the activation steps.

<Info>
Your account starts on the **Free** plan, with no card and no expiry, with up to 250 checkouts per month.
</Info>

---

## Step 2: Activation

Three short steps, the same for everyone (details in [Account activation](/en/guides/onboarding)):

<Steps>
  <Step title="Phone verification">
    Enter your mobile number in international format and type in the code you receive by SMS.
  </Step>
  <Step title="Capacity and details">
    State in which capacity you rent: **private individual** (you declare to AADE without issuing documents) or **business** (you issue receipts or invoices). A tax ID lookup fills in your details from the registry.
  </Step>
  <Step title="Connect your booking channel">
    Pick the channel you use:

    - **Hosthub**: in Hosthub click your name at the top right → **Settings** → API keys section → **Create new API key**. Copy the key, paste it into the **Hosthub API Key** field and click **Test connection**. Once you see "Connection successful. Property sync has started.", click **Continue**.
    - **Airbnb Live**: leave your Airbnb account email and a phone number, and we complete the connection together with you in a short session (see [Airbnb connection](/en/guides/airbnb)).
    - **Hospitable**: paste the API key you issue in Hospitable (see [Hospitable connection](/en/guides/hospitable)).
  </Step>
</Steps>

Once these are done, you enter the panel. Booking sync starts right away.

---

## Step 3: Invoicing provider

If you issue documents, connect your provider under **Settings → Integrations**, whenever it suits you:

<Steps>
  <Step title="New connection">
    Click **New connection** and pick the provider you use.
  </Step>
  <Step title="Connection details">
    For **Elorus** you need the API key (Settings → API settings → **Create new key**) and the **Organization ID**, shown in the URL of the Settings → Organization page.
  </Step>
  <Step title="Fiscal details">
    Enter the tax id, and the legal form and business name are filled in from the AADE registry. They are needed for the AADE declarations and the VAT regime.
  </Step>
  <Step title="Test the connection">
    Click **Test connection**. On success the connection shows as active and you can issue documents.
  </Step>
</Steps>

<Info>
Booking sync, AADE declarations and analytics work from the moment your channel is connected. Add the invoicing provider whenever you are ready. Provider credentials are stored encrypted.
</Info>

---

## Step 4: AADE Connect and your first property

<Steps>
  <Step title="AADE Connect">
    Under **Settings → AADE Connect**, connect your TAXISnet credentials and match each property to its AADE property (AMA). Without a match, its bookings do not appear under Declarations (see [AADE Connect settings](/en/guides/aade-connect)).
  </Step>
  <Step title="Property setup">
    Under **Settings → Properties**, open your first property. For the Climate Resilience Fee set its **Regime**, rooms and beds. If you issue documents, also set:

    | Field | What it is |
    |-------|------------|
    | **Organization** | The invoicing-provider organization that issues the documents |
    | **Default Receipts Contact** | The retail customer in Elorus used on receipts |
    | **Invoice Series / Receipt Series** | Numbering series for invoices and receipts (or "No series") |
    | **ΤΑΚΚ characteristics** | Detached house, floor area, regime — they decide the ΤΑΚΚ tax that goes on the document |

    Settings save automatically. See the full [property guide](/en/guides/properties).
  </Step>
</Steps>

---

## Your first booking

Once a property is fully configured, its bookings appear under **Bookings** with status **READY** (green indicator).

<Steps>
  <Step title="Send the booking">
    Click the send button next to it. It carries your provider's name (e.g. **"Send to Elorus"**). You can also select several for a bulk send.
  </Step>
  <Step title="See the result">
    Within seconds the status becomes **SENT** and the link to the document appears. The AADE declaration shows up under **Declarations**.
  </Step>
  <Step title="Let DeskBoy carry on by itself">
    Enable [auto-invoicing](/en/guides/auto-invoicing) and [automatic final declaration](/en/guides/declarations), and the next bookings are handled without you.
  </Step>
</Steps>

<Check>
Your first document has been issued.
</Check>

---

## Available integrations

Under **Settings → Integrations** you find all connections:

| Integration | What it does |
|-------------|--------------|
| **Hosthub** | Automatic booking sync |
| **Hospitable** | Bookings from all your Hospitable channels (Airbnb, Booking.com, Vrbo, direct) |
| **Airbnb Live** | Direct connection to your Airbnb account, bookings arrive automatically |
| **Elorus** | Document issuance and myDATA submission |
| **AADE Connect** | Short-term rental declarations to AADE |

A booking connection is deleted from the delete icon on its card. Its credentials are destroyed immediately, while bookings with issued documents and their declarations are kept as tax history.

## What's next

<CardGroup cols={2}>
  <Card title="Property setup" icon="house" href="/en/guides/properties">
    Contacts, series, regime and ΤΑΚΚ characteristics for every property.
  </Card>
  <Card title="Auto-invoicing" icon="clock" href="/en/guides/auto-invoicing">
    Set a run time and forget manual sending.
  </Card>
  <Card title="Bookings & statuses" icon="list-check" href="/en/guides/checkouts">
    What each status means and what to do for each.
  </Card>
  <Card title="Team" icon="users" href="/en/guides/team">
    Invite collaborators and your accountant.
  </Card>
</CardGroup>
