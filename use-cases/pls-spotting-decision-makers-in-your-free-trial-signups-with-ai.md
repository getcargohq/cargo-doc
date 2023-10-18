# 🏹 PLS: Spotting decision makers in your free trial signups with AI

## **Context**

A lead has just signed up to your product's free trial. but you're not sure if it's a decision maker worth closing?

This a use case from Cargo's AI community to solve this challenge using Cargo's native GPT-4 integration. The goal is to make sure the AI doesn't make too many mistakes using a good chain of thoughts.



## Why this matters <a href="#h_73c8220b74" id="h_73c8220b74"></a>

**Boost Sales Efficiency**: Focus on prospects who have the authority to make purchase decisions

**Strategic Triangulation**: Identify key players in your prospect's team for building social proof ahead of the decision-making process

**Customise Engagement**: Tailor your approach based on the type of decision-maker (e.g., founder vs team manager)

## **Phase 1:** Data Preparation:

<figure><img src="../.gitbook/assets/brandbird (8).png" alt=""><figcaption></figcaption></figure>

1. Ensure you're capturing a field such as job title in your signup. It's beneficial to include team size
2. Make sure you're filtering out non-professional emails. Otherwise use a recipe from the Cargo community to filter these out for you:



## Phase 2: Pit the AI vs a REGEX function

* **Step 1**: Set up a backup classifier using REGEX (reach out to tariq@getcargo.io the full prompt)

<figure><img src="../.gitbook/assets/brandbird (9).png" alt=""><figcaption></figcaption></figure>

* **Step 2**: Configure a GPT classifier (reach out to tariq@getcargo.io the full prompt)

<figure><img src="../.gitbook/assets/brandbird (10).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/brandbird (11).png" alt=""><figcaption></figcaption></figure>

* **Step 3**: Introduce an 'adjudicator' GPT classifier capable of revising the REGEX output (reach out to tariq@getcargo.io the full prompt)

<figure><img src="../.gitbook/assets/brandbird (13).png" alt=""><figcaption></figcaption></figure>



## Phase 3: Refining results

* **The goal**: Since GPT is prone to error every now and then, you'd want to bias the output slightly towards false positives. Remember, a minute spent on a mistakenly classified decision-maker is less costly than missing out on a potential lead
*
* **Step 5:** Add a verification step comparing GPT vs REGEX
* **Step 6:** For potential false negatives, consult the 'adjudicator' node&#x20;

{% hint style="info" %}
Logic:&#x20;

IF there's strong evidence, consider overruling the REGEX in favor of GPT's suggestion ELSE IF there's a consensus or risk of false positives, proceed with that output
{% endhint %}



## Phase 4: Routing Decision Makers:

<figure><img src="../.gitbook/assets/brandbird (15).png" alt=""><figcaption></figcaption></figure>

* Found a decision-maker lead? Notify your sales rep via Slack and integrate with your CRM and outreach tools
* Otherwise, consider enriching the lead to identify a stakeholder before integrating with your tools



## Takeaway

Test this process initially, evaluate its performance, and once satisfied, roll it out in production

Need a template? I've been using one with Cargo clients in prod. Reply to this email for the full prompt, code, and template

