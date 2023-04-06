---
description: This page explains how to setup Cargo on a Google BigQuery warehouse.
---

# Use Cargo on Google BigQuery

Cargo reads data from existing tables and creates its own datasets, schemas, and tables. It should be noted that **Cargo never overwrites existing data**.

Cargo uses the Google Cloud BigQuery client to read and write data via the BigQuery API. When downloading records of a Cargo Entity or Segment into a file, Cargo uses Google Cloud Storage.

To perform these actions, Cargo must have certain permissions in Google Cloud. Therefore, setup is required to ensure that Cargo has the necessary permissions.

## Enable the necessary APIs

Cargo uses some Google APIs that must be enabled. To do so:

1. Go to the Google Cloud Console.
2. Select **APIs & Services**.
3. Select **Enabled APIs & Services**.

<figure><img src="../.gitbook/assets/Capture d’écran 2023-04-05 à 18.59.22.png" alt=""><figcaption><p>Enable APIs in Google Cloud</p></figcaption></figure>

4. Search for and enable the following APIs:
   1. BigQuery API
   2. Cloud Resource Manager API.

## Create a Service Account

Cargo will use this service account to access the APIs enabled in the previous step.

To create a service account, follow these steps:

1. Go to the Google Cloud Console.
2. Click on **IAM & Admin**.
3. Click on **IAM**.

<figure><img src="../.gitbook/assets/Capture d’écran 2023-04-05 à 18.29.33.png" alt=""><figcaption><p>Open IAM to create a Service Account</p></figcaption></figure>

4. Click on **Service Accounts**.
5. Click on **Create service account**.
6. Give the service account a name.
7. Grant the following roles:
   1. BigQuery Data Editor
   2. BigQuery Job User
   3. Project IAM Admin
   4. Storage Admin.
8. Click on **Done**.

The next step is to generate a key:

1. In **Service Accounts**, click on the created service account.
2. Click on **Keys**.
3. Click on **Add Key**.
4. Choose **Create new key**.
5. Select **JSON**.
6. Click on **Create**.

This should download a file to your computer.

## Creating a New Workspace on Cargo

To create a new workspace on Cargo, follow these steps:

1. In the **Create new workspace** form, define a **prefix** that Cargo will use to prefix the datasets and schemas it creates, in order to avoid any conflicts.
2. Copy and paste the content of the file into the field labeled **Service Account**.
3. To determine which **location** to use, follow these steps:
   1. In the Google Cloud Console, open BigQuery.
   2. Choose a dataset.
   3. Look for the **Data location** value.

<figure><img src="../.gitbook/assets/Capture d’écran 2023-04-05 à 18.49.37.png" alt=""><figcaption><p>Find data location in BigQuery</p></figcaption></figure>

## Setup completed 🎉

You are ready to use Cargo !

<figure><img src="https://media.giphy.com/media/Gjoz5izVy7gSA/giphy.gif" alt=""><figcaption></figcaption></figure>
