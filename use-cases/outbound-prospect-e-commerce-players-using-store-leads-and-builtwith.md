# 🤼 Outbound: Prospect e-commerce players using Store Leads and BuiltWith

## **Context**

Targeting e-commerce businesses and need to identify those using Shopify, WooCommerce Checkout, or Magento?&#x20;

We've spotted a popular template in the Cargo community and decided to share it.

Challenge: Sometimes, Store Leads might not locate the account. We'll show you how to use Cargo's HTTP connector to query the BuiltWith API for this case.

## **Setting up your data source**

Start with a webhook or a dataset in Cargo - your call. Just ensure your dataset includes a column with the company domain.

## **Make a call to Store Leads**

Select a Store Leads node from the catalog in your Cargo workflow, map the value of the domain to be passed, and you're set.

<figure><img src="../.gitbook/assets/storeleads run tuto.gif" alt=""><figcaption></figcaption></figure>

## **Set a back up with Builtwith**

For the records that Store Leads fails to enrich, you can make an API call to BuiltWith to retrieve the tech stack used by that company, like in the illustration below.

<figure><img src="../.gitbook/assets/builtwith call.gif" alt=""><figcaption></figcaption></figure>

Here's the little JS snippet we used to flatten all the names of the technologies returned by BuiltWith into a single string

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
