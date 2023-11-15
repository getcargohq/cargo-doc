# 🏹 Outbound: New job post intent strategy with Lonescale

## **Context**

You suspect that when a certain kind of ICP-like (Ideal Customer Profile) company posts a specific kind of job posting, it's a strong signal that they're ready to buy your product? \
\
A lot of GTM teams we work with certainly think so and so we have built different versions of a strategy using a tool called Lonescale for them.\
\
The trouble with job postings is that they can be high volume at times, and if you don't want to chase every company that is hiring in your segment, then you may spend a lot of time sorting through these leads manually.&#x20;

We thought we could use the AI feature in Cargo to make this process smarter.

Here's how it works:

## **Setting up your Lonescale**

Cargo is set up to listen to webhooks. You simply need to copy create a workflow with a Webhook as its base.&#x20;

Then you just need to copy Cargo's webhook URL in to your Lonescale interface.

Illustration below:

\<GIF>

## **Check for existing accounts or contacts**

You might want to make sure you're don't to reach out to existing clients, accounts or contacts in your CRM.&#x20;

There are multiple ways of doing this, you could make a search in your CRM, or if you have an entity in Cargo mapped to your CRM you could do a base search there (illustration below)\


\<GIF>

## **Set up criteria for AI to evaluate the relevance of the job description**

Since you don't want to go after every single offer that Lonescale will send to you, you want to set up some criteria for what qualifies as a relevant job posting or not.\
\
We're sharing a template you could use for a prompt that works well by awarding points when particular keywords are found.\
\
To use this, replace the values inside the '< >' to something custom your situation

{% code overflow="wrap" %}
```
// Prompt 1
Determine if this job posting aligns with <your main criteria>:

<Criteria 1>: Seek  "<Keyword1>" or "<Keyword2>" avoid "<Keyword3>" favor mentions of "<Keyword4>", avoid "<Keyword5>". (award +1 point when conditions are met)

<Criteria 2>: Exclude "<Keyword6>" or "<Keyword7>" (award +1 point when conditions are met)

<Criteria 3>: Favor mentions of "<Keyword8>", "<Keyword9>" (award +1 point when conditions are met)

Sum the amount of points you awarded and list the points breakdown below

Here is the content of the job description to analyse:
{{nodes.start.job_description}} //replace this with the correct node reference
```
{% endcode %}

This will produce a long text containing the criteria and the points awared, you can use the prompts below to clean up and sort this reponse into useable insights.\


{% code overflow="wrap" %}
```
// Prompt 2 - Conclusion
In less than 10 words, write if the text passage in reference below concludes that it's a good fit or not? Provide just the 10 words output and nothing else

Frame the output like 'Job desc is a good fit' or vice versa

text: {{nodes.ai1.output}} /replace this with the correct node reference

rule: don't include the passed text above in your output
```
{% endcode %}

{% code overflow="wrap" %}
```
// Prompt 3 - Points sum

In less than 10 characters sum the points awarded in the analysis below, Provide only an integer with the string 'points' attached

text: {{nodes.ai1.output}} //replace this with the correct node reference

rule: don't include the passed text above in your output
```
{% endcode %}

{% code overflow="wrap" %}
```
// Prompt 4 - Points breakdown

Cleanly write out the points breakdown mentioned in this text analysis in a tabular form. You're maniacally concise in providing this information, don't provide anything extra
  
text: {{nodes.ai1.output}} //replace this with the correct node reference

rule: don't include the passed text above in your output
```
{% endcode %}

## **Filter out job posts that don't meet the requirements**

Now you're ready to sort the right job posts in order of pertinence\
\
Use a filter node, as below:\


\<GIF>

## **Search for stakeholders belonging to the hiring company**

You have retained the right job posts that are pertinent and now you can using your data provider to find the right stakeholders to reach out to with an email.\
\
You can set up an Apollo (or equivalent) search node, as below:

## **Use a group node to loop through these stakeholders and send an email**

Select a group node and set the input data as below:\
\<GIF>\
\
Within the group node, you'd want to setup a personalised outreach email and then push this to an existing sequence.\
\
Here's an example of a prompt we used to generate an email based on the contents of the job description and role of the person receiving the email (make sure to replace the placeholders inside '<>').

{% code overflow="wrap" %}
```
// Prompt 5 - Email body generation

Construct a very concise, sharp outreach email (less than 50 words max) that speaks to the contents of the job description referred below and adapt it to the role of the person indicated below. 

The idea is to link the points in the job description to <insert your main value proposition>

Make sure the email sounds natural and not just a boring salesy email, refer to the fact that they're hiring someone.

Case 1: If the job description had mentioned <Keyword1> or <Keyword2> as being important, emphasize <insert main punchline here>.

Case 2: If the recipient's job title is <Keyword3> or <Keyword4> or similar, emphasize <insert main personalisation here>.

Here's an example of the language that you can use to keep in line with the tone of the sender:

Example1: "<Provide an example from your previous emails"
Example2: "<Provide another example from your previous emails>"

Job description: {{parentNodes.start.job_description}} //replace this with the correct node reference
```
{% endcode %}

Now you have a crafted email ready to send. You'll probably want to add a manual review process here. You can either do this inside Cargo by enabling the manual review toggle (as below) or disabling automatic email emission inside your Outreach tool (Lemlist in illustration below).\
\
There you go, sit back and watch the leads flow in :sunglasses:. It works!
