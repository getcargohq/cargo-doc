# 🔧 Add new columns to your entity

Entities are a high-level data abstraction, while workflows handle data record by record. To bridge this gap and offer flexibility, Cargo provides custom and computed columns.



***

## **1. Computed Columns:**

<figure><img src="../../.gitbook/assets/add computed column (2).gif" alt=""><figcaption></figcaption></figure>

### **Purpose:**&#x20;

&#x20;Powerful columns with expressions or embedded code

### **Setup:**

* Click the three dots and **Edit**
* Proceed to the **Columns tab**
* Add a new **Computed column**

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-17 at 13.55.19.png" alt=""><figcaption></figcaption></figure>

* Choose the **data type**
* Add an expression ([see here to learn more](https://app.gitbook.com/o/4mORJs1gC0yIX9GWp4Rp/s/xm3PV8WN8Sxx6tS7U2FC/\~/changes/67/segments)) to define the formula for your computed column
* Save & **Re-sync**
* Push a new custom value through a workflow

***

## **2. Custom Columns:**

### **Purpose:**&#x20;

Add a new column (string, integer, boolean)

### **Setup:**

* Click the three dots and **Edit**
* Proceed to the **Columns tab**
* Add a new **Custom column**

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-17 at 13.54.50.png" alt=""><figcaption></figcaption></figure>

* The rest of the process is the same as the above for creating a computed column

***

## 3. Metrics columns:

<figure><img src="../../.gitbook/assets/Add metrics column.gif" alt=""><figcaption></figcaption></figure>

### **Purpose:**&#x20;

Add a column with an aggregated expression on related entities

### **Setup:**

* Click the three dots and **Edit**
* Proceed to the **Columns tab**
* Add a new **Metrics column**

<figure><img src="../../.gitbook/assets/Screenshot 2023-10-17 at 14.26.16.png" alt="" width="297"><figcaption></figcaption></figure>

* **Label** the new column
* Choose the **aggregation type**
* Choose the **related entity** which will supply the aggregated relation
* **Filter** on the right dimension

***

**Note:**

1. See here a [live example](https://docs.getcargo.io/use-cases/plg-entity-level-scoring) of setting up a computed column using an AI prompt&#x20;
2. Familiarise yourself with [Segments](https://docs.getcargo.io/segmentation/introduction) and [Workflows](https://docs.getcargo.io/orchestration/using-the-workflow-editor) sections to familiarise with expressions and workflow-related concepts.



