# 🏹 PLS: Personalise your first touchpoint for a Typeform signup

When a lead expresses interest on your Typeform, you want to draft a personalised first touchpoint in order to make sure you close them.



Within the Cargo community, we've seen our users build tons of AI recipes, here is one we thought was pretty neat. Let's set you up to leverage Alfie's AI recipe to nail that first touchpoint.

<figure><img src="../.gitbook/assets/Screenshot 2023-10-18 at 17.53.44.png" alt="" width="354"><figcaption></figcaption></figure>

### Setup your incoming data

Generating a personalised touchpoint assumes that you've collected some amount of data on the incoming lead, what brought them to your form and how to get back to them.&#x20;

Here's the fields we recommend you capture before you go further.

* _Company Email:_ You'll need this to get back to them. Ideally, block non-company emails
* _Company Size (optional):_ You may want to filter out non-ICP leads
* _Role (optional)_: You may want to filter out non-decision making users&#x20;
* Linkedin Profile Url (optional): Helpful to add personal context&#x20;
* Company website (optional): Helpful to add company context (or you can extrac th domain from the email above, if professional email)&#x20;
* _Reason For Interest_: Open field, lets you capture freely what pain brought the lead to your form
* _Feature Of Interest:_ A dropdown with a concise list of 4-5 key value propositions that most of our leads would fall into. Make sure to leave a catch-all term (e.g. spend management solution) as well as an 'other'.

### Associate a list of benefits for each potential feature of interest&#x20;

For each type of response on _Feature Of Interest_ you can associate with three bullet points each on the _Benefits Associated._&#x20;

It's pretty simple, you can generate a simple list of combinations, on a separate tab like so:

<figure><img src="../.gitbook/assets/Screenshot 2023-10-18 at 19.00.58.png" alt=""><figcaption></figcaption></figure>

One that's done, you can use a simple formula like this to generate the right values for the Benefits Associated column in Feuille 1

```
// Adapt to suit your cell references
=IFERROR(VLOOKUP(E2, 'Feuille 2'!A:B, 2, FALSE), "Not Found")
```

### Run the Intro email AI recipe

Scroll through the library in your Cargo add-on to locate this recipe. You then need to fill out a few parameter values to make sure the output matches what you're looking for. \
\
**Here's some suggestions:**

_Key Benefits_: Use the output we generated above from your _BenefitsAssociated_ column

_Pains_: Reference the _Reason For Interest column we created above_

_Solution:_ Reference the Feature Of Interest we created above

_Person Context:_ Reference the Linkedin URL column above

_Company Context_: Reference the Company website column above

### Sit back and let GPT do the work

Just make sure you push this to your outreach tool (feature coming soon on :wink:)

<figure><img src="../.gitbook/assets/Google sheets.gif" alt=""><figcaption></figcaption></figure>

\
\
