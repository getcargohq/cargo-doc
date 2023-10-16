# 🧢 Expressions 101

## **Crafting Expressions:**

* Expressions in Cargo are a bit like **formulas in Excel**, where you combine data and functions.
* To invoke the power of JavaScript, **wrap your input with \{{ \}}**. Anything outside is treated as plain text. \<add visual>
* **Autocompletion:** It's like a predictive text. If you've run a node before, typing '.' will suggest possible entries. \<add gif>
* **Node output:** Every node in a Cargo workflow gives feedback when successfully run. The  "In" shows the input, "Out" displays the outcome. If a node didn't generate any output, "Out" might be blank.

***

## Liquid syntax

In every workflow in Cargo, expressions allow you to access the available data, you should use a liquid-like syntax starting with '\{{' and closing with '\}}'.&#x20;

```javascript
{{nodes.NAMEOFTHENODE.attributes}}
```

Whether you want to use AI prompt to explain an action or to configure an action, you will always use these principles.&#x20;

For instance, if you want to see which data you have at your disposal when starting the workflow, you can write <mark style="color:green;">\{{nodes.start.</mark> too see the available data at this point.&#x20;

<figure><img src="../../.gitbook/assets/Capture d’écran 2023-05-08 à 15.44.21.png" alt=""><figcaption></figcaption></figure>

if you would like to get the information enriched by the "Apollo" nodes in the example below you would do <mark style="color:green;">\{{nodes.node\_3\[...]\}}</mark> and select the attributes you want like below\
_Hint: You can rename the nodes to whatever you please_

<figure><img src="../../.gitbook/assets/Capture d’écran 2023-05-08 à 15.50.12.png" alt=""><figcaption></figcaption></figure>

## Autocompletion

When you want to preview which data you have available to use in an expression entering dot ( . ) character within the curly brackets ( \{{ \}} ) will trigger a preview of available nodes, as in the GIF below.

In the example below, we're able to select the email option after having entered the '.' character after start, i.e. <mark style="color:green;">\{{nodes.start.</mark>

<figure><img src="../../.gitbook/assets/Autocomplete (2) (1).gif" alt=""><figcaption></figcaption></figure>

_Hint: only runs that have already executed before your node will be available in the preview, as otherwise the preview has no means of knowing whether they exist_



## Node output

Whenever a node executes you can inspect the information that went into and and was outputted from the node using the 'IN' and 'OUT' buttons on the top right of the Edit modal on the right of the screen.



## Fallback logic

A very powerful Cargo feature is the ability to set fallback values.

This can be used for occasions when you know that data being returned will be inconsistent in some way. It is used as a fallback logic to deal with inconsistent data. It takes the first attribute, and if empty, take the second one.

To use multiple attributes in a field, you can use the double pipe “||”.&#x20;

<figure><img src="../../.gitbook/assets/Capture d’écran 2023-05-08 à 15.57.54.png" alt=""><figcaption><p><em>Fallback logic</em></p></figcaption></figure>



**The fallback logic is often used within a waterfall enrichment step**: when pushing an enriched data to your CRM, you want to make sure something is pushed. For instance, you have two different sources of email data, you put both to maximize coverage rate.



##

##

##

##

##

## You can execute anyJavaScript operator within an expression.

[More here](https://docs.getcargo.io/expressions/expressions-101/javascript-snippets)

<figure><img src="../../.gitbook/assets/Screenshot 2023-05-08 at 7.58.35 PM.png" alt=""><figcaption><p>Example of Javascript expression</p></figcaption></figure>




