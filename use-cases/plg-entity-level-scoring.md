# 🏎 PLG: Entity-level scoring

By the end of this tutorial, you will understand how to set up entity-level scoring in Cargo, use AI to enhance your scores, and effectively create segments based on those scores

***

## **Introduction to Entity-Level Scoring:**

Typically, scoring mostly happens for the workflow level where records are processed and scored one-by-one.

However, you will come across use cases where it’s not efficient to leave the scoring to the workflow execution level and instead you want to create entire segments as a function of their score. There will be times when a simple numeric score won’t cut it and instead you’d use AI to use categorisation to create the scoring.

**Picture this**: You’re running a PLG motion want to identify high-potential users by scoring if the person is a key decision maker and whether they’ve sufficiently used the product automated score for each entity. You want to build a segment of high-potential users and engage them in a nurturing sequence

This is where entity-level scoring comes in. Let's delve deeper with an example of how we’re doing this for ourselves at Cargo



## **Setting Up Entity-Level Scoring with Cargo:**

### **Begin with the Basics:**

* In your Cargo workspace, navigate to the entities tab and select the contacts entity (for instance)
* Click the three-dots on the top-right of your screen and select the 'columns tab'

<figure><img src="../.gitbook/assets/entities_contacts 2023-09-29 at 05.40.22.png" alt="" width="264"><figcaption></figcaption></figure>



* Add a computed column and click add to insert new fields

<figure><img src="../.gitbook/assets/Screenshot 2023-10-03 at 11.22.39.png" alt="" width="375"><figcaption></figcaption></figure>



*   Now, you can start adding your scoring criteria

    * Choose the data type for the new column. For this tutorial, we’ll choose #Number

    <figure><img src="../.gitbook/assets/Screenshot 2023-09-29 at 05.44.50.png" alt="" width="269"><figcaption></figcaption></figure>

    * For the expression input, click on the small Library icon as in the image below to choose from one of the available recipes

    <figure><img src="../.gitbook/assets/Screenshot 2023-10-03 at 11.27.11.png" alt="" width="375"><figcaption></figcaption></figure>

    <figure><img src="../.gitbook/assets/Screenshot 2023-09-29 at 05.48.35.png" alt="" width="271"><figcaption></figcaption></figure>

    * Now you can start adding your scoring criteria

<figure><img src="../.gitbook/assets/Screenshot 2023-09-29 at 05.50.02.png" alt="" width="270"><figcaption></figcaption></figure>







### **Build a Score Using Defined Parameters:**

* Choose the attributes (columns) and assign weights to them based on their importance to your score
* For example, here we’re taking the column app\_run\_count that tracks how many cycles of runs a user has performed on Cargo. Every time a user has executed more than 15 runs, we add a score of +20 to their score

<figure><img src="../.gitbook/assets/Screenshot 2023-09-29 at 05.54.34.png" alt="" width="273"><figcaption></figcaption></figure>



* Similarly, here we can attribute a positive score of 20 whenever the user signed up with a corporate email rather than a personal email

<figure><img src="../.gitbook/assets/Screenshot 2023-09-29 at 05.58.25.png" alt="" width="271"><figcaption></figcaption></figure>



*   Other attributes we could have leveraged

    * Deployed workspaces in the last month
    * Total members on workspace made
    * Engagement on marketing emails
    * Duration since the last purchase



### **Enhancing Your Score with AI:**

* So far we were using columns or attributes that were easily classifiable using simple logic. What if we wan’t to use a score on something not so straightforward. We had a use case where we wanted to classify whether a user was a decision maker inside a team, and not just an individual contributor.
* Setting one up is pretty simple. Here we chose an AI recipe from the library
* In the configuration, pass the name of the column that contains the the job title of the user

<figure><img src="../.gitbook/assets/Screenshot 2023-09-29 at 06.04.54.png" alt="" width="270"><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2023-09-29 at 06.06.37.png" alt="" width="264"><figcaption></figcaption></figure>

* Pressing the check button on the top right and resyncing the entity will now create a new column with the output of your AI classifier

<figure><img src="../.gitbook/assets/Screenshot 2023-09-29 at 06.12.12.png" alt=""><figcaption></figcaption></figure>

* You can now use this column in your points-based scoring as shown above

<figure><img src="../.gitbook/assets/Screenshot 2023-09-29 at 06.13.33 (1).png" alt="" width="269"><figcaption></figcaption></figure>

* You can set up your own recipe if you’d like to play around with the prompt. Here’s the kind of prompt we were using.

<figure><img src="../.gitbook/assets/Screenshot 2023-09-29 at 06.08.34.png" alt="" width="268"><figcaption></figcaption></figure>

### **Creating a Segment Based on Your Score:**

* Filter on a threshold of score that suits you

<figure><img src="../.gitbook/assets/Screenshot 2023-09-29 at 06.15.01.png" alt="" width="367"><figcaption></figcaption></figure>

* Click on "Create Segment" and you’re good to go.

<figure><img src="../.gitbook/assets/Screenshot 2023-09-29 at 06.15.10.png" alt="" width="168"><figcaption></figcaption></figure>





















