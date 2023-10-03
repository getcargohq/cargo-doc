---
description: >-
  In Cargo, we believe in the power of automation & doing things at scale. Most
  of the actions will be made with variables to enable the workflow to
  orchestrate each record in a personalized way.
---

# 🧢 Expression 101

#### **Deep Dive: Understanding Expressions**

* **Learning Outcome:** Grasp how Cargo’s syntax builds on JavaScript operators.
  * **Expressions 101:** The basics.
  * **JS Recipes:** JavaScript tricks and tips.
  * **AI Recipes:** Integrating AI logic.



**Crafting Expressions:**

* Expressions in Cargo are a bit like **formulas in Excel**, where you combine data and functions.
* To invoke the power of JavaScript, **wrap your input with \{{ \}}**. Anything outside is treated as plain text. \<add visual>
* **Autocompletion:** It's like a predictive text. If you've run a node before, typing '.' will suggest possible entries. \<add gif>
* **Node output:** Every node in a Cargo workflow gives feedback when successfully run. The  "In" shows the input, "Out" displays the outcome. If a node didn't generate any output, "Out" might be blank.

***

In every workflow in Cargo, expressions allow you to access the available data, you should use a liquid-like syntax starting with '\{{' and closing with '\}}'.&#x20;

```javascript
{{nodes.NAMEOFTHENODE.attributes}}
```

Whether you want to use AI prompt to explain an action or to configure an action, you will always use these principles.&#x20;

For instance, if you want to see which data you have at your disposal when starting the workflow, you can write <mark style="color:green;">\{{nodes.start.</mark> too see the available data at this point.&#x20;

<figure><img src="../.gitbook/assets/Capture d’écran 2023-05-08 à 15.44.21.png" alt=""><figcaption></figcaption></figure>

if you would like to get the information enriched by "Apollo" you would do <mark style="color:green;">\{{nodes.node\_3\[...]\}}</mark> and select the attributes you want like below

<figure><img src="../.gitbook/assets/Capture d’écran 2023-05-08 à 15.50.12.png" alt=""><figcaption></figcaption></figure>

#### Fall back logic

A very powerful Cargo feature is the ability to set Fallback Values.

This can be used for occasions when you know that data being returned will be inconsistent in some way. It is used as a fallback logic to deal with inconsistent data. It takes the first attribute, and if empty, take the second one.

To use multiple attributes in a field, you can use the double pipe “||”.&#x20;

<figure><img src="../.gitbook/assets/Capture d’écran 2023-05-08 à 15.57.54.png" alt=""><figcaption><p><em>Fallback logic</em></p></figcaption></figure>

The fallback logic is often used with waterfall logic: when pushing an enriched data to your CRM, you want to make sure something is pushed. For instance, you have two different source of email data, you put both to maximize coverage rate.

<figure><img src="../.gitbook/assets/Capture d’écran 2023-05-08 à 16.28.09.png" alt=""><figcaption></figcaption></figure>

You can execute JavaScript within an expression.

<figure><img src="../.gitbook/assets/Screenshot 2023-05-08 at 7.58.35 PM.png" alt=""><figcaption><p>Example of Javascript expression</p></figcaption></figure>



**How to use it**

{% embed url="https://app.guideflow.com/embed/zpe5e9a8pn" %}





