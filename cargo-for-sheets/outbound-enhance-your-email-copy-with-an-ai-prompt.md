# 🤼 Outbound: Enhance your email copy with an AI prompt

You've written an email copy but it's not quite there yet. Maybe it's too long and not personalised enough with the classic approach.

We noticed a neat little trick to speed up the iteration process, just by using a smart way.

<figure><img src="../.gitbook/assets/image (2).png" alt="" width="214"><figcaption></figcaption></figure>

### Setup your incoming data

<figure><img src="../.gitbook/assets/Getcargo (4) (2).gif" alt=""><figcaption></figcaption></figure>

First up, you'll want to collect some amount of data on the **prospect**.

Here's some fields we recommend you capture before you go further.

* _Role (optional)_: The prompt may adapt the message given the role of the recipient
* Linkedin Profile Url (optional): If you're using the LLM option, the AI will scrape the profile and return interesting insights
* Company website (optional): Helpful to add company context with the LLM option enabled
* _Their mission_: Open field, lets you capture freely what the recipient's commpany does
* _Feature Of Interest:_ A dropdown with a concise list of 4-5 key value propositions that most of our leads would fall into. Make sure to leave a catch-all term (e.g. spend management solution) as well as an 'other'.

Next, it helps to provide some details about your **product** too.

* Benefits: A list of benefits that the product brings
* Mission: What you're trying to achieve with your product

### The email you want to start with

Take your email, whatever it looks like, and throw it into a column that your prompt can access

{% code overflow="wrap" %}
```
Dear [Name],

I recently had the opportunity to explore your company's mission at https://www.getcargo.io/ and was impressed by your commitment to providing a semantic layer for sales on top of data warehouses.

I understand the challenges that come with translating complex data into actionable sales strategies. The potential of your data warehouse could be untapped, leading to missed opportunities and inefficiencies.

I would love to discuss how my expertise could benefit your team and help you achieve your mission. Please let me know a convenient time for a call or a meeting.

Looking forward to your positive response.

Best Regards,
[Your Name]
```
{% endcode %}

As you can tell, this one is far too long and too vague to make any impact on the recipient

### Refine this prompt to generate the first email

Feel free to modify this one

{% code overflow="wrap" %}
```
You are an experienced sales copywriter who trains sales reps to write extraordinary emails. Improve the email below for one of your clients by turning it into your quintenssentioally short and sharp message (not more than 60 words) and spotlight a pain or benefit from the product's mission below
```
{% endcode %}

The part limiting the maximum number of words possible was really key since GPT tends to ramble once you provide so many inputs.

Already the output looks better than where we starred

{% code overflow="wrap" %}
```
Dear [Name],

Struggling to translate complex data into actionable strategies? Our tool instantly generates call transcripts, pushing the most relevant info to your Salesforce using the BANT framework. Let's unlock the full potential of your data warehouse together. 

Ready to boost your bottom line? Let's chat.

Best,
[Your Name]
```
{% endcode %}

### Generate a follow-up too, by passing the previous email as context

A simple prompt like this seems to do the job well enough:

{% code overflow="wrap" %}
```
Can you provide me a follow up I could use after this first email (not more than 40 words). As you know we should always bring value, not just asking if they see my previous email. Things like pushing one content,a video, or interactive demo.
```
{% endcode %}

Notice the output below

{% code overflow="wrap" %}
```
Dear [Name],

I thought you might be interested in a demo of our tool that seamlessly integrates call data with your productivity tools, providing insights into call trends. It could be a game-changer for your RevOps at Spendesk.

Best,
[Your Name]
```
{% endcode %}



Just make sure you proofread a sample of the outputs to iterate on your prompt for a language that suits you :wink:



\
\
