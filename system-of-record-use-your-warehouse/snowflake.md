# Use Cargo on Snowflake

✅ What Cargo can do

1. **Read** data from schemas and tables, even if they are spread across multiple databases,
2. **Writes** them into new schemas and tables

❌ What Cargo will never do

1. **Overwrite** existing schemas and tables

(instead it always creates its own schemas and tables when needed)

To achieve all of this, some setup is required to ensure that Cargo has the necessary permissions in Snowflake

## Create a dedicated DB for Cargo needs

Create a **dedicated DB** for Cargo needs (all data managed by Cargo will be stored here)

```sql
CREATE DATABASE cargo_db;
```

## Create a user for Cargo

Grant the necessary permissions for Cargo to run commands as an **authenticated user** on the database you just created above

```sql
-- Create a role for cargo
CREATE ROLE cargo_role;

-- Grant the cargo database you created above to cargo role
GRANT ALL ON DATABASE cargo_db TO ROLE cargo_role;

-- Create a warehouse for cargo
CREATE WAREHOUSE cargo_wh WITH WAREHOUSE_SIZE='XSMALL' WAREHOUSE_TYPE='STANDARD' AUTO_SUSPEND=60 AUTO_RESUME=true;

-- Grant warehouse to cargo role
GRANT USAGE on WAREHOUSE cargo_wh to role cargo_role;

-- Create a user for cargo
CREATE USER cargo_user PASSWORD='abc123' DEFAULT_ROLE=cargo_role DEFAULT_WAREHOUSE=cargo_wh MUST_CHANGE_PASSWORD=false;

-- Grant role to user
GRANT ROLE cargo_role TO USER cargo_user;

-- Cargo user may needs to access data outside the 'cargo_db' database.
GRANT SELECT ON ALL TABLES IN SCHEMA <database_name>.<schema_name> TO cargo_user;
```

Make sure the Cargo user has **access to the following permissions** on `cargo_db`:

* `OWNERSHIP`
* `MODIFY`
* `MONITOR`
* `USAGE`
* `CREATE SCHEMA`

You can use the following command to **check the granted privileges** of the database

```sql
SHOW GRANTS ON DATABASE cargo_db
```

## For Snowflake accounts hosted on GCP and Azure

Make sure you **provide an RSA private key** while creating your account

This key is linked to your user. It will automatically ingest data in your Snowflake instance

To start, open a terminal window and **generate a private key**

```bash
$ openssl genrsa 2048 | openssl pkcs8 -topk8 -inform PEM -out rsa_key.p8 -nocrypt
```

Then **generate a public key**

```bash
$ openssl rsa -in rsa_key.p8 -pubout -out rsa_key.pub
```

Execute an `ALTER USER` command to **assign the public key** to your Snowflake user.

```sql
ALTER USER cargo_user SET RSA_PUBLIC_KEY='YOUR_PUBLIC_KEY';
```

And **copy-paste the private key** in your workspace configuration

<figure><img src="../.gitbook/assets/Screenshot 2023-04-24 at 12.32.07 PM.png" alt=""><figcaption></figcaption></figure>

## Allowed IP Addresses

If you're using Snowflake's Allowed IPs network policy, you'll need to **add the Cargo IP addresses** to your list. Please contact aurelien@getcargo.io to have this configured for you.

## Setup completed 🎉

You are ready to use Cargo!&#x20;

<figure><img src="https://media.giphy.com/media/ZWbeEcbeo0cKI/giphy.gif" alt=""><figcaption><p>Go go go 🏎️</p></figcaption></figure>
