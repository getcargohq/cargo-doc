# 🏹 PLS: Slack your AE when a client attains a usage threshold

## **Context**

If you have a product-led motion and you're tracking your customer's product usage, use this as a trigger to unlock your Account Executive's (aka AE) time in order that they can have the right conversation at the right time to find upselling opportunities.

There are mutliple solutions for how to track usage data, for this piece we assume that you're already storing the output inside your data warehouse, where Cargo comes into play.

We'll be showing you how to do the following steps within Cargo:\
\- **Step 1**: Setup a product usage threshold that triggers an alert to be sent to your AEs\
\- **Step 2**: Locating the right owner for the account\
\- **Step 3**: Synthesising product usage information to make it actionable (optional)\
\- **Step 4**: Sending a slack message to the owner

## **Setting up your trigger threshold**

Since your product usage data is already stored in your data warehouse, inside Cargo you can set up an entity that pulls from this table.

Thanks to Cargo's 'Computed columns' feature, you can easily create an expression that computes a ratio for your target metrics. In the example below we are using the column tracked\_hours and comparing it to the total\_free\_hours. The idea is that once a user attains a certain ratio of tracked hours on the platform they are good prospect to be contacted by your AE team.

The only thing you need to ensure is that there's a way to identify the owner of the prospect/ account linked to a prospect.\
\
Here's how it would work:\
\- **Step 1a**: Setup a computed column that divides tracked\_hours by total\_free\_hours to calculate a 'free usage' ratio

<figure><img src="../.gitbook/assets/adding comp column usage ratio.gif" alt="" width="375"><figcaption></figcaption></figure>

\- **Step 1b**: Setup a segment that triggers when 75% of the 'free usage' ratio is attained

<figure><img src="../.gitbook/assets/set a threshold filter on segment (1).gif" alt="" width="375"><figcaption></figcaption></figure>

## **Finding the right account owner**

Once the segment you created in step 1b above enrols the right user to a workflow, the first thing you need to do is locate the right owner. Luckily, as part of Cargo's territory feature, we're pulling member IDs from your CRMs and slack.

You can use the territory node to map the right CRM ID (in this case Salesforce) and Slack ID together.

## Synthesising information for action

This step is optional but the idea is not to send a indigestable mass of information to the owner, but instead a neat synthesis that lends itself to action. Use the AI capability to prompt GPT as you like using information from your the product usage data table.\
\
Here's an example prompt that worked well for us:

<pre data-overflow="wrap"><code>You're an assistant Account Executive preparing a summary (less than 100 words) about a client-user. The reason you're doing this is that there's a potential upsell opportunity here as they get close to the end of their quota. Take whichever information is available in the Account and Usage data below and craft a concise summary in bullet points which could help your boss AE pick up the phone and engage this client in a conversation:

<strong>Account data 
</strong>Title: //reference the right field in your data
Parent Account Name: //reference the right field in your data
Description: //reference the right field in your data
Reporting Segment: //reference the right field in your data
Country: //reference the right field in your data
Website: //reference the right field in your data
Domain: //reference the right field in your data
Segment: //reference the right field in your data
Headcount: //reference the right field in your data
Last Funding Round: //reference the right field in your data
Revenue Estimate: //reference the right field in your data
Total Capital Raised: //reference the right field in your data

Usage data:
Users: //reference the right field in your data
Last Activity Date: //reference the right field in your data
Account Score Tier: //reference the right field in your data
</code></pre>

## **Slack message to owner**

By this point you have the ingredients to ping your AE with an actionable nudge. Use our Slack node to craft your message, here's one that worked well for us:

<pre><code><strong>Hi //reference the right field in your data,
</strong><strong>
</strong>A starter account you currently own has consumed >75% hours of their free hours quota
<strong>
</strong><strong>Now would be a good time to check on them and discuss Enterprise plan conversion.
</strong>
Here's a helpful summary created by a bot:
//reference the data synthesis created above
</code></pre>

Test it out, and once you're happy, enable the workflow to make the process systematic.
