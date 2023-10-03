# ⚙ Copy of Advanced concepts

## Leverage the semantic layer

Cargo is a headless platform. It plugs into any system of record (BigQuery, Snowflake, Postgres, …) and never duplicates/stores data on its side. Here are the benefits of not owning the storage for data teams:

* _Data governance_ - You keep the control of the data. Your data is not spread in another system. You can easily plug/unplug Cargo without losing your data.
* _Data access_ - All changes you are making in your models (with DBT / lookML) are automatically updated into Cargo. You don’t have to struggle with data syncs across different systems. On the other hand, you can use Cargo data in your BI tools
* _Cost efficient_ - You are not paying several time the same record.



## How it technically works

As mentioned above, all your data stays in your data warehouse. To do so, a dedicated database needs to be created where you will give to Cargo a read and write access. Cargo is storing data in dedicated schemas and tables in the database.

<figure><img src="../.gitbook/assets/Screenshot 2023-04-11 at 12.44.01 PM (1).png" alt=""><figcaption></figcaption></figure>

#### **Entity**

An entity is a data object that you want to leverage in Cargo. Most of the time, it’s going to be a `Contact`, a `Company` or an `Event`.

When you create an entity in Cargo, we are going to ask you to write the SQL query that define this entity.

From then, we are creating a table called `ENTITIES_{UUID}.DEFAULT` with the results of this sql query. This table will be updated on a regular basis (defined in the settings)

Like in a CRM, a user is able to create custom columns for each entity. To do so, we don’t override data of the `DEFAULT` table but we are storing the values in another table called `ENTITIES_{UUID}.CUSTOM`

<figure><img src="../.gitbook/assets/Screenshot 2023-04-11 at 12.39.51 PM.png" alt=""><figcaption></figcaption></figure>

#### **Segment**

Users can filter entities with our query builder. They then can save it as a segment. The portion of the segment will be stored in a table called `SEGMENTS_{UUID}.DEFAULT`and we will store the changes (new records added, removed, updated) in a table called `SEGMENTS_{UUID}.CHANGES_{UUID}`

<figure><img src="../.gitbook/assets/Screenshot 2023-03-22 at 19.50.57.png" alt=""><figcaption></figcaption></figure>

**Data stream ingestion**

<figure><img src="../.gitbook/assets/Screenshot 2023-04-11 at 12.29.47 PM.png" alt=""><figcaption></figcaption></figure>

As you read above, with custom columns, we have the ability to write back data in the warehouse. To do so, we are not directly updating the table in the warehouse but we have built a pipeline to load the new data in batches.

1. Data pushed to firehose
2. Data stored in batches in a S3 (can be yours)
3. Batches loaded in your warehouse in a staging table (no cost)
4. Records dispatched in the right tables during the next sync.

