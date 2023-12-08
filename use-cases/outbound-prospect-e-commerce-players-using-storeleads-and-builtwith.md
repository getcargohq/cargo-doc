# 🤼 Outbound: Prospect e-commerce players using Storeleads and Builtwith

## **Context**

Are you selling to e-commerce players want to segment those on Shopify, WooCommerce Checkout or Magento?

We noticed this neat template being used in the Cargo community and thought we make it public.

One challenge with Storeleads data is that it won't always find the account in its database. Which why we'll demonstrate how to use our HTTP connector to make an API request to the Builtwith API and retrieve this data.

## **Setting up your data source**

You can use either a Webhook or a dataset in Cargo to enrol records from. Since Storeleads expects a company domain, your dataset should at least have a column containing one.

## **Make a call to Storeleads**

Select a Storeleads node from the catalog in your Cargo workflow, map the value of the domain to be passed, and you're set.

<figure><img src="../.gitbook/assets/storeleads run tuto.gif" alt=""><figcaption></figcaption></figure>

## **Set a back up with Builtwith**

For the records that Storeleads fails to enrich, you can make an API call to Builtwith to retrieve the tech stack used by that company, like in the illustration below.

<figure><img src="../.gitbook/assets/builtwith call.gif" alt=""><figcaption></figcaption></figure>

Here's the little JS snippet we used to flatten all the names of the technologies returned by Builtwith into a single string

{% code overflow="wrap" %}
```
{{nodes.bw_call.Results.flatMap(r => r.Result.Paths.flatMap(p => p.Technologies.map(t => t.Name))).join(', ');}}
```
{% endcode %}

## **Route the leads that meet the criteria to your CRM**

We used another little script to parse through the string generated above to check if any of the interesting names popped up in their tech stack

{% code overflow="wrap" %}
```
{{nodes.builtwith_output.technologies.split(', ').some(name => ['Shopify', 'WooCommerce Checkout', 'Magento'].includes(name)) ? 'YES' : 'NO'; }}
```
{% endcode %}

Once this is done, you can use a branch to set some rules on which results from either Storeleads or Builtwith pass the bar and should be retained in your CRM.&#x20;

In the illustration below we're keeping the ones that returned a yes above

<figure><img src="../.gitbook/assets/branch.gif" alt=""><figcaption></figcaption></figure>

There you go, sit back and talk to your new prospects.
