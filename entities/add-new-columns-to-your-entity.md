# Add new columns to your entity

_By the end of this section, you should be able to:_

1. Know the difference between a custom column and a computed column
2. Know how to create a custom column in your entity
3. Know how to create a computed column in your entity



Entities are a high-level data abstraction, while workflows handle data record by record. To bridge this gap and offer flexibility, Cargo provides custom and computed columns.

## **1. Custom Columns:**

### **Purpose:**&#x20;

Add a new column (string, integer, boolean)

### **Setup:**

*   Click the three dots and **Edit**





    <figure><img src="../.gitbook/assets/Screenshot 2023-10-02 at 11.49.31.png" alt=""><figcaption></figcaption></figure>
* Proceed to the **Columns tab**

<figure><img src="../.gitbook/assets/Screenshot 2023-10-02 at 11.50.54.png" alt=""><figcaption></figcaption></figure>

* Add a new **Custom column**

<figure><img src="../.gitbook/assets/Screenshot 2023-10-02 at 11.51.32.png" alt=""><figcaption></figcaption></figure>

*   Choose the **data type**



    <figure><img src="../.gitbook/assets/Screenshot 2023-10-02 at 11.52.49.png" alt=""><figcaption></figcaption></figure>


* Save & **Re-sync**
* Push a new custom value through a workflow

***

## **Computed Columns:**

### **Purpose:**&#x20;

Powerful columns with expressions or embedded code.

### **Setup:**

*   ![](<../.gitbook/assets/Screenshot 2023-10-02 at 12.10.55.png>)Click the three dots and **Edit**





    <figure><img src="../.gitbook/assets/Screenshot 2023-10-02 at 11.49.31.png" alt=""><figcaption></figcaption></figure>
* Proceed to the **Columns tab**

<figure><img src="../.gitbook/assets/Screenshot 2023-10-02 at 11.50.54.png" alt=""><figcaption></figcaption></figure>

* Add a new **Computed column**

<figure><img src="../.gitbook/assets/Screenshot 2023-10-02 at 11.58.01.png" alt=""><figcaption></figcaption></figure>

* Choose the **data type**

<figure><img src="../.gitbook/assets/Screenshot 2023-10-02 at 12.11.41.png" alt=""><figcaption></figcaption></figure>

### **Option 1: Write your expression**

* Add an expression ([see here to learn more](https://app.gitbook.com/o/4mORJs1gC0yIX9GWp4Rp/s/xm3PV8WN8Sxx6tS7U2FC/\~/changes/67/segments)) to define the formula for your computed column

<figure><img src="../.gitbook/assets/Screenshot 2023-10-02 at 12.11.16.png" alt=""><figcaption></figcaption></figure>

### **Option 2: Choose an AI or JS recipe**

* ![](<../.gitbook/assets/Screenshot 2023-10-02 at 12.15.42.png>)

You can write your AI prompt or JS code here:

![](<../.gitbook/assets/Screenshot 2023-10-02 at 12.16.12.png>)









**Note:**

1. See here a[ live example ](http://127.0.0.1:5000/o/4mORJs1gC0yIX9GWp4Rp/s/xm3PV8WN8Sxx6tS7U2FC/)of setting up a computed column using an AI prompt&#x20;
2. Familiarise yourself with [Segments](https://app.gitbook.com/o/4mORJs1gC0yIX9GWp4Rp/s/xm3PV8WN8Sxx6tS7U2FC/\~/changes/67/segments) and [Workflows](https://app.gitbook.com/o/4mORJs1gC0yIX9GWp4Rp/s/xm3PV8WN8Sxx6tS7U2FC/\~/changes/67/segments) sections to familiarise with expressions and workflow-related concepts.



