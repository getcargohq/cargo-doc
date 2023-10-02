# Creating entities in Cargo

_By the end of this section, you should be able to:_

1. Understand what an entity is and why you need one
2. Follow a step-by-step guide to set up an entity



## **Why Create an Entity?**

**Think of it this way:** You've set up various data connectors in Cargo. While each source has valuable data, you get 10x more insights when you merge them under a unified definition.

Imagine connecting contact details from your Hubspot dataset with product usage info from Amplitude. This connection is made possible through entities.



### **Step 1: Querying Data**

*   **Name it:** Start with a descriptive name for your entity.



    <figure><img src="../.gitbook/assets/Screenshot 2023-10-02 at 11.03.06.png" alt=""><figcaption></figcaption></figure>
* **Query it:** Use SQL to extract necessary data.&#x20;

{% hint style="info" %}
Most SQL queries will follow the following basic template. If you've never used SQL before, play around with this structure to begin with:
{% endhint %}

```
SELECT [column_name1], [column_name2]
FROM [dataset_name_1]
WHERE [condition1 = value] AND [condition2 = value]
GROUP BY 1,2 --add as many numbers as the columns you've chosen in SELECT
```

Often you'd like to join to a secondary table in order to have a consolidated view in your entity. In this case, add the below to your code:

```
JOIN [dataset_name_2]
ON [dataset_name_1].[id_column_dataset_name_!
```

* **Preview**: Before moving on, check if the data looks right. Use column selectors for better clarity

<figure><img src="../.gitbook/assets/Screenshot 2023-10-02 at 11.26.47.png" alt=""><figcaption></figcaption></figure>



### **Step 2: Designate Your Identifiers**

When setting up an entity, you need a way to uniquely identify each record:

1.  **Primary column selection:**

    <figure><img src="../.gitbook/assets/Screenshot 2023-10-02 at 11.28.55.png" alt=""><figcaption></figcaption></figure>

    * **What is it?** This is like the "unique name" for each record in your dataset
    * **Action:** From your columns, choose one that acts as this unique identifier. This could be something like a 'Customer ID' or 'Email Address'


2.  **Time-based identifier (optional):**

    * **What is it?** If your data has time-stamps or dates (like "Date of Purchase"), you might want to identify records based on these
    * **Action:** Select the column which holds this time-based information

    <figure><img src="../.gitbook/assets/Screenshot 2023-10-02 at 11.32.51.png" alt=""><figcaption></figcaption></figure>



### **Step 3: Building Connections (Defining Relationships)**

Take two datasets: one lists names of prospects, and the other lists details of projects.&#x20;

Wouldn't it be helpful if you knew which prospect belongs to which project? That's what relationships mean for entities

**First, ask yourself:**

* _Do I need this new entity to connect with another existing entity?_

If yes, follow these steps:

1.  **Select related Entity:**

    * **Action:** Choose the entity you wish to connect with



    <figure><img src="../.gitbook/assets/Screenshot 2023-10-02 at 11.36.17.png" alt=""><figcaption></figcaption></figure>
2.  **Determine relationship type:**

    <figure><img src="../.gitbook/assets/Screenshot 2023-10-02 at 11.37.12.png" alt=""><figcaption></figcaption></figure>



    **What is it?** Relationships can be:

    * **One-to-One:** One record in your entity matches one in another. E.g., One employee has one unique employee ID.
    * **One-to-Many:** One record in your entity matches multiple in another. E.g., One book author wrote several books.

    **Action:** Decide which type fits your data best. \<add visual>
3.  **Identify the matching key on your entity:**



    * **Action:** Pick the column in your current entity that you want to use for matching. This might be something like 'global\_id'

    <figure><img src="../.gitbook/assets/Screenshot 2023-10-02 at 11.38.35.png" alt=""><figcaption></figcaption></figure>
4. **Identify key on the other entity:**

<figure><img src="../.gitbook/assets/Screenshot 2023-10-02 at 11.41.12.png" alt=""><figcaption></figcaption></figure>

* **Action:** Choose the corresponding column in the other entity that matches with your chosen key

5. **Redo the process, but this time starting from the other entity**, in order to ensure that the relationship is two-way
   1. The only thing that will change is that the left column and right column will be inversed
