---
description: >-
  In Cargo, we believe in the power of automation & doing things at scale. Most
  of the actions will be made with variables to enable the workflow to
  orchestrate each record in a personalized way.
---

# ✍ Syntax

In every workflow in Cargo, to access the available data, you should use a liquid-like syntax starting with '\{{' and closing with '\}}'.&#x20;

```javascript
{{nodes.NAMEOFTHENODE.attributes}}
```

Whether you want to use AI prompt to explain an action or to configure an action, you will always use these principles.

For instance, if you want to see which data you have at your disposal when starting the workflow, you can write <mark style="color:green;">\{{nodes.start.</mark> too see the available data at this point.&#x20;

<figure><img src=".gitbook/assets/Capture d’écran 2023-05-08 à 15.44.21.png" alt=""><figcaption></figcaption></figure>

if you would like to get the information enriched by "Apollo" you would do <mark style="color:green;">\{{nodes.node\_3\[...]\}}</mark> and select the attributes you want like below

<figure><img src=".gitbook/assets/Capture d’écran 2023-05-08 à 15.50.12.png" alt=""><figcaption></figcaption></figure>

#### Fall back logic

A very powerful Cargo feature is the ability to set Fallback Values.

This can be used for occasions when you know that data being returned will be inconsistent in some way. It is used as a fallback logic to deal with inconsistent data. It takes the first attribute, and if empty, take the second one.

To use multiple attributes in a field, you can use the double pipe “||”.&#x20;

<figure><img src=".gitbook/assets/Capture d’écran 2023-05-08 à 15.57.54.png" alt=""><figcaption><p><em>Fallback logic</em></p></figcaption></figure>

The fallback logic is often used with waterfall logic: when pushing an enriched data to your CRM, you want to make sure something is pushed. For instance, you have two different source of email data, you put both to maximize coverage rate.

<figure><img src=".gitbook/assets/Capture d’écran 2023-05-08 à 16.28.09.png" alt=""><figcaption></figcaption></figure>



**How to use it**

{% embed url="https://app.guideflow.com/embed/zpe5e9a8pn" %}





