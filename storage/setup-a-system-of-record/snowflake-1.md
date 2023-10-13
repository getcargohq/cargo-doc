# Use Cargo on PostgreSQL

✅ What Cargo can do

1. **Read** data from schemas and tables
2. **Writes** them into new schemas and tables

❌ What Cargo will never do

1. **Overwrite** existing schemas and tables

(instead it always creates its own schemas and tables when needed)

To achieve all of this, some setup is required to ensure that Cargo has the necessary permissions in Snowflake

## Prerequisites

If your database is not on AWS RDS, make sure you have the following extensions installed:

* **plv8** - required for computed columns, as Cargo needs to run Javascript UDF on the database.
* **aws\_s3** - required to download the records of a Cargo entity or segment.

You might also want to create a specific user for Cargo, with limited accesses on your database.

## Setup

The only thing you have to do is to copy/paste the database credentials in Cargo.

## Setup completed 🎉

You are ready to use Cargo!&#x20;

<figure><img src="https://media.giphy.com/media/ZWbeEcbeo0cKI/giphy.gif" alt=""><figcaption><p>Go go go 🏎️</p></figcaption></figure>
