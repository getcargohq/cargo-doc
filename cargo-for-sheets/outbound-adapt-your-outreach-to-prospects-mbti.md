# 🏹 Outbound: Adapt your outreach to prospect's MBTI

You're not happy with the typical personalisation in a mass outbound email and want to go one step further. In the Cargo for sheets community we noticed an interesting tactic and decided to make a template out of it.

Turns out, it can increase reply rates and conversion rate over and above your standard personalisation hacks.

\
The trick is to chain your prompts.



### Provide a column of Linkedin links

Your starting point is to provide a column of LinkedIn links. All the other prompts are built on the information based in here.

Make sure you have the LLM option enabled to be able to browse the contents of the link.

<figure><img src="../.gitbook/assets/Screenshot 2023-11-10 at 19.25.12.png" alt="" width="169"><figcaption></figcaption></figure>

### Chain your prompts

Your first prompt will refer to the column of Linkedin links and will ask GPT to deduce the MBTI information using a quick analysis of public information on the prospect's profile

{% code overflow="wrap" %}
```
Help me determine this person's MBTI profile form the LinkedIn profile link. Can you take a guess at extraversion vs introversion? Try to give scores for each category from 1 to 5

Profile link: {{LinkedinLink}}
```
{% endcode %}

Refine the output of the first prompt to get a usable answer

{% code overflow="wrap" %}
```
OK, now make a quick summary about this person (1 paragraph). then add buletpoints with the dominant letter and score for each category and score. No need to add disclaimers
```
{% endcode %}

### Add a template email and ask GPT to add an icebreaker

Add the template email to a column in google sheet and refer to this column in the next prompt

{% code overflow="wrap" %}
```
Dear [Name],

I thought you might be interested in a demo of our tool that seamlessly integrates call data with your productivity tools, providing insights into call trends. It could be a game-changer for your RevOps at Spendesk.

Best,
[Your Name]
```
{% endcode %}

Your next prompt is going to refer to this email column and the output of the refined MBTI prompt and attempt to modify the language of the email

{% code overflow="wrap" %}
```
Adapt the language of the email template and add an icebreaker to this email deduced from the MBTI analysis 

Email template: {{EmailTemplate}}
MBTI analysis: {{SecondPromptOutput}}

```
{% endcode %}

Et voila, see if that improves your copy.\
\
Just make sure you proofread a sample of the outputs to iterate on your prompt for a language that suits you :wink:



\
\
