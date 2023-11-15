# 🏹 Outbound: Classify your prospect as B2B or B2c

Often the product you're selling will have a different impact on a prospect given their value proposition. When building lists you'd want to make sure that you're getting this right in order to optimise your conversion rates.

The most typical classification we see is to classify whether a lead is a B2B or B2C business.

Here's a neat set of prompts to do this right inside your Google Sheet using Cargo.

### Provide a column of Linkedin links

Your starting point is to provide a column of LinkedIn links or Company website links. The following prompts will browse these links to extract information.

Make sure you have the LLM option enabled to be able to browse the contents of the link.

<figure><img src="../.gitbook/assets/Screenshot 2023-11-10 at 19.25.12.png" alt="" width="169"><figcaption></figcaption></figure>

### Chain your prompts

Your first prompt will refer to the column of Linkedin/ Website links and will ask GPT to deduce the value proposition of the prospect.

{% code overflow="wrap" %}
```
Help me synthesise the value proposition of the company in the lnk from this LinkedIn/Website link below. Can you take a guess at whether they are likely to be selling to other businesses (B2B) or consumers directly (B2C) ? 

Rule: Give scores for each category (B2B or B2c) from 1 (least) to 5 (most)

Profile link: {{LinkedinLink/WebsiteLink}} //Replace with the right column reference
```
{% endcode %}

Refine the output of the first prompt to get a usable answer

{% code overflow="wrap" %}
```
OK, now make a deduction from another analysis above to classify in one words whether the company in question is a B2C or B2B business.

Rule1: No need to add disclaimers
Rule2: Return only a one word response (i.e. 'B2B' or 'B2C')
```
{% endcode %}

Et voila, see if that helps you classify your leads better.\
\
As always, make sure you do a few tests before to see if it works :wink:



\
\
