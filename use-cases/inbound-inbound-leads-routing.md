# 🔔 Inbound: Inbound leads routing

At the end of this tutorial, you will grasp the process of automating lead assignments and updates in Salesforce, triggered by an inbound lead sign-up on your website, and ensuring timely Slack notifications to the relevant sales representatives.

#### **Context**

A lead has just signed up on your website. This sets off a webhook trigger in the Hubspot form which sends the lead over to Cargo’s workflow.

## **Setup: Integrate with HubSpot**

1. In your Cargo workflow, you will find a **webhook URL**. This webhook will act as the listening point for any new leads signing up via your HubSpot forms
2. Now, switch over to HubSpot. Navigate to the workflow associated with your form and set the **destination of this workflow to the copied webhook URL** from Cargo
3. Once a lead is received you can observe the data contained therein



## Phase 1: Check if lead already exists

* **Clean the Domain and Email**: Once the lead data reaches Cargo, the first step is to clean and validate the domain and email submitted during the sign-up. This ensures accurate data for further actions.
* **Query Salesforce for Existing Contact**: Post-cleaning, use the validated domain to check Salesforce if this contact already exists.
* Use a branch node treat the lead differently if the lead exists already



## Phase 2: Enrich the leads

* **For New Contacts**: If the contact does not exist in Salesforce, use Clearbit and Cognism to enrich the data of this lead using the cleaned email. Enrichment provides additional details and context about the lead that can be vital for the sales process
* **For Existing Contacts:** If the contact already exists in Salesforce, you may want to periodically refresh their data. Set a criterion, say, every 180 days, to re-enrich these contacts and keep their details up-to-date
* Regardless of the route - new or existing, now search for the associated account in Salesforce using the cleaned domain



## Phase 3: Prioritise and route

* **Account Assignment Check**: Query Salesforce to determine if the account is already assigned to an existing sales representative
* **Assignment**: If the account isn't assigned, create or update the user in Salesforce with the correct properties
* **Upsert Operation**: Whether the lead is new or existing, upsert this account and contact data into Salesforce and assign the owner. "Upsert" ensures that the record is inserted if it doesn’t exist and updated if it does
* **Immediate Notification**: Ping the assigned sales representative on Slack to alert them of the new or updated lead, ensuring immediate attention and follow-up



## Takeaway

By the end of this sequence, you've successfully handled an incoming lead in several second validating, enriching, and intelligently routing to the right rep in real-time.

This automation ensures that you capitalise on the momentum of a lead's interest, driving faster conversions.











