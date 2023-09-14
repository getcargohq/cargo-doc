# Use Cargo on AWS Redshift

Cargo reads data from schemas and tables, even if they are spread across multiple databases, and writes them into new schemas and tables.

It's important to note that **Cargo never overwrites existing schemas and tables**. Instead, it creates its own schemas and tables specifically for this purpose.

To write data into the database, Cargo uses files stored in S3 and imports the data of these files using the `COPY` command.

For the computed column feature, Cargo creates external function on Redshift calling a Lambda on your AWS. The lambda runs the Javascript code you define for the column in Cargo.

To achieve all of this, some setup is required to ensure that Cargo has the necessary permissions.

## Create a dedicated DB for Cargo needs

All data managed by Cargo will be stored and transformed in a dedicated database on your Redshift cluster.

```sql
CREATE DATABASE cargo_db;
```

## Create a DB user for Cargo

In order for Cargo to run commands, it must be authenticated as a Redshift user with the necessary permissions on the database you just created above.

```sql
-- Create the user
CREATE USER cargo_user WITH PASSWORD '<strong_password>';

-- Grant to the user permissions on the database Cargo will use
GRANT ALL ON DATABASE cargo_db TO cargo_user;

-- Allow the user to create functions
CREATE ROLE cargo_create_replace_function;
GRANT CREATE OR REPLACE FUNCTION TO ROLE cargo_create_replace_function;
GRANT ROLE cargo_create_replace_function TO cargo_user;

-- For the computed column feature
GRANT USAGE ON LANGUAGE exfunc TO cargo_user;

-- Cargo user may needs to access data outside the 'cargo_db' database.
GRANT SELECT ON ALL TABLES IN SCHEMA <database_name>.<schema_name> TO cargo_user;
```

## Allow Cargo IP

Depending on the configuration of Redshift, it may be necessary to whitelist Cargo's public IP address.

To whitelist the IP:

1. Open the VPC security group used for Redshift.
   * For Redshift Serverless, follow these steps to find the security group:
     * Go to **Workgroup configuration**.
     * Go to **Network and configuration**.
     * Click on **VPC security group**.
2. Click on **Inbound rules**.
3. Click on **Edit inbound rules**.
4. Click on **Add a new rule**.
5. Set the following values:
   * **All traffic**
   * **Source custom**
   * **CARGO IP**

At the moment, Cargo does not support SSH. Therefore, Redshift cannot only be accessed through private or internal networks. To be accessible, it must be made publicly available.

## DB connection

Cargo will use this information to connect to the Redshift database:

**Hostname - Port - Database name**

For Redshift Serverless:

* Select the workgroup to see the workgroup configuration.
* Copy the endpoint value.
*   Extract the hostname, port, and database name from the endpoint value.

    The endpoint has the following format: `hostname:port/database_name`.

**User - Password**

This refers to the user created earlier.

## Cross account access

Cargo uses the `COPY` and `UNLOAD` commands to efficiently load and export data. These commands are executed from your Redshift, but read or write data to Cargo's S3 bucket.

To enable this functionality, your Redshift cluster needs access to Cargo's S3 bucket. This can be achieved by setting up cross-account access.

Once you submit the form to create the workspace, Cargo create a role with the necessary access to their S3 bucket for you.

To complete the setup, you need to create a policy and a role on AWS that is connected to this role. Then, attach the role to your Redshift cluster (or namespace if using Redshift Serverless), and provide us with the ARN of the role.

The steps are detailed in this document, but you can also refer to the full AWS documentation [here](https://repost.aws/knowledge-center/redshift-s3-cross-account).

### Create a policy

1. Open the IAM console.
2. Select **Policies** and click **Create policy**.
3.  Choose JSON and copy the following policy. Make sure to replace `<cargo_role_arn>` with the ARN of the role created by Cargo for you.

    ```
    {
      "Version": "2012-10-17",
      "Statement": [
        {
          "Sid": "CrossAccountPolicy",
          "Effect": "Allow",
          "Action": "sts:AssumeRole",
          "Resource": "<cargo_role_arn>"
        }
      ]
    }

    ```
4. Click **Next**, set a meaningful name, and create the policy.

### Create a role

1. Open the IAM console.
2. Choose **Policies** and click **Create role**.
3. Choose **AWS service** as **Trusted entity type**, and select **Redshift - Customizable** as Use case.
4. Click **Next**.
5. Select the policy created in the previous step, and click **Next**.
6. Set a meaningful name
7. Create the role.

### Give Redshift access to AWS Lambda

To compute the values of computed columns using external functions, Redshift need access to AWS Lambda.

1. Go back to IAM console
2. Find the role
3. Select the tab **Trust relationships**
4. Click on **Edit trust policy** and add the following statement

```
{
  "Effect": "Allow",
  "Principal": {
    "Service": "lambda.amazonaws.com"
  },
  "Action": "sts:AssumeRole"
}
```

5. Click on **update policy**
6. Now choose the **permissions** tab
7. Click on **Add permissions**, **Attach policies**
8. And attach the following AWS policies:
   1. AWSLambdaExecute
   2. AWSLambdaRole

### Attach the role to Redshift

#### For Redshift Serverless

1. Select the namespace of your Redshift.
2. Open the **Security and encryption** tab.
3. Click on **Manage IAM roles**.
4. Click on **Manage IAM roles** again and select **Associate IAM roles**.
5. Select the role created earlier, and click on Associate IAM roles

## Lambda Functions

In Cargo, you can create computed columns on entities. It allows you to generate the column value based on Javascript code.

The column values are computed on the Redshift side, in a user-defined function, when we fetch the data to display it in Cargo. But Javascript code can't run on Redshift directly.

The solution to the problem is to put the Javascript code inside a Lambda function, and create a user-defined function calling this Lambda function. For more details, see [this AWS documentation](https://docs.aws.amazon.com/redshift/latest/dg/udf-creating-a-lambda-sql-udf.html).&#x20;

Which means Cargo needs to be able to create Lambda functions in the same AWS account as Redshift.

To do this, you have to create a user for us with the Lambda policies, generate credentials, and copy/paste these credentials in the Redshift setup.

1. Open the IAM console once again.
2. Select **users**
3. Click **create user**
4. Give it a name, like **"cargo\_lambda"**
5. Click on **next**
6. Select **Attach policies directly**
7.  Check **AWSLambda\_FullAccess**

    _(we are working to improve this part and ask for less permissions)_
8. Click **next**, and create the user

The user has been created

1. Select the created user in the users list
2. Open the **Security credentials** tab
3. Scroll down to the **Access keys** section
4. Click on **Create access key**
5. Choose **Third-party service** and check the **confirmation** checkbox
6. Click **next**
7. Add a description, like **"Access key for Cargo Redshift setup"**
8. Click **Create access key**

Copy the **Access key** in the **accessKeyId** field, and the **Secret access key** in the **secretAccessKey** field on Cargo.&#x20;

## Setup completed 🎉

You are ready to use Cargo!

<figure><img src="https://media.giphy.com/media/9rjzS2QYAk1paKD7uk/giphy.gif" alt=""><figcaption></figcaption></figure>
