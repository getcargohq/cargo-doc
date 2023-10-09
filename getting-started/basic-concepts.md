---
description: >-
  Welcome to the Cargo documentation!  Here you will learn how to use the Cargo
  platform to build your future-proofed revenue architecture.
---

# 🧢 Basic concepts



## Key Concepts

#### Workspaces

Each account has one or more workspaces. A workspace serves as a standalone environment for your revenue orchestration.. Connectors, workflows, and analytics are not shared across workspace.

#### System of Record

Cargo connects to data warehouses like Snowflake, BigQuery, and Redshift.

<figure><img src="../.gitbook/assets/Capture d’écran 2023-05-07 à 14.53.09.png" alt=""><figcaption><p><em>Supported System of Records</em></p></figcaption></figure>

#### Connectors - loads your datasets&#x20;

Connectors are integrations with 3rd party systems. Connectors are end systems, used to trigger actions in your GTM tools.  It also support the webhook connection to trigger a workflow in response to specific events or conditions.

<figure><img src="../.gitbook/assets/Capture d’écran 2023-05-07 à 14.52.56.png" alt=""><figcaption><p><em>Connectors Catalog</em></p></figcaption></figure>

**Entities**

Cargo ingests data without copying it to a proprietary system, just like a BI tool.&#x20;

Each object pulled in from a data source is called an entity and is treated like a table. Entities are the [foundations of your revenue architecture](https://www.getcargo.io/blog/business-entities-the-foundation-of-your-revenue-architecture). _Common entities include Users, Companies, Transactions, Events, Workspaces etc._

Defining relationships _(has many, has one)_ between each of your entity is an important step that will foster segmentation later on. For example, Users typically belong to many Accounts, Events are a many-to-one objects attached to a User within an Account, and Transactions lookup to Accounts.



**Segments**

_Segments_ let you group users or accounts (or any entity) based on specific attributes. You can build a segment from Characteristics, Activities and based on other segments.

<figure><img src="../.gitbook/assets/Capture d’écran 2023-05-08 à 11.20.34.png" alt=""><figcaption><p><em>Segment builder</em></p></figcaption></figure>

#### Workflows

The heart of Cargo is the Workflow Editor. A workflow is a collection of nodes connected together to automate a process. You can orchestrate different scenarios including scoring, routing, enrichment and more to systemize your go-to-market operations&#x20;

<figure><img src="../.gitbook/assets/Capture d’écran 2023-05-07 à 15.32.38.png" alt=""><figcaption><p><em>Workflows</em></p></figcaption></figure>

You can trigger a workflow from a segment made on top of your entities, or from a third party app through a webhook.

Each workflow features an analytics panel that keep track of each version of the workflows, and monitor execution status.

