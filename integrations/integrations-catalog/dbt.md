---
description: This page explains how to setup the DBT on Cargo.
---

# 💾 DBT

Connect your DBT account to extract your DBT models to cargo datasets.

### How to authenticate?

Log In to your Dbt account. On Header navigation bar click on the cog icon at the right, then click on **Account settings**

<figure><img src="../../.gitbook/assets/Screenshot 2024-01-09 at 19.35.17.png" alt=""><figcaption></figcaption></figure>

Click on service tokens at the settings panel, then Click on **+ new token**

<figure><img src="../../.gitbook/assets/Screenshot 2024-01-09 at 19.37.11.png" alt=""><figcaption></figcaption></figure>

Set **Read-only** permission on **All projects, then generate a key** and copy past it to you Cargo DBT connector config

<figure><img src="../../.gitbook/assets/dbt screen with hidden password.png" alt=""><figcaption></figcaption></figure>

then click on Account on the left, there you can find there your DBT **Account ID.**

<figure><img src="../../.gitbook/assets/Screenshot 2024-01-09 at 19.36.09.png" alt=""><figcaption></figcaption></figure>

&#x20;Then click on **Deploy** > **Environments** and select you production environment

<figure><img src="../../.gitbook/assets/Screenshot 2024-01-11 at 11.24.01.png" alt=""><figcaption></figcaption></figure>

you can find the **Environment ID** from the URL `.../projects/<PROJECT_ID>/environments/<ENVIRONMENT_ID>`
