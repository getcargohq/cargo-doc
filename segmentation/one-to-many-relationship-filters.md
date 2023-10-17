# 💠 One to many relationship filters

When you have two entities joined together in a relationship inside Cargo using a one-to-many relationship, you have the ability to do a cross-entity filter on the quantifiable columns of the related entity.

<figure><img src="../.gitbook/assets/1-to-many rel filters.gif" alt=""><figcaption></figcaption></figure>

Types of relationship filters you can apply inside Cargo:

**Frequency**

The frequency type filter is always available for such a filter across related entities

<figure><img src="../.gitbook/assets/Screenshot 2023-10-17 at 16.07.56.png" alt="" width="219"><figcaption></figcaption></figure>



**Period (only if time column is setup)**

The periodic filters are only available if your entity contains a column with a time value. In this case, you can filter for records that appear x days prior to the current date

<figure><img src="../.gitbook/assets/Screenshot 2023-10-17 at 16.08.47.png" alt="" width="218"><figcaption></figcaption></figure>
