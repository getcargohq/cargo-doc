# 🤼 Outbound: Find your prospect's competitor

Mentioning your prospect's competitors in a cold outreach is proven to improve your reply rates.&#x20;

Here's a neat set of prompts to replace the manual search and do this right inside your Google Sheet using Cargo.

Before you start, make sure you have the LLM option enabled to be able to browse the contents of the links you provide.

<figure><img src="../.gitbook/assets/Screenshot 2023-11-10 at 19.25.12.png" alt="" width="169"><figcaption></figcaption></figure>

### Provide a column of Company names and Website domains

Your starting point is to provide a column of Company names and website domains (without the prefixes, e.g. 'www', and suffixes like '/en.html'.&#x20;

The following prompts will browse these links to extract information.

### Knit together some prompts

Your first prompt will refer to the column of Company names/ Website domain names and will ask GPT to deduce the value proposition of the prospect.

{% code overflow="wrap" %}
```
Identify competitors for this company ({{ Company }}) on the web

website: https://www.similarweb.com/website/{{ Website domain }}/#competitors
```
{% endcode %}

Refine the output of the first prompt to get a usable answer

{% code overflow="wrap" %}
```
OK, now make a deduction from another analysis above to retain just the company names separated by commas only. Don't anything else to the output.
```
{% endcode %}

Et voila, see if that helps your KPIs.\
\
As always, make sure you do a few tests before to see if it works :wink:



\
\
