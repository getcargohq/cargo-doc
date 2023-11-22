# 🤼 Outbound: Company headcount intent strategy with Captain Data

## **Context**

This signal allows you to define a growth rate that makes a company a good candidate.

For small and medium-sized businesses (SMBs) with 100 to 200 full-time employees (FTEs), a 20% growth in their workforce over the last six months is a big deal.

The trouble is that such data will often be found on Linkedin, which is famously bad at opening up its databases through an API. Which is why it helps to use specialist providers like Captain data to automate this process.

## **Setting up your Captain Data dataset**

Before you do that you need to setup your Captain Data workflow and your Linkedin Sales Navigator search to feed it.

**Step 1**: Setup a filter for employee growth on your Linkedin Sales Navigator

<figure><img src="../.gitbook/assets/empGrowth tuto1.gif" alt=""><figcaption><p>Setup a filter for headcount growth</p></figcaption></figure>

**Step 2**: Define the two-part enrichment logic in your Captain Data

<figure><img src="../.gitbook/assets/configure captain tuto1.gif" alt=""><figcaption></figcaption></figure>

* _Search Sales Navigator Companies:_ Pass the link of the query you created above
* _Extract Linkedin Company Profile:_ Find the stakeholders that would be worth reaching out to capitalise on this signal.

**Step 3**: Create a dataset and segment with the results of the Captain Data workflow inside Cargo&#x20;

<figure><img src="../.gitbook/assets/Create CD dataset cargo tuto1.gif" alt=""><figcaption></figcaption></figure>

* _Create a dataset referring to the Captain Data workflow we created above_
* _Create a new segment based on this dataset_

The following part will show you how to configure a Cargo workflow on top of this segment.

## **Set up your Cargo workflow**

**Step 1**: Filter out any existing accounts in your CRM

You might want to make sure you're don't to reach out to existing accounts in your CRM (or maybe you do?).

<figure><img src="../.gitbook/assets/Salesforce search node tuto1.gif" alt=""><figcaption></figcaption></figure>

If you want to do this inside Cargo, a simple way is to setup a a search node with Salesforce (in this case) if the return results an empty array, the workflow can proceed - otherwise stop.

**Step 2**: Execute the Captain Data nodes inside Cargo

Cargo is natively connected to the Captain Data API. This means that you can trigger workflows in Captain Data inside and recover their outputs once the execution completes.

<figure><img src="../.gitbook/assets/Captain data workflow cargo tuto1 (1).gif" alt=""><figcaption><p>Setup a captain data write and read nodes respectively</p></figcaption></figure>

## **Loop through each stakeholder and email them**

Once you have the good list of stakeholders to reach out, you want your workflow to loop through each of them and send them an email linked to the intent signal of employee growth

<figure><img src="../.gitbook/assets/Group node setup apollo-zeroB-salesloft tuto1.gif" alt=""><figcaption></figcaption></figure>

* Set up a group node inside Cargo\
  This permits you to accept the elements of an array (in this case, the output of captain data)
* Find emails with Apollo
* Verify emails with Neverbounce
* Push to a Salesloft cadence

There you go, now you're set.
