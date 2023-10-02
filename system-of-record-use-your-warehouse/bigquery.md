# Use Cargo on Google BigQuery

✅ What Cargo can do

1. **Read** data from schemas and tables, even if they are spread across multiple databases,
2. **Writes** them into new schemas and tables

❌ What Cargo will never do

1. **Overwrite** existing schemas and tables

(instead it always creates its own schemas and tables when needed)



**How it works**: Cargo uses the Google Cloud BigQuery client to read and write data via the BigQuery API. When downloading records of a Cargo Entity or Segment into a file, Cargo uses Google Cloud Storage.

To perform these actions, Cargo must have certain permissions in Google Cloud. Therefore, setup is required to ensure that Cargo has the necessary permissions.

## Enable the necessary APIs

Cargo uses some Google APIs that must be enabled. To do so:

1. Go to the Google Cloud Console.
2. Select **APIs & Services**.
3. Select **Enabled APIs & Services**.
4. Search for and **enable the following APIs**:
   1. BigQuery API
   2. Cloud Resource Manager API.

## Create a Service Account

Cargo will use this service account to access the APIs enabled in the previous step.

To create a service account, follow these steps:

1. Go to the Google Cloud Console.
2. Click on **IAM & Admin**.
3. Click on **IAM**.
4. Click on **Service Accounts**.
5. Click on **Create service account**.
6. Give the service account a name.
7. **Grant** the following roles:
   1. BigQuery Data Editor
   2. BigQuery Job User
   3. Storage Admin.
8. Click on **Done**.

## Generate a Key

Following the steps below to generate a key:

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
   2. Choose a **dataset**.
   3. Look for the **Data location** value.

## Setup completed 🎉

You are ready to use Cargo!

<figure><img src="https://media.giphy.com/media/Gjoz5izVy7gSA/giphy.gif" alt=""><figcaption></figcaption></figure>
