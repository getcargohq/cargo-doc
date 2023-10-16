---
description: >-
  Relationships allow you to build a 360-degree view on your entity data,
  effectively joining different entities together using common identifier
---

# 🔁 Relationships

## Step 1: Build a relationship between the SalesforceAccounts and Audiences entity



<figure><img src="../.gitbook/assets/Screenshot 2023-10-09 at 10.04.13.png" alt=""><figcaption></figcaption></figure>

Pressing the above will open a modal like below. Below we go through what it means:



<figure><img src="../.gitbook/assets/Screenshot 2023-10-09 at 10.03.16.png" alt=""><figcaption></figcaption></figure>

**Entity**: The other entity you want to build a relationship with, in this case it is 'Audiences'

**Kind:** Whether each unique record SalesforceAccounts maps to multiple records in audiences

**Left column:** The id column in your SalesforceAccounts entity that would map to an adjacent column in your Audiences entity. In this case we've chose Salesforce\_account\_id

**Right column:** The id column in the Audiences entity that maps to the id column you chose above for the SalesforceAccounts entity



## Step 2: Build the relationship the other way round (this between the Audiences entity and the SalesforceAccounts entity

Navigate to the Audiences entity, and add a relationship. For the modal that appears, follow the same process as above but inverse your choices as show below

<figure><img src="../.gitbook/assets/Screenshot 2023-10-09 at 10.38.01.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2023-10-09 at 10.37.27.png" alt=""><figcaption><p>In this case, both SalesforceContacts and Audiences have many-to-many relationship possibilities, but this could have been different</p></figcaption></figure>

