---
description: >-
  Welcome to the Cargo documentation!  Here you will learn how to use the Cargo
  platform to build your future-proofed revenue architecture.
---

# 🎉 Introduction

## About Cargo

Cargo is the first warehouse native revenue platform that unlocks data access for revenue teams to automate their data operations. It provides a simple layer enabling them to orchestrate use cases like ABM, account scoring, lead routing and more, … to generate more revenue.

## Where to start <a href="#where-to-start" id="where-to-start"></a>

<table data-view="cards"><thead><tr><th></th><th align="center"></th><th></th></tr></thead><tbody><tr><td></td><td align="center">🚢 <a href="broken-reference">Explore integrations</a></td><td></td></tr><tr><td></td><td align="center">🏢 <a href="http://localhost:5000/o/4mORJs1gC0yIX9GWp4Rp/s/xm3PV8WN8Sxx6tS7U2FC/">Create workspaces</a></td><td></td></tr><tr><td></td><td align="center">🚧 <a href="https://app.gitbook.com/o/4mORJs1gC0yIX9GWp4Rp/s/xm3PV8WN8Sxx6tS7U2FC/~/changes/35/workflow-actions">Workflow actions</a></td><td></td></tr><tr><td></td><td align="center">⭐️  <a href="https://app.gitbook.com/o/4mORJs1gC0yIX9GWp4Rp/s/xm3PV8WN8Sxx6tS7U2FC/~/changes/35/getting-started">Getting Started</a></td><td></td></tr></tbody></table>



## Key Concepts

#### Workspaces

Each account has one or more workspaces. A workspace serves as a standalone environment for your revenue orchestration.. Connectors, workflows, and analytics are not shared across workspace.

#### Connectors&#x20;

Connectors are integrations with 3rd party systems. Connectors are end systems, used to trigger actions in your GTM tools.

<figure><img src=".gitbook/assets/Capture d’écran 2023-05-07 à 14.52.56.png" alt=""><figcaption><p><em>Connectors Catalog</em></p></figcaption></figure>

#### System of Records

Cargo connects to data warehouses like Snowflake, BigQuery, and Redshift.  It also support the webhook connection to trigger a workflow in response to specific events or conditions.

<figure><img src=".gitbook/assets/Capture d’écran 2023-05-07 à 14.53.09.png" alt=""><figcaption><p><em>Supported System of Records</em></p></figcaption></figure>

**Entities**

Cargo ingests data without copying it to a proprietary system, just like a BI tool.&#x20;

Each object pulled in from a data source is called an entity and is treated like a table. Entities are the [foundations of your revenue architecture](https://www.getcargo.io/blog/business-entities-the-foundation-of-your-revenue-architecture). _Common entities include Users, Companies, Transactions, Events, Workspaces etc._

Defining relationships _(has many, has one)_ between each of your entity is an important step that will foster segmentation later on. For example, Users typically belong to many Accounts, Events are a many-to-one objects attached to a User within an Account, and Transactions lookup to Accounts.



**Segments**

_Segments_ let you group users or accounts (or any entity) based on specific attributes. You can build a segment from Characteristics, Activities and based on other segments.

<figure><img src=".gitbook/assets/Capture d’écran 2023-05-08 à 11.20.34.png" alt=""><figcaption><p><em>Segment builder</em></p></figcaption></figure>

#### Workflows

The heart of Cargo is the Workflow Editor. A workflow is a collection of nodes connected together to automate a process. You can orchestrate different scenarios including scoring, routing, enrichment and more to systemize your go-to-market operations&#x20;

<figure><img src=".gitbook/assets/Capture d’écran 2023-05-07 à 15.32.38.png" alt=""><figcaption><p><em>Workflows</em></p></figcaption></figure>

You can trigger a workflow from a segment made on top of your entities, or from a third party app through a webhook.

Each workflow features an analytics panel that keep track of each version of the workflows, and monitor execution status.



## 🎊 Product changelog

Want to know about the latest features and bug fixes in our product? Check out our [changelog](http://changelog.getcargo.io).



## 🚑 Need help?

You can always contact us via aurelien@getcargo.io or via the live chat in the bottom left corner.
