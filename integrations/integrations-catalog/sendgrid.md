---
description: This page explains how to setup the Sendgrid integration on Cargo.
---

# 📤 Sendgrid

Use Sendgrid to send template emails. Fill the handlebars values directly from Cargo.

### How to authenticate?

Open Sendgrid, go to **Settings**, **API Keys** and click on **Create API Key**.

Create a **Restricted access key** for Cargo, with the following access

* &#x20;**Mail Send** (Full access)
* **Template Engine** (Read access)

<figure><img src="../../.gitbook/assets/Capture d’écran 2023-07-11 à 10.45.42.png" alt=""><figcaption><p>Create restricted access API Key on Sendgrid</p></figcaption></figure>

Finally, put the generated key in the connector config on Cargo.

### Available actions

**Write** - Send an email
